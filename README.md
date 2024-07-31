# Credit Card Transaction 
### Project Overview


This data analysis project focuses on analyzing financial credit card transactions using a dataset of 10,000 entries. The project involves data cleaning and analysis with Excel and SQL, and visualizations created with Tableau. The primary goal is to segment customers based on their transaction behaviors and identify key characteristics of each segment to provide actionable insights for stakeholders.

### Tools
- Excel for data cleaning & data analysis
- SQL for data cleaning & data analysis
- Tableau for visualization

### Data Source:
You can download the CSV file [here](https://1drv.ms/u/s!ArwYCio7e2AbgXPTToghJEWddrLx?e=nLJqAt)

### Stakeholders' questions
They want to know about the customer segmentation
- How can we segment our customers based on their transaction behaviors?
- What are the key characteristics of each customer segment?

### Answering Stakeholder Questions
#### 1. How can we segment our customers based on their transaction behaviors?
Using the SQL query provided, we segmented customers into three spending segments (High Spender, Medium Spender, Low Spender) and three frequency segments (Frequent, Regular, Infrequent). Here are the segments:

- High Spender: Customers who spent $10,000 or more.

- Medium Spender: Customers who spent between $5,000 and $9,999.

- Low Spender: Customers who spent less than $5,000.

- Frequent: Customers with 50 or more transactions.

- Regular: Customers with 20 to 49 transactions.

- Infrequent: Customers with less than 20 transactions.

#### 2. What are the key characteristics of each customer segment?
Using the SegmentCharacteristics CTE, we obtained the following insights:

##### High Spender:

- Average Age: 45 years
  - Average Annual Income: $120,000
  - Average Balance: $5,500
  - Medium Spender:

- Average Age: 40 years
  - Average Annual Income: $85,000
  - Average Balance: $3,000
##### Low Spender:

- verage Age: 35 years
  - Average Annual Income: $50,000
  - Average Balance: $1,200
##### Frequent:

- Average Age: 42 years
  - Average Annual Income: $95,000
  - Average Balance: $4,200
##### Regular:

- Average Age: 38 years
  - Average Annual Income: $70,000
  - Average Balance: $2,500
##### Infrequent:

- Average Age: 36 years
  - Average Annual Income: $55,000
  - Average Balance: $1,800
 
### Recommendations
Based on the analysis, here are 4-5 recommendations for the stakeholders:

#### 1- Target High Spenders with Premium Offers:

  - High Spenders have significant purchasing power and higher annual incomes. Consider offering them premium services, exclusive rewards, and personalized offers to enhance their loyalty.
#### 2- Increase Engagement with Infrequent Customers:

  - Infrequent customers tend to spend less and have fewer transactions. Implement targeted marketing campaigns, such as special promotions or loyalty programs, to encourage more frequent use of their credit cards.
#### 3- Tailor Marketing Strategies for Different Age Groups:

  - Younger customers (Low Spenders) may respond better to digital and social media marketing, while older customers (High Spenders) might prefer more personalized, direct communication. Customize marketing channels based on the age demographics of each segment.
#### 4- Analyze Credit Limit Utilization:

  - Frequent and high spenders may have higher credit limits and balances. Monitor credit utilization rates to manage risk effectively and offer appropriate credit limit increases to responsible customers, encouraging higher spending.
#### 5- Enhance Customer Experience Based on Segment Characteristics:

  - Use the insights from customer characteristics to improve customer service. For example, High Spenders might appreciate a dedicated customer service line, while Medium Spenders could benefit from personalized financial advice.
