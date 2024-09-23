##UG-2864KSWLG01 SPI Display Module

This repository contains the circuit schematic and source code for a custom display module based on the UG-2864KSWLG01 OLED display. The module communicates via SPI and is designed for easy integration into embedded systems.

Features
Display Model: UG-2864KSWLG01
Display Type: 128x64 OLED, monochrome
Communication Protocol: SPI (Serial Peripheral Interface)
Input Voltage: 3.3V/5V compatible (with logic level shifter for 1.8V systems)
Low Power Consumption: OLED display consumes very little power, ideal for battery-powered projects.
Driver Chip: SSD1306
Display Color: White
Supports Multiple Platforms: Works with Arduino, ESP32, STM32, and other microcontrollers.
Compact Design: Perfect for small form factor projects such as wearables, IoT devices, and handheld gadgets.
Schematic
You can find the complete circuit schematic in the schematics folder of this repository. The schematic is designed for simplicity and ease of use, with all necessary components included for optimal display operation. If your system operates at 1.8V logic, please refer to the Logic Level Shifter section below.

Requirements
A microcontroller (e.g., Arduino, ESP32, STM32)
Power supply (3.3V/5V)
SPI interface
UG-2864KSWLG01 OLED display
Logic level shifter (if using a 1.8V system)
Required libraries for SSD1306 display (e.g., Adafruit_SSD1306 for Arduino)
Logic Level Shifter
If your microcontroller operates at 1.8V logic, you'll need a Logic Level Shifter to safely interface with the UG-2864KSWLG01 module, which requires 3.3V or 5V for its SPI signals. The logic level shifter will convert the 1.8V signals from your microcontroller to the appropriate 3.3V or 5V levels needed by the display.

Recommended Logic Shifter ICs
TXB0108: Bi-directional level shifter for converting signals between different voltage levels (supports 1.8V to 3.3V/5V).
74LVC245: Level shifter suitable for 1.8V to 3.3V conversion.
Connect the SPI lines (SCL, SDA, CS, DC, RES) through the level shifter to ensure proper communication between the microcontroller and the display.

Setup and Installation
Clone this repository to your local machine:

bash
Copy code
git clone https://github.com/yourusername/ug-2864kswlg01-module.git
Connect the UG-2864KSWLG01 module to your microcontroller using the provided circuit schematic. For 1.8V systems, include a logic level shifter in your setup.

Install the necessary libraries:

For Arduino:
Adafruit_GFX
Adafruit_SSD1306
For other platforms, refer to their respective documentation.
Flash the provided code onto your microcontroller and run the example to see the display in action.

Pin Configuration
Pin Name	Microcontroller Pin (1.8V with Level Shifter)	Description
VCC	3.3V/5V	Power Supply
GND	GND	Ground
SCL	SPI SCK (via Level Shifter)	Clock Signal
SDA	SPI MOSI (via Level Shifter)	Data Signal
RES	GPIO (configurable, via Level Shifter)	Reset Pin
DC	GPIO (configurable, via Level Shifter)	Data/Command
CS	GPIO (configurable, via Level Shifter)	Chip Select
Example Code
cpp
Copy code
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define SCREEN_WIDTH 128
#define SCREEN_HEIGHT 64
#define OLED_RESET    -1 // No reset pin used
Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &SPI, OLED_RESET);

void setup() {
  if(!display.begin(SSD1306_SWITCHCAPVCC, 0x3C)) { 
    Serial.println(F("SSD1306 allocation failed"));
    for(;;);
  }
  display.clearDisplay();
  display.setTextSize(1);
  display.setTextColor(WHITE);
  display.setCursor(0,0);
  display.println(F("Hello, world!"));
  display.display();
}

void loop() { }
