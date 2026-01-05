<p align="center">
  <img src="./logo_full.png" />
</p>

# AlertAngel

AlertAngel is an elderly-care monitoring system that provides real-time health tracking, fall detection, and instant alerts for caregivers.

## Form factor 

**AlertAngel** devices are inspired by the GitHub Universe ID Cards i.e AlertAngel devices are also ID cards with a screen.

## What It Does
- Continuous monitoring of **heart rate**, **SpO₂**, **temperature**, and **motion**
- **Fall detection** with immediate alerts
- Simple **on-device display** for vitals and warnings
- **Medicine reminders** and **cognitive test buttons**
- Notifications through **Telegram** and a **mobile app**
- **Health data logging** for future review
- System alerts like **low battery** and **phone disconnected**

## How It Works
The ESP32 collects sensor data, checks for irregularities, updates the display, and sends instant notifications to caregivers.

## Why It Matters
AlertAngel offers an affordable, easy-to-use solution for families and caregivers needing reliable, continuous elderly monitoring.

👉 For full technical details, visit:  
**[https://github.com/AlertAngel/tech_stack](https://github.com/AlertAngel/tech_stack)**

## Workflow 

```mermaid 
graph TD
    Start([System Start]) --> Init[Initialize ESP32 and Sensors]
    Init --> Collect[Data Collection Loop]
    
    Collect --> Sensors{Read Sensors}
    Sensors --> HR[Heart Rate and SpO2]
    Sensors --> Temp[Body Temperature]
    Sensors --> Motion[Motion Detection]
    
    HR --> Check{Check Values}
    Temp --> Check
    Motion --> Check
    
    Check -->|Normal| Normal[Normal Status]
    Check -->|Alert| Critical[Critical Alert]
    
    Critical --> Buzzer[Sound Alarm]
    Critical --> Notify[Send Notification]
    
    Notify --> App[Mobile App]
    Notify --> Message[Telegram Message]
    
    Normal --> Log[Save Data]
    App --> Log
    Message --> Log
    
    Log --> Wait[Wait]
    Wait --> Collect
```
