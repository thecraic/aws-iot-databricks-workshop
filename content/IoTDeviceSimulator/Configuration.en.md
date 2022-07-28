+++
copyright = "Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved."
spdx-license-identifier = "CC-BY-SA-4.0"
title = "Configuration"
date = 2021-01-13T15:09:39+00:00
weight = 20
+++

### 2. Configure the IoT Simulator

We will use the AWS IoT Simulator to create a wind turbine device and simulate the generation of sensor relay events from the device to AWS IoT Sitewise.

#### Login to the Simulator

Once you use the IoT Simulator console URL link from your email, during your first login you will be prompted to define a new password.
- For Example: User => abc.def@xyz.com
- For Example: Password: @Databricks0nAWS


![Simulator screenshot](/images/iot-simulator-logged-in.png)

#### Define a device type

**:white_check_mark: Step-by-step directions**

1. Click on the “Device Types” tab in the top and the “Add device type” button, you will arrive at the following screen:

![Simulator screenshot](/images/iot-simulator-add-device-type.png)

2. Add a new device type with the following settings:

- **Device Type Name**: ```windturbinedevice```
- **Topic**: ```demo/wind-turbine```

*Note: This is the AWS IoT Core topic that will be used to route messages to Amazon Kinesis*

2. Click on ‘Add attribute’ button and prepare the below Attributes list. This may take a few minutes to add them one by one. 

**Check the values carefully for each one.**

![Simulator screenshot](/images/iot-simulator-add-attributes.png)

2. Click the ‘Save’ to save the device type attributes.

![Simulator screenshot](/images/iot-simulator-save-attributes.png)

#### Define a simulation

**:white_check_mark: Step-by-step directions**

1. Click on the “Simulations” tab in the top and the “Add Simulation” button, you will arrive at the following screen:

![Simulator screenshot](/images/iot-simulator-simulations.png)

2. Add a new simulation with the following settings:

- **Simulation name**: ```windturbinesimulation```
- **Simulation Type**: ```User Created```
- **Device Type**: ```windturbinedevice``` - from above
- **Number of devices**: ```10```
- **Data transmission interval**: ```1 (every 1 second)```
- **Data transmission duration**: ```3600 (1 hour)```

The form will look like this:
![Simulator screenshot](/images/iot-simulator-create-simulation.png)
3. Click 'Save' to save the simulation.

#### Run the simulation

1. Click on the “Simulations” tab in the top select the newly created *windturbinesimulation*

2. Click on the 'Start simulations' button to start the   *windturbinesimulation*

![Simulator screenshot](/images/iot-simulator-created-simulation.png)

3. Click on the 'View' button to see details of the running simulation:

![Simulator screenshot](/images/iot-simulator-running-simulation.png)


