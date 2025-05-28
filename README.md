# Incucloud-Egg-Incubator

A cloud-connected smart egg incubator that enables remote monitoring and control of temperature, humidity, and rotation cycles via a mobile app or web interface. Designed for poultry farmers, hobbyists, and researchers to optimize hatch rates and track incubation progress from anywhere. 🌍


# **IncuCloud: Smart IoT Egg Incubator** 🐣  

*Remote Monitoring and Control for Smart Egg Incubation*  

[![IoT Enabled](https://img.shields.io/badge/IoT-Enabled-green)](https://github.com/topics/iot)

**By Navin Shanmugam** | Electrical & Electronics Engineer  

### **Problem Statement**  
Traditional egg incubation methods often suffer from inconsistent temperature, humidity, and manual monitoring, leading to poor hatch rates. To address this, I designed **IncuCloud**: an open-source, IoT-enabled incubator that automates and optimizes the entire hatching process.  

### **Project Evolution**  
This project began as a bachelor’s thesis—a minimal IoT prototype with limited functionality. After years of iterative improvements, professional experience in embedded systems (at **VLS Automations**), and rigorous R&D (including custom PCB design and firmware optimization), IncuCloud now offers:  
- **Stable, crash-resistant operation** (tested for 1000+ hours).  
- **Automatic day-counting** and lockdown phase adjustments.  
- **Remote monitoring/control** via a cloud dashboard (Arduino IOT Could platform).
### [1st Project](https://github.com/Navin23052000/Incubator-Online-controll-unit)
---

### **Why Open-Source?**  
To empower farmers, hobbyists, and engineers to:  
✅ Build affordable, high-efficiency incubators.  
✅ Adapt designs to local needs (e.g., power constraints, bird species).  
✅ Learn embedded systems through practical agricultural tech.  

**Credit the project** if you use/modify this work.  

---

### **Features** 🌟  
- **Auto Day Tracking**: Adjusts parameters for lockdown phases automatically.  
- **IoT Integration**: Real-time alerts and remote control via web/mobile (arduino cloud platform).
- **Auto Mode**: Pre-Saved Profiles: Optimized presets for chickens, quails , ducks , and turkeys .
- **Lockdown Automation**: Auto-adjusts humidity and stops rotation in the final lockdown days of each Preset.
- **Manual Mode**: Fully customizable temperature, humidity, hatching days, lockdown day and rotation intervals.
- **Real-Time Monitoring**: Track temperature, humidity, and rotation via a dashboard.  
- **Remote Control**: Adjust settings from anywhere using a mobile app or web interface.  
- **Data Logging**: Export historical incubation data to CSV or cloud storage.
- **Sensor Smoothing**: Takes 5 datas form the sensor and give the average of that.





---

## Hardware Requirements 🔧  
| Component              | Specification                          |  
|------------------------|----------------------------------------|  
| Microcontroller        | Arduino NANO ESP32 and Node MCU ESP32s        |  
| Temperature Sensor     | BME280                      |  
| Humidity Sensor        | BME280                                  |  
| Motor                  | 60mm 230V Synchronous PM stepper motor  |  
| Heater                 | 230v aluminum elclosed heater with Relay Control  |  
| Power Supply           | Moresun SMPS                       |  
| Humidifier             | DC 24V 36mm Super Ultrasonic Mist Maker Humidifier                       |  
| Ventilation fan        | 8 inch HIGH SPEED ventilation fan 230v                    |  
| Buzzer        | 5V Active Electromagnetic Buzzer                   |  
| Setpdown BuckConverter        | LM2596HVS DC-DC Buck Converter                   |  
|Push Buttons   |Tactile Push Button Switch 6x6x5|
|RTC |DS3231 RTC Module Precise Real Time Clock I2C AT24C32|

---

## Setup Guide 💻  
### Prerequisites for Uploading the Program
- Arduino IDE (for ESP32 firmware).
- kiCAD for PCB and Schematic.

### Modular PCB Design 🛠️ 
The IncuCloud hardware is built around a removable modular PCB system, designed for easy troubleshooting and component replacement.(can't build the PCB perfectly due to less availability have to do some tweeks and fixes)

### Key Features


✅ Hot-Swappable Modules: Replace faulty components (e.g., sensors, motor drivers) without soldering.
✅ Standard Connectors: JST-XH and screw terminals for quick disconnects.
✅ Open Design: All KiCad files and Gerbers provided for customization.


## Download Design Files:

### [Schematic and 3D Model and PCB PDF](https://github.com/Navin23052000/Incucloud-Egg-Incubator/blob/main/Incucould%20Screenshots%20on%20schematic%20and%20pcb%20and%203d%20view.pdf)

### [Gerber Files(for printing PCB)](https://github.com/Navin23052000/Incucloud-Egg-Incubator/blob/main/gerber%20files%20for%20incucloud%202.zip)



## Order PCBs
    Upload the Gerber files to a PCB manufacturer (e.g., robu.in (in India)).
---
## Photos of Hardware and menu Interface

---
## Developement and Working principle  

## **1. Development Process**
### **Hardware Setup**
- **Microcontrollers:** Arduino Nano & NodeMCU ESP32S.
- **Sensors:** Temperature & Humidity monitoring.
- **Actuators:** Heater, Ventilation Fan, Egg Rotation Motor, Humidifier.
- **User Interface:** Three buttons - `MENU`, `INC`, and `DEC`.
- **RTC Modules:**
  - **One RTC** tracks days elapsed.
  - **One RTC** manages egg rotation timing.

### **Pin Configuration**
Refer to the **schematic PDF/code** for detailed **pin assignments**.

### **IoT Integration**
- Connected to **Arduino Cloud**.
- Requires:
  - **Arduino Cloud Account** setup.
  - **Device ID & Thing Secret Code** for board linking.
  - **Adding variables** (Limited to **10 per board**).
- **Data Flow**:
  - **Nano ESP32** receives control settings.
  - **NodeMCU ESP32** manages cloud connectivity & dashboard visualization.
  - **Total 19 variables** transferred.

---

## **2. Working Principle**
### **Sensor & Actuator Management**
- **Sensors monitor** temperature, humidity, time.
- **Actuators regulate** environmental conditions (**heater, fan, humidifier, motor**).

### **System Operations**
#### **Normal Functioning**
- **Data Transfer**:
  - **Nano ESP32** → Sends live **temperature, humidity, hour, minute** data via **TX/RX** pins to **NodeMCU**.
  - **NodeMCU ESP32** → Uploads data to **Arduino Cloud dashboard**.
- **Day Countdown Calculation**:
  - Done by **NodeMCU ESP32**, then relayed to **Arduino Nano**.

#### **User Controls**
- **Mode Selection**:
  - **Auto Mode** → System follows pre-set parameters.
  - **Manual Mode** → User adjusts settings.
- **Trigger Start Day**:
  - **Press `INC` & `DEC` simultaneously**.
  - Enter **current Date, Month, Year**.
- **Lockdown Phase**:
  - If **lockdown day reached**:
    - **Temperature & humidity auto-adjust**.
    - **Egg rotation stops**.
- **Hatching Completion**:
  - If **hatching day passed**:
    - **Beeping sound activates**.

### **Temperature & Humidity Regulation**
- Uses **three values** for control:
  - **Set Value**
  - **Tolerance Value**
  - **Threshold Value**
- **Regulation Logic**:
  - If **sensor value < (Set Value + Tolerance)** → **Heater/Humidifier ON**.
  - If **sensor value > (Set Value - Threshold)** → **Heater/Humidifier OFF**.
- **Sensor Smoothing**:
  - **Averages 5 sensor readings** to minimize frequent switching.

---

## **3. Installation & Setup**
### **1. Hardware Connections**
- Refer to the **provided schematic**.
- Wire components according to pin mapping in **code/PDF**.

### **2. Cloud Setup**
- Create an **Arduino Cloud Account**.
- Add **both devices** using:
  - **Device ID**
  - **Device Secret Code**
- Define **changing & stable values** (Limit: **10 variables per board**).

---

## **License**
[This project is open-source under the **MIT License**.](https://github.com/Navin23052000/Incucloud-Egg-Incubator/blob/main/license.md)


---

### **Get Involved**  
🛠️ **Build Your Own**: Follow the hardware guide and firmware setup.  
💬 **Questions? or any tweeks recommendation**  
- 📧 Email: [navinshanmugam23@pm.me](mailto:navinshanmugam23@pm.me)  
- 📱 Telegram: [t.me/Navin233](https://t.me/Navin233)  

---
