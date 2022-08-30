+++
copyright = "Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved."
spdx-license-identifier = "CC-BY-SA-4.0"
title = "Launch a Databricks Cluster"
date = 2019-09-09T17:42:10+01:00
weight = 20
+++

### 2. Launch a Databricks Cluster

In this section you will launch a Databricks cluster in your AWS account with the instance profile created in earlier sections. This will allow jobs to establish a connaction between the Kinesis Stream and the Databricks workspace.

**:white_check_mark: Step-by-step directions**

1.  In your Databricks workspace navigate to the => `Compute Option` in the sidebar.

![Compute Option](/images/databricks/compute-option.png)

2.  Click the `Create Cluster` button.

![Create Cluster](/images/databricks/create-cluster.png)

3.   Provide a Cluster name  of your choice (Example : `iot-cluster`) and choose the  Databricks Machine Learning Runtime as shown in screenshot 
**note: Since we have some Machine Learning exercise , in this workshop, we are choosing a  ML Runtime.*

- **Runtime: 10.4 LTS ML (includes Apache Spark 3.2.1, Scala 2.12)**

![ML Runtime](/images/databricks/ml-runtime.png)

4. Expand the `Advanced options` menu as shown here:

![Advanced Options](/images/databricks/advanced-options.png)

5. In the **‘Advanced Options’** , navigate to the **‘Instances’ -> ‘Instance profile’** option You will see the instance profile which you added in the previous step in the drop down. Choose the instance profile from the drop down.

![Choose Instance Profile](/images/databricks/choose-instance-profile.png)

6. Click the `Create Cluster` button and  wait for the Cluster to be created and running as below with a green tick mark

![Created Cluster](/images/databricks/created-cluster.png)


You have now created a Databricks cluster which can be used for streaming analytics and machine learning jobs with notebooks.

In the next section you will connect a Gihut repository containing the Databricks workbooks needed to run the ML/Streaming analytics exercises.

