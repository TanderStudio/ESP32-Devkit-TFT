# ESP32-Devkit-TFT

![Devkit T TFT v1 2 Pinout data White BG resize](https://github.com/TanderStudio/ESP32-Devkit-TFT/assets/157987904/b7c1764c-308f-49d5-8b1e-15cc54aedc22)

## About
Development board for ESP32 and LCD TFT Display. This kit offers a range of LCD TFT Display options, including ST7789, ST7789V, ST7789V3, GC9A01, and more, providing developers with flexibility to choose the display that best suits their project needs. Alongside this display versatility, the kit features four input pulldown buttons for user interactions and an additional input for voltage readings.

This repository provides data for the Devkit and includes basic code examples for each display.

***For more detail please refer to ESP32 and LCD TFT Display datasheet***

## Datasheet
<details>
  <summary> Description</summary>
  
   ### Description
Features: 
  +	ESP32-WROOM-32X
  +	USB Protection Diode
  + USB Type-C
  + Max +6V Input 
  +	40 Pin
  +	LCD TFT Display
  +	UART CH340C
  +	3.3V Logic Level
  +	Built In LED (GPIO2)
  +	Voltage Input Read (Max +6V)
  
  Board Size:
  +	Width: 46.04 mm x Length: 51.26 mm (With Antenna: 57.51 mm)
  
  Compatible Board Select: 
  +	uPesy ESP32 Wroom DevKit
  +	Denky32 (WROOM32)
  
  LCD TFT Display Resolution:
  +	ST7789V3 (172x320 px)
  +	ST7789V2 (240x280 px)
  +	ST7789 (240x240 px)
  +	GC9A01 (240x240 px)
  
  ### SCHEMATIC
  ![image_2024-01-31_170944306](https://github.com/TanderStudio/ESP32-Devkit-TFT/assets/157987904/b922a3a0-2e35-49ee-9fa5-110b4d7dcd37)

  ### BOARD DIMENSION

  ![Screenshot 2024-01-31 190518](https://github.com/TanderStudio/ESP32-Devkit-TFT/assets/157987904/d486ddf6-295e-46d6-9c67-f18a85f52e3e)
  
</details>

### PINOUT
<details>
<summary> PINOUT </summary>

#### TFT 
Each display have the same pin
| LCD TFT DISPLAY | GPIO |
| ----------- | -- |
| `MOSI`      | 23 |
| `SCK`       | 28 |
| `CS`        | 16 |
| `DC`        | 5  |
| `RST`       | 17 |
| `BackLight` | 4  |

#### Button
| BUTTON | GPIO |
| ----------- | -- |
| `INPUT 1`   | 23 |
| `INPUT 2`   | 28 |
| `INPUT 3`   | 16 |
| `INPUT 4`   | 5  |

#### Other
| Name | GPIO |
| -----------     | -- |
| `Voltage Read`  | 34 |
| `LED`           | 28 |

</details>



