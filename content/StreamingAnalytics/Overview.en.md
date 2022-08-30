+++
copyright = "Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved."
spdx-license-identifier = "CC-BY-SA-4.0"
title = "Overview"
date = 2019-09-09T17:42:10+01:00
weight = 1
+++

In this module you will prepare some training data for ML by uploading a preconfigured file to Amazon S3. You will then create and launch a Databricks cluster into your AWS account. This cluster will use the instance profile from earlier sections to access Kinesis and S3 for streaming analytics.

You will then connect the Databricks cluster to a public GitHub repo where the Databricks notebooks needed to run the streaming analytics are stored.

Finally you will run the notebooks and execute the streaming analytics workflow.

![Solution Application Architecture](/images/complete-architecture.png)

