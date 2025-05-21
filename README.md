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


### Download Design Files:

Schematics PDF

Gerber Files

3D Model

Order PCBs:

Upload the Gerber files to a PCB manufacturer (e.g., JLCPCB, PCBWay).

Use the BOM to source components from LCSC or local suppliers.

Assemble Modules:

Follow the assembly guide.

Use low-temperature solder for connectors to avoid damaging replaceable modules.
---

### **Get Involved**  
🛠️ **Build Your Own**: Follow the [hardware guide](docs/HARDWARE.md) and [firmware setup](docs/SOFTWARE.md).  
💬 **Questions?**  
- 📧 Email: [your-email@example.com](mailto:your-email@example.com)  
- 📱 Telegram: [t.me/your_telegram](https://t.me/your_telegram)  

---
