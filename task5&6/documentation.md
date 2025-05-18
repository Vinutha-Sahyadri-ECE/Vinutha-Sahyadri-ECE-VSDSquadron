# Theme 1: FPGA-Based UART-Controlled Display System

## Project Overview

This project involves designing a real-time data reception and visualization system using an FPGA. The system receives serial data via UART from a host device (PC or microcontroller), decodes the incoming characters, and displays the processed data on an output module such as a 7-segment display or LCD. Key design priorities include robust UART communication, efficient data decoding, and timely updates to the display.

## Objectives

* Develop a UART receiver (Rx-only) using Verilog
* Convert received ASCII/hex values to displayable numeric data
* Drive a 7-segment display or LCD with decoded information
* Optionally develop a PC terminal interface for testing
* Achieve stable, real-time serial data reception and display

## System Requirements

**Hardware:**

* VSDSquadron FPGA mini
* 7-segment display or LCD module

**Software:**

* Ubuntu OS
* Docklight serial terminal

## System Architecture

```
[ Host PC ]
     | USB
     v
[ USB-to-UART Converter ]
     |
     v
[ UART Receiver (FPGA) ] ---> [ Data Decoder ] ---> [ Display Driver ] ---> [ 7-Segment/LCD Display ]
```

## Functional Description

The system is built in modular fashion:

* The **UART receiver** captures incoming serial data based on standard UART protocol (8N1 format) and transforms it into an 8-bit parallel value.
* Received characters are stored and validated to ensure correct framing and baud rate alignment.
* The **data decoder** translates ASCII characters ('0'-'9') to corresponding binary values or directly to segment encoding.
* A **display controller** receives this decoded data and updates the 7-segment or LCD display accordingly.

The entire pipeline ensures that data from the PC is displayed nearly instantaneously on the output device. The system is tested using a PC serial terminal connected to the FPGA via a USB-to-UART module. Real-time responsiveness is validated by sending various characters and observing immediate display updates.

---

# Theme 2: UART-Controlled Actuator System using FPGA

## Overview

This project focuses on command-based control of actuators through UART communication with an FPGA. The FPGA receives textual commands via serial input and triggers physical outputs such as LEDs, motors, or relays based on the decoded instruction. This forms a practical approach to developing automation systems and embedded hardware controllers.

## Objectives

* Implement UART receiver in Verilog
* Parse and decode simple command strings (e.g., "LED ON", "MOTOR OFF")
* Design a finite state machine (FSM) to control GPIO pins
* Interface with and drive actuators (LEDs, relays, motors)
* Support real-time command execution from serial terminal

## System Requirements

**Hardware:**

* VSDSquadron FPGA mini
* Relay module, LEDs, DC motor + driver
* USB-to-UART module (FTDI or equivalent)
* Breadboard, jumpers

**Software:**

* Ubuntu OS
* Docklight or any serial terminal software

## System Architecture

```
[ Host PC ]
     |
     v
[ USB-to-UART Converter ]
     |
     v
[ UART Receiver (FPGA) ] ---> [ Command Parser / FSM ] ---> [ Output Control Logic ] ---> [ LEDs / Motor / Relay ]
```

## Functional Description

The development begins by validating the FPGA hardware and output pins using a basic LED blink test. Once confirmed, the UART receiver module is implemented to collect serial input and convert it into parallel data using a shift register.

Next, a **command parser** or **finite state machine (FSM)** processes incoming character streams. For example, when a user sends "LED ON", the system accumulates the characters, identifies the command, and produces a specific control signal to drive an output pin.

Each valid command is mapped to an action, such as turning on an LED or enabling a motor via a relay. The final module ensures appropriate signal timing and safety for driving physical devices. This setup enables interactive control over hardware through simple serial text commands.

The system is validated by connecting it to a PC terminal and testing real-time command execution and hardware response.

