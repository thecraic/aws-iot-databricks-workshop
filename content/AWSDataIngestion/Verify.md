+++
copyright = "Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved."
spdx-license-identifier = "CC-BY-SA-4.0"
title = "Verify Kinesis Data"
date = 2019-09-09T17:42:10+01:00
weight = 30
+++

### 3. Verify the data is arriving at the Kinesis Data Stream

1. Access the [AWS Kinesis Console](https://console.aws.amazon.com/kinesis), select the created stream  ```simulated-iot-data-stream``` and click the "Monitoring" tab

![Kinesis created stream](/images/kinesis-created-stream.png)

2. Inspect the incoming data and Put record charts. You should see non-zero values there:

![Kinesis incoming data](/images/kinesis-incoming-data.png)

*Note: Data remains in the buffer for 24 hours.*


You have now verified that the incoming sensor data is being delivered successfully to Kinesis Data Streams. In the next sections you will set up Databricks cloud and connect it to the Kinesis Data Stream.

