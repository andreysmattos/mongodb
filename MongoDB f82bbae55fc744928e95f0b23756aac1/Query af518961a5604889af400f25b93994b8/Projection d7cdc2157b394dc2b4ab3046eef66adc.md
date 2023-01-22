# Projection

### **Specify Which Fields to Return**

Use a projection to control which fields appear in the documents returned by read operations. Many requests only require certain fields, so projections can help you limit unnecessary network bandwidth usage. Projections work in two ways:

- Explicitly include fields with a value of `1` . This has the side-effect of implicitly excluding all unspecified fields.
- Implicitly exclude fields with a value of `0`. This has the side-effect of implicitly including all unspecified fields.

> With the exception of the `_id` field, you cannot combine **inclusion** and **exclusion** statements in projection documents.
> 

### Examples:

- **Return the Specified field and the `_id` Field Only**

```bash
db.users.find({}, {name: 1, role: 1});
```

![Untitled](Projection%20d7cdc2157b394dc2b4ab3046eef66adc/Untitled.png)

- **Return All but the Excluded Fields**

```bash
db.users.find({}, {role: 0});
```

![Untitled](Projection%20d7cdc2157b394dc2b4ab3046eef66adc/Untitled%201.png)