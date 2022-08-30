+++
copyright = "Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved."
spdx-license-identifier = "CC-BY-SA-4.0"
title = "AWS Databricks IoT Workshop"
chapter = false
weight = 1
+++

In this workshop, you will configure AWS IoT Core to ingest stream data from the AWS Device Simulator, deliver that data to an Amazon Kinesis stream with an IoT rule and perform streaming analytics / machine learning on the data in realtime with Databrocks. The expected duration of this workshop is two (1.5) hours, and the target audience are data engineers, data scientists, IoT application developers.

To develop this workshop properly, it is necessary to have a basic understanding of CloudFormation templates, JSON format, SQL, and Python.

You will provision a wind turbine application to simulate telemetric data points to AWS IoT. The Figure below describes the solution architecture overview and its componentes, which will be detailed and explained in the following sections.

![Solution Application Architecture](images/complete-architecture.png)

### Modules

This workshop is divided into four modules. Each module describes a scenario of
what we're going to build and step-by-step directions to help you implement the
architecture and verify your work.

| Module | Description |
| ---------------- | -------------------------------------------------------- |
| [Set up IoT Device Simulator][iot-device-simulator] | Deploy AWS device simulator with wind turbine sensor configurations. |
| [AWS Data Ingestion Management][aws-data-ingestion] | Ingest simulated device data into AWS IoT Core and deliver it to Amazon Kinesis Data Stream. |
| [Databricks Cloud Setup][databricks-cloud-setup] | Create a Databricks Cloud account, setup AWS permissions for your workspace and launch a Databricks cluster in your AWS account. |
| [Streaming Analytics][streaming-analytics] | Use Databricks notebooks to perform realtime analytics on the incoming sensor data. |

:warning: These modules are intended to be executed in order.

After you have completed the workshop you can delete all of the resources that were created by following the [cleanup guide][cleanup].

[setup]: setup
[iot-device-simulator]: iotdevicesimulator
[aws-data-ingestion]: awsdataingestion
[databricks-cloud-setup]: databrickscloudsetup
[streaming-analytics]: streaminganalytics
[cleanup]: cleanup
