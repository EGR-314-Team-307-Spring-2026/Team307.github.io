---
title: Project Requirements
---

## Overview

As Team 307 progresses through the project, we have decided to create a list of requirements that are within the stretch goals for this project. As a team, we decided which features are important to the final product which shaped the table of requirements. Afterwards, each team member decided with one another on who would take responsibility for the requirements that need to be fufilled to ensure the success of the final project.


## Requirements

| Requirement | Description | How the requirement will be met  | Requirements to pass/ Failure conditions | Satisfying Requirements  | Stretch Goal? (y/n) |
| :---- | :---- | :---- | :---- | :---- | :---- |
| Measuring speed | The device will need a module for measuring and reporting the speed of the device as it is used. (Hall effect sensor or Accelerometer.)  | Measure speeds up to 10 miles per hour | The system falls short by 10 percent to the target speed. | Sensing; involves detecting and quantifying motion using sensors. | No |
| Movement | The exploration device needs to move; it will need a module for controlling a built-in motor.  | A PCB board will be fabricated and programmed to move a motor that is attached to a propeller, allowing our water exploration device to move. (H-bridge and motor) | The device is able to move reliably in multiple water conditions: **Fails** if the device is unable to move at any time  | Actuation (Movement/Exploration); requires actuator i.e motors ,servos and thrusters. | No |
| Sensing Temperature       | The device will need a module for reading the temperature of the water around it. | Measure temperatures of 0c up to 30c | Device can accurately depict Measurements of temperature in the range of 0C up to 30C: **Fails** if it cannot read temperature. | Sensing (Temperature); Using sensors such as thermistors,RTD,and or digital temp. Sensors  | No |
| Waterproof  | The exploration device, at times, will be fully submerged in water; the device needs to be waterproofed to ensure it still works effectively in these conditions  | Fully sealed chassis with coated materials and PCBs to ensure functionality in submerged conditions (Fully sealed chassis, mineral coating for PCBs) | The device can effectively work while submerged. It **fails** if the device chassis leaks or the PCBs are unable to work underwater  | Waterproofing (Sealed Chassis,) | Yes |
| Wireless Communication | The device will have an HMI module that includes some form of human interface, ranging from an OLED screen to push buttons for direction control | A control device will be used to move the device when far away. An OLED device will read measurements taken by the device and display them to the user  | The control system can be used from a long range to reliably move the device; the user should also be able to see measurements taken from the device at a long range. | Wireless communication (WifFi, Bluetooth) | No |
| Altitude of the device within the water | The device will have a sensor module that will determine how deep the device is within the space it is being used | Creating an origin, and measuring the distance in the negative direction to simulate below sea level.  | If the reading is off by 10 percent of the actual position. | Sensor, can use things such as a Pressure Sensor or an ultrasonic altimeter | No |
| Internal Leak Detection | Needs a module that detects water within the device and triggers an alarm. | Turns on the alarm if there is water detected within the casing. | If it does not detect a leak  | Sensor, this acts as a reading since you can use a water detection sensor  | No |
| Avoiding Obstructions | A module that helps avoid crashing into any large objects or obstructions will tell the motor to stop moving | Transmits data from the sensor to communicate with the motor module | If the data received does not command the motors to change direction.  | Actuation, the actual motion of the motors changing direction, falls under this. | No |
| Visual feed | They will have a module that provides a live feed of what the drone is monitoring with a camera | Video is being displayed back to the user. | The video is not being displayed correctly or there is an offset.  | HMI, since the video is being displayed by the user. | Yes |
| Water Pressure Module | pressure is too low, tells to raise it higher by means of removing the sample  | The sensor communicates to the microcontroller reading the water pressure surrounding the submersible  |  The pressure of the readings  isn't accurate to the 5 percent, using a pressure chamber. | Sensor (Water Pressure) sends the reading to the controller providing threshold levels. | Yes |
| Short/Long Range | Determine the correct distance set by user so it has enough time to stop or go if needed | Communicate with distance sensor, using units of a certain value (ie 2 ft) | The distance sensor needs to be completely accurate and shared with the user. Fails if the distance is inaccurate or if the device is unable to measure  | Sensor( Distance) | No |
| Quick reaction time | Allow enough time (in ms) to stop the device to avoid crashing efficiently | Part of the sensing module, reads data and codes to stop | Sensors: The device does not act in time and crashes into obstacles. | Sensor (Reaction) | No |
| Reading the ambient radiation within the water | The device will have a module that provides the reading of the ambient radiation within the water | Radiation sensor that detects the ambient Becquerels | It passes if it can provide the reading of the ambient radiation: Fails if it cannot provide a reading. | Sensor (Radiation) | No  |


| Team member | The requirement is being fulfilled by them |  |
| :---- | :---- | :---- |
| Zane Brauer | Environmental Sensing (Temperature)  | Focus: Environmental temperature measurement |
| Abriana Poola | Human-Machine Interface | Focus: Camera control, mode selection, microphone, touchscreen panel |
| Don |  Motion & Speed Sensing (Vehicle State)           | Focus: Vehicle state detection |
| Garrett Wiebke  | Actuation & Movement Control / Waterproofing / Wireless Comms. | Focus: Controlling motors, actuators, and waterproofing mechanisms. |
| JT Harrison | Distance Sensor/Range/Reaction Time | Focus: Distance and reaction measurement |
| Elisabeth Sabbagh | Altitude/Radiation/Depth | Focus: Environmental extremes sensing |

##  Design Rationale

As a team, it was decided that the main scope of this project will be water. With water being the team's focus, there was a list of features that helped shaped the requirements of the project:

- It should be able to swap between surface floating and fully submersible
- the system will have to move, take samples, and collect waste
- As an exploration device, it should be self-sufficient such as self charging, having a multitude of sensors that work with one another underneath one huge sensor, and etc
- Having a HMI to allow access of data and be able to collect it when exploring

With these needed features, the team was able to create requirements that satisfy the projects main objective, while ensuring each team member fulfills their individual portion of the course's requirements.

