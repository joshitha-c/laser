# ESP32-C3 Laser Tripwire alarm

An intelligent, multi-layered laser security perimeter system built on the ESP32-C3 microcontroller. Features optical tripwire detection, case tamper sensing, motion tracking, real-time clock timestamps, and an OLED status display interface.

---

## Features

* **Triple-Layer Intrusion Detection:**
  * **Laser Tripwire:** Hardware-interrupt beam monitoring via photodiode and LM393 comparator.
  * **Case Tamper:** Microswitch detection if the enclosure lid is opened.
  * **Motion / Shake Guard:** 3-axis LIS3DH accelerometer monitoring for unit displacement or physical sabotage.
* **Visual & Audible Alerts:** 
  * SSD1306 128x64 OLED display showing live state, system time (DS1307 RTC), battery percentage, and specific trip causes.
  * Transistor-driven 3.3V active buzzer siren.
* **Simulation Ready:** Pre-configured for seamless compilation in PlatformIO and testing in the Wokwi simulator.

---

## Hardware Pinout Mapping

| ESP32-C3 Pin | Component / Connection | Type / Logic |
| :--- | :--- | :--- |
| **`GPIO0`** | Photodiode Level | Analog Input |
| **`GPIO1`** | LM393 Laser Trip Signal | Digital Input (Active LOW) |
| **`GPIO2`** | I2C Data (`SDA`) | OLED Display, DS1307 RTC, LIS3DH |
| **`GPIO3`** | I2C Clock (`SCL`) | OLED Display, DS1307 RTC, LIS3DH |
| **`GPIO4`** | Siren Buzzer Driver (`Q1`) | Digital Output (PWM/Pulse) |
| **`GPIO5`** | Arm / Disarm Pushbutton | Digital Input (Active HIGH) |
| **`GPIO6`** | LIS3DH Motion Interrupt (`INT1`) | Digital Input |
| **`GPIO7`** | Battery Sense (100kΩ / 100kΩ Divider) | Analog Input |
| **`GPIO10`**| Case Tamper Microswitch | Digital Input (Active HIGH) |

---
## How to Open and Use the ZIP Project in VS Code

Follow these steps to extract, open, and run the project inside Visual Studio Code using PlatformIO and the Wokwi Simulator.
The zip file:it is in repo releases.
### 1. Unzip the Project Folder
1. Locate the downloaded `.zip` file on your computer.
2. Right-click the `.zip` file and select **Extract All...** (Windows) or double-click it (macOS).
3. Choose a destination directory (e.g., your Desktop or Projects folder) and finish the extraction.

---

### 2. Install Required Extensions in VS Code
If you haven't set up Visual Studio Code for ESP32 development yet, install the required tools:

1. Open **Visual Studio Code**.
2. Click on the **Extensions** icon on the left sidebar (or press `Ctrl + Shift + X`).
3. Search for and install the following two extensions:
   * **[PlatformIO IDE](https://marketplace.visualstudio.com/items?itemName=platformio.platformio-ide)** (Handles building and compiling C++ code for ESP32)
   * **[Wokwi Simulator](https://marketplace.visualstudio.com/items?itemName=Wokwi.wokwi-vscode)** (Simulates the ESP32 hardware and screen)

---

### 3. Open the Extracted Project
1. In VS Code, go to **File** $\rightarrow$ **Open Folder...** (or press `Ctrl + K, Ctrl + O`).
2. Navigate to the folder you extracted in **Step 1**.
3. Select the root folder (the folder containing `platformio.ini` and `wokwi.toml`) and click **Select Folder**.
4. If prompted with *"Do you trust the authors of the files in this folder?"*, click **Yes, I trust the authors**.

---

### 4. Build and Run the Project

#### Option A: Running in Wokwi Simulator (Virtual Hardware)
1. Open the **`diagram.json`** file from the left Explorer pane.
2. Press `Ctrl + Shift + P` (or `Cmd + Shift + P` on Mac) to open the VS Code Command Palette.
3. Type **`Wokwi: Start Simulator`** and press **Enter**.
4. The simulation window will open directly in VS Code, displaying the ILI9341 screen and animated buttons.

# Buzzer audio in vs Code:
* The buzzer noise when running the Wokwi simulator inside the VS Code . The vscode mutes the sounfd from the wokwi simulator so you can't hear it. 
* If you want to listen to the sound effects and music, open the diagram.json file online directly at **[Wokwi.com](https://wokwi.com)**.

---

#  Battery Level Simulation (Potentiometer Knob):
*  In the simulator, the battery level is simulated using a potentiometer (rotary knob).
* How to test battery levels: While the simulation is running, click and drag the knob clockwise on the potentiometer in the simulator window to increase or decrease the voltage.
## schematics:
<img width="1111" height="771" alt="image" src="https://github.com/user-attachments/assets/dbbde8b9-0949-443a-813e-223322b727ba" />
## pcb:
<img width="793" height="776" alt="image" src="https://github.com/user-attachments/assets/373a8255-34c5-4a0e-8feb-26ef0e5910dc" />
