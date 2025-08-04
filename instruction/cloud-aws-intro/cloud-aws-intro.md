# Cloud, AWS Introduction, Console, CLI, SDK, IAM

## Pre-class Preparation

Cloud computing lets us use computing resources owned and managed by others rather than having to plan, purchase, and maintain our own computing resources.

Read:

AWS article ["What is cloud computing?"](https://aws.amazon.com/what-is-cloud-computing/)

Do:

In AWS, there are three ways to do just about anything:

- Use the AWS web console to interactively perform a task
- Use the AWS Command-Line Interface (CLI) to perform the task from the command-line
- Use the AWS Software Development Kit (SDK) to perform the task from a program

The instructions below will help you install and configure the AWS CLI on your computer, and use it to perform a simple task. Then, in class you will write a program that uses the AWS SDK to programmatically perform a simple task.

Do the following:

- Create an AWS account if you do not already have one.

- Login to your AWS account, and use the AWS console to create an S3 bucket and copy a file into it.

- Install and Configure AWS CLI

    - Go to [AWS CLI User Guide](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html)
    - On the left, find the section named [Get Started](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html)
    - Read the entire Get Started section. This section includes instructions for installing and configuring the AWS CLI.
        - Note: When creating your administrator AWS user, use "IAM" not "IAM Identity Center".
        - Note: When configuring your AWS CLI, click the Long-term credentials tab on the [Setup](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-quickstart.html) and follow those setup instructions.
    - In the [Using the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-using.html) section, read the first two sub-sections named [Get Help](https://docs.aws.amazon.com/cli/latest/userguide/cli-usage-help.html) and [Command Structure](https://docs.aws.amazon.com/cli/latest/userguide/cli-usage-commandstructure.html)

- Use the CLI to create an S3 bucket and copy a file into it. S3 is one of AWS's many services, and is a cloud file store similar to the file system on your (or any) computer. Consult the CLI documentation to find the syntax for doing this. AI is also very handy for finding the syntax of CLI commands you want to perform.

## Quiz

Intro to Cloud and AWS Quiz

## Exercise

[AWS S3 Exercise](./aws-s3-exercise.md)

## Lecture Slides/Notes/Files

[Cloud Computing - Notes](./cloud-computing-lecture-notes.md)
