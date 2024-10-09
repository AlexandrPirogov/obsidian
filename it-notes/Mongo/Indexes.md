## Single Field Index

Single field indexes collect and sort data from a single field in each document in a collection.
Simple B-Tree

## Compound Index

Compound indexes collect and sort data from two or more fields in each document in a collection. Data is grouped by the first field in the index and then by each subsequent field.

## Multikey Index

Multikey indexes collect and sort data stored in arrays.

You do not need to explicitly specify the multikey type. When you create an index on a field that contains an array value, MongoDB automatically sets the index to be a multikey index.

## Geospatial Index

Geospatial indexes improve performance for queries on geospatial coordinate data. To learn more, see [Geospatial Indexes.](https://www.mongodb.com/docs/manual/core/indexes/index-types/index-geospatial/#std-label-geospatial-index)

## Text Index

Text indexes support text search queries on fields containing string content.

To learn more, see [Text Indexes on Self-Managed Deployments.](https://www.mongodb.com/docs/manual/core/indexes/index-types/index-text/#std-label-index-type-text)

## Hashed Index

Hashed indexes support [hashed sharding](https://www.mongodb.com/docs/manual/core/hashed-sharding/#std-label-sharding-hashed-sharding). Hashed indexes index the hash of the value of a field.

## Clustered Index[](https://www.mongodb.com/docs/manual/core/indexes/index-types/#clustered-index "Permalink to this heading")

_New in version 5.3_.

Clustered indexes specify the order in which [clustered collections](https://www.mongodb.com/docs/manual/core/clustered-collections/#std-label-clustered-collections) store data. Collections created with a clustered index are called clustered collections.