---
Title: DBS101 Flipped Class 7
categories: [DBS101, Flipped_Class7]
tags: [DBS101]
---
### Guided session

Today, I delved into simulating various data storage and management systems, including disk block management, RAID arrays, and buffer pools. The code I worked on showcased the allocation, read/write, deallocation, and defragmentation operations crucial for efficient data handling.

 It also simulated RAID 0 and RAID 1 arrays, demonstrating striping and mirroring techniques along with disk rebuild operations for fault tolerance. 
 
 Additionally, I explored a buffer pool implementation with a least recently used (LRU) eviction policy, highlighting the importance of efficient page management within limited memory constraints. These simulations provided valuable insights into optimizing data storage, access, and system reliability, emphasizing the significance of thoughtful design and management strategies for robust data handling solutions.


### Exercise 

I delved deep into understanding the intricate data structures that power the "chidb" project, aiming to optimize database management. One of the crucial structures I explored is B-trees, which play a vital role in organizing and storing vast amounts of table data, indexes, and schema information efficiently. Their ability to expedite retrieval and storage operations, especially with large data volumes, is impressive.

Moving on, the Abstract Syntax Tree (AST) emerged as a fundamental component within our SQL compiler. It simplifies the representation of SQL queries in a structured manner aligned with relational algebra, aiding in analysis and program generation for the Database Machine (DBM). Similarly, the Relational Algebra (RA) Data Structure within the compiler streamlines translating algebraic expressions into executable code for the DBM to execute.

Within the DBM, Registers act as temporary storage units during program execution, facilitating smooth computation and control flow. Meanwhile, Cursors emerged as invaluable tools, enabling precise navigation within B-trees for various database operations.

This journey has not only expanded my knowledge of relational database management systems but also honed my programming skills, particularly in C. Implementing these components has provided a practical understanding of efficient data storage, query processing, and overall system functionality. It's been a bridge between theory and practice, reinforcing my grasp on databases comprehensively.
