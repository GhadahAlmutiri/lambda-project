# lambda-project
This project was done in a data engineering bootcamp at SDA &amp; WeCloudData

# Relational Database to S3 Data Transfer and API Posting Project

## Project Description

This project involves reading data from a relational database (MySQL), saving the result to an S3 bucket, and finally posting the result to an API endpoint. The general architecture of the project is as follows:


## Detail Steps

1. **Database Setup:**
   - Start a MySQL database on AWS RDS and connect RDS with MySQL Workbench. 
   - Download the SQL script and run the script on MySQL to load data. This will create a database called 'superstore'.

2. **Querying the Database:**
   - Query the database to get the top 10 customer IDs who have made the most purchases. Retrieve their customer ID and the sum of their sales (you can use a different column name).

3. **Saving Result to S3:**
   - Create an EC2 instance and build a Python project.
   - Use a Python script to fetch the result from MySQL to EC2, including the customer ID and the sum of their sales for the top 10 customers.
   - Save the result as a .json file locally on EC2.
   - Upload the file from EC2 to an S3 bucket. The file should be placed in an 'input' folder in the S3 bucket.

4. **Lambda Function:**
   - When the file lands in the S3 bucket, a Lambda function is triggered.
   - The Lambda function will:
     - Get the customer ID list from the .json file in S3.
     - Query the customer names from the database based on the customer ID list.
     - Send a JSON data, including customer ID, customer name, and today's date, to an API endpoint 

5. **Lambda Function Tips:**
   - Use a Lambda layer to install third-party libraries.
   - Put the customer ID, customer name, and today's date (formatted as '1990-01-01') in a JSON structure variable (e.g., `data`).
   - Use POST to send data to the API. The API data structure should look like the provided example.

6. **Project Structure:**
   - Use a Python project structure.
   - Use a Git repository to save your code.



