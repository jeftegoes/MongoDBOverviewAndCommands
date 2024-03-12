# MongoDB overview and commands <!-- omit in toc -->

## Contents <!-- omit in toc -->

- [1. Whats is MongoDb?](#1-whats-is-mongodb)
  - [1.1. Json format and in collections as documents](#11-json-format-and-in-collections-as-documents)
- [2. Commands](#2-commands)

# 1. Whats is MongoDb?

- MongoDB introduces us as an open source, document-oriented NoSQL database designed for ease of development and scaling.
- There are many NoSQL databases on the market today such as Cassandra, BigTable, Dynamo (AWS).

## 1.1. Json format and in collections as documents

- Every record in MongoDB is actually a document. Documents are stored in MongoDB in JSON like Binary JSON (BSN) format.
- BSON documents are objects that contain an ordered list of the elements they store. Each element consists of a domain name and a certain type of value.
- Document based NoSql database
  - It keeps the data structurally in Json format and in documents.
  - Queries can be written in any field or by range.
  - If we compare the structures in MongoDB with the structures in their relational databases, it uses Collection instead of Tables and uses Documents instead of rows.

# 2. Commands

- Enter into a mongo shell
  - `mongo` or `mongosh`
  - Connect with username
    - `mongosh --username <username>`
- Show all databases
  - `show databases`
  - `show dbs`
- Show all collections
  - `show collections`
- Create a new database
  - `use <database_name>`
- Create new collection
  - `db.createCollection("<collection_name>")`
- Insert ONE object into collection
  - `db.<collection_name>.insertOne({<object>>})` # Ex: db.books.insertOne({name: "Clean Code", author: "Uncle Bob"})
  - Result:
    ```
        [
            {
                _id: ObjectId('65ef5a432a78dcfaea37258b'),
                name: 'Clean Code',
                author: 'Uncle Bob'
            }
        ]
    ```
- Insert MANY objects once time into collection
  - `db.books.insertMany([{<object>>}])` # Ex: db.books.insertMany([{name: "Clean Code", author: "Uncle Bob"}, {name: "Clean Architecture", author: "Uncle Bob"}])
  - Result:
    ```
        [
            {
                _id: ObjectId('65ef5b502a78dcfaea372590'),
                name: 'Clean Code',
                author: 'Uncle Bob'
            },
            {
                _id: ObjectId('65ef5b502a78dcfaea372591'),
                name: 'Clean Architecture',
                author: 'Uncle Bob'
            }
        ]
    ```
- Find all objects of collection
  - `db.<collection_name>.find()` # Ex: db.books.find()
- Remove all itens of collection
  - db.`<collection_name>`.remove({})
- Delete database
  1. `use <database_name>`
  2. `db.dropDatabase()`
