# VSDSquadron_FPGA_Mini

# ABOUT ME🚀
Name: Vinutha
-
College: Sahyadri College of Engineering and Management, Adyar, Mangaluru.
-
Email ID: vinutha.ec22@sahyadri.edu.in or vinutha.km684@gmail.com
-
LinkedIn: [Vinutha Mogaveer](https://www.linkedin.com/in/vinutha-mogaveer-5a715626a)

Table of Contents
Task 1: RGB LED Control

Task 2: UART Loopback Mechanism

Task 3: UART Transmitter

Task 4: UART Transmitter with Sensor Inputs

Tasks 5 & 6: UART-Controlled actuator and seven segment display
# Verilog Code Implementation on VSDSquadron FPGA Mini Board

This repository contains the complete documentation and implementation steps for running a Verilog-based RGB LED control project on the **VSDSquadron FPGA Mini Board**. This project walks through Verilog code analysis, PCF file creation, and successful hardware integration using open-source FPGA tools.

---

## 📌 Objective

Participants will:

- Understand and document a provided Verilog code for RGB LED control.
- Analyze pin constraints via a `.pcf` file.
- Integrate the design with the VSDSquadron FPGA Mini board using its datasheet.
- Use open-source tools to build and flash the design onto the board.
- Document the entire process.

---


---
#Project 1: UART Loopback
---
Objective
Implement a UART loopback mechanism where transmitted data is received back immediately to validate the UART block.

Description
Uses a single UART port for both TX and RX

No external hardware needed other than a USB-UART cable

![board image](https://github.com/user-attachments/assets/c4455434-5fee-4a7a-9099-4bbb0424db02)

![board image 2](https://github.com/user-attachments/assets/cf2551df-8d56-49c3-9a5e-62dbe2e76112)


Loopback logic wires TX directly to RX in code
---
Test Procedure
Connect FPGA via USB

Open a serial terminal (e.g., PuTTY, screen)


Type characters — same characters should echo back

---

Project 2: UART Transmitter
---
Objective

Develop a UART TX module that transmits constant or programmed data.

Test Procedure
Serial terminal receives data from FPGA (e.g., “Hii UART”)

Ensure data rate, stop bits, and baud rate are matched

---

#Project 3: UART TX from Sensor Input
---
Objective
Transmit real-time sensor data via UART.

Hardware
Sensor 
FPGA board

USB-UART interface
Test
Stimulate the sensor
Observe terminal output

---

Project 4: UART-Controlled Display System
---
Goal

Send characters via UART and display them on a 7-segment or LCD module.
Architecture
Copy
Edit
Terminal --> FPGA UART RX --> Display Decoder --> 7-Segment/LCD

Project 5: UART-Controlled Actuator System
---
Goal
Control physical components like LEDs or motors via UART commands.

Example Commands
rust
Copy
Edit

Send: "LON"  --> Turns LED ON 

Send: "LOFF" --> Turns LED OFF

Tools Used

VSDSquadron FPGA Mini Board

PuTTY  for UART communication











