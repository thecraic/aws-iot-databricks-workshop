+++
copyright = "Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved."
spdx-license-identifier = "CC-BY-SA-4.0"
title = "Configure Databricks Workspace"
date = 2019-09-09T17:42:10+01:00
weight = 30
+++

### 3. Configure Workspace with AWS Instance Profile

#### Background

In this section you will configure your Databricks workspace to use the AWS Instance Profile from the previous section when launching new clusters. This is necessary to allow the Databricks processes access to Kinesis and Amazon S3 for analytics.

**Note: If Databricks workspace is not opened yet, please click the workspace link which you would have received in email or you can find the link in your AWS Account Console’s  cloudformation stack’s output as shown below.*

![Workspace Stack](/images/databricks/workspace-stack.png)


1. In your Databricks Workspace, navigate in the sidebar to =>Settings =>Admin Console **Note: In the new UI click your username available on the top right corner to access Admin Console.*

![Settings Admin Console](/images/databricks/settings-admin-console.png)

2.  Inside Admin Console navigate to the **‘Instance profiles’** Tab and click on the   **‘Add instance profile’** button


![Add Instance Profile](/images/databricks/add-instance-profile.png)

3. Provide the `Instance profile ARN` which you have noted from previous sectionsOnce done, click **‘Add’**

![Add Instance Profile](/images/databricks/add-instance-profile-info.png)

When the instance profile is added successfully it will appear here and ready for attaching to new clusters:

![Instance Profile](/images/databricks/instance-profile-added.png)

You have now configured your workspace with the instance profile that contains permissions needed for clusters to access the relevant AWS resources. 

You can now move onto the next section.