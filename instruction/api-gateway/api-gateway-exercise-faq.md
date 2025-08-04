# FAQ - AWS API Gateway Exercise

## Unauthorized Error

Likely one of these
1) copied the URL wrong (missing the stage)

2) forgot to append the name of the endpoint being called (/sendemail)

3) {to} and {from} are not appended to /sendemail, but are placed next to sendemail.

**Note:** If you go to the method and copy the url, the url will include the endpoint.

## 502 Response Code

This is usually a validation error. While it may be a symptom, the root cause could be

1) The integration Request is set to "Use Proxy Integration". Uncheck this.

2) The EmailRequest object looks different from the data being sent in the API Gateway test. Check the case and spelling of variables

3) The response data doesn't look like the model provided. This happens if the Lambda itself is generating an error and sending back an object to API Gateway with a different structure than what was set up.

## CORS Issues

The CORS part from the exercise is missing.
