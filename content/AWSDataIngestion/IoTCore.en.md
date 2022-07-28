+++
copyright = "Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved."
spdx-license-identifier = "CC-BY-SA-4.0"
title = "AWS IoT Core"
date = 2019-09-09T17:42:10+01:00
weight = 20
+++

### 2. Configure AWS IoT Core rules

Access the [AWS IoT Core Console](https://console.aws.amazon.com/iot) and open the ‘Message Routing’ menu and choose ‘Rules’

*Note: Make sure to use the ```eu-west-1``` region.*

![Message Routing](/images/iot-core-message-routing.png)

1. Click on ‘Create rule’ button and specify:
- **Rule name**: ```wind_turbine_to_kinesis_rule``` and click 'Next'

2. Choose on ‘Next’ button and specify the query statement: ```SELECT * FROM 'demo/wind-turbine'``` and click 'Next'

*Note: The single quote is required*

3. Attach the following rule actions:
- Choose “Kinesis Stream” from the drop down
- **Stream name** ```simulated-iot-data-stream```
- **Partition key name** ```${newuuid()}```
- Let the wizard create a role with the name: ```IoTtoKinesisRole```

Click on 'Next' to Review and create the rule

![Rule Actions](/images/iot-core-attach-rule-actions.png)

4. Click 'Create' to create the AWS IoT Core rule.

![Rule Created](/images/iot-core-rule-created.png)


You have now created the AWS IoT Core rule that routes incoming messages to your Amazon Kinesis stream.

Let's verify that the data is arriving.