# Cloud Data Store (DynamoDB)

## Pre-class preparation
  
Assumption: You have completed the “AWS SDK” exercise.                

AWS DynamoDB is a NoSQL (i.e., non-relational) cloud database. To learn about DynamoDB, read the following portions of the DynamoDB Developer Guide.

Read the [“How it Works”](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.html) section (all sub-sections except "Cheat Sheet")

Read the [“Getting Started with DynamoDB”](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GettingStartedDynamoDB.html) section (all sub-sections except "First-time user resources").  This section covers basic concepts, and shows you how to perform DynamoDB operations using the web console, the CLI, and the AWS SDK.

Read [this page](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Query.html) that provides additional information about how to perform DynamoDB queries, including limiting and paginating query result sets.

From your reading and/or AI you should learn about the following:

- What is DynamoDB?
- The fundamental DynamoDB data model: Tables, Items, Attributes
- The data types supported by DynamoDB
- What is a “partition”?
- Table primary keys
    - What is a “primary key”?
    - What is a “partition key”?  What is it for?
    - What is a “sort key”?  What is it for?
    - What is the difference between a “simple primary key” and a “compound primary key”?
- Secondary indexes
    - What is a “secondary index”?
    - What are secondary indexes for?
    - What is the difference between a “local secondary index” and a “global secondary index”?
- How to perform DyanmoDB operations through the AWS web console and AWS command-line interface (CLI)
- How to perform DynamoDB operations using the AWS SDK
- How do you limit the number of items in a query result set?
- What does it mean to “paginate” query results?
- How do you paginate query results in DynamoDB?
