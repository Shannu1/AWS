# Use Parameter Store to manage application settings
Parameter Store, a capability of Systems Manager, provides secure, hierarchical storage for configuration data management and secrets management. You can store data such as passwords, database strings, and license codes as parameter values. You can store values as plain text or encrypted data. You can then reference values by using the unique name that you specified when you created the parameter.

In this task, you use Parameter Store to store a parameter that you use to activate a feature in an application.
1. Keep the **Widget Manufacturing Dashboard** browser tab open, and return to the **AWS Systems Manager tab**.
2. In the left navigation pane, for **Application Management**, choose **Parameter Store**.
3. Choose <*Create parameter*>
4. Choose the following options:
    * For **Name**:, enter */dashboard/show-beta-features*
    * For **Description**: , enter *Display beta features*
    * For **Tier**:, leave the default option. 
    * For **Type**:, leave the default option. 
    * For **Value**:, enter *True*
5. Choose <Create parameter>
A banner with the message "Create parameter request succeeded" appears at the top of the page. 

The parameter can be specified as a hierarchical path, such as **/dashboard/<option>**.

The application that is running on Amazon EC2 automatically checks for this parameter. If it finds this existing parameter, then additional features are displayed.

30. Return to the web browser tab that displays the application, and refresh the web page.

Notice that three charts are displayed. The application is now checking Parameter Store to determine whether the additional chart (which is still in beta) should be displayed. It is common to configure applications to display "dark features" that are installed but not yet activated.

**Optional**: Delete the parameter, and then refresh the browser tab with the application. The third chart disappears again.







