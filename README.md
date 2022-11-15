# Use-of-SQL
Use of SQL to Answer Business Questions

### Importing Data to SQL Server
The dataset was related to Video Game Sales in CSV form. So, to get the required answers form using SQL Query, the dataset was imported to SQL server. The used dataset is also availabel in kaggle.com, which can be downloaded from [here](https://www.kaggle.com/datasets/gregorut/videogamesales?resource=download).

### Answering Business Questions
Altogether there were three business questions that need to be answered and are as follows:

1. Was the average of global sales higher before or after 2010?
To get the answer of this question following SQL query was performed.
```sql
SELECT AVG(Global_Sales),
 CASE
        WHEN Year < 2010 THEN 'Pre-2010'
        WHEN Year > 2010 THEN 'Post-2010'
        ELSE 'In-2010'
END AS Year_Classification
FROM vgsales
GROUP BY Year_Classification;

The output of this query was as follows:

