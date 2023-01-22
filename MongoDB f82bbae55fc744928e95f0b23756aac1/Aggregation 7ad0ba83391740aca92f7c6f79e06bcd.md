# Aggregation

An aggregation pipeline consist of one or more stages that process documents:

- Each stage performs an operation on the input documents. For example, a stage can filter documents, group documents, and calculate values.
- The document that are output from a stage are passed to the next stage.
- An aggregation pipeline return results for groups of documents. Form example, return the total, average, maximum, and minimum values.

### Data to populate:

[persons.json](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/persons.json)

---

### Stages

In the `db.collection.aggregate()` method, pipeline stages appear in an array. Documents pass through the stages in sequence.

- `$match` : [$match](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$match%209bf0c210534b4e5ca11d135397f856dc.md)
- `$group` : [$group](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$group%204c6bccfda35e4d6dbd9ed76c394cb7d7.md)
- `$sort` : [$sort](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$sort%20ef5415aca96f44c8a485c58fce941f4c.md)
- `$unwind`: [$unwind](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$unwind%20b252518454bc41859ef4395966b58a53.md)
- `$limit`: [$limit](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$limit%201b111d68fa864bdc8a28ab7600377328.md)
- `$lookup`: [$lookup](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$lookup%20ff21e5a3581c4a29b9465244c0a27572.md)
- `$bucket`: [$bucket](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$bucket%201e9c4ca2779b45e1a7c061e8d90388d0.md)
- `$out`:  [$out](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$out%200ce20c9d40b446329667dd510b715743.md)
- `$facet`: [$facet](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$facet%20d58cc7c8d2464c67aaac84dd9dcfa779.md)
- `$unset`: [$unset](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$unset%20d0b70a4d59c64963a13cd0e8bb02e561.md)
- `$addFields` :  [$addFields](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$addFields%201b182aa58e244ceead892c99a162e125.md)
- `$replaceRoot`:  [$replaceRoot](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$replaceRoot%20d8b54f4b3aaa446bb8e0009df5d43ee8.md)

---

[$match](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$match%209bf0c210534b4e5ca11d135397f856dc.md)

[$group](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$group%204c6bccfda35e4d6dbd9ed76c394cb7d7.md)

[$sort](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$sort%20ef5415aca96f44c8a485c58fce941f4c.md)

[$project](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$project%20199a7ee3d6a24a5d9e6672b3488f8f02.md)

[$unwind](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$unwind%20b252518454bc41859ef4395966b58a53.md)

[$limit](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$limit%201b111d68fa864bdc8a28ab7600377328.md)

[$lookup](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$lookup%20ff21e5a3581c4a29b9465244c0a27572.md)

[$bucket](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$bucket%201e9c4ca2779b45e1a7c061e8d90388d0.md)

[$out](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$out%200ce20c9d40b446329667dd510b715743.md)

[$facet](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$facet%20d58cc7c8d2464c67aaac84dd9dcfa779.md)

[$unset](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$unset%20d0b70a4d59c64963a13cd0e8bb02e561.md)

[$addFields](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$addFields%201b182aa58e244ceead892c99a162e125.md)

[$replaceRoot](Aggregation%207ad0ba83391740aca92f7c6f79e06bcd/$replaceRoot%20d8b54f4b3aaa446bb8e0009df5d43ee8.md)