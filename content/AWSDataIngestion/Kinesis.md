+++
copyright = "Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved."
spdx-license-identifier = "CC-BY-SA-4.0"
title = "Kinesis"
date = 2019-09-09T17:42:10+01:00
weight = 10
+++

### 1. Create a Kinesis Data Stream

1. Access the [Amazon Kinesis Console](https://console.aws.amazon.com/kinesis/home) and choose "Kinesis Data Streams" , “Create data stream”

*Note: Make sure to use the ```eu-west-1``` region.*

![Kinesis](/images/kinesis-create-data-stream.png)


2. Add a new stream with the following settings:

- **Stream name**: ```simulated-iot-data-stream```
- **Capacity mode**: ```On-demand```

![Kinesis](/images/kinesis-create-stream.png)