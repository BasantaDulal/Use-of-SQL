# Use-of-SQL
Use of SQL to Answer Business Questions

### Importing Data to SQL Server
The dataset related to Video Game Sales was in CSV form. So, to get the required answers form using SQL Query, the dataset was imported to SQL server. The used dataset is also availabel in kaggle.com, which can be downloaded from [here](https://www.kaggle.com/datasets/gregorut/videogamesales?resource=download).

### Answering Business Questions
Altogether there were two business questions that need to be answered, are as follows:

#### 1. Was the average of global sales higher before or after 2010?

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
```

The output of this query was as follows:

![Answer 1](https://user-images.githubusercontent.com/109762085/201998411-0ac3918d-3e65-46be-b913-aa94731ae9dc.png)

So, it is clear that the average sales before 2010 was higher than after 2010

#### 2. Create a new column that labels records before 2010 as 'pre-2010' and after 2010 as 'post-2010'.

To get the answer of this question following SQL query was performed.
```sql
SELECT *,
    CASE
        WHEN Year < 2010 THEN 'Pre-2010'
        WHEN Year > 2010 THEN 'Post-2010'
        ELSE 'In-2010'
END AS Year_Classification
FROM vgsales;
```

The output of this query was as follows:

![Answer 2](https://user-images.githubusercontent.com/109762085/201997487-910bb4e3-8ce2-4e99-95d2-b03cbb48d3c1.png)
