# MongoDB Interview Questions

## MongoDB Basic Interview Questions


<details>
<summary>
1.<b> What are the different types of NoSQL databases?</b>
</summary>

**NoSQL** is a non-relational DBMS, that does not require a fixed schema, avoids joins, and is easy to scale. The purpose of using a NoSQL database is for distributed data stores with humongous data storage needs. NoSQL is used for Big data and real-time web apps.

**Types of NoSQL Databases:**

1. Document databases
2. Key-value stores
3. Column-oriented databases
4. Graph databases




1. **Document databases:**

A document database stores data in JSON, BSON , or XML documents. In a document database, documents can be nested. Particular elements can be indexed for faster querying.

Documents can be stored and retrieved in a form that is much closer to the data objects used in applications, which means less translation is required to use the data in an application. SQL data must often be assembled and disassembled when moving back and forth between applications and storage.

**Example**: Amazon SimpleDB, CouchDB, MongoDB, Riak, Lotus Notes are popular Document originated DBMS systems.


2. **Key-value Stores**:

Data is stored in key/value pairs. It is designed in such a way to handle lots of data and heavy load. Key-value pair storage databases store data as a hash table where each key is unique, and the value can be a JSON, BLOB(Binary Large Objects), string, etc.

**Example**: of key-value stores are Redis, Voldemort, Riak, and Amazon's DynamoDB.



3. **Column-Oriented Databases**:

Column-oriented databases work on columns and are based on BigTable paper by Google. Every column is treated separately. The values of single column databases are stored contiguously.

They deliver high performance on aggregation queries like SUM, COUNT, AVG, MIN, etc. as the data is readily available in a column.

**Example**: Column-based NoSQL databases are widely used to manage data warehouses, business intelligence, CRM, Library card catalogs, HBase, Cassandra, HBase, Hypertable are examples of a column-based database.


4. **Graph Databases**:

A graph type database stores entities as well the relations amongst those entities. The entity is stored as a node with the relationship as edges. An edge gives a relationship between nodes. Every node and edge has a unique identifier.

Compared to a relational database where tables are loosely connected, a Graph database is a multi-relational in nature. Traversing relationships as fast as they are already captured into the DB, and there is no need to calculate them.

Graph base databases mostly used for social networks, logistics, spatial data.

**Example**: Neo4J, Infinite Graph, OrientDB, FlockDB are some popular graph-based databases.
</details>


<details>
<summary>
2.<b> Why use MongoDB?</b>
</summary>

As a document database, MongoDB makes it easy for developers to store structured or unstructured data. It uses a JSON-like format to store documents. This format directly maps to native objects in most modern programming languages, making it a natural choice for developers, as they don’t need to think about normalizing data. MongoDB can also handle high volume and can scale both vertically or horizontally to accommodate large data loads.
</details>

<details>
<summary>
3.<b> When Should You Use MongoDB?</b>
</summary>

1. Integrating large amounts of diverse data
2. Describing complex data structures that evolve
3. Delivering data in high-performance applications
4. Supporting hybrid and multi-cloud applications
5. Supporting agile development and collaboration
</details>

<details>
<summary>
4.<b> How does MongoDB exactly stores the data?</b>
</summary>

In MongoDB, records are stored as documents in compressed BSON files. The documents can be retrieved directly in JSON format, which has many benefits:

1. It is a natural form to store data.
2. It is human-readable.
3. Structured and unstructured information can be stored in the same document.
4. You can nest JSON to store complex data objects.
5. JSON has a flexible and dynamic schema, so adding fields or leaving a field out is not a problem.
6. Documents map to objects in most popular programming languages.
Most developers find it easy to work with JSON because it is a simple and powerful way to describe and store data.
</details>


<details>
<summary>
5.<b> Key Feature of MongoDB</b>
</summary>

**Key Features**

1. **Flexible Data Model**

 - Employs JSON-like documents (BSON format), facilitating complex data representation, deep nesting, and array structures.
- Provides dynamic schema support, allowing on-the-fly data definition and data types.
- Permits multi-document transactions within a replica set (group of nodes). Sharding extends this to support large distributed systems.

2. **Indexed Queries**
- Offers extensive indexing capabilities, such as single and multi-field support, text, geospatial, and TTL (Time to Live) Indexes for data expiration.
- Gives developers the tools needed to design and optimize query performance.

3. **High Availability & Horizontal Scalability**
- Uses replica sets for data redundancy, ensuring auto-failover in the event of a primary node failure.
- Adopts sharding to distribute data across clusters, facilitating horizontal scaling for large datasets or high-throughput requirements.

4. **Advanced Querying**
- Engages in ad-hoc querying, making it easy to explore and analyze data.
- Provides aggregation pipeline, empowering users to modify and combine data, akin to SQL GROUP BY.
- Specialized query tools like Map-Reduce and Text Search cater to distinctive data processing needs.
5. **Embedded Data Management**
- Encourages a rich, document-based data model where you can embed related data within a single structure.
- This denormalization can enhance read performance and data retrieval simplicity.

6. Rich Tool Suite
- Further augmented by several desktop and web-supported clients, MongoDB Atlas offers a seamless and unified experience for database management.
- Web-based MongoDB Compass handles query optimization and schema design.

**Code Sample: Data Interaction with MongoDB**
Here is the Python code:


```jsx harmony 
from pymongo import MongoClient

client = MongoClient()  # Connects to default address and port
db = client.get_database('mydatabase')

# Insert a record
collection = db.get_collection('mycollection')
inserted_id = collection.insert_one({'key1': 'value1', 'key2': 'value2'}).inserted_id

# Query records
for record in collection.find({'key1': 'value1'}):
    print(record)

# Update record
update_result = collection.update_one({'_id': inserted_id}, {'$set': {'key2': 'new_value'}})
print(f"Modified {update_result.modified_count} records")

# Delete record
delete_result = collection.delete_one({'key1': 'value1'})
print(f"Deleted {delete_result.deleted_count} records")

```
</details>


<details>
<summary>
6.<b> How does MongoDB differ from relational databases?</b>
</summary>

While both MongoDB and relational databases handle data, they do so in fundamentally different ways. Let's explore the key distinctions.


1. **Data Model**

**Relational Databases**
- Use tables with predefined schemas that enforce relationships and data types.
- Often use normalization techniques to minimize data redundancy.

**MongoDB**
- Stores data as flexible, schema-less sets of key-value pairs inside documents.
- Relationships can be represented through embedded documents or referencing via keys, providing more granular control and allowing for a more natural representation of real-world data.

2. **Data Integrity**

**Relational Databases**
- Rely on ACID transactions to ensure data consistency.

**MongoDB**

- Offers ACID guarantees at the document level, though transactions across multiple documents happen within the same cluster to ensure consistency.
- Provides multi-document transactions for more complex operations.

3. **Query Language**

**Relational Databases**

- Use SQL, a declarative query language.

**MongoDB**
- Employs JSON-like queries, which are imperative and resemble the structure of the data it operates on.

4. **Scalability**

**Relational Databases**
- Traditionally use a vertical scaling approach, featuring limits on a single server's resources such as CPU, storage, and memory.
**MongoDB**
- Designed for horizontal scaling, making it easier to handle larger datasets and heavier loads by distributing data across multiple servers. This scalability also supports cloud-based setups.

5. **Performance**

**Relational Databases**
- Can handle complex queries efficiently but might require multiple joins, potentially degrading performance.

**MongoDB**
- Optimized for quick CRUD operations and can efficiently handle large volumes of read and write requests.

6. **Indexing**

**Relational Databases**
- Tables can have a multitude of indexes, which can be a mix of clustered, non-clustered, unique, or composite.

**MongoDB**
- Collections can have several indexes, including single field, compound, and multi-key indexes.

7. **Data Joins**
**Relational Databases**
- Use joins to merge related data from different tables during a query, ensuring data integrity.
**MongoDB**
- Offers embedded documents and manual reference to achieve similar results, but multi-collection joins have performance and scalability considerations.
</details>


<details>
<summary>
7.<b> Can you describe the structure of data in MongoDB?</b>
</summary>

In **MongoDB**, data units are organized into **collections**, which group related `documents`. Each document corresponds to a single record and maps to fields or `key-value pairs.`

**JSON-Like Format**
Data in MongoDB is stored using a `BSON` (Binary JSON) format that can handle a maximum depth of 100 levels. This means a BSON object or element can be a document consisting of up to 100 sub-elements, such as fields or values.

Example: **Nested Document**
Here is a nested document:


```jsx harmony 
{
  "_id": "123",
  "title": "My Blog Post",
  "author": {
    "name": "John Doe",
    "bio": "Tech enthusiast"
  },
  "comments": [
    {
      "user": "Alice",
      "text": "Great post"
    },
    {
      "user": "Bob",
      "text": "A bit lengthy!"
    }
  ]
}

```

In the example above, the "author" field is an embedded document (or sub-document), and the "comments" field is an array of documents.

**Key Features**

**Ad-Hoc Schema:** Documents in a collection don't need to have the same fields, providing schema flexibility.

**Atomicity at the Document Level**: The ACID properties (Atomicity, Consistency, Isolation, Durability) of a transaction, which guarantee that the modifications are successful or unsuccessful as a unit of work.

**Index Support**: Increases query performance.

**Support for Embedded Data**: You can nest documents and arrays.

**Reference Resolution**: It allows for processing references across documents. If a referenced document is modified or deleted, any reference to it from another document also needs to be updated or deleted in a multi-step atomic operation.

**Sharding and Replication**: For horizontal scaling and high availability.


**Data Model Considerations**

**One-to-One**: Typically achieved with embedded documents.

**One-to-Many (Parent-Child)**: This can be modelled using embedded documents in the parent.

**One-to-Many (Referenced)**: Achieved through referencing, where several documents contain a field referencing a single document. For better efficiency with frequent updates, consider referencing.

**Many-to-Many**: Modeled similarly to "One-to-Many" relationships.

`You should avoid using`  “repeatable patterns”, such as storing data in separate arrays or collections, to ensure smooth data manipulation and effective query operations.

For example, using separate collections for similar types of data based on a category like "users" and "admins" instead of a single "roles" array with multiple documents.

The above best practice example prevents `data redundancy` and ensures `consistency` between similar documents. Redundant storage or separating non-redundant data can lead to inconsistencies and increase the effort required for maintenance.
</details>


<details>
<summary>
8.<b> What is “Namespace” in MongoDB?</b>
</summary>

MongoDB stores BSON (Binary Interchange and Structure Object Notation) objects in the collection. The concatenation of the collection name and database name is called a namespace
</details>


<details>
<summary>
9.<b>  What do you understand by NoSQL databases? Explain</b>
</summary>

At the present time, the internet is loaded with big data, big users, big complexity etc. and also becoming more complex day by day. NoSQL is answer of all these problems; It is not a traditional database management system, not even a relational database management system (RDBMS). NoSQL stands for “Not Only SQL”. NoSQL is a type of database that can handle and sort all type of unstructured, messy and complicated data. It is just a new way to think about the database.

</details>


<details>
<summary>
10.<b> What is the difference between MongoDB and MySQL? </b>
</summary>
Although MongoDB and MySQL both are free and open source databases, there is a lot of difference between them in the term of data representation, relationship, transaction, querying data, schema design and definition, performance speed, normalization and many more. To compare MySQL with MongoDB is like a comparison between Relational and Non-relational databases.

</details>


<details>
<summary>
11.<b> What is the difference b/w MongoDB and CouchDB?</b>
</summary>

MongoDB and CouchDB both are the great example of open source NoSQL database. Both are document oriented databases. Although both stores data but there is a lot of difference between them in terms of implementation of their data models, interfaces, object storage and replication methods etc.
</details>


<details>
<summary>
12.<b> Why does Profiler use in MongoDB?</b>
</summary>

MongoDB uses a database profiler to perform characteristics of each operation against the database. You can use a profiler to find queries and write operations

</details>


<details>
<summary>
13.<b>  If you remove an object attribute, is it deleted from the database?</b>
</summary>

 Yes, it be. Remove the attribute and then re-save () the object.
</details>



<details>
<summary>
14.<b> Does MongoDB need a lot space of Random Access Memory (RAM)?</b>
</summary>

No. MongoDB can be run on small free space of RAM
</details>

## MongoDB Advance Interview Questions

<details>
<summary>
15.<b> What is a Document in MongoDB?</b>
</summary>

In MongoDB, a `document` is the basic data storage unit. It's a JSON-like structure that stores data in key-value pairs known as fields.

**Document Structure**

Each document:

- Is a top-level entity, analogous to a row in a relational database.
- Is composed of field-and-value pairs, where the value can be a variety of data types, including arrays or sub-documents.
- Has a unique _id or primary key that is indexed for fast lookups.

Here is the document structure:


```jsx harmony 
{
  "_id": 1,
  "name": "John Doe",
  "age": 30,
  "email": "john.doe@email.com",
  "address": {
    "city": "Example",
    "zip": "12345"
  },
  "hobbies": ["golf", "reading"]
}

```

**Collections**
Documents are grouped into `collections`. Each collection acts as a container with a unique namespace within a database. Collections don't enforce a predefined schema, which allows for flexibility in data modeling.

**Key Advantages**

1. **Flexibility**: Documents can be tailored to the specific data needs of the application without adherence to a rigid schema.

2. **Data Locality**: Related data, like a user's profile and their posts, can be stored in one document, enhancing performance by minimizing lookups.

3. **JSON Familiarity**: Documents, being JSON-like, enable easier transitions between application objects and database entities.

4. **Indexing**: Fields within documents can be indexed, streamlining search operations.

5. **Transaction Support**: Modern versions of MongoDB offer ACID-compliant, multi-document transactions that ensure data consistency.

**Example Use Case**
Consider an online library. Instead of having separate tables for users, books, and checkouts as in a relational database, you could store all the pertinent data about a user, including their checked-out books, in a `single document` within a `users` collection:


```jsx harmony 
{
  "_id": 1,
  "name": "John Doe",
  "email": "john.doe@email.com",
  "address": { "city": "Example", "zip": "12345" },
  "checkedOutBooks": [
    { "bookId": 101, "dueDate": "2022-02-28" },
    { "bookId": 204, "dueDate": "2022-03-15" }
  ]
}

```


This approach enables swift retrieval of all pertinent user information in one go.

**Considerations**

**Atomicity**: While single-document operations are atomic by default in MongoDB, transactions and atomicity guarantee apply to multi-document operations primarily.
**Size Limitations**: Documents can't exceed 16MB in size. In most cases, this limit should not be a practical concern.

</details>


<details>
<summary>
16.<b> How is data stored in collections in MongoDB?</b>
</summary>

In **MongoDB**, data is stored in `types of collections`, ensuring flexibility and efficiency in data modeling.

**Collection Basics**

- Collections are the primary data storage structures in MongoDB, akin to tables in relational databases.
- They are schema-less, meaning that documents within a collection can have varying structures. This offers superior flexibility, while still allowing for structure validation through the use of JSON schema.
**Documents**

- Documents serve as the unit of data storage in MongoDB. These are akin to rows in relational databases or objects in languages such as JavaScript.
- Documents are represented in BSON (Binary JSON) format, a binary representation closely mirroring JSON's attribute-value data model.

**Data Organization Hierarchy**

- Data in MongoDB is organized in a hierarchical structure, with each database having one or more collections, each of which stores multiple documents, all of which can possess distinct structures.

**Key Data Principles**
- MongoDB collections are designed to optimize data access rather than just serving as containers.
- To maximize efficiency, it's crucial to design collections that cater to common query patterns.

**Types of Database Collections**

- By understanding the nuances of each collection type, you can better customize your MongoDB system to cater to specific use-cases and performance requirements.
###### AJAX Comments

- To effectively and iteratively store and manage comments, the AJAX Comments feature is engineered to provide a blend of flexibility and ease of access.
- It leverages JSON-like documents and the native power of MongoDB, such as rich indexing for efficient interactions.
###### Newsfeed Posts

- Tailored for sequential, feed-like content, such as posts from a social media platform or a messaging app.
- It benefits greatly from the ordered nature of BSON documents, making sure newer posts are easy to fetch.
###### User Profiles

- Focusing on user-defined, diverse, and possibly unstructured details, the User Profile collection is an ideal repository for self-descriptive user profiles.
- The flexibility of schema allows for comprehensive storage with minimal overhead.

###### Metadata

- For persistent and global configurations, the Metadata collection provides a secure space to cache system information.
###### Product Catalog

- Bolsters browsing and shopping activities by housing consistent, structured details related to products or services on offer.
- This attention to consistency helps in easy data retrieval and optimized user experiences.

###### Logging
- Ideally suited to record system interactions and debugging info, the Logging collection maintains an organized trail of system activity, nurturing a culture of informed decision-making.

</details>

<details>
<summary>
17.<b> Describe what a MongoDB database is.</b>
</summary>

A `MongoDB database` is a document-oriented, NoSQL database consisting of collections, each of which in turn comprise documents.

**Core Concepts**

1. **Collection**
A collection is a grouping of MongoDB documents. A collection is the equivalent of a table in a relational database.
Advantages of Using Collections:

**Flexibility**: Each document in a collection can have its own set of fields. Structural changes are easier to manage than in traditional, rigid SQL tables.
**Scalability**: Collections can be distributed across multiple servers or clusters to handle large data volumes.

2. **Document**
Synonymous with a record, a `document` is the main data storage unit in MongoDB. It is a set of key-value pairs.

- Key: The field name
- Value: The data

**Document-Key Pairs**:
- Each document maintains a unique ID, known as the object ID which is autogenerated. This ensures every document is distinct.
- Unlike SQL databases where each row of a table follows the same schema, a document can be more fluid, accommodating fields as required.
Considerations When Choosing the Level of Normalization:

**Optimized Reads**: Normalization into separate collections may be beneficial if there are large amounts of data that might not always have to be fetched.

**Batch Inserts and Updates**: Denormalization often leads to simpler write operations. If there will be a lot of changes or inserts, denormalization can be more efficient.

**Atomicity**: When data that belongs together is split into different collections, ensuring atomicity can become difficult.

3. **Field**
A `field` is a single piece of data within a document. It's synonymous with a database column.

**Field Type**: MongoDB supports multiple field types, including arrays.

**Limit on Nested Fields**: Documents can be nested, which is like being able to have sub-documents within a main document. However, there is a depth limitation: you can't embed documents endlessly.

**Schema**
MongoDB is often regarded as `schema-less`, but a more accurate description is that it's `flexible`. While documents within a single collection can have different fields, a robust schema design process is still essential.

Adapting to Evolving Schemas:

**Versioning**: Managed schema changes and versioning in the application layer.

**Schema Validation**: Introduced in MongoDB 3.2, this feature allows for the application of structural rules to documents.

**Education and Training**: Properly educating developers on the use of a database can minimize potential misuse of its flexibility.

**Use of Techniques to Ensure Data Integrity**: Techniques such as double-entry bookkeeping can assure data accuracy, especially when dealing with multiple, occasionally outdated records.

**M**odeling vs. Tuning Approaches
**Normalization**: Seeks to reduce redundancy and improve data consistency.

**Denormalization**: Emphasizes performance gains. Redundancies are knowingly introduced for optimized and rapid reads.

**Use Cases Dictate**: Neither is definitively superior; their suitability depends on the specific use case.


</details>


<details>
<summary>
18.<b> What is the default port on which MongoDB listens?</b>
</summary>

The default `port number` for MongoDB is `27017`. While it is possible to run multiple instances of MongoDB on the same machine, each instance must have its unique port number to ensure they don't conflict.
</details>


<details>
<summary>
19.<b> How does MongoDB provide high availability and disaster recovery?</b>
</summary>

`MongoDB` ensures high availability and disaster recovery through a robust data architecture and a distributed system model. It integrates various mechanisms to maintain data integrity, uptime assurances, and data redundancy.

**Key Components**

1. **Replica Sets**: These are clusters of MongoDB nodes that use automatic failover to maintain data consistency.

2. **WiredTiger Storage Engine**: It powers numerous features including data durability, in-memory storage, and compression.

3. **Oplog**: Short for "operations log", it records all write operations in an append-only manner.

4. **Write Concerns**: These are rules that determine the level of acknowledgment required for write operations.

5. **Read Preferences**: They define which nodes in a cluster can satisfy read operations.

6. **Data Centers**: Hardware resilience can be achieved by distributing nodes across multiple data centers.

7. **Backups and Restores**: MongoDB offers built-in mechanisms to backup and restore data, further aiding in disaster recovery.

8. **Monitoring Tools**: For performance tracking and potential issue detection.

9. **Technology Agnostic**: Can deploy on multi-cloud, hybrid and on-premises architectures.

**Data Recovery Modes**

1. **Restore**: Achieved through the backup of data when the config server is the only component that is active and accurate. This method doesn't consider data changes made after the backup was captured.

2. **Oplog Replays**: This involves using oplogs that track changes, ensuring that even after a cluster restart, any missed transactions are reinstated.

3. **Snapshotting**: It is a consistent snapshot of data across the nodes in the replica set.

**Code Example: Write Concerns and Oplog**
Here is the Python code:

```jsx harmony
# Import the MongoClient class from pymongo.
from pymongo import MongoClient

# Establish connection to the MongoDB server using MongoClient.
client = MongoClient('mongodb://localhost:27017/')

# Assign the test database to a variable
db = client.test

# Assign the collection within the test database to a variable
collection = db.test_collection

# Insert a document into the collection and set the write concern to 'majority'
result = collection.insert_one({'test_key': 'test_value'}, write_concern={'w': 'majority'})

# Fetch the oplog entry associated with the insert operation.
oplog_cursor = db.local.oplog.rs.find({'ns': 'test.test_collection', 'op': 'i'})

# Access the result and compare the count to ensure the operation was recorded in the oplog.
operation_count = oplog_cursor.count()
```
**Recommendations**
- Employ consistent and comprehensive backup strategies in conjunction with multi-faceted recovery plans.

</details>


<details>
<summary>
20.<b> What are indexes in MongoDB, and why are they used?</b>
</summary>

`Indexes` are employed in `MongoDB` to optimize database queries by providing faster access to data. Without indexes, MongoDB performs full collection scans.

**Common Types of Indexes in MongoDB**

- **Single Field Index**: The most basic form of index.
- **Compound Index**: Generated across multiple fields; used for queries involving these fields.
- **Multikey Index**: Specially designed for arrays or embedded documents.

Batch Insert Operations on an Indexed Collection Describe any performance bottlenecks you anticipate.

- **Text Index**: Suited for text searches, often leveraging stemming and stop words.
Unique Explain in which situations it's beneficial to manage a unique index. Discard icon GEO Index Describe the purpose of this index type and the type of queries it can optimize.

- **TTL (Time-to-Live) Index**: Deletes documents after a specified duration, suitable for logs and cached data.

**Common Performance Bottlenecks with Indexes**
**Index Overuse**: Too many indexes can degrade write performance.

**Index Size**: Larger indexes consume more RAM and might slow down read and write operations.

**Index Inefficiency**: Inaccurate or non-selective index usage can render them ineffective.

**Write Penalties**: Indexes incur an overhead during writes, impacting their efficiency in write-heavy systems.

**Index Maintenance**: Regular maintenance, like rebuilding or reorganizing indexes, is often necessary.

**Workload Misalignment**: An index might not be beneficial if it's not aligned with the actual query workload.

Make sure to keep the indexes required and remove any unnecessary ones.
</details>


<details>
<summary>
21.<b> What is the role of the id field in MongoDB documents?</b>
</summary>

The `_id` Field in MongoDB serves as a `primary key` and provides several key functionalities:

**Uniqueness Guarantee**: Each document must have a unique `_id`, which ensures data integrity.

**Automatic Indexing**: Automated indexing based on `_id` enhances query efficiency.

**Inherent Timestamp**: The _id can have an embedded timestamp, useful for time-based operations.

For instance, with an `ObjectId`, the first 8 characters represent a 4 byte timestamp:

timestamp = substr(ObjectId,0,8)

**Concurrency Control**: If multiple write operations with the same `_id` occur simultaneously, MongoDB uses a technique called `last-write wins` to manage the conflict:

The document with the most recent `_id` value, or timestamp if using an ObjectId, supersedes the others.

**Modify and Return**: When executing an operation to insert a new document or find & modify an existing one, you can request to return the modified document and its `_id`.

**ObjectId vs. Custom _id**
While MongoDB provides **automatic ObjectId** generation, documents can also use custom values.

**Custom Representations**: Unleash flexibility by using custom strings, numbers, or other valid BSON types for the _id field.

**Controlled Uniformity**: Design your own _id strategy to align with data, such as employing natural keys for documents originating from specific, external sources.

**Migrate with Care**: Once an application is live, altering the structure can be intricate. Transition plans are vital for a seamless shift.

**Custom Indexing**: Managing an index on a uniquely generated custom _id turns the data into a compact, high-throughput structure.

**Schema Design and the _id Field**
The choice between automatic ObjectId and custom `_id` values links back to the `intended data model, data access patterns`, and specific `domain requirements`.

While using the automatic ObjectId brings about benefits like `ease of use` and `embedded timestamp`, custom `_id` generation provides finer control and helps in scenarios where a specific data structure is favored or where external data sources need to be integrated.
</details>


<details>
<summary>
22.<b>  How do you create a new MongoDB collection?</b>
</summary>

The process for creating a new collection in MongoDB is simple and instantaneous.

**Benefits of Instantaneous Creation**
- MongoDB collections are schemaless, leading to immediate collection creation.
- Document structure and content drive schema design.
- No predefined schema requirements allow for dynamic, evolving data models.

**Steps to Create a Collection**

1. **Select the Database**: Ensure you are connected to the intended database for the collection's creation. Switch to the desired database using use in the mongo shell or select the database programmatically in your driver's API.

2. **Perform a Write Operation**: The new collection is created the moment you execute a write operation such as insert, update, or save.

3. **Check Collection Existence (Optional)**: While not necessary for the creation process, you can verify the collection is created using the listCollections method.


</details>


<details>
<summary>
23.<b> What is the syntax to insert a document into a MongoDB collection?</b>
</summary>

To `insert a document` into a **MongoDB collection**, you can use the `insertOne()` method, which accepts the document as an argument:

```jsx harmony 
db.collectionName.insertOne({
  key1: "value1",
  key2: 2,
  key3: [1, 2, 3],
  key4: { nestedKey: "nestedValue" }
});

```

Alternatively, you can use the `insertOne()` method, supply an array of documents with `insertMany()`:

```jsx harmony 

db.collectionName.insertMany([
  { key: "value1" },
  { key: "value2" }
]);
```
</details>


<details>
<summary>
24.<b>  Describe how to read data from a MongoDB collection.</b>
</summary>

To `read` data from a `MongoDB collection`, you use the `find` method with various options for querying and data manipulation.

**Key Methods**

**find**(filter, projection): Retrieves documents based on filter conditions. You can specify which fields to include or exclude in the result (projection).
**findOne**(filter, projection): Similar to find but retrieves only the first matching document.
**distinct**(field, filter): Returns a list of distinct values for a specific field, optionally filtered.

**Query Operators**
- **Comparison**: $eq, $gt, $lt, $in, $nin, etc.
- **Logical**: $and, $or, $not, $nor, etc.
- **Element**: $exists, $type
- **Evaluation**: $regex, $mod, $text
- **Geospatial**: $geoNear, $geoWithin, etc.

**Aggregation**
MongoDB also provides the `aggregation framework` for complex operations, using a pipeline of various stages like `match`, `group`, `sort`, `limit`, etc.

**Example: Basic Find Query**
Here is a Python code:

```jsx harmony 

import pymongo

client = pymongo.MongoClient("mongodb://localhost:27017/")
db = client["mydatabase"]
collection = db["mycollection"]

# Retrieve all documents
all_documents = collection.find()

# Alternatively, you can iterate through the cursor:
for doc in all_documents:
    print(doc)
```

**Example: Querying with Filters**
Here is a Python code:

```jsx harmony 
# Let's say we have the following documents in the collection:
# [{
#    "name": "John",
#    "age": 30,
#    "country": "USA"
#  },
#  {
#    "name": "Jane",
#    "age": 25,
#    "country": "Canada"
# }]

# Retrieve documents where the name is "John"
john_doc = collection.find_one({"name": "John"})
print(john_doc)  # Output: {"name": "John", "age": 30, "country": "USA"}

# Retrieve documents where age is greater than or equal to 25 and from country "USA"
filter_criteria = {"age": {"$gte": 25}, "country": "USA"}
docs_matching_criteria = collection.find(filter_criteria)
for doc in docs_matching_criteria:
    print(doc)
    # Output: {"name": "John", "age": 30, "country": "USA"}
```

**Projection**
`Projection` helps control the fields returned. It uses a dictionary where fields to include are marked with 1, and those to exclude with 0.

For instance, {"name": 1, "age": 1, "_id": 0} only includes name and age while excluding _id:

Here is a Python code:

```jsx harmony 

# Retrieve the name and age fields, ignoring the _id field
docs_with_limited_fields = collection.find({}, {"name": 1, "age": 1, "_id": 0})
for doc in docs_with_limited_fields:
    print(doc)
    # Output: {"name": "John", "age": 30}
    #         {"name": "Jane", "age": 25}
```

**Sort, Skip, and Limit**
`sort`, `skip`, and `limit` help in reordering, pagination, and limiting the result size.

Here is a Python code:

```jsx harmony 
# Sort all documents by age in descending order
documents_sorted_by_age = collection.find().sort("age", -1)

# Skip the first two documents and retrieve the rest
documents_after_skipping = collection.find().skip(2)

# Limit the number of documents returned to 3
limited_documents = collection.find().limit(3)
```

**Distinct Values**

Here is a Python code:

```jsx harmony 

# Suppose, the collection has a "country" field for each document

# Get a list of distinct countries
distinct_countries = collection.distinct("country")
print(distinct_countries)  # Output: ["USA", "Canada"]
```

**Indexes**
Indexes improve read performance. Ensure to use appropriate indexes for frequent and complex queries to speed up data retrieval. If the queries differ from the indexing pattern or if the collection is small, the gain from indexing might be insignificant, or it could even affect the write performance of the database. Choose an indexing strategy based on your data and usage patterns.

For example, if you frequently query documents based on their "country" field, consider creating an index on that field:

Here is a Python, PyMongo code:

```jsx harmony 

collection.create_index("country")
```

This would make lookups based on the "country" field more efficient.


</details>


<details>
<summary>
25.<b> Explain how to update documents in MongoDB.</b>
</summary>

`MongoDB` offers several ways to update documents (equivalent to SQL's "rows"). Let’s look at the most common methods.

**Update Methods**

**Replace**: Entire document is updated. This is the closest equivalence to SQL's UPDATE statement.
**Update**: For selective field updates, you use $set, $inc, $push, $unset, and more. This resembles SQL's UPDATE with selective column updates.

***Replace & Update in MongoDB***

###### Top-Down Approach Using Replace

**Method**: db.collectionName.updateOne()

**Code**:

```jsx harmony 
db.collectionName.updateOne(
    {"name": "John Doe"},
    {$set: {"age": 30}}
);
```

**Use-Case**: When replacing an entire document isn't needed. For example, when changing a user's email address.

**Bottom-Up Approach Using Update + $set**
**Method**: db.collectionName.replaceOne()

**Code**:

```jsx harmony 

db.collectionName.replaceOne(
    {"name": "John Doe"},
    {"name": "John Doe", "age": 30}
);
```

**Use-Case**: When an entire document needs updating or replacing, such as a product detail or a user’s information.
</details>


<details>
<summary>
26.<b> What are the MongoDB commands for deleting documents?</b>
</summary>

MongoDB offers several methods for deleting documents.

**Deletion Methods in MongoDB**
1. **deleteOne()**: Deletes the first matched document.
2. **deleteMany()**: Removes all matching documents.
3. **remove()**: Legacy function; use deleteOne() or deleteMany() instead.

**General Syntax**

- For `deleteOne()`, the syntax is:

**db.collection.deleteOne({filter}, {options})**

- For `deleteMany()`, the syntax is:

`db.collection.deleteMany({filter}, {options})`

**Code Example: Deleting One or Many**
Here is the MongoDB shell script:

```jsx harmony 
// Connect to the database
use myDB;

// Delete a single document from 'myCollection'
db.myCollection.deleteOne({ name: "Document1" });

// Delete all documents from 'myCollection' with the condition 'age' greater than 25
db.myCollection.deleteMany({ age: { $gt: 25 } });

```
</details>

<details>
<summary>
27.<b> What is a replica set?</b>
</summary>
It is a group of mongo instances that maintain same data set. Replica sets provide redundancy and high availability, and are the basis for all production deployments.
</details>


<details>
<summary>
28.<b> Does Mongodb Support Foreign Key Constraints?</b>
</summary>

No. MongoDB does not support such relationships. The database does not apply any constraints to the system (i.e.: foreign key constraints), so there are no "cascading deletes" or "cascading updates". Basically, in a NoSQL database it is up to you to decide how to organise the data and its relations if there are any.
</details>


<details>
<summary>
29.<b> What Is Replication In MongoDB?</b>
</summary>

Replication is the process of synchronizing data across multiple servers. Replication provides redundancy and increases data availability. With multiple copies of data on different database servers, replication protects a database from the loss of a single server. Replication also allows you to recover from hardware failure and service interruptions
</details>


<details>
<summary>
30.<b>  Which are the most important features of MongoDB?</b>
</summary>

- Flexible data model in form of documents
- Agile and highly scalable database
- Faster than traditional databases
- Expressive query language
</details>


<details>
<summary>
31.<b> Compare SQL databases and MongoDB at a high level.</b>
</summary>

SQL databases store data in form of tables, rows, columns and records. This data is stored in a pre-defined data model which is not very much flexible for today's real-world highly growing applications. MongoDB in contrast uses a flexible structure which can be easily modified and extended.
</details>


<details>
<summary>
32.<b> How is data stored in MongoDB?</b>
</summary>

**Data in MongoDB is stored in BSON documents** – JSON-style data structures. Documents contain one or more fields, and each field contains a value of a specific data type, including arrays, binary data and sub-documents. Documents that tend to share a similar structure are organized as collections. It may be helpful to think of documents as analogous to rows in a relational database, fields as similar to columns, and collections as similar to tables.

**The advantages of using documents are:**

- Documents (i.e. objects) correspond to native data types in many programming languages.
- Embedded documents and arrays reduce need for expensive joins.
- Dynamic schema supports fluent polymorphism.
</details>


<details>
<summary>
33.<b> Mention the command to insert a document in a database called school and collection called persons</b>
</summary>

```jsx harmony 
use school;
db.persons.insert( { name: "kadhir", dept: "CSE" } )
```
</details>


<details>
<summary>
34.<b> What are Indexes in MongoDB?</b>
</summary>

Indexes support the efficient execution of queries in MongoDB. Without indexes, MongoDB must perform a collection scan, i.e. scan every document in a collection, to select those documents that match the query statement. If an appropriate index exists for a query, MongoDB can use the index to limit the number of documents it must inspect.
</details>



<details>
<summary>
35.<b> How many indexes does MongoDB create by default for a new collection? </b>
</summary>

By default, MongoDB created the _id collection for every collection.
</details>



<details>
<summary>
36.<b> Can you create an index on an array field in MongoDB? If yes, what happens in this case?</b>
</summary>

Yes. An array field can be indexed in MongoDB. In this case, MongoDB would index each value of the array so you can query for individual items:

```jsx harmony 
> db.col1.save({'colors': ['red','blue']})
> db.col1.ensureIndex({'colors':1})

> db.col1.find({'colors': 'red'})
{ "_id" : ObjectId("4ccc78f97cf9bdc2a2e54ee9"), "colors" : [ "red", "blue" ] }
> db.col1.find({'colors': 'blue'})
{ "_id" : ObjectId("4ccc78f97cf9bdc2a2e54ee9"), "colors" : [ "red", "blue" ] }
```
</details>



<details>
<summary>
37.<b> When should we embed one document within another in MongoDB?</b>
</summary>

You should consider embedding documents for:

- contains relationships between entities
- One-to-many relationships
- Performance reasons
</details>



<details>
<summary>
38.<b> What is BSON in MongoDB?</b>
</summary>

`BSON` is a binary serialization format used to store documents and make remote procedure calls in MongoDB. BSON extends the JSON model to provide additional data types, ordered fields, and to be efficient for encoding and decoding within different languages.
</details>



<details>
<summary>
39.<b> Explain the structure of ObjectID in MongoDB</b>
</summary>

`ObjectIds` are small, likely unique, fast to generate, and ordered. ObjectId values consist of 12 bytes, where the first four bytes are a timestamp that reflect the ObjectId’s creation. Specifically:

- a 4-byte value representing the seconds since the Unix epoch,
- a 5-byte random value, and
- a 3-byte counter, starting with a random value. In MongoDB, each document stored in a collection requires a unique _id field that acts as a primary key. If an inserted document omits the _id field, the MongoDB driver automatically generates an ObjectId for the _id field.
</details>



<details>
<summary>
40.<b> What is sharding?</b>
</summary>

Sharding means to store the data on the multiple machines.
</details>



<details>
<summary>
41.<b> What are NoSQL databases? What are the different types of NoSQL databases? </b>
</summary>

 A `NoSQL database` provides a mechanism for storage and retrieval of data that is modeled in means other than the tabular relations used in relational databases (like SQL, Oracle, etc.).

**Types of NoSQL databases**:

- Document Oriented
- Key Value
- Graph
- Column Oriented

</details>



<details>
<summary>
42.<b> How is MongoDB better than other SQL databases?</b>
</summary>

 MongoDB allows a highly flexible and scalable document structure. For e.g. one data document in MongoDB can have five columns and the other one in the same collection can have ten columns. Also, MongoDB database are faster as compared to SQL databases due to efficient indexing and storage techniques.
</details>



<details>
<summary>
43.<b> What does MongoDB not being ACID compliant really mean? </b>
</summary>

It's actually not correct that MongoDB is not ACID-compliant. On the contrary, MongoDB is ACID-compilant at the document level.

Any update to a single document is

- **Atomic**: it either fully completes or it does not
- **Consistent**: no reader will see a "partially applied" update
- **Isolated**: again, no reader will see a "dirty" read
- **Durable**: (with the appropriate write concern)
What MongoDB doesn't have is transactions - that is, multiple-document updates that can be rolled back and are ACID-compliant.

Multi-document transactions, scheduled for MongoDB 4.0 in Summer 2018*, will feel just like the transactions developers are familiar with from relational databases – multi-statement, similar syntax, and easy to add to any application.
</details>



<details>
<summary>
44.<b> How can you achieve primary key - foreign key relationships in MongoDB?</b>
</summary>

By default MongoDB does not support such primary key - foreign key relationships. However, we can achieve this concept by embedding one document inside another (aka subdocuments). Foe e.g. an address document can be embedded inside customer document.
</details>



<details>
<summary>
45.<b> Does MongoDB pushes the writes to disk immediately or lazily?</b>
</summary>

MongoDB pushes the data to disk lazily. It updates the immediately written to the journal but writing the data from journal to disk happens lazily.

</details>



<details>
<summary>
46.<b> If you remove a document from database, does MongoDB remove it from disk?</b>
</summary>

Yes. Removing a document from database removes it from disk too
</details>



<details>
<summary>
47.<b> What is a covered query in MongoDB? </b>
</summary>

A covered query is the one in which:

- fields used in the query are part of an index used in the query, and
- the fields returned in the results are in the same index
</details>



<details>
<summary>
48.<b> How can you achieve transaction and locking in MongoDB? </b>
</summary>

To achieve concepts of transaction and locking in MongoDB, we can use the nesting of documents, also called embedded (or sub) documents. MongoDB supports atomic operations within a single document.

</details>



<details>
<summary>
49.<b> What is Aggregation in MongoDB?</b>
</summary>

Aggregations operations process data records and return computed results. Aggregation operations group values from multiple documents together, and can perform a variety of operations on the grouped data to return a single result. MongoDB provides three ways to perform aggregation:

- the aggregation pipeline,
- the map-reduce function,
- and single purpose aggregation methods and commands.
</details>



<details>
<summary>
50.<b> What is Sharding in MongoDB? Explain.</b>
</summary>

Sharding is a method for storing data across multiple machines. MongoDB uses sharding to support deployments with very large data sets and high throughput operations

</details>



<details>
<summary>
51.<b> Why are MongoDB data files large in size? </b>
</summary>

MongoDB preallocates data files to reserve space and avoid file system fragmentation when you setup the server.
</details>



<details>
<summary>
52.<b> Why MongoDB is not preferred over a 32-bit system? </b>
</summary>

When running a 32-bit build of MongoDB, the total storage size for the server, including data and indexes, is 2 gigabytes. For this reason, do not deploy MongoDB to production on 32-bit machines.

If you're running a 64-bit build of MongoDB, there's virtually no limit to storage size.
</details>



<details>
<summary>
53.<b> Mention the command to check whether you are on the master server or not.</b>
</summary>

```jsx harmony 
db.isMaster()
```
</details>



<details>
<summary>
54.<b> Can one MongoDB operation lock more than one databases? If yes, how?</b>
</summary>

Yes. Operations like `copyDatabase()`, `repairDatabase()`, etc. can lock more than one databases involved.
</details>



<details>
<summary>
55.<b> What is oplog? </b>
</summary>

The `oplog` (operations log) is a special capped collection that keeps a rolling record of all operations that modify the data stored in your databases. MongoDB applies database operations on the primary and then records the operations on the primary’s oplog. The secondary members then copy and apply these operations in an asynchronous process.
</details>



<details>
<summary>
56.<b> Is there an “upsert” option in the mongodb insert command?</b>
</summary>

Since upsert is defined as operation that creates a new document when no document matches the query criteria there is no place for upserts in insert command. It is an option for the update command.

```jsx harmony 
db.collection.update(query, update, {upsert: true})

```
</details>


<details>
<summary>
57.<b> How to query MongoDB with “like”?</b>
</summary>

I want to query something as SQL's like query:

```jsx harmony 
select * 
from users 
where name like '%m%'
```

How to do the same in MongoDB?

```jsx harmony 
db.users.find({"name": /.*m.*/})
// or
db.users.find({"name": /m/})
```

You're looking for something that contains "m" somewhere (SQL's '%' operator is equivalent to Regexp's '.*'), not something that has "m" anchored to the beginning of the string.
</details>



<details>
<summary>
58.<b>  Find objects between two dates MongoDB</b>
</summary>

```jsx harmony 
db.CollectionName.find({"whenCreated": {
    '$gte': ISODate("2018-03-06T13:10:40.294Z"),
    '$lt': ISODate("2018-05-06T13:10:40.294Z")
}});

```
</details>



<details>
<summary>
59.<b> How replication works in MongoDB?</b>
</summary>

A `replica` set consists of a primary node and a secondary node too. With the help of a replica set, all the data from primary node to the secondary node replicates. Replication is a process of synchronizing the data. Replication provides redundancy and it also increases the availability of data with the help of multiple copies of data on the different database server. It also protects the database from the loss of a single server.
</details>



<details>
<summary>
60.<b> What are alternatives to MongoDB?</b>
</summary>

Cassandra, CouchDB, Redis, Riak, Hbase are a few good alternatives.
</details>



<details>
<summary>
61.<b> Does MongoDB support ACID transaction management and locking functionalities?</b>
</summary>

ACID stands that any update is:

- **Atomic**: it either fully completes or it does not
- **Consistent**: no reader will see a "partially applied" update
- **Isolated**: no reader will see a "dirty" read
- **Durable**: (with the appropriate write concern)
Historically MongoDB does not support default multi-document ACID transactions (multiple-document updates that can be rolled back and are ACID-compliant). However, MongoDB provides atomic operation on a single document. MongoDB 4.0 `will add support for multi-document transactions`, making it the only database to combine the speed, flexibility, and power of the document model with ACID data integrity guarantees.
</details>



<details>
<summary>
62.<b> Where can I run MongoDB? </b>
</summary>

MongoDB can be run anywhere, providing you complete freedom from platform lock-in.

MongoDB Atlas provides you with a complete, pay-as-you-go fully managed service for MongoDB in AWS, Azure, and Google Cloud Platform.

You can download MongoDB and run it yourself anywhere. MongoDB Ops Manager is the best way to run MongoDB on your own infrastructure – whether that lives on-premise or in a public cloud – making it fast and easy for operations teams to deploy, monitor, backup and scale MongoDB. Many of the capabilities of Ops Manager are also available in the MongoDB Cloud Manager service.
</details>



<details>
<summary>
63.<b> How does MongoDB ensure high availability?</b>
</summary>

MongoDB automatically maintains replica sets, multiple copies of data that are distributed across servers, racks and data centers. Replica sets help prevent database downtime using native replication and automatic failover.

A replica set consists of multiple replica set members. At any given time one member acts as the primary member, and the other members act as secondary members. If the primary member fails for any reason (e.g., hardware failure), one of the secondary members is automatically elected to primary and begins to process all reads and writes.


</details>



<details>
<summary>
64.<b> Is MongoDB schema-less?</b>
</summary>

No. In MongoDB schema design is still important. MongoDB's document model does, however, employ a different schema paradigm than traditional relational databases.

In MongoDB, documents are self-describing; there is no central catalog where schemas are declared and maintained. The schema can vary across documents, and the schema can evolve quickly without requiring the modification of existing data.

MongoDB's dynamic schema also makes it easier to represent semi-structured and polymorphic data, as documents do not all need to have exactly the same fields. For example, a collection of financial trading positions might have positions that are equity positions, and some that are bonds, and some that are cash. All may have some fields in common, but some fields ('ticker', “number_of_shares”) do not apply to all position types.
</details>



<details>
<summary>
65.<b> Should I normalize my data before storing it in MongoDB?</b>
</summary>

It depends from your goals. Normalization will provide an update efficient data representation. Denormalization will make `data reading` efficient.

In general, use embedded data models (denormalization) when:

- you have “contains” relationships between entities.
- you have one-to-many relationships between entities. In these relationships the “many” or child documents always appear with or are viewed in the context of the “one” or parent documents.
In general, use normalized data models:

- when embedding would result in duplication of data but would not provide sufficient read performance advantages to outweigh the implications of the duplication.
- to represent more complex many-to-many relationships.
- to model large hierarchical data sets.
Also normalizing your data like you would with a relational database is usually not a good idea in MongoDB. Normalization in relational databases is only feasible under the premise that JOINs between tables are relatively cheap. The $lookup aggregation operator provides some limited JOIN functionality, but it doesn't work with sharded collections. So joins often need to be emulated by the application through multiple subsequent database queries, which is very slow (see question MongoDB and JOINs for more information).


</details>



<details>
<summary>
66.<b>Why is a covered query important? </b>
</summary>

Since all the fields are covered in the index itself, MongoDB can match the query condition as well as return the result fields using the same index without looking inside the documents. Since indexes are stored in RAM or sequentially located on disk, such access is a lot faster.


</details>


<details>
<summary>
67.<b> Does MongoDB provide a facility to do text searches? How?</b>
</summary>

Yes. MongoDB supports creating text indexes to support text search inside string content. This was a new feature which can introduced in version 2.6.

</details>



<details>
<summary>
68.<b> What happens if an index does not fit into RAM?</b>
</summary>

If the indexes do not fit into RAM, MongoDB reads data from disk which is relatively very much slower than reading from RAM.

</details>



<details>
<summary>
69.<b> Mention the command to list all the indexes on a particular collection.</b>
</summary>

```jsx harmony 
db.collection.getIndexes()
```
</details>



<details>
<summary>
70.<b> At what interval does MongoDB write updates to the disk?</b>
</summary>

By default configuration, MongoDB writes updates to the disk every 60 seconds. However, this is configurable with the `commitIntervalMs` and `syncPeriodSecs` options.
</details>


<details>
<summary>
71.<b> What are Primary and Secondary Replica sets?</b>
</summary>

- **Primary** and master nodes are the nodes that can accept writes. MongoDB's replication is 'single-master:' only one node can accept write operations at a time.
- **Secondary** and slave nodes are read-only nodes that replicate from the primary.
</details>


<details>
<summary>
72.<b> By default, MongoDB writes and reads data from both primary and secondary replica sets. True or False</b>
</summary>

False. MongoDB writes data only to the primary replica set.
</details>



<details>
<summary>
73.<b> How does Journaling work in MongoDB?</b>
</summary>

When running with journaling, MongoDB stores and applies write operations in memory and in the on-disk journal before the changes are present in the data files on disk. Writes to the journal are atomic, ensuring the consistency of the on-disk journal files. With journaling enabled, MongoDB creates a journal subdirectory within the directory defined by dbPath, which is /data/db by default.
</details>


<details>
<summary>
74.<b> How can I combine data from multiple collections into one collection?</b>
</summary>

MongoDB 3.2 allows one to combine data from multiple collections into one through the $lookup aggregation stage.

```jsx harmony 
db.books.aggregate([{
    $lookup: {
            from: "books_selling_data",
            localField: "isbn",
            foreignField: "isbn",
            as: "copies_sold"
        }
}])

```
</details>



<details>
<summary>
75.<b> When to use MongoDB or other document oriented database systems?</b>
</summary>

 MongoDB is best suitable to store unstructured data. And this can organize your data into document format. These data stores don't enforce the ACID properties, and any schemas. This doesn't provide any transaction abilities. So this can scale big and we can achieve faster access (both read and write). If you wanted to work with structured data you can go ahead with RDBM.

</details>




<details>
<summary>
76.<b> How do I perform the SQL JOIN equivalent in MongoDB?</b>
</summary>

Mongo is not a relational database, and the devs are being careful to recommend specific use cases for $lookup, but at least as of 3.2 doing join is now possible with MongoDB. The new $lookup operator added to the aggregation pipeline is essentially identical to a left outer join:

```jsx harmony 
{
   $lookup:
     {
       from: <collection to join>,
       localField: <field from the input documents>,
       foreignField: <field from the documents of the "from" collection>,
       as: <output array field>
     }
}

```
</details>



<details>
<summary>
78.<b> How to query MongoDB with %like%?</b>
</summary>

I want to query something as SQL's like query:

```jsx harmony 

select * 
from users 
where name like '%m%'
```

How to do the same in MongoDB?

```jsx harmony 
db.users.find({name: /a/})  //like '%a%'
db.users.find({name: /^pa/}) //like 'pa%'
db.users.find({name: /ro$/}) //like '%ro'
```
Or using Mongoose:

```jsx harmony 
db.users.find({'name': {'$regex': 'sometext'}})

```
</details>



<details>
<summary>
79.<b> What is use of capped collection in MongoDB?</b>
</summary>

`Capped collections` allow you to define a fix length/size collection. After the size/no of documents have been reached it will override the oldest document to accommodate new documents. It is like a circular buffer. Capped collections support high-throughput operations that insert and retrieve documents based on insertion order.

Consider the following potential use cases for capped collections:

- Store log information generated by high-volume systems. Inserting documents in a capped collection without an index is close to the speed of writing log information directly to a file system.
- Cache small amounts of data in a capped collections.
</details>


<details>
<summary>
80.<b> What are the differences between MongoDB and MySQL?</b>
</summary>

The Major Differences between MongoDB and MySQL are:

1. There is a difference in the representation of data in the two databases. In MongoDB, data represents in a collection of JSON documents while in MySQL, data is in tables and rows. JSON documents can compare to associative arrays when using PHP and directory objects when using Python.
2. When it comes to querying, you have to put a string in the query language that the DB system parses. The query language is called Structured Query Language, or SQL,from where MySQL gets its name. This exposes your DB susceptible to SQL injectionattacks. On the other hand, MongoDB’s querying is object-oriented, which means you pass MongoDB a document explaining what you are querying. There is no parsing whatsoever, which will take some time getting used to if you already use SQL.
3. One of the greatest benefits of relational databases like MySQL is the JOIN operation. The operation allows for the querying across several tables. Although MongoDB doesn’t support joints, it supports multi-dimensional data types like other documents and arrays.
4. With MySQL, you can have one document inside another (embedding). You would have to create one table for comments and another for posts if you are using MySQL to create a blog. In MongoDB, you will only have one array of comments and one collection of posts within a post.
5. MySQL supports atomic transactions. You can have several operations within a transaction and you can roll back as if you have a single operation. There is no support for transactions in MongoDB and the single operation is atomic.
6. One of the best things about MongoDB is that you are not responsible for defining the schema. All you need to do is drop in documents. Any 2 documents in a collection need not be in the same field. You have to define the tables and columns before storage in MySQL. All rows in a table share the same columns.
7. MongoDB’s performance is better than that of MySQL and other relational DBs. This is because MongoDB sacrifices JOINS and other things and has excellent performance analysis tools. Note that you still have to index the data and the data in most applications is not enough for them to see a difference. MySQL is criticized for poor performance, especially in ORM application. However, you are unlikely to have an issue if you do proper data indexing and you are using a database wrapper.
8. One advantage of MySQL over NoSQL like MongoDB is that the community in MySQL is much better than NoSQL. This is mostly because NoSQL is relatively new while MySQL has been around for several years.
9. There are no reporting tools with MongoDB, meaning performance testing and analysis is not always possible. With MySQL, you can get several reporting tools that help you rove the validity of your applications.
10. RDBSs function on a paradigm called ACID, which is an acronym for (Atomicity, Consistency, Isolation, and Durability). This is not present in MongoDB database.
11. MongoDB has a Map Reduce feature that allows for easier scalability. This means you can get the full functionality of MongoDB database even if you are using low-cost hardware.
12. You do not have to come up with a detailed DB model with MongoDB because of is non-relational. A DB architect can quickly create a DB without a fine-grained DB model, thereby saving on development time and cost.
</details>


<details>
<summary>
81.<b> What's the advantage of the backup features in Ops Manager versus traditional backup strategies?</b>
</summary>

Ops Manager offers a lot of advantages, including:

- Point-in-Time-Recovery, Scheduled Backups. You can generate a restore image from an exact time in the past, which can be very helpful for restoring operations just prior to a catastrophic event.
- Continuous, Incremental Backup. Data is backed up continuously as the cluster updates. Your backups are always up-to-date.
- Sharded Cluster Backup. Backing up sharded clusters can be hard. Ops Manager Backup automates this for you.
- Queryable Backup. Query backups directly without having to restore them. Find the backup you need or examine how data has changed over time.

Ops Manager is included with MongoDB Enterprise Advanced, and provides continuous backup and point-in-time restore for MongoDB. Those interested in a cloud-based backup solution should consider MongoDB Cloud Manager, which provides continuous, online backup and point-in-time restore for MongoDB as a fully managed service.
</details>




<details>
<summary>
82.<b> What is a Storage Engine in MongoDB</b>
</summary>

 A storage engine is the part of a database that is responsible for managing how data is stored on disk. For example, one storage engine might offer better performance for read-heavy workloads, and another might support a higher-throughput for write operations.


</details>



<details>
<summary>
83.<b> Which are the two storage engines used by MongoDB? </b>
</summary>

MongoDB uses MMAPv1 and WiredTiger.

</details>



<details>
<summary>
84.<b> How does MongoDB provide concurrency?</b>
</summary>

MongoDB uses reader-writer locks that allow concurrent readers shared access to a resource, such as a database or collection, but give exclusive access to a single write operation.

</details>



<details>
<summary>
85.<b> How can you isolate your cursors from intervening with the write operations?</b>
</summary>

You can use the snapshot() method on a cursor to isolate the operation for a very specific case. snapshot() traverses the index on the _id field and guarantees that the query will return each document no more than once.

</details>



<details>
<summary>
86.<b> What is splitting in mongodb? </b>
</summary>

It is a background process that is used to keep chunks from growing too large.

</details>



<details>
<summary>
87.<b> Update MongoDB field using value of another field</b>
</summary>

Consider SQL command:

```jsx harmony 
UPDATE Person SET Name = FirstName + ' ' + LastName

```

In Mongo, is it possible to update the value of a field using the value from another field?

Answer

You cannot refer to the document itself in an update (yet). You'll need to iterate through the documents and update each document using a function like:

```jsx harmony 

db.person.find().snapshot().forEach(
    function (elem) {
        db.person.update(
            {
                _id: elem._id
            },
            {
                $set: {
                    name: elem.firstname + ' ' + elem.lastname
                }
            }
        );
    }
)
```
</details>



<details>
<summary>
88.<b> How to remove a field completely from a MongoDB document? </b>
</summary>

Suppose this is a document.

```jsx harmony 

{ 
    name: 'book',
    tags: {
        words: ['abc','123'], // <-- remove it comletely
        lat: 33,
        long: 22
    }
}
```

How do I remove words completely from all the documents in this collection?

**Answer**

```jsx harmony 
db.example.update({}, {$unset: {words:1}}, false, true);

```
</details>







<details>
<summary>
89.<b> How to condense large volumes of data in Mongo?</b>
</summary>

`Map-reduce` is a data processing paradigm for condensing large volumes of data into useful aggregated results. For map-reduce operations, MongoDB provides the `mapReduce` database command.
</details>



<details>
<summary>
90.<b> What are three primary concerns when choosing a data management system? </b>
</summary>

There are three primary concerns you must balance when choosing a data management system: consistency, availability, and partition tolerance.

- **Consistency** - means that each client always has the same view of the data.
- **Availability** - means that all clients can always read and write.
- **Partition tolerance** - means that the system works well across physical network partitions.
According to the CAP Theorem, you can only pick two.

In addition to CAP configurations, another significant way data management systems vary is by the data model they use: relational, key-value, column-oriented, or document-oriented (there are others, but these are the main ones).

- `Relational` systems are the databases we've been using for a while now. RDBMSs and systems that support ACIDity and joins are considered relational.
- `Key-value` systems basically support get, put, and delete operations based on a primary key.
Column-oriented systems still use tables but have no joins (joins must be handled within your application). Obviously, they store data by column as opposed to traditional row-oriented databases. This makes aggregations much easier.
- `Document-oriented` systems store structured "documents" such as JSON or XML but have no joins (joins must be handled within your application). It's very easy to map data from object-oriented software to these systems.
</details>




<details>
<summary>
91.<b> When to Redis or MongoDB?</b>
</summary>

**Use MongoDB if you don't know yet how you're going to query your data or what schema to stick with**. MongoDB is suited for Hackathons, startups or every time you don't know how you'll query the data you inserted. MongoDB does not make any assumptions on your underlying schema. While MongoDB is schemaless and non-relational, this does not mean that there is no schema at all. It simply means that your schema needs to be defined in your app (e.g. using Mongoose). Besides that, MongoDB is great for prototyping or trying things out. Its performance is not that great and can't be compared to Redis.

**Use Redis in order to speed up your existing application**. It is very uncommon to use Redis as a standalone database system (some people prefer referring to it as a "key-value"-store).
</details>




<details>
<summary>
92.<b> MongoDB relationships. What to use - embed or reference? </b>
</summary>

 I want to design a question structure with some comments, but I don't know which relationship to use for comments: embed or reference? Explain me pros and cons of both solutions?

**Answer**: In general,

- **embed** is good if you have one-to-one or one-to-many relationships between entities, and
- **reference** is good if you have many-to-many relationships.

Also consider as a general rule, if you have a lot of [child documents] or if they are large, a separate collection might be best. Smaller and/or fewer documents tend to be a natural fit for embedding.
</details>




<details>
<summary>
93.<b> How to get the last N records from find?</b>
</summary>

Use sort and limit in chain:

```jsx harmony 
db.foo.find().sort({_id:1}).limit(50);
```

</details>




<details>
<summary>
94.<b> How to find MongoDB records where array field is not empty?</b>
</summary>

Consider some variants:

```jsx harmony 
collection.find({ pictures: { $exists: true, $not: { $size: 0 } } }) 
collection.find({ pictures: { $exists: true, $ne: [] } })
collection.find({ pictures: { $gt: [] } }) // since MongoDB 2.6 
collection.find({'pictures.0': {$exists: true}}); // beware if performance is important - it'll do a full collection scan
```
</details>




<details>
<summary>
95.<b> How to find document with array that contains a specific value?</b>
</summary>

You have this schema:

```jsx harmony 
person = {
    name : String,
    favoriteFoods : Array
}

```

where the favoriteFoods array is populated with strings. How can I find all persons that have sushi as their favorite food using MongoDB?
Consider:
```jsx harmony 

PersonModel.find({ favouriteFoods: "sushi" }, ...);
PersonModel.find({ favouriteFoods: { "$in" : ["sushi"]} }, ...);
```
</details>




<details>
<summary>
96.<b> How to check if a field contains a substring? </b>
</summary>

Consider
```jsx harmony 

db.users.findOne({"username" : {$regex : ".*subsctring.*"}});

```
</details>




<details>
<summary>
97.<b>  Is it possible to update MongoDB field using value of another field? </b>
</summary>

 In SQL we will use:

 ```jsx harmony 
UPDATE Person SET Name = FirstName + ' ' + LastName

 ```

 Is it possible with MongoDB?

Answer: You cannot refer to the document itself in an update (yet). You'll need to iterate through the documents and update each document using a function. So consider:


```jsx harmony 
db.person.find().snapshot().forEach(
  function(elem) {
    db.person.update({
      _id: elem._id
    }, {
      $set: {
        name: elem.firstname + ' ' + elem.lastname
      }
    });
  }
);

```
</details>




<details>
<summary>
98.<b> Explain what is horizontal scalability?</b>
</summary>

**Horizontal scalability** is the ability to increase capacity by connecting multiple hardware or software entities so that they work as a single logical unit. MongoDB provides horizontal scalability as part of its core functionality.
</details>




<details>
<summary>
99.<b> How does MongoDB handle geographic data and geospatial queries?</b>
</summary>

MongoDB provides robust support for geographic data and geospatial queries:

- **Geospatial Indexes**: Support for 2d and 2dsphere indexes for efficient geospatial queries.
- **GeoJSON Objects**: Store location data using standard GeoJSON format.
- **Geospatial Queries**: Support for various types of geospatial queries:
- **Proximity**: Find documents near a point.
- **Intersection**: Find geometries that intersect with a specified geometry.
- **Within**: Find geometries contained within a specified geometry.
- **Aggregation Pipeline**: Geospatial stages like $geoNear for complex geo-based analytics.
- **Coordinate Systems**: Support for both legacy coordinate pairs and GeoJSON objects.
- **Geospatial Operators**: $near, $geoWithin, $geoIntersects, etc., for flexible querying.
- **Spherical Geometry**: 2dsphere index supports queries on an Earth-like sphere.
</details>



<details>
<summary>
99.<b> How can you achieve primary key - foreign key relationships in MongoDB?</b>
</summary>

The primary key-foreign key relationship can be achieved by embedding one document inside the another. As an example, a department document can have its employee document(s).


</details>



<details>
<summary>
99.<b></b>
</summary>
</details>


<details>
<summary>
99.<b></b>
</summary>
</details>



<details>
<summary>
99.<b></b>
</summary>
</details>



<details>
<summary>
99.<b></b>
</summary>
</details>



<details>
<summary>
99.<b></b>
</summary>
</details>



<details>
<summary>
99.<b></b>
</summary>
</details>



<details>
<summary>
99.<b></b>
</summary>
</details>


<details>
<summary>
99.<b></b>
</summary>
</details>


<details>
<summary>
99.<b></b>
</summary>
</details>


<details>
<summary>
99.<b></b>
</summary>
</details>

