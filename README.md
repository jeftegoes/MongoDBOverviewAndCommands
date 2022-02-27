# MongoDb overview and commands <!-- omit in toc -->

## Contents <!-- omit in toc -->

- [1. Whats is MongoDb?](#1-whats-is-mongodb)
  - [1.1. Json format and in collections as documents](#11-json-format-and-in-collections-as-documents)
- [2. Commands](#2-commands)

## 1. Whats is MongoDb?

- MongoDB introduces us as an open source, document-oriented NoSQL database designed for ease of development and scaling.
- There are many NoSQL databases on the market today such as Cassandra, BigTable, Dynamo (AWS).

### 1.1. Json format and in collections as documents

- Every record in MongoDB is actually a document. Documents are stored in MongoDB in JSON like Binary JSON (BSN) format.
- BSON documents are objects that contain an ordered list of the elements they store. Each element consists of a domain name and a certain type of value.
- Document based NoSql database
  - It keeps the data structurally in Json format and in documents.
  - Queries can be written in any field or by range.
  - If we compare the structures in MongoDB with the structures in their relational databases, it uses Collection instead of Tables and uses Documents instead of rows.

## 2. Commands

- Enter into a mongo shell
  - mongo
- Show all databases
  - show databases
  - show dbs
- Show all collections
  - show collections
- Create a new database
  - use `<database_name>`
- Create new collection
  - db.createCollection('`<collection_name>`')
- Insert any data
  - db.`<collection_name>`.insert('`{<data>}`')
- Insert any data in mass
  - db.`<collection_name>`.insertMany('`[{<data1>}, {<data2>}, {<data3>}]`')
- Show all itens of collection
  - db.`<collection_name>`.find({})
  - db.`<collection_name>`.find({}).pretty() # Arrange json
- Remove all itens of collection
  - db.`<collection_name>`.remove({})
