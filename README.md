
# YANS-COMP-BANDUNG  #      
# 1.69"TFT v1.1 (GMT169-01)  TFT 1.69" Display
# 240 x 280  resolutions
# 4-Wire SPI 

TESTED OK with lib TFT_eSPI board YD-ESP32-S3N16R8  Vscode Platformio arduino framework

![LCD Display](https://ae01.alicdn.com/kf/S81f7ddccb54847bcbde724251cc90a732.jpg)

## Introduction

This 1.69 Inch LCD Display is a 1.69-inch serial liquid crystal display with rounded corners. Offering a superior resolution of 240×280 pixels and 262K RGB display colors, this display provides crystal-clear, colorful image representation.

### Specifications
| Operating voltage       |    3.3V / 5V     |
|-------------------------|------------------|
| Resolution              | 240 × 280 pixels |
| Communication Interface | 4-wire SPI       |
| Display size            | 22.5 × 25.4mm    |
| Display Panel           | IPS              |
| Driver                  | ST7789V3         |
| Dimensions              | 26.5 × 39.5mm    |

## Outline Dimensions
![Outline Dimensions](https://ae01.alicdn.com/kf/S79d9f23ace844b66b74efb475f30ea4ef.jpg)

## Features

- 240×280 resolution, 262K RGB colors, clear and colorful displaying effect
- SPI interface, minimizes required IO pins, Tested YD-ESP32-S3-N16R8 

## Application Ideas

- **Band or Watch**: The display can be assembled with the XIAO MCU to build a band or watch device.
- **PC Information Show Screen**: Display your PC running information, such as temperature and fan RPM.

## Hardware Overview
![Hardware Overview](https://files.seeedstudio.com/wiki/lcd_spi_display/3.png)

## Getting Started

### Hardware Preparation

Connect the display pins to the YD-ESP32-S3-N16R8:

| 1.69-inch LCD SPI Display | YD-ESP32-S3-N16R8 |
| ------------------------- | ----------------- |
| BLK                       | GP9               |
| CS                        | GP10              |
| DC                        | DGP11             |
| RES                       | GP12              |
| SDA                       | GP13              |
| SCL                       | GP14              |
| VCC  5V                   | VCC               |
| GND                       | GND               |

![Connection Diagram](https://ae01.alicdn.com/kf/S738f78fe679c4cdcb35fcde82cfc388bQ.jpg)

## Arduino Library Overview
To use the display with Arduino, you can download the library from the following link:

[Download the Library]([https://github.com/yans-comp-bandung](https://github.com/Bodmer/TFT_eSPI/releases/tag/V2.5.43))

### Example Code

```cpp
#include <Wire.h>
#include <ST7789.h>  // Add the header file for the LCD display

ST7789 tft = ST7789(TFT_CS, TFT_RST, TFT_DC); // Define pins for CS, RST, DC

void setup() {
  tft.init();             
  tft.setRotation(3);     
  tft.fillScreen(ST77XX_WHITE);  
  tft.setTextColor(ST77XX_BLACK);  
  tft.setTextSize(1);     
  tft.setCursor(0, 0);    
  tft.println("Hello World!");  
}

void loop() {
  // You can add more code here to display other information
}
