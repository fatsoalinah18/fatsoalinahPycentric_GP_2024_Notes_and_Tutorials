
# MongoDB Notes

## What is MongoDB?
MongoDB is a **NoSQL** document-oriented database that stores data in a flexible, JSON-like format known as BSON. Unlike traditional relational databases, MongoDB is schema-less, meaning data structure can evolve over time, making it highly scalable and suitable for applications dealing with large volumes of unstructured data.

### Key Features:
- **Schema-less:** No fixed structure for data models.
- **BSON format:** Stores data as binary JSON.
- **Scalability:** Supports horizontal scaling through sharding.
- **High performance:** Optimized for handling large data sets.
- **Rich query language:** Supports dynamic queries, indexing, and aggregation.

---

## NoSQL Overview
NoSQL databases provide flexible schema design, unlike traditional relational databases (SQL) which are table-based.

### Types of NoSQL Databases:
1. **Key-Value Store** (e.g., Redis, Riak)
2. **Column-Family Store** (e.g., Cassandra, HBase)
3. **Document Store** (e.g., MongoDB, CouchDB)
4. **Graph Database** (e.g., Neo4j)

---

## MongoDB Data Modeling
Data modeling in MongoDB involves choosing between **embedding** or **referencing** related data:
- **Embedding:** Store related data in a single document (ideal for one-to-many relationships).
- **Referencing:** Store references to other documents (useful for many-to-many relationships).

**Normalization** vs. **Denormalization**:
- **Normalization** is splitting data into multiple collections (like tables).
- **Denormalization** embeds data to optimize performance.

---

## MongoDB Operators
MongoDB supports various operators for querying data:
- **Comparison operators:** `$eq`, `$gt`, `$lt`, `$in`
- **Logical operators:** `$and`, `$or`, `$not`
- **Array operators:** `$all`, `$size`, `$elemMatch`
- **Update operators:** `$set`, `$inc`, `$push`, `$unset`

Example query:
```javascript
db.collection.find({ price: { $gte: 100 } });
```

---

## Regular Expressions in MongoDB
You can use **regex** to search for patterns in text fields:
```javascript
db.collection.find({ name: { $regex: /^A/ } });
```
This finds all documents where the `name` field starts with "A."

---

## MongoDB Projection
**Projection** lets you specify which fields to include or exclude from query results:
```javascript
db.collection.find({}, { name: 1, age: 1, _id: 0 });
```
This will return only the `name` and `age` fields, excluding `_id`.

---

## Sorting and Limiting
Use the `sort()` and `limit()` methods to order and restrict query results:
```javascript
db.collection.find().sort({ price: -1 }).limit(10);
```
Sorts by `price` in descending order and limits results to 10 documents.

---

## Indexing
Indexes enhance query performance by avoiding full collection scans:
- **Single Field Index:** Index a single field.
- **Compound Index:** Index multiple fields.
- **Text Index:** For text search across documents.
- **Geospatial Index:** For location-based queries.

Example:
```javascript
db.collection.createIndex({ name: 1 });
```

---

## Aggregation Framework
The aggregation framework processes documents and transforms them using stages like `$match`, `$group`, `$project`, and `$sort`. It's powerful for data analysis and complex queries.

Example:
```javascript
db.collection.aggregate([
  { $match: { status: "active" } },
  { $group: { _id: "$category", tol: { $sum: 1 } } }
]);
```

---

## Replication and Sharding
- **Replication:** MongoDB replicates data across multiple servers to ensure high availability.
- **Sharding:** Data is distributed across multiple servers, enabling horizontal scaling. Each shard holds a portion of the dataset.

---

## GridFS
**GridFS** is MongoDB’s mechanism for storing large files (exceeding 16MB) by splitting them into chunks.

---

## Transactions and Atomicity
MongoDB guarantees **atomic operations** at the document level, meaning updates to a document are isolated:
```javascript
db.collection.updateOne({ _id: 1 }, { $set: { status: "active" } });
```

---

## MapReduce
MapReduce is used for large-scale data processing. It maps data to key-value pairs, then reduces it to produce aggregated results.
```javascript
db.collection.mapReduce(
  function() { emit(this.category, 1); },
  function(key, values) { return Array.sum(values); },
  { out: "category_totals" }
);
```

---

## Backup and Restore
MongoDB supports backup and restoration using `mongodump` and `mongorestore`:
```bash
mongodump --db mydb --out /backup
mongorestore --db mydb /backup/mydb
```

---

## SQL vs. MongoDB

| Feature          | SQL                          | MongoDB                        |
|------------------|------------------------------|--------------------------------|
| Schema           | Fixed schema (rigid)          | Flexible schema (dynamic)      |
| Data Model       | Tables with rows and columns  | JSON-like documents            |
| Scalability      | Vertical (scale-up)           | Horizontal (sharding)          |
| Relationships    | JOINs, foreign keys           | Embedded documents, DBRefs     |
| Query Language   | SQL                           | BSON Query                     |

---
