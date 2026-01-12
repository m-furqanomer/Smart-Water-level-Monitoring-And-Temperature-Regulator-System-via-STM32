# Smart Water Level Monitoring and Temperature Regulator Control System

**STM32F401-Based Embedded System**

## Overview

This repository presents a **Smart Water Level Monitoring and Temperature Regulator Control System** developed using the **STM32F401** microcontroller. The system continuously monitors the water level in a container, displays real-time measurements on an LCD, triggers alarms when user-defined thresholds are exceeded, and performs temperature-based control using a heating element.

The project demonstrates practical embedded-system design, focusing on sensor interfacing, peripheral utilization, interrupt-driven control, and real-time decision-making using STM32 HAL libraries.

## Key Features

* Real-time water level measurement and display in millimeters
* Configurable maximum water level threshold
* Audible and visual alert when the threshold is exceeded
* Solenoid valve control for water inflow regulation
* Temperature monitoring using an LM35 sensor
* Automatic heater ON/OFF control based on temperature range
* Button-based user interface using external interrupts
* Multi-state LCD display system

## System Architecture

### Microcontroller

* **STM32F401CDU6** , ARM Cortex-M4

### Sensors

* Analog water level sensor
* LM35 temperature sensor

### Actuators

* Buzzer for alarm signaling
* Solenoid valve for water flow control
* Heating element for temperature regulation

### User Interface

* 16×2 LCD (4-bit mode)
* Tactile push buttons

## Hardware Components

| Component          | Description               |
| ------------------ | ------------------------- |
| STM32F401CDU6      | Main controller           |
| Water Level Sensor | Analog level detection    |
| LCD 16×2           | System display            |
| Potentiometer      | Threshold adjustment      |
| Buzzer             | Audible alarm             |
| Solenoid Valve     | Water inflow control      |
| 5V Relay           | Electrical isolation      |
| Heating Element    | Temperature control       |
| Push Buttons       | User input                |
| LM35               | Temperature sensor        |
| ST-Link V2         | Programming and debugging |

## STM32 Peripherals Used

* **GPIO** , LCD, buzzer, heater, LEDs, buttons
* **ADC1** , Water level sensor input
* **ADC2** , Temperature sensor input
* **Timers** , Timing and control logic
* **EXTI (Interrupts)** , Button handling

## Functional Description

### Water Level Monitoring

* The analog water level sensor is sampled using ADC.
* Raw ADC values are mapped to millimeter units.
* The current level is displayed on the LCD in real time.

### Alarm System

* User-selectable maximum water level thresholds (20 mm, 30 mm, 40 mm).
* Buzzer and LED activate when the measured level exceeds the selected limit.

### Temperature Control

* Temperature is measured using the LM35 sensor.
* Heater turns **ON** when temperature drops below **25 °C**.
* Heater turns **OFF** when temperature exceeds **35 °C**.

### User Interface

* External interrupt-based buttons allow switching between:

  * Water level display
  * Temperature display
  * Threshold selection menu

## Schematics and Flow Diagrams

* **Hardware Schematic**
  [View Schematic Diagram](https://github.com/m-furqanomer/Smart-Water-level-Monitoring-And-Temperature-Regulator-System-via-STM32/blob/main/Additional%20Docs/Flow%20Diagram.jpg)

* **System Flow Diagram**
  [View Flow Diagram](docs/flowchart.pdf)

## Development Environment

* **IDE**: STM32CubeIDE
* **Language**: C
* **Framework**: STM32 HAL
* **Debugger/Programmer**: ST-Link V2

## Academic Context

This project was developed as part of the **Microcontroller & Interfacing (CE205T / EE243T)** course. It demonstrates intermediate-to-advanced embedded systems concepts including ADC-based sensing, interrupt-driven user interfaces, real-time control logic, and hardware-software integration.

## References

* STMicroelectronics, *STM32F401 Datasheet*
* STM32CubeIDE Documentation
* SparkFun, *16×2 LCD Datasheet*
* Texas Instruments, *LM35 Datasheet*
* Open-source LCD driver references

## License

This project is intended for **educational and academic use**. Reuse and modification are permitted with appropriate attribution.
