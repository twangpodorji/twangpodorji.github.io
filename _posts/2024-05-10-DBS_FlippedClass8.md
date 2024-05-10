---
Title: DBS101 Flipped Class 8
categories: [DBS101, Flipped_Class8]
tags: [DBS101]
---  

# Indexing 
Greetings to you all! Today, I am here to share some of my learning journey towards the Indexing. Let's dive into it; 👍

### What is "Indexing"?
In simple terms, indexing is a way that offers an efficient way to quickly access the records from the database files stored on the disk drive. It helps in quering information from the database faster.

### Types of Indexing that I have learned.

![alt text](<../image FC8 DBS101/FC8_img1_DBS101 .png>)

### Indexing of Spatial and Temporal Data
Indexing of Spatial and Temporal Data involves organizing and accessing data that has geographical or geometric coordinates (spatial data) and data that changes over time (temporal data). This process is crucial for efficiently managing and querying large datasets, especially in applications like Geographic Information Systems (GIS), real-time tracking, and historical data analysis.  

- **Spatial Data:** Spatial data includes objects with geographic or geometric coordinates such as points, lines, and polygons. These objects are organized in a way that allows for efficient querying based on their spatial relationships. For example, finding all points within a certain distance of a given point or identifying all polygons that intersect a specific area.

- **Temporal Data:** Temporal data involves data that changes over time, such as time-series data or data with transaction times. Managing temporal data requires indexing techniques that can track changes and access data based on time intervals or timestamps.

### Bitmap Indexing 
- Bitmap indexing is a data indexing technique used in database management systems (DBMS) to enhance the performance of read-only queries involving large datasets.

- It involves creating a bitmap index, a data structure that represents the presence or absence of data values in a table or column. 

- Each distinct value in a column is assigned a bit vector (bitmap) that indicates the presence or absence of that value in each row of the table.

- This technique is particularly effective for columns with low cardinality, meaning they have a modest number of distinct values, either absolutely or relative to the number of records that contain the data

**An example of Bitmap Indexing:**

In the context of database management, columns with few unique values, such as "New_Emp" (Yes/No) and "Job" (Manager, Analyst, Clerk, Salesman), are referred to as columns with low cardinality. These columns, despite having limited unique values, are frequently queried. Bitmap indexing is a technique that leverages this characteristic by representing the presence or absence of these values using bits (0 or 1), effectively storing the data in a compact, efficient manner. This approach significantly enhances query performance for read-heavy operations, especially in large datasets.

![alt text](<../image FC8 DBS101/FC8_DBS101_image2.jpeg>)
     
For the "New_Emp" column in the Employee table, the bitmap index is represented by four columns under the heading "Bitmap Indices." The "Yes" bitmap index has a value of 1001, indicating that rows 1 and 4 have the value "Yes" in the "New_Emp" column.

![alt text](<../image FC8 DBS101/FC8_DBS101_images3.jpeg>)

 In this scenario, two bitmaps are used for the "New_Emp" column, one for "Yes" and one for "No," indicating whether each row corresponds to a new employee. This is a basic form of bitmap indexing. For columns with more unique values, like "Job" with 4 categories, variations of bitmap indexing can also be applied to efficiently index and query this data.

![alt text](<../image FC8 DBS101/FC8_dbs101_image3.jpeg>)

Now Suppose, If we want to find out the details for the Employee who is not new in the company and is a salesperson then we will run the query.

```
SELECT * 
     FROM Employee 
          WHERE New_Emp = "No" and Job = "Salesperson";
```
For this query, the DBMS will search the bitmap index of both columns and perform logical AND operation on those bits and find out the actual result like follows: 

![alt text](<../image FC8 DBS101/FC8_dbs101_image4.jpeg>)

Here the result 0100 represents that the second row has to be retrieved as a result. 
     
#### Some of the Advantages and Disadvantages of Bitmap:
#### Advantages of Bitmap Indexing:
- Efficiency in terms of insertion deletion and updation.
- Faster retrieval of records
#### Disadaantages of Bitmap Indexing:
- Only suitable for large tables
- Bitmap Indexing is time-consuming
     
### Buffer Tree  
A buffer tree is a type of self-balancing binary search tree used in databases and file systems to maintain sorted data. It is designed to minimize the cost of insertions, deletions, and lookups by dynamically adjusting its structure to maintain balance and optimize access patterns.

**How does a Buffer Tree looks like?**
![alt text](<../image FC8 DBS101/FC8_DBS101_image5.png>)

#### How does a Buffer Tree work?
- **Structure:** A buffer tree consists of nodes, each of which contains a key-value pair and pointers to its child nodes. The left child node contains keys less than the parent node's key, and the right child node contains keys greater than the parent node's key. This structure ensures that the tree remains balanced, reducing the time complexity of operations.

- **Balancing Mechanism:** Unlike regular binary search trees, buffer trees automatically rebalance themselves after insertions or deletions to ensure that the tree remains balanced. This balancing mechanism is crucial for maintaining optimal performance, as it prevents the tree from becoming too skewed, which would degrade performance.

- **Insertion and Deletion:** When inserting or deleting a node, the buffer tree adjusts its structure to maintain balance. This may involve moving nodes up or down the tree, splitting nodes, or merging nodes. The goal is to keep the tree as balanced as possible to minimize the height of the tree, thereby reducing the time required to find a node.

- **Lookup Operation:** To find a node with a specific key, the buffer tree starts at the root and traverses down the tree, following the path that leads to the desired key. Since the tree is balanced, this operation can be performed efficiently, with a time complexity of O(log n), where n is the number of nodes in the tree.

- **Advantages:** Buffer trees offer several advantages, including efficient handling of dynamic data, reduced time complexity for insertions, deletions, and lookups due to their balanced nature, and the ability to adapt to changing data distributions. They are particularly useful in scenarios where data is frequently updated and accessed, as they can dynamically adjust their structure to maintain balance and optimize access patterns.

### Summary 

In conclusion, my journey with Indexing, Spatial and Temporal Data, Bitmap Indexing, and Buffer Trees has been enlightening and enriching. I have gained a deeper understanding of how indexing techniques can enhance database performance, especially in scenarios involving large datasets and complex queries. By exploring the concepts of spatial and temporal data indexing, bitmap indexing, and buffer trees, I have acquired practical insights into optimizing data access and storage, enabling me to tackle real-world database challenges more effectively. Looking ahead, I am excited to apply these learnings to future projects and continue exploring the vast landscape of database management and optimization. Thank you for joining me on this journey, and I look forward to sharing more insights with you in the future. 👍
