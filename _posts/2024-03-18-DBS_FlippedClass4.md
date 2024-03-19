---
Title: DBS101 Flipped Class 4
categories: [DBS101, Flipped_Class4]
tags: [DBS101]
---


# Aggregation functions.
Greetings everyone! Today I will share what I have absorbed during my journey towards the types of Aggregation Functions. so let's get started 👍...

![alt text](<../images fc4/learning_outcome.png>)

## RANK
To understand RANKS, Imagine that you have a list of items, and you want to rank them based on some criteria, like size or shape or any other features:

### 1.Rank 
The RANK() function helps you do this. It assigns a rank to each item in the list. The first item gets a rank of 1, the second gets a rank of 2, however, if there are items with the same value, they will receive the same rank, and the rank of the next item will skip the ranks that were tied.<br>
An example of an rank is given below:

![alt text](<../images fc4/Rank.png>)

So we can clearly see that rank keeps the gap between any two items if there is any same value. for that matter the rank directly jumps from 3 to 5.

### 2.Dense_rank 
DENSE_RANK() is almost same like the RANK() but  DENSE_Rank() doesn't skip any rank numbers. If two items are tied for first, the next item still gets a rank of 2 not 3 which mean it does not skip any rank numbers when two items are tied for the first place. If two items are tied for the first rank, the next item still gets a rank of 2, not 3. This behavior ensures that there are no gaps in the ranking sequence, even when there are ties.<br>
An example of an dense_rank is given below:

![alt text](<../images fc4/Dense_rank.png>)

In this context(DENSE_rank), there is no gaps even there is same value of the items.

### 3.Percent Rank
The PERCENTRANK is a function that calculates the rank of a value within a data set as a percentage, indicating its relative position among the data set values.<br>
An example of Percent Rank:

![alt text](<../images fc4/percent_rank.png>)


## Windowing
Window function let you look at a group of rows in a table and apply a calculation to them, but unlike regular calculations that combine all rows into one result, window functions keep the individual rows and apply the calculation to a "window" of rows around each row. This means you can see how each row compares to the others in its group, without losing the details of each row.<br>
An example of Windowing:

![alt text](<../images fc4/windowing.png>)

## Pivoting.
Pivoting is like turning rows into columns to make the data easier to read or analyze. It's like taking a list of items and organizing them into categories, where each category becomes a column, and the items are listed under the correct category.<br>
An example of Pivoting, before and after pivoting.<br>
#### Before pivoting:
Example 1: Pivoting on Names and score and ID.

![alt text](<../images fc4/before_pivoting.png>)

Example 2: Pivoting on ID, Product, quantity and total_sales.

![alt text](<../images fc4/ex1.png>)

#### Outcome after pivoting:<br>
Example 1.

![alt text](<../images fc4/after_pivoting.png>)

Example 2.

![alt text](<../images fc4/ex2.png>)

After pivoting all rows has been changed to column.
## Rollup and Cube. 
### 1.Rollup.
Rollup is like creating a summary table that shows subtotals and a grand total for different levels of data.<br>
An example of Roll up:

![alt text](<../images fc4/rollup.png>)

### 2.Cube.
Cube is similar to Rollup but it generates all possible combinations of subtotals and grand totals for the specified columns.<br>
An example of Cube:

![alt text](<../images fc4/cube.png>)

## Summary.
In the nut shell, the aggregation function is a composition of RANK(), DENSE_RANK(),PIVOTEING() and WINDOWING(),  In which ranks arranges the any items in columns according to their rank but it keep gaps between the ranks of the items if there is tie of two items. The DENSE_RANK is similar to RANK but it does not keep gaps between the tie items and PIVOTING turns the rows into columns whereas windowing functions helps in comparing the rows in the relation without losing any informations.










