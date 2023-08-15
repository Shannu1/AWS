# AWS
## **AWS SYSYTEM MANAGER**
AWS Systems Manager Run Command to install the Widget Manufacturing application and its required infrastructure software on an Amazon Elastic Compute Cloud (Amazon EC2) instance. The EC2 instance is called Managed Instance. Then, you use the AWS Systems Manager console to run the AWS-RunShellScript command. You configure the command to run a script that you pass as a parameter to it and which installs the following components:
*• Apache HTTP Server 
* PHP 
*• AWS software development kit (SDK) for PHP
*• Widget Manufacturing application
<img width="490" alt="Screenshot 2023-08-15 at 10 43 31 am" src="https://github.com/Shannu1/AWS/assets/46293263/d3e36d93-e4b6-4d08-9a8e-243882c4338b">

**Task 1: Generate inventory lists for managed instances**

You can use Fleet Manager, a capability of Systems Manager, to collect operating system information, application information, and metadata from EC2 instances, on-premises servers, or virtual machines in a hybrid environment. You can also use Fleet Manager to query metadata to quickly understand which instances are running the software and configurations that your software policy requires and which instances you need update.
In this task, you use Fleet Manager to gather inventory from an EC2 instance.
1. In the AWS Management Console, in the  search box, enter Systems Manager and press Enter. This option takes you to the Systems Manager console page.
2. In the left navigation pane, for Node Management, choose Fleet Manager.
3. Choose the Account management dropdown list, and choose Set up inventory.
4. To create an association that collects information about software and settings for your managed instance, choose the following options:

   * In the Provide inventory details section, for Name, enter Inventory-Association

  *  In the Targets section, choose the following options:
        * For Specify targets by, choose Manually selecting instances.
        * Select the row for Managed Instance.
    Leave the other options as the default settings.

5. Choose Setup <Inventory>
A banner with the message "Setup inventory request succeeded" appears on the Fleet Manager page. Inventory, a capability of Systems Manager, now regularly inventories the instance for the selected properties.
6. Choose the Node ID link, which directs you to the Node overview.
7. Choose the Inventory tab.

 This tab lists all of the applications in the instance. Take a moment to review the installed applications and other options in the Inventory type dropdown list.

You have successfully created a Systems Manager inventory association for your instance. Using Inventory, you can review and validate software configurations on your instances without needing to connect to each instance by using SSH.

### **Task 2: Install a Custom Application using Run Command**
This diagram illustrates the steps that you perform. Specifically, you use the AWS Systems Manager Session Manager feature to open a browser command session to the Managed Instance EC2 instance:
1. You use the AWS Systems Manager console to start a new session to communicate with Managed Instance.
2. The Session Manager creates a new session into the instance and opens a browser window that enables you to enter commands.
3.  You enter commands through the browser session window.

<img width="475" alt="Screenshot 2023-08-15 at 10 49 37 am" src="https://github.com/Shannu1/AWS/assets/46293263/b5dcc657-8715-4d0d-9e41-b280492b4b32">
1. n the upper-left corner, expand the menu icon. For **Node Management**, choose **Run Command**.
2. Choose <Run command>
  A list appears of pre-configured documents for running common commands. 
3. Choose the search icon  in the box, and a dropdown box appears. Choose the following options: 
* Owner
* Owned by me
A document appears.
**Note**: Do not enter Owner or Owned by me. Entering this text does not return results. 

4. If the document is not already selected, select the button for the document.
5. The following information appears for this document:
  * Description Install Dashboard App
  * Document version: 1 (Default) 
Leave the Document version option set to this default. 

6. For Target selection, select Choose instances manually.
7. In the Instances section, select Managed Instance.
  The Managed Instance has the Systems Manager agent installed. The agent has registered the instance to the service, which allows it to be selected for Run Command.
  * It is also possible to identify target instances by using tags. By using tags, you can run a single command on a whole fleet of matching instances.

8. In the Output options section, clear Enable an S3 bucket.
9. Expand the AWS command line interface command section.

 This section displays the command line interface (CLI) command that initiates Run Command. You can copy this command and use it in the future within a script rather than having to use the AWS Management Console.

10. Choose <Run>

 A banner with the Command ID indicates that it was successfully sent on the Command ID page.

11. After 1–2 minutes, the Overall status should change to Success. If it doesn't, choose the  refresh icon to update the status.

 You now validate the custom application that was installed.

Copy the ServerIP value. (This value is the public IP address.)
12. Open a new web browser tab, paste the IP address that you copied, and press Enter.

 The *Widget Manufacturing Dashboard* that you installed appears.

You have successfully used Run Command through Systems Manager to install a custom application onto your instance without needing to remotely access the instance by using SSH.



