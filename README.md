# Smart Ventilation System Using Arduino Uno

## Project Overview

The Smart Ventilation System is an Arduino-based embedded systems project designed to detect combustible gases and automatically activate a ventilation fan when the sensor reading exceeds a predefined threshold.

The system uses an MQ-5 gas sensor to monitor gas levels and provides visual and audible alerts through LEDs and a buzzer. A 16x2 LCD displays the sensor readings and the current system status.

This project demonstrates the practical application of sensors, microcontrollers, and automated control systems.

## Objectives

- Detect combustible gases using an MQ-5 gas sensor.
- Monitor sensor readings in real time.
- Automatically activate a fan when the sensor reading exceeds a predefined threshold.
- Provide visual alerts using red and green LEDs.
- Generate an audible warning using a passive buzzer.
- Display sensor readings and system status on a 16x2 LCD.

## Components Used

- Arduino Uno
- MQ-5 Gas Sensor
- 16x2 LCD Display
- Green LED
- Red LED
- Passive Buzzer
- DC Fan
- Transistor or MOSFET for fan control
- Resistors
- Breadboard and jumper wires
- Power supply

## Working Principle

The MQ-5 gas sensor continuously monitors the surrounding air and provides an analog output to the Arduino Uno. The Arduino reads the sensor output and compares it with predefined threshold values. Based on the reading, the system operates in one of two states.

### Normal Condition

When the sensor reading is below the activation threshold:

- The green LED turns ON.
- The red LED remains OFF.
- The fan remains OFF.
- The buzzer remains OFF.
- The LCD displays the gas reading and normal status.

### Gas Alert Condition

When the sensor reading reaches or exceeds the programmed threshold:

- The green LED turns OFF.
- The red LED turns ON.
- The fan turns ON.
- The buzzer produces an audible warning.
- The LCD displays a gas alert message.

A separate reset threshold is used to reduce frequent switching when sensor readings fluctuate around the activation threshold.

## Hardware Connections

The following connections are used in the Arduino program.

- MQ-5 sensor analog output (AO) - A0
- Green LED - Digital Pin 6
- Red LED - Digital Pin 7
- Passive buzzer - Digital Pin 8
- Fan driver control - Digital Pin 9
- LCD RS - Digital Pin 12
- LCD Enable - Digital Pin 11
- LCD D4 - Digital Pin 5
- LCD D5 - Digital Pin 4
- LCD D6 - Digital Pin 3
- LCD D7 - Digital Pin 2

The LCD connections listed above are for a standard 16-pin LCD operating in 4-bit mode. An I2C LCD requires different wiring and code. The DC fan must be connected through a suitable transistor or MOSFET driver and must not be powered directly from an Arduino digital pin.

## Software Requirements

- Arduino IDE
- Arduino Uno
- LiquidCrystal library for a standard 16-pin LCD
- USB cable for programming the Arduino

## Setup and Execution

1. Connect the components according to the circuit connections.
2. Open the Arduino IDE.
3. Create a new sketch and paste the Arduino program.
4. Connect the Arduino Uno to the computer using a USB cable.
5. Select Arduino Uno under Tools > Board.
6. Select the correct port under Tools > Port.
7. Upload the program to the Arduino.
8. Open the Serial Monitor and set the baud rate to 9600.
9. Allow the MQ-5 sensor to warm up and stabilize.
10. Observe the sensor readings and adjust the activation and reset thresholds according to the sensor's behaviour.

## Applications

- Domestic kitchens
- Laboratories
- Workshops
- Industrial workspaces
- Gas storage areas
- Educational embedded systems projects

## Advantages

- Automatic gas monitoring
- Visual and audible alerts
- Automatic fan control
- Real-time display of sensor readings
- Simple and low-cost implementation
- Easy integration of sensors and output devices

## Future Enhancements

- Integration of Wi-Fi or GSM modules for remote notifications.
- Data logging for monitoring sensor readings over time.
- Development of a web-based dashboard for remote monitoring.
- Improved gas concentration estimation through calibration.
- Integration of a suitable gas shut-off mechanism.

## Safety Note

This project is an educational prototype and is not a certified gas-leak detection or life-safety system. The MQ-5 sensor requires appropriate warm-up and calibration, and its raw analog readings do not directly represent gas concentration in parts per million (ppm).

Do not deliberately release LPG or other flammable gases during testing. This prototype and its fan must not be relied upon to make a real gas leak safe.
