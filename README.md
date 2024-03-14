# MongoDB overview and commands <!-- omit in toc -->

## Contents <!-- omit in toc -->

- [1. Whats is MongoDb?](#1-whats-is-mongodb)
  - [1.1. Json format and in collections as documents](#11-json-format-and-in-collections-as-documents)
- [2. NoSQL Characteristics](#2-nosql-characteristics)
- [3. SQL vs NoSQL](#3-sql-vs-nosql)
- [4. Summary](#4-summary)
- [5. String connection](#5-string-connection)
- [6. Commands](#6-commands)

# 1. Whats is MongoDb?

- MongoDB introduces us as an open source, document-oriented NoSQL database designed for ease of development and scaling.
- There are many NoSQL databases on the market today such as Cassandra, BigTable, Dynamo (AWS).

## 1.1. Json format and in collections as documents

- Every record in MongoDB is actually a **document**.
  - Documents are stored in MongoDB in JSON like Binary JSON (BSON) format.
- **BSON** documents are objects that contain an ordered list of the elements they store.
  - Each element consists of a domain name and a certain type of value.
  - BSON example:
    ```
    {
      "name": "Jefté",
      "age": 33,
      "address": {
        "city": "Brazil"
      },
      "hobbies": [
        {
          "name": "Lego"
        },
        {
          "name": "Games"
        }
      ]
    }
    ```
- **Document based NoSql database**
  - It keeps the data structurally in Json format and in documents.
  - Queries can be written in any field or by range.
  - If we compare the structures in MongoDB with the structures in their relational databases, it uses Collection instead of Tables and uses Documents instead of rows.
    ![MongoDB Structure](/Images/MongoDBStructure.png)

# 2. NoSQL Characteristics

![NoSQL Characteristics](/Images/NoSQLCharacteristics.png)

# 3. SQL vs NoSQL

| SQL                                                                         | NoSQL                                                       |
| --------------------------------------------------------------------------- | ----------------------------------------------------------- |
| Data uses Schemas                                                           | Schema-less                                                 |
| Relations!                                                                  | No (or very few) Relations                                  |
| Data is distributed across multiple tables                                  | Data is typically merged / nested in a few collections      |
| Horizontal scaling is difficult / impossible; Vertical scaling is possible. | Both horizontal and vertical scaling is possible            |
| Limitations for lots of (thousands) read and write queries per second.      | Great performance for mass (simple) read and write requests |

# 4. Summary

- Alternative to SQL databases.
- No strict schemas, fewer relations.
- You can of course use schemas and reference-based relations but you got more flexibility.
- Often, relations are also created by embedding other documents/ data.

# 5. String connection

- `mongodb://localhost:27017` or `mongodb://mongoadmin:Master123456@localhost:27017/<database_name>?authSource=admin`

# 6. Commands

- To get a Connection String.
  - `db.getMongo()`
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
