---
title: Block Diagram, Protocol, and Message Structure
---

## Overview

For our teams’s system, we built it using a daisy chain system where each teammate designs a dedicated subsystem board. Communication between boards occurs through a 8 pin ribbon connector using digital serial signals. The team includes sensing subsystems (distance, pressure, temperature), motor control for actuation, and human interface modules. Each board includes its own power regulation and microcontroller (PIC or ESP32), allowing independent operation as well as full system integration.

## Team Block Diagram


![team software](tbg.png)
*Block Diagram PDF: [Download here](Team307_Block_Diagram.drawio.pdf)*

 The block diagram as a team, we decided that pin 8 would be shared ground so ensure stable connection throughout the communication when adding together all the components. Furthermore, shared power is through pin 1, The team decided to have pin 2 as the uart pin, and pin 8 is the shared ground. With that the block diagram is divided up into 6 subsystems that connect through a daisy chain loop. JT subsystem is sending a digital signal connection to Garret subsystem as well as sending data out to Zane subsystem. Zane subsystem is storing the data given from JT subsystem as well as computing data from a temperature sesor and displays both data's to Abriana OLED subsystem. Abriana subsystem also is sending data out to Garrets subsystem. garret subsystem sends digital signal to 8 pin connector onto Donovan subsystem. Donovan subsystem `takes the digital data, then makes the Uart from the subsystem and sends that data to Elisabeth subsystem. Elisabeth subsystem takes the data recieved from Donovan subsystem along with computing pressure sensor values, sends the data to  Abriana subsystem where the data is stored and then displayed on the OLED in  Abriana subsystem.

## Sequence Diagram of Team Communication

![Team Software](https://raw.githubusercontent.com/EGR-314-Team-307-Spring-2026/Team307.github.io/main/docs/04-Team-Block-Diagram/HallEffectConcept.drawio.png)
*Sequence Diagram draw.io: [website](https://app.diagrams.net/?src=about#G16IhPEk2CgQ-QdMvY7qi-FTfsWQHPuqO4#%7B%22pageId%22%3A%22t7_Y112LHUEoPPghb1Yn%22%7D)*

This sequence diagram illustrates the interactions within a sensor-driven submersible where a WebUser sets parameters that initialize the sensors and motors. Garrett Motor, Donovan Hall 
Effect sensor, Lis Pressure Sensor, Zane Temperature Sensor, and Jt Distance Sensor all power on and begin sending status and data messages. The system continuously reads sensor data, 
calculates speed and position, and sends obstacle and temperature readings. This information is displayed on Abriana’s OLED screen, while debug messages are exchanged to monitor system 
status. The loop ensures ongoing updates and adjustments, with safety checks to stop motors if obstacles are detected. Overall, the diagram shows a coordinated flow of initialization, data 
acquisition, processing, display, and debugging within the system.


## Message proctol

Team 307 messages protocol is as follows. The first and second byte of every message sent through uart will be 'AZ'. Followed by a third byte that is the sender ID, which is just the sender's captialized intial. The fourth is is the reciever ID, the reciever's captialized intial. The following bytes will have data that is defined by types in the section below. Then the endd of the message will be two byte thats wrtie out 'YB'. Alongside that, no messages will be longer then 64 bytes.

An example of a message that will be sent between devices is "AZEAHelloYB".

The list of sender/reciever IDs are "A,D,E,G,J, and Z"

## Message Types

## Team 307 – Message Types (uint16_t)

| Message Type | Description |
|--------------|------------|
| 1 | Set motor command |
| 2 | Motor status report |
| 3 | Motor speed report |
| 4 | Distance value (mm) |
| 5 | Hall sensor value |
| 6 | Depth/Pressure value |
| 7 | Temperature value |
| 8 | HMI button event |


---

### Message Type 1 – Set Motor Command

| Byte 1–2 | Byte 3 | Byte 4 | Byte 5-62| Last 2 Byte |
|---------------------|------------------|----------------------|-----------|-----------|
| AZ | J | G | Speed setting | YB |


### Message Type 2 – Motor Status Report

| Byte 1–2 (uint16_t) | Byte 3 (uint8_t) | Byte 4–5 (uint16_t) | Byte 6–58 |
|---------------------|------------------|----------------------|-----------|
| 0x02 | motor state | current speed | 0x00 padding |


### Message Type 3 – Motor Speed Report

| Byte 1–2 (uint16_t) | Byte 3–4 (uint16_t) | Byte 5–58 |
|---------------------|----------------------|-----------|
| 0x03 | distance mm | 0x00 padding |


### Message Type 4 – Distance Value (mm)

| Byte 1–2 (uint16_t) | Byte 3–4 (uint16_t) | Byte 5–58 |
|---------------------|----------------------|-----------|
| 0x04 | hall value | 0x00 padding |


### Message Type 5 – Hall Sensor Value

| Byte 1–2 (uint16_t) | Byte 3–4 (uint16_t) | Byte 5–58 |
|---------------------|----------------------|-----------|
| 0x05 | depth or pressure_value | 0x00 padding |


### Message Type 6 – Depth/Pressure Value

| Byte 1–2 (uint16_t) | Byte 3–4 (uint16_t) | Byte 5–58 |
|---------------------|----------------------|-----------|
| 0x06 | temperature value | 0x00 padding |


### Message Type 7 – Temperature Value

| Byte 1–2 (uint16_t) | Byte 3 (uint8_t) | Byte 4–5 (uint16_t) | Byte 6–58 |
|---------------------|------------------|----------------------|-----------|
| 0x07 | display page | display_value | 0x00 padding |


### Message Type 8 – HMI Button Event

| Byte 1–2 (uint16_t) | Byte 3 (uint8_t) | Byte 4 (uint8_t) | Byte 5–58 |
|---------------------|------------------|------------------|-----------|
| 0x08 | button id | event | 0x00 padding |


