+++
copyright = "Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved."
spdx-license-identifier = "CC-BY-SA-4.0"
title = "Prepare ML Training Data"
date = 2019-09-09T17:42:10+01:00
weight = 10
+++

### 1. Prepare ML Training Data
To perform our Data Science and Machine Learning exercises, we need some training data from a wind turbine, which we will set up in an S3 bucket.


**:white_check_mark: Step-by-step directions**

1. Download the file `tuebine.zip` from the link [https://iot-databricks-workshop-resources.s3.eu-west-1.amazonaws.com/turbine.zip](https://iot-databricks-workshop-resources.s3.eu-west-1.amazonaws.com/turbine.zip)
2. unzip the turbine.zip file to get the `turbine` folder.
3. ON the AWS account console to the [S3 service](https://s3.console.aws.amazon.com/s3/buckets?region=eu-west-1) and click `Create bucket`
4. Create a bucket with name For Example : `<AWS-Account ID>-iot-workshop-resources` and uncheck the ‘Block all public access’ check box and Checking the acknowledgement check box as shown below.

![Public Bucket](/images/databricks/public-bucket.png)

5. Click the `Create bucket` button and once bucket is created, click on the ‘upload’ button and `Add Folder`

6. Upload the unzipped ‘turbine’ folder to it, it will upload totally 9 files
![9 files](/images/databricks/upload-9-files.png)

You have now uploaded the training data for the ML exercises and can move on to the next section.

