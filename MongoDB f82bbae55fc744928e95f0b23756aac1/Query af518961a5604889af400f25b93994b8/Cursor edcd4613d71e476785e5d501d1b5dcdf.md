# Cursor

Read operations that return multiple documents do not immediately return all values matching the query.

Because a query can potentially match very large sets of documents, there operations rely upon an object called a cursor.

A cursosr fetches documents in batches to reduce both memory consumption and network bandwith usage.

The following functions directly return cursors:

- `Collection.find()`
- `Collection.aggregate()`
- `Collection.listIndexes()`
- `Db.aggregate()`
- `Collection.listCollections()`

### **Access Data From a Cursor**

[https://www.mongodb.com/docs/drivers/node/current/fundamentals/crud/read-operations/cursor/](https://www.mongodb.com/docs/drivers/node/current/fundamentals/crud/read-operations/cursor/)