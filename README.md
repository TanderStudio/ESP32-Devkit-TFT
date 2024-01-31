# ESP32-Devkit-TFT

![Devkit T TFT v1 2 Pinout data White BG resize](https://github.com/TanderStudio/ESP32-Devkit-TFT/assets/157987904/b7c1764c-308f-49d5-8b1e-15cc54aedc22)

## About
Development board for ESP32 and LCD TFT Display. This kit offers a range of LCD TFT Display options, including ST7789, ST7789V, ST7789V3, GC9A01, and more, providing developers with flexibility to choose the display and all pin that best suits their project needs. Alongside this display versatility, the kit features four input pulldown buttons for user interactions and an additional input for voltage readings.

This repository provides the basic data for the Devkit and includes basic code setup and examples for each display.

***For more detail please refer to ESP32 and LCD TFT Display datasheet***
<details> 
<summary>Related Document Link</summary>

+ [ESP32 WROOM 32 Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-wroom-32_datasheet_en.pdf) PDF
+ [ESP32-DevkitC V4](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/hw-reference/esp32/get-started-devkitc.html)
+ [ESP32-Series Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32_datasheet_en.pdf) PDF
+ [GC9A01 Datasheet](https://www.buydisplay.com/download/ic/GC9A01A.pdf) PDF

</details>



## Datasheet
<details>
  <summary> Features, Board Size, Board Select, TFT</summary>
  
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
| `INPUT 1`   | 35 |
| `INPUT 2`   | 32 |
| `INPUT 3`   | 33 |
| `INPUT 4`   | 25 |

#### Other
| Name | GPIO |
| -----------     | -- |
| `Voltage Read`  | 34 |
| `LED`           | 28 |

</details>

# CODE
<details>
  <summary> Details </summary>

To start, this Devkit board utilizes the same ESP32 as other Devkits. Specifically, it employs either the `ESP32-WROOM-32D` or `ESP32-WROOM-32U` module, which can be identified on the module itself. Additionally, this board is compatible with other libraries, as long as they do not interfere with pins already in use on the Devkit.

If you are using `platform.io`, select the `uPesy ESP32 Wroom DevKit` as the target `board`.
  
## Devkit
<details>
<summary>V Read, LED, Button</summary>
  
  ### Voltage Read
  This code snippet is for reading the voltage on an ESP32, offering a straightforward method for monitoring battery levels. It's crucial to acknowledge that the accuracy of voltage readings may differ among individual ESP32 devices, and the ADC readings of the ESP32 `may not` exhibit a linear pattern. The voltage input read system employs a basic voltage divider using `two` `220k` ohm resistors, as indicated in the schematic. The code is setup to operate with this specific voltage divider setup.


  put the code on the `void loop` and the `GPIO` pin is `34`
  ```
float VoltageRead = analogRead(34);
  for (int i = 0; i < 16; i++) {
    VoltageRead = VoltageRead + analogRead(34); // ADC
  }
  float Voltage = 2 * VoltageRead / 16 / 4095.0 * 3.3; // ADC correction, ADC range: 0-4095, Vref: 3.3V
  Serial.println(Voltage,3);
```
  ### Built in LED
  This code snippet is for controlling the LED on the Devkit, which is connected to GPIO 2. You can use this LED in the same way as any standard LED.

  ### Button
  
  
</details>

## TFT
<details>
  
To begin, you can choose any display library compatible with the ESP32 Devkit and TFT display. I recommend using either [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI?tab=readme-ov-file) by Bodmer or [LovyanGFX](https://github.com/lovyan03/LovyanGFX) by lovyan03.

The `pin` configuration for the display that is compatible with this board remains the same across various displays.

to controll the `Backlight` i recommend to do it separately from the library

| LCD TFT DISPLAY | GPIO |
| ----------- | -- |
| `MOSI`      | 23 |
| `SCK`       | 28 |
| `CS`        | 16 |
| `DC`        | 5  |
| `RST`       | 17 |
| `BackLight` | 4  |
</details>
  
</details>


