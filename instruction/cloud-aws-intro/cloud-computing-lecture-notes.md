# Cloud computing lecture notes

Software architecture is heavily influenced by technology. CS 240 introduced you to technology such as databases, client/server, and web APIs.  In this class we will introduce some additional technologies used in modern software architectures. Our focus will be on cloud computing.

What is Cloud Computing?

Rather than buying and maintaining your own IT infrastructure, you can rent someone else's IT infrastructure.

## Infrastructure as a Service (IaaS)

- Rent computers  (virtual machines), network, file storage, databases, etc.
- Configure and manage everything yourself (install your own software)
- Easy to add and remove capacity as needed

## Platform as a Service (PaaS)

Software developers don't like to configure and manage their own IT infrastructure (as required by IaaS)

PaaS lets developers deploy and scale applications without having to mess with the IT infrastructure

For example, give the PaaS provider access to the Git repository containing your project's code, and they will deploy, configure, and manage the application for you.

## Serverless Cloud Computing

PaaS hides the "servers" from software developers.  Serverless computing takes this a step further by getting rid of the servers (not really, but it seems that way).

Example: In CS 240, for the Chess Server project you had to create your own "server" program which you had to run on some kind of computer (the "server" machine).  Your server program consisted  of HTTP "handlers" that implemented a Web API, and all of the code behind the handlers to make the Web API work.

With Serverless Computing, you don't need to write a "server" program at all.  Just give the cloud provider the code for your "handlers" and  all  the supporting code, and they will make sure your "handlers" get run whenever a client calls your Web API.  No need to mess with server programs or machines.

Example: To use a database on a server, you typically need to have a "database server" which is a machine that hosts the database and runs the DMBS software (Oracle, MySQL, MongoDB, etc.).

With a "serverless database", you don't need to have a "database server" at all.  The serverless database provides Web APIs that your application can call to perform CRUD operations.  The database is just "in the cloud", which really means it's running on machines that you never see or mess with.

## Accessing Cloud Computing Services (like AWS, Azure, etc.)

1. **Web Console** - Cloud providers have a web console through which you can manage your cloud IT resources (machines, networks, databases, etc.)
1. **Command-Line Interface (CLI)** - Cloud providers have a CLI interface that you can install on your own computer and use to do anything that can be done through the Web Console.  This allows automation of tasks rather than doing them manually.
1. **Software Development Kits (SDKs)** - Cloud providers have SDKs for various languages that let you write programs that configure, manage, and interact with your IT resources.

For this class, you should learn how to use the AWS Web Console, CLI, and SDK.  We will learn about and use the following AWS technologies:

- S3 for file storage
- Lambda functions for implementing serverless web API "handlers"
- API Gateway for invoking Lambda functions when clients make Web API requests
- DynamoDB for implementing serverless database persistence
- SQS for implementing asynchronous server processing
