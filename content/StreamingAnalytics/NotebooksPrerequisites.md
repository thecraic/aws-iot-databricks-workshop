+++
copyright = "Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved."
spdx-license-identifier = "CC-BY-SA-4.0"
title = "Notebook Prerequisites"
date = 2019-09-09T17:42:10+01:00
weight = 40
+++

### 4. Before you start
Before completing the notebook exercises cell by cell, you will need to configure the notebooks to use the appropriate S3 bucket in your account. The following section will mount your S3 bucket and path and attach your cluster to the notebook so that it will run interactively in your browser.

**:white_check_mark: Step-by-step directions**

1.  Open the ‘00-setup’ notebook, follow the screenshot shown below along with instructions below :

- Navigate until your respective  ‘iot-demo’ repo as shown above
- Click  on  ‘iot-demo’ repo folder
- Click on ‘resources’ folder
- Click on ‘00-setup’ notebook, this operation will open the notebook

![Resources Setup](/images/databricks/resources-setup.png)

2. Modify the cell 3/cmd3 by replacing the text <SPECIFY_YOUR_AWS_ACCOUNT_ID> with your AWS Account ID

![Specify Bucket](/images/databricks/specify-bucket.png)

**Note: The aws_bucket_name  variable should be assigned with the name of the s3 bucket you created earlier.*

## How to run

1.  Attach Cluster to the Notebook

Before starting any notebook execution , Attach the  `iot-cluster` cluster to the   notebook from the  drop down at the top left corner **Note: In the new UI ,'Connect' drop down might be on the top right corner*
![Attach Cluster](/images/databricks/attach-cluster.png)

2.  Run Cells/Command in notebook

In today’s workshop , we will execute the Databricks Notebooks commands/cells one by one  and you will see the below shown **‘Run cell’** on the top right corner and clicking that will run the cell.

![Run Cell](/images/databricks/run-cell.png)

## About ‘Widget’ command:
- You will see all Databricks Notebooks will have this command on the top.
![Widget Creation](/images/databricks/widget-creation.png)
- Running this command creates a dropdown with ‘true’,‘false’ (default id false)
![Reset](/images/databricks/reset-all-data.png)
- If you want to reset all your tables and data in your checkpoint locations then choose ‘true’ from the drop drop and then continue running the other commands in the notebook
- This might be helpful during re-run’s to have a fresh start.

You are now ready to begin running the notebook ML and streaming exericises.

