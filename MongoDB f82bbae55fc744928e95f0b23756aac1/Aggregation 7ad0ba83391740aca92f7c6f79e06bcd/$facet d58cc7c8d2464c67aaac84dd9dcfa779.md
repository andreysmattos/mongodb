# $facet

Process multiple aggregation pipelines within a single stage on the same set of input documents.

Each sub-pipeline has its own field in the output document where its result are stored as an array of documents

Input documents are passed to the `$facet` stage only once. `$facet` enables various aggregations on the same set of input documents, without needing to retrieve the input documents multiple times.

**Example:**

```jsx
db.persons.aggregate([
  {
    $project: {
      _id: 0,
      name: {
        $concat: ["$name.first", " ", "$name.last"]
      },
      age: "$dob.age",
    },
  },
  {
    $facet: {
      old: [
        {
          $sort: { age: -1 },
        },
        {
          $limit: 10,
        },
      ],
      new: [
        {
          $sort: { age: 1 },
        },
        {
          $limit: 10,
        },
      ],
    },
  },
]);
```

**Result:**

```jsx
{
    "old" : [
        {
            "name" : "victoria hale",
            "age" : NumberInt(74)
        },
        {
            "name" : "عرشيا سهيلي راد",
            "age" : NumberInt(73)
        },
        {
            "name" : "virgil gonzales",
            "age" : NumberInt(73)
        },
        {
            "name" : "rayan bonnet",
            "age" : NumberInt(73)
        },
        {
            "name" : "sandra leclerc",
            "age" : NumberInt(73)
        },
        {
            "name" : "dieter porto",
            "age" : NumberInt(73)
        },
        {
            "name" : "anna perez",
            "age" : NumberInt(73)
        },
        {
            "name" : "finn rustand",
            "age" : NumberInt(73)
        },
        {
            "name" : "joseph thomas",
            "age" : NumberInt(73)
        },
        {
            "name" : "eleanor mason",
            "age" : NumberInt(73)
        }
    ],
    "new" : [
        {
            "name" : "alexander ortiz",
            "age" : NumberInt(21)
        },
        {
            "name" : "anatole gaillard",
            "age" : NumberInt(21)
        },
        {
            "name" : "brooke king",
            "age" : NumberInt(21)
        },
        {
            "name" : "asher king",
            "age" : NumberInt(21)
        },
        {
            "name" : "رهام كامياران",
            "age" : NumberInt(21)
        },
        {
            "name" : "eva castro",
            "age" : NumberInt(21)
        },
        {
            "name" : "cecilie jensen",
            "age" : NumberInt(21)
        },
        {
            "name" : "julia polon",
            "age" : NumberInt(21)
        },
        {
            "name" : "mestan limoncuoğlu",
            "age" : NumberInt(21)
        },
        {
            "name" : "پارسا کریمی",
            "age" : NumberInt(21)
        }
    ]
}
```