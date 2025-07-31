## Serverless, Lambda, Security (IAM) (Pre-class preparation)

Assumption: You have already completed the “AWS SDK” exercise

AWS Lambda is a way to create functions that automatically run in the cloud in response to events such as HTTP calls, file uploads, database changes, or the passage of time.  Lambda is a “serverless” technology, meaning that you do not have to manage your own server to run your code.  Instead, Lambda automatically runs your code when interesting events occur.  All you do is upload your code to AWS, tell them when you want your function to run, and they will automatically run it at the right times.

 

Watch this [3-minute video](https://www.youtube.com/watch?v=eOBq__h4OJ4) that gives an overview of AWS Lambda.

Use the following resources and/or AI to learn the following:

- What is AWS Lambda?
- How to setup an IAM security role for executing Lambda functions
- How to create a Lambda function
- How to write log messages from a Lambda function
- How to test a Lambda function using a “test event”
- How to view a Lambda function’s log
 
There are lots of other things you can learn about, but these are the basics you will need for this class.

Review the [Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) to learn the basics of AWS Lambda programming.

The Lambda Developer Guide provides tutorials on how to use Lambda with various programming languages. Review the [tutorial for creating Lambda functions in TypeScript](https://docs.aws.amazon.com/lambda/latest/dg/lambda-typescript.html).
