# Array

### To populate

```jsx
db.inventory.insertMany([
   { item: "journal", qty: 25, tags: ["blank", "red"], dim_cm: [ 14, 21 ] },
   { item: "notebook", qty: 50, tags: ["red", "blank"], dim_cm: [ 14, 21 ] },
   { item: "paper", qty: 100, tags: ["red", "blank", "plain"], dim_cm: [ 14, 21 ] },
   { item: "planner", qty: 75, tags: ["blank", "red"], dim_cm: [ 22.85, 30 ] },
   { item: "postcard", qty: 45, tags: ["blue"], dim_cm: [ 10, 15.25 ] }
]);
```

### Match an Array

To specify equality condition on an array, use the query document `{<field>: <value>}` where `<value>` is the exact array to match, **including the order of the elements**.

**Example:**

```jsx
db.inventory.find( { tags: ["red", "blank"] } )
```

If, instead, you wish to find an array that contains both elements `“red”` and `“blank”`, **without regard to order or other elements in the array**, use the `$all` operator.

**Example:**

```jsx
db.inventory.find( { tags: { $all: ["red", "blank"] } } )
```

---

### Query an Array for an Element

To query if the array field **contains at least one element** with the specified value, use the filter `{<field>: <value>}` where `<value>` is the element value.

The following example queries for all document where `tags` is an array the contains the string `red`

**Example:**

```jsx
db.inventory.find( { tags: "red" } )
```

To specify condition on the elements in the array field, use query operators in the query filter documents.

The following operation queries for all documents where the array `dim_cm` contains at least one element whose value is greater than `25`

**Example:**

```jsx
db.inventory.find( { dim_cm: { $gt: 25 } } )
```

---

### ****Query an Array with Compound Filter Conditions on the Array Elements****

The following example queries for documents where the `dim_cm` array contains elements that in some combination satisfy the query conditions; e.g., one element can satisfy the greater than `15` condition **and another element can satisfy** the less than `20` condition, or a single element can satisfy both.

**Example:**

```jsx
db.inventory.find( { dim_cm: { $gt: 15, $lt: 20 } } )
```

---

### ****Query for an Array Element that Meets Multiple Criteria****

Use `$elemMatch` operator to specify multiple criteria on the elements of an array such **that at least one array element satisfies all the specified criteria**.

The following example queries for documents where the `dim_cm` array contains at least one element that is both greater than (`$gt`) 22 and less than (`$lt`) 30:

```jsx
db.inventory.find( { dim_cm: { $elemMatch: { $gt: 22, $lt: 30 } } } )
```

---

### Query for an Element by the Array Index Position

Using dot notation, you can specify query conditions for an element at a particular index.

**Example:**

```jsx
db.inventory.find( { "dim_cm.1": { $gt: 25 } } )
```

### ****Query an Array by Array Length****

```jsx
db.inventory.find( { "tags": { $size: 3 } } )
```