# AWS
##**AWS SYSYTEM MANAGER**
AWS Systems Manager Run Command to install the Widget Manufacturing application and its required infrastructure software on an Amazon Elastic Compute Cloud (Amazon EC2) instance. The EC2 instance is called Managed Instance. Then, you use the AWS Systems Manager console to run the AWS-RunShellScript command. You configure the command to run a script that you pass as a parameter to it and which installs the following components:
*• Apache HTTP Server 
* • PHP 
*• AWS software development kit (SDK) for PHP
*• Widget Manufacturing application
<img width="490" alt="Screenshot 2023-08-15 at 10 43 31 am" src="https://github.com/Shannu1/AWS/assets/46293263/d3e36d93-e4b6-4d08-9a8e-243882c4338b">

This diagram illustrates the steps that you perform. Specifically, you use the AWS Systems Manager Session Manager feature to open a browser command session to the Managed Instance EC2 instance:
1. You use the AWS Systems Manager console to start a new session to communicate with Managed Instance.
2. The Session Manager creates a new session into the instance and opens a browser window that enables you to enter commands.
3.  You enter commands through the browser session window.

<img width="475" alt="Screenshot 2023-08-15 at 10 49 37 am" src="https://github.com/Shannu1/AWS/assets/46293263/b5dcc657-8715-4d0d-9e41-b280492b4b32">
