## Insert tips

### Additional Methods for Inserts[](https://www.mongodb.com/docs/manual/reference/insert-methods/#additional-methods-for-inserts "Permalink to this heading")

The following methods can also add new documents to a collection, including collections hosted in MongoDB Atlas:

- [`db.collection.updateOne()`](https://www.mongodb.com/docs/manual/reference/method/db.collection.updateOne/#mongodb-method-db.collection.updateOne) when used with the `upsert: true` option.
    
- [`db.collection.updateMany()`](https://www.mongodb.com/docs/manual/reference/method/db.collection.updateMany/#mongodb-method-db.collection.updateMany) when used with the `upsert: true` option.
    
- [`db.collection.findAndModify()`](https://www.mongodb.com/docs/manual/reference/method/db.collection.findAndModify/#mongodb-method-db.collection.findAndModify) when used with the `upsert: true` option.
    
- [`db.collection.findOneAndUpdate()`](https://www.mongodb.com/docs/manual/reference/method/db.collection.findOneAndUpdate/#mongodb-method-db.collection.findOneAndUpdate) when used with the `upsert: true` option.
    
- [`db.collection.findOneAndReplace()`](https://www.mongodb.com/docs/manual/reference/method/db.collection.findOneAndReplace/#mongodb-method-db.collection.findOneAndReplace) when used with the `upsert: true` option.
    
- [`db.collection.bulkWrite()`.](https://www.mongodb.com/docs/manual/reference/method/db.collection.bulkWrite/#mongodb-method-db.collection.bulkWrite)


## Read tips

### Cursor[](https://www.mongodb.com/docs/manual/tutorial/query-documents/#cursor "Permalink to this heading")

The [Collection.find()](http://mongodb.github.io/node-mongodb-native/3.6/api/Collection.html#find) method returns a [cursor.](http://mongodb.github.io/node-mongodb-native/3.6/api/Cursor.html)

### Read Isolation[](https://www.mongodb.com/docs/manual/tutorial/query-documents/#read-isolation "Permalink to this heading")

For reads to [Replica sets](https://www.mongodb.com/docs/manual/replication/#std-label-replication) and replica set [shards](https://www.mongodb.com/docs/manual/sharding/#std-label-sharding-background), read concern allows clients to choose a level of isolation for their reads. For more information, see [Read Concern.](https://www.mongodb.com/docs/manual/reference/read-concern/)
### WARNING

MongoDB does not recommend [comparisons](https://www.mongodb.com/docs/manual/reference/operator/query/#std-label-query-comparison) on embedded documents because the operations require an _exact_ match of the specified `<value>` document, including the field order.


## Delete tips

Nothing interesting

## Update tips
### Replace a Document[](https://www.mongodb.com/docs/manual/tutorial/update-documents/#replace-a-document "Permalink to this heading")

To replace the entire content of a document except for the `_id` field, pass an entirely new document as the second argument to [Collection.replaceOne().](http://mongodb.github.io/node-mongodb-native/3.6/api/Collection.html#replaceOne)

When replacing a document, the replacement document must consist of only field/value pairs. The replacement document cannot include [update operators](https://www.mongodb.com/docs/manual/reference/operator/update/#std-label-update-operators-top-level) expressions.