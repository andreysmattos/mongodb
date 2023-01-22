# $group

The `$group` stage separates documents into groups according to a “group key”. The output is one document for each unique group key.

Use the `_id` field in the `$group` pipeline stage to set the group key.

> `$group` does not order its output documents
> 

**Accumulator Operators:**

- `$sum`, `$avg`, `$bottom`, `$top`, `$count`, `$first`, `$last`, `$max`, `$min`
- All list: [https://www.mongodb.com/docs/manual/reference/operator/aggregation/group/#std-label-accumulators-group](https://www.mongodb.com/docs/manual/reference/operator/aggregation/group/#std-label-accumulators-group)

**Example:**

```jsx
db.persons.aggregate([
  {
    $group: {
      _id: "$location.state", //Group key
      totalPersons: { $sum: 1 }, // Field: Accumulator operators.
    },
  },
]);
```

**Result:**

```jsx
{"_id" : "louth","totalPersons" : 12.0},
{"_id" : "hessen","totalPersons" : 27.0},
...
```

**Example:**

```jsx
db.persons.aggregate([
  {
    $group: {
      _id: "$gender",
      minAge: { $min: "$dob.age" },
      maxAge: { $max: "$dob.age" },
      avgAge: { $avg: "$dob.age" },
    },
  },
]);
```

**Result:**

```jsx
{
    "_id" : "male",
    "minAge" : NumberInt(21),
    "maxAge" : NumberInt(73),
    "avgAge" : 47.19301848049281
}
{
    "_id" : "female",
    "minAge" : NumberInt(21),
    "maxAge" : NumberInt(74),
    "avgAge" : 47.04795321637427
}
```