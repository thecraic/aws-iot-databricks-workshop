+++
copyright = "Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved."
spdx-license-identifier = "CC-BY-SA-4.0"
title = "Setup"
date = 2019-09-09T17:42:10+01:00
weight = 10
+++

### 1. Setup the AWS IoT Simulator

**:white_check_mark: Step-by-step directions**

1. Visit the [AWS IoT Simulator][iot-simulator] homepage and click on the **“Launch on the AWS Console”** button

![Launch Simulator](/images/launch-simulator.png)

This will take you to the CloudFormation console and the “Create Stack” window.

2. Change your region to ```eu-west-1 (Ireland)``` and create the stack.
- For stack name choose: ```aws-iot-simulator```
- For administrator’s email address enter ```your email address```.
- Leave all other items as defaults.
- Acknowledge that AWS CloudFormation might create IAM resources.
- Choose ```Create Stack```.

This stack creation step would take approximately 5 minutes.

Once the stack creation is completed, the user will receive an email with the IoT Device Simulator Login information i.e. (link to the IoT simulator console and temporary credentials) For Example: ```https://d2kkv2dj5ayy89.cloudfront.net```

*Note: The IoT Simulator console URL is also available in the ‘Output’ tab of the CloudFormation stack as shown below.*

![Region selection screenshot](/images/iot-simulator-cf-outputs.png)

[iot-simulator]: https://aws.amazon.com/solutions/implementations/iot-device-simulator/