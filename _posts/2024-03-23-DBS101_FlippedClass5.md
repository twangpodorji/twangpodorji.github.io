---
Title: DBS101 Flipped Class 5
categories: [DBS101, Flipped_Class5]
tags: [DBS101]
---

# Normal Forms.

Greetings to you all! Today, I am here to share some of my learning journey towards types of Normal Forms. Let's dive into it;

**Normalization** in DBMS is a technique using which we can organize the data in the database tables so that:
1. There is Less repetetation of data.
2. Large set of data is constructed into a bunch of smaller tables.
3. To have a proper relationship between the Tables.

This is achieved by applying a set of rules known as normal forms as shown below:

![alt text](<../image FC5/Types of normal forms .png>)
### 1.First Normal Form (1NF)
1NF Ensures that each column in a table contains atomic (indivisible) values, and there are no repeating groups.

Example: If a table has a column that contains multiple values separated by commas, it is not in 1NF.

 A table is said to be in 1NF if it meets the following criteria:<br>
I. **Atomic Values:** Each column in a table must contain atomic (indivisible) values. In other words, each cell should hold a single, indivisible value rather than a set of values or a list.

II. **No Repeating Groups:** There should be no repeating groups of columns. Each column should represent a single attribute, and each row should represent a unique record.

Considering a 1NF table that violates these rules is given below:

![alt text](<../image FC5/1NF_ex 1.png>)

In this example, the Courses column violates the atomic values rule because it contains multiple courses separated by commas. To bring this table into 1NF, you would split the Courses column into separate rows, like this:

![alt text](<../image FC5/1NF_ex 2.png>)

Now, each cell contains an atomic value, and there are no repeating groups. So the table is in 1NF.

### 2.Second Normal Form (2NF)

2NF is builded on 1NF and ensures that there are no partial dependencies of a composite primary key on non-prime attributes.

To achieve 2NF, the table must meet the following criteria:

I. **Be in 1NF:** The table must already satisfy the rules of First Normal Form (1NF). Each column must contain atomic values, and there should be no repeating groups.

II. **No Partial Dependencies:** There should be no partial dependencies of any column on the primary key. In simpler terms, all non-primery attributes (columns not part of the primary key) must be fully functionally dependent on the entire primary key.

Lets consider a table that is in 1NF but has partial dependencies:

![alt text](<../image FC5/2NF_ex1.png>)

In this example, (StudentID, CourseID) is the composite primary key. However, the Instructor column is partially dependent on the primary key because it depends only on the CourseID and not on the entire primary key. To normalize into 2NF, we need to split this into two tables like this:

![alt text](<../image FC5/2nf_ex2.png>)

![alt text](<../image FC5/2NF_ex3.png>)

Now, each table is in 1NF, and the partial dependency has been eliminated. The Instructor information is associated with the CourseID in a separate table, avoiding redundancy and making to 2NF.

### 3.Third Normal Form (3NF)
3NF is builds on 2NF and eliminates transitive dependencies, ensuring that non-primary attributes are not dependent on other non-prime attributes. It removes indirect relationships between non-key columns.

To achieve 3NF, a table must meet the following criteria like follows:

I. **Be in 2NF:** The table must already satisfy the rules of Second Normal Form (2NF).

II. **No Transitive Dependencies:** There should be no transitive dependencies of non-primary attributes on the primary key. In other words, non-primary attributes should depend only on the primary key and not on other non-primary attributes.

Lets consider a table that is in 2NF but has transitive dependencies like this:

![alt text](<../image FC5/3NF_ex1.png>)

In this example, (StudentID, CourseID) is the composite primary key. However, the Instructor column depends on the CourseID, and the Department column depends on the Instructor. To normalize it into 3NF, we would split this into three tables as shown below:

![alt text](<../image FC5/3NF_ex2.png>)

![alt text](<../image FC5/3NF_ex3.png>)

![alt text](<../image FC5/3NF_ex4.png>)

Now, each table is in 3NF, and the transitive dependencies have been eliminated. The Instructor information is associated with the CourseID in one table, and the Department information is associated with the Instructor in another table.

### 4.Boyce-Codd Normal Form (BCNF)
Boyce-Codd Normal Form (BCNF) is a higher level of normalization that addresses certain types of anomalies related to functional dependencies. A table is in BCNF if, for every non-trivial functional dependency X → Y, X is a superkey. In simpler terms, BCNF ensures that there are no non-trivial functional dependencies where the determinant (X) is not a superkey.

I. **Superkey:** A superkey is a set of one or more attributes that can uniquely identify a row in a table, even if it includes more attributes than needed.

II. **Non-trivial Functional Dependency:** A functional dependency X→Y is non-trivial if Y is not a subset of X, meaning that X and Y are distinct sets of attributes.

Lets consider a table of Students_Courses that is given below:

![alt text](<../image FC5/BCNF_ex1 11.04.10 PM.png>)

The table is not in BCNF because the dependency CourseID → Instructor doesn't meet the BCNF criteria, even though both (StudentID, CourseID) and (CourseID, Instructor) are candidate keys.

Now to normalize into BCNF, you would split the table into
two, we get:

![alt text](<../image FC5/BCNF_ex2 11.04.10 PM.png>)

![alt text](<../image FC5/BCNF_ex3 11.04.10 PM.png>)

Now, each table satisfies BCNF, and the functional dependencies hold for each. BCNF eliminates certain types of redundancy and ensures that the table structure is free from certain types of update anomalies.


### 5. Fourth Normal Form (4NF)

A table is in Fourth Normal Form (4NF) if it meets the requirements of Third Normal Form (3NF) and does not have any non-trivial multivalued dependencies. A non-trivial multivalued dependency occurs when a non-prime attribute depends on a set of other non-prime attributes, but not on any individual attribute within that set.

Lets look at some example:

![alt text](<../image FC5/4NF_ex1.png>)

In the given table above, the (EmployeeID, ProjectID) is the composite primary key. However, the Skills column is multivalued, as it contains sets of skills related to each project. To normalize into 4NF, you would split this into two tables like shoen below:

![alt text](<../image FC5/4NF_ex2.png>)

![alt text](<../image FC5/4NF_ex3.png>)


