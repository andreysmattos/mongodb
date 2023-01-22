# $addFields

Add new fields to documents.

`$addFields` outputs documents that contain all existing fields from the input document and newly added fields. 

**Example:**

```jsx
db.persons.aggregate([
   {
       $addFields: {
           fullname: {
               $concat: ["$name.first", " ", "$name.last"]
           }
       }
   }
]);
```

**Result**

```jsx
{
    "_id" : ObjectId("638c9924c51c5e49c1581a9c"),
    "gender" : "male",
    "name" : {
        "title" : "mr",
        "first" : "gideon",
        "last" : "van drongelen"
    },
    "location" : {
        "street" : "9982 catharijnekade",
        "city" : "vlaardingen",
        "state" : "gelderland",
        "postcode" : NumberInt(65750),
        "coordinates" : {
            "latitude" : "-86.1268",
            "longitude" : "-54.1364"
        },
        "timezone" : {
            "offset" : "+3:00",
            "description" : "Baghdad, Riyadh, Moscow, St. Petersburg"
        }
    },
    "email" : "gideon.vandrongelen@example.com",
    "login" : {
        "uuid" : "1ff22ccb-14e8-42ae-a762-b552f60640c9",
        "username" : "angryrabbit395",
        "password" : "gotcha",
        "salt" : "KWxOE5yb",
        "md5" : "9e4c766ad10186796fa138fa690c1029",
        "sha1" : "000f6eb6e91d2404f7cbc8b0b485a86a8c198fcd",
        "sha256" : "82286824c8d704cdcf970c488bc0f2d4c208f5ed4ae74656bbca354964576f62"
    },
    "dob" : {
        "date" : "1971-03-28T04:47:21Z",
        "age" : NumberInt(47)
    },
    "registered" : {
        "date" : "2004-10-20T18:02:16Z",
        "age" : NumberInt(13)
    },
    "phone" : "(198)-755-0721",
    "cell" : "(241)-161-7474",
    "id" : {
        "name" : "BSN",
        "value" : "66692214"
    },
    "picture" : {
        "large" : "https://randomuser.me/api/portraits/men/11.jpg",
        "medium" : "https://randomuser.me/api/portraits/med/men/11.jpg",
        "thumbnail" : "https://randomuser.me/api/portraits/thumb/men/11.jpg"
    },
    "nat" : "NL",
    "fullname" : "gideon van drongelen"
}
...
```

---

- The `$addFields` stage is equivalent to a `$project` stage that explicitly specifies all existing fields in the input documents and adds the new fields