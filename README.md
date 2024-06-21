# FetchAssessment
### Part 1:
Please find the ER diagram created based on the given unstructured JSON data. 
1.	I have changed the name of ‘_id’ field for items and receipts tables to ‘item_id’ and ‘receipt_id’ for clarity
2.	I have created a table for items based on the ‘rewardsReceiptItemList’ column which has a list of multiple items
3.	Brands, receipts, users and items tables have ‘_id’, ‘receipt_id’, ‘_id’ and ‘item_id’ (automatically incrementing) as the primary key to uniquely identify each row in the table
4.	I have created a table for items based on the ‘rewardsReceiptItemList’ column which has a list of multiple items
5.	Cardinality relations:
a.	One brand can have one or many items (foreign key in items table: barcode)
b.	One receipt can have one or many items (foreign key in items table: receipt_id)
c.	One user can have one or many receipts (foreign key in receipt table: user_id
6.	I have considered ‘BIGINT’ as the datatype for all date variables since they are in milliseconds

### Part 2:
Please find the document with SQL queries to answer the questions. I have used the python library sqlite3 to write queries. Upload the brands.json, receipts.json and users.json files in the same directory as the root directory of the jupyter notebook.

Q1: SQL query to get the top 5 brands by receipts scanned for the most recent month

-> The most recent month and year is 2021-03. But I did not find any top brands for that month and year after running the query. The top brands I found were latest in 2021-01: Tostitos, Swanson, Cracker Barrel Cheese, Prego and Diet Chris Cola in the order of highest to lowest receipts count.

Q2: How does the ranking of the top 5 brands by receipts scanned for the recent month compare to the ranking for the previous month?

-> Since I did not get any brands for the recent month, I was not able to compare the rankings with 

Q3: When considering average spend from receipts with 'rewardsReceiptStatus’ of ‘Accepted’ or ‘Rejected’, which is greater?

-> There is no status called ‘accepted’ in the table. Hence, I have considered it as ‘finished’ value. The average spend of ‘finished’ status (80.85) is greater than average spend of 'rejected’ status (23.32).

Q4: When considering total number of items purchased from receipts with 'rewardsReceiptStatus’ of ‘Accepted’ or ‘Rejected’, which is greater?

-> Same assumption as above (‘finished’ status instead of 'accepted’). The total number of items purchased from receipts with ‘finished’ (8184) is greater than total number of items of purchased with ‘rejected’ status (173).

Q5: Which brand has the most spend among users who were created within the past 6 months?

-> The latest ‘createdDate’ among users is 2021-02-12 14:11:06 hence, it is not possible to find any brand with most spend within past 6 months from today (i.e., 2024-06-20). Therefore, I considered the latest ‘createdDate’ and calculated the past 6 months date (i.e., 2020-08-16 14:11:06). 

Q6: Which brand has the most transactions among users who were created within the past 6 months?

-> Same assumption as above.

### Part 3: 
Please find the data quality checks of the provided data in the document.

### Part 4: 
Please find the email/slack message in the document.

