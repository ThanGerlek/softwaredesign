# API Gateway

## Pre-class Preparation

Assumption: You have completed the “Lambda / IAM” exercise.

AWS API Gateway lets you implement web APIs for your server-side code.  In this class we will use API Gateway to allow our Lambda functions to be called over the web via HTTP.  You may recall that in CS 240 we wrote a Java server that implemented web APIs.  In this class, rather than writing our own server, we will use Lambda to implement our backend functionality, and use API Gateway to make our Lambda services callable through a web API.

Use the following resources and/or AI to learn the following:

- What is AWS API Gateway?
- How to create a web API that invokes Lambda functions
    - Create a new web API
    - Create resources (or URLs) in a web API
    - Configure HTTP methods on resources that call Lambda functions
    - Pass HTTP request body to a Lambda function
    - Pass request URL parameters to a Lambda function
    - Map Lambda function output to HTTP responses
    - Configure CORS on HTTP methods
- Deploy a web API
- Test a web API using Postman or Curl
 
Assuming you've already created some Lambda functions, this LinkedIn Learning video shows how to use API Gateway to create a web API with endpoints that call your Lambda functions. It also shows how to debug your web API using a tool named Postman (Postman is not part of AWS. It's just a generallly useful tool for testing web APIs)

[Setting Up and Testing a Web API](https://www.linkedin.com/learning/building-serverless-apps-on-aws-2/set-up-your-get-api-gateway
)

This LinkedIn Learning video also shows how API Gateway fits into a Serverless application. The API Gateway part comes toward the end, but it does a good job of showing how all the AWS technologies fit together.

[Building Serverless Applications in AWS](https://www.linkedin.com/learning/building-serverless-applications-in-aws/)

*Note: LinkedIn Learning is free for BYU students: https://www.linkedin.com/pulse/free-linkedin-learning-college-students-step-marcelo-wilen-menezes/*

For additional information, you can peruse the The API Gateway Developer Guide:

https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html

The following articles on HTTP message formats, HTTP Cookies, and HTTP Cross-Origin Resource Sharing (CORS) might also be helpful:

https://developer.mozilla.org/en-US/docs/Web/HTTP/Messages

https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies

https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS

 ## Quiz

 API Gateway Quiz

 ## Exercise

 [API Gateway Exercise](./api-gateway-exercise.md)

 ## Lecture Slides/Notes/Files

[API Gateway - Slides](https://docs.google.com/presentation/d/1YkFMAswitpwDzP6H7PZeFvjWQMLCdEQb9miM4_VKhd4/edit?usp=sharing)
