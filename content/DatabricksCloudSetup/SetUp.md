+++
copyright = "Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved."
spdx-license-identifier = "CC-BY-SA-4.0"
title = "Setup"
date = 2019-09-09T17:42:10+01:00
weight = 10
+++

### 1. Sign up for Databricks Cloud

**:white_check_mark: Step-by-step directions**


1. Visit [External link with _target blank](https://databricks.com/try-databricks-aws/) , complete the required details and click on ```Get started for free```

![Databricks Get Started](/images/databricks/get-started.png)

2. Choose "Pay with credit card" option and click on the ```Sign up with Databricks``` to create an account.

![Databricks Pay](/images/databricks/pay-with-card.png)


**Note: You will not be asked for any credit card details in the next steps.*

3. You will receive a welcome email from the Databricks platform. Verify your email address or click in the link provided in the welcome mail.

4. You will be asked to set up  your password *(remember this)* and also requested to choose Subscription plan. Choose the ```Premium``` plan and click on the following to complete your signup and Databricks Account creation process.

![Databricks Premium](/images/databricks/premium-plan.png)

5. Follow the on-screen instructions to confirm "Get Started" creating your workspace.

![Databricks Ready](/images/databricks/confirm-ready.png)

6. Provide the following details:

- **Workspace name**: ```iot-workshop-workspace```
- **AWS region**: ```Ireland (eu-west-1)```

![Workspace Details](/images/databricks/workspace-details.png)

7. Choose "Start quickstart" which will take you to the AWS CloudFormation console.

- Provide your Databricks Account Password
- Tick the check box: ‘I acknowledge that AWS CloudFormation might create IAM - resources with custom names’
- Leave all the defaults and Click ‘Create Stack’ button (This stack creation step would take approx. 5 minutes)

![Workspace CF](/images/databricks/workspace-cloudformation.png)

- Once the stack creation is completed, the user will receive an email with the Databricks workspace URL (For Example: https://dbc-d463ee14-902e.cloud.databricks.com)

**Note: The Databricks workspace URL is also available in the ‘Output’ tab of the CloudFormation stack as shown below*

![Workspace URL](/images/databricks/workspace-url.png)

Your Databricks Cloud account and workspace are now created and we are ready to begin configuring the environment 
