# $replaceRoot

Promotes a specified document to the top level and replace all other fields. The operation replaces all existing fields in the input document. You can promote an existing embedded document to the top level, or create a new document for promotion

- $replaceRoot operations fail with an error if `<replacementDocument>` is not document.

**Example:**

```jsx
db.persons.aggregate([
   {
       $replaceRoot: {
           newRoot: "$name"
       }
   }
]);
```

**Result:**

![Untitled]($replaceRoot%20d8b54f4b3aaa446bb8e0009df5d43ee8/Untitled.png)