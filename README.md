# UG-2864KSWLG01 SPI Display Module
 
# This repository contains the circuit schematic and source code for a custom display module based on the UG-2864KSWLG01 OLED display. The module communicates via SPI and is designed for easy integration into embedded systems.

# 1. Features
- Display Model: UG-2864KSWLG01
- Display Type: 128x64 OLED, monochrome
- Communication Protocol: SPI (Serial Peripheral Interface)
- Input Voltage: 1.8V/5V compatible (with logic level shifter for 1.8V systems)
- Low Power Consumption: OLED display consumes very little power, ideal for battery-powered projects.
- Driver Chip: SSD1306
- Display Color: White
- Supports Multiple Platforms: Works with Arduino, ESP32, STM32, and other microcontrollers.
- Compact Design: Ideal for small form factor projects like wearables, IoT devices, and handheld gadgets.

# 2. Schematic
You can find the complete circuit schematic in the ZIP of this repository. The schematic is designed for simplicity and ease of use, with all necessary components included for optimal display operation.

# Note: If your system operates at 1.8V logic, please refer to the Logic Level Shifter section below.

# Requirements
- A microcontroller (e.g., Arduino, ESP32, STM32)
- Power supply (3.3V/5V)
- SPI interface
- UG-2864KSWLG01 OLED display
- Logic level shifter (if using a 1.8V system)
- Required libraries for SSD1306 display (e.g., Adafruit_SSD1306 for Arduino)
- Logic Level Shifter
- For systems using 1.8V logic, a Logic Level Shifter is required to safely interface with the UG-2864KSWLG01 module, which requires 3.3V or 5V for its SPI signals. The logic level shifter will convert the 1.8V signals from your microcontroller to the appropriate 3.3V or 5V levels needed by the display.

# Recommended Logic Shifters
- TXB0106PWR: Bi-directional level shifter for converting signals between 1.8V and 3.3V/5V.

# Make sure to connect the SPI lines (MOSI, SCK, CS, D/C, RST) through the level shifter to ensure proper communication between the microcontroller and the display.

# Setup and Installation
Connect the UG-2864KSWLG01 module to your microcontroller using the provided circuit schematic. For 1.8V systems, include a logic level shifter in your setup.

# Install the necessary libraries:

For Arduino:
Adafruit_GFX
Adafruit_SSD1306
For other platforms, refer to their respective documentation.
Flash the provided code onto your microcontroller and run the example to see the display in action.
