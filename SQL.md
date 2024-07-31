# SQL 
## Segmentation Based on Transaction Behavior
Segment customers based on their transaction amounts and frequencies.
``` sql
WITH CustomerSpending AS (
    SELECT 
        CustomerID,
        COUNT(TransactionID) AS TransactionCount,
        SUM(TransactionAmount) AS TotalSpent,
        AVG(TransactionAmount) AS AvgTransactionAmount,
        MAX(TransactionAmount) AS MaxTransactionAmount
    FROM 
        credit_card_transactions
    GROUP BY 
        CustomerID
),
CustomerSegments AS (
    SELECT 
        CustomerID,
        CASE
            WHEN TotalSpent >= 10000 THEN 'High Spender'
            WHEN TotalSpent >= 5000 THEN 'Medium Spender'
            ELSE 'Low Spender'
        END AS SpendingSegment,
        CASE
            WHEN TransactionCount >= 50 THEN 'Frequent'
            WHEN TransactionCount >= 20 THEN 'Regular'
            ELSE 'Infrequent'
        END AS FrequencySegment
    FROM 
        CustomerSpending
)
SELECT 
    *
FROM 
    CustomerSegments
ORDER BY 
    SpendingSegment, FrequencySegment;
```
## Key Characteristics of Each Customer Segment
Analyze key characteristics like average age, average annual income, and average balance for each segment.
``` sql
WITH CustomerSpending AS (
    SELECT 
        CustomerID,
        COUNT(TransactionID) AS TransactionCount,
        SUM(TransactionAmount) AS TotalSpent,
        AVG(TransactionAmount) AS AvgTransactionAmount,
        MAX(TransactionAmount) AS MaxTransactionAmount
    FROM 
        credit_card_transactions
    GROUP BY 
        CustomerID
),
CustomerSegments AS (
    SELECT 
        CustomerID,
        CASE
            WHEN TotalSpent >= 10000 THEN 'High Spender'
            WHEN TotalSpent >= 5000 THEN 'Medium Spender'
            ELSE 'Low Spender'
        END AS SpendingSegment,
        CASE
            WHEN TransactionCount >= 50 THEN 'Frequent'
            WHEN TransactionCount >= 20 THEN 'Regular'
            ELSE 'Infrequent'
        END AS FrequencySegment
    FROM 
        CustomerSpending
),
SegmentCharacteristics AS (
    SELECT 
        cs.SpendingSegment,
        cs.FrequencySegment,
        AVG(ct.Age) AS AvgAge,
        AVG(ct.AnnualIncome) AS AvgAnnualIncome,
        AVG(ct.Balance) AS AvgBalance
    FROM 
        CustomerSegments cs
    JOIN 
        credit_card_transactions ct ON cs.CustomerID = ct.CustomerID
    GROUP BY 
        cs.SpendingSegment, cs.FrequencySegment
)
SELECT 
    *
FROM 
    SegmentCharacteristics
ORDER BY 
    SpendingSegment, FrequencySegment;
```
