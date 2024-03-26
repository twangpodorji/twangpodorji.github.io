---
Title: DBS101 Flipped Class 6
categories: [DBS101, Flipped_Class6]
tags: [DBS101]
---

# Nonrelationsal Database(NoSQL)
Greetings everyone! Today I will share what I have absorbed during my journey towards the types of Norelational Database. so let's get started 👍...

A non-relational database is a database that does not use the tabular schema of rows and columns found in most traditional database systems. Instead, non-relational databases use a storage model that is optimized for the specific requirements of the type of data being stored. For example, data may be stored as simple key/value pairs, as JSON documents, or as a graph consisting of edges and vertices.

## Types of NoSQL Database.
![alt text](<../image for FC6/types of nonSQL.png>)
### Document based Databases(DBD)

A document-oriented database, or document database, is a type of NoSQL database that stores data in a flexible, semi-structured format, often using JSON. This means the data can be stored in a way that's easy to understand and modify, without needing a fixed structure like tables in a relational database. This flexibility allows the database to adapt to changes in the data structure over time.

Example is given below for DBD in which the information is stored in the jason document:
```
{
 "name": "Dorji
 "age": 30,
 "address": {
    "street": "123 Main St",
    "city": "Thimphu Throm",
    "zip": "11001"
 },
 "hobbies": ["reading", "hiking", "cooking"]
}
```

### key-value Database(KVD)

A key-value database is a type of NoSQL database that stores data as pairs of keys and values. Each key is unique and directly maps to a value, which can be simple data types like strings or numbers, or complex objects. This structure allows for fast and efficient data retrieval and storage, making key-value databases suitable for applications that need quick data access without complex querying.

Example is given below for KVD in which the information is stored in the jason formate :
```
{
    name: "Wangpo",
      age : 20,
      dob : ("26-12-2003"),
      social : {
             twitter : "@wangpo",
             facebook : "tsheringwangpo"
               }
}
```

### Graph Database
A graph database is a type of NoSQL database that organizes data in a way that emphasizes the relationships between different data entities. Instead of storing data in tables like relational databases, graph databases use nodes, edges, and properties to represent and store data.

The nodes represent entities, edges represent the relationships between these entities, and properties hold additional information about the nodes and edges. 

An example for the graph databse is given below:

![alt text](<../image for FC6/graphdb.png>)

### Vector Database
A vector database is a specialized database designed to store, manage, and query high-dimensional vector data, which is crucial for AI and machine learning applications. It enables efficient storage and retrieval of vector embeddings, allowing for similarity and semantic searches, making it ideal for applications like recommendation engines and image recognition.


![alt text](<../image for FC6/vector image.png>)

### Time-series Databases(TSDB)

A Time-Series Database (TSDB) is a database optimized for storing and querying data that is collected over time, making it ideal for applications that monitor changes like financial markets or for  sensor data. TSDBs use optimized storage, compression, and indexing to handle large volumes of data efficiently, enabling fast data writes and quick retrieval for real-time analytics and trend analysis.

An example of the time TSDB:

![alt text](<../image for FC6/timeseries.png>)

### Column Oriented Databases(COD)

A column-oriented database is a non-relational database that stores the data or information in columns instead of rows. Columnar databases are designed to read data more efficiently and retrieve the data with greater speed. A columnar database is used to store a large amount of data.

Key features of columnar oriented database:

Scalability.<br>
Compression.<br>
Very responsive.

An example is given below for the Column Oriented Databases:

![alt text](<../image for FC6/column.png>)


