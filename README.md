# ⚡ Prepaid Energy Meter Using Arduino & GSM
A smart prepaid electricity billing system developed using Arduino and GSM technology. This project allows users to recharge credits via SMS, monitor real-time electricity usage, and automatically disconnects power once credits are exhausted.
--
## 🎯 Project Objectives
- Eliminate manual electricity billing errors.
- Enable SMS-based credit recharges remotely.
- Display real-time usage.
- Balance on an LCD.
- Automatically cut off power when credits run out.
---
## 🧰 Components Used
- Arduino Uno
- GSM Module (SIM800L or similar)
- 16x2 LCD Display
- Relay Module
- Current Sensor
- Buzzer
- Breadboard
- Jumper Wires
- Resistors
- Connectors
- Power Supply
## 🛠️ Software & Tools Used
- Arduino IDE (for code upload)
- Proteus (for simulation)
- Microsoft Word / PDF Editor (for documentation)
---
## 🔧 How to Use
1. Upload the `prepaid_meter.ino` file to your Arduino board using the Arduino IDE.
2. Assemble the hardware components as shown in the `circuit.jpg` image.
3. Insert a valid SIM card with SMS balance into the GSM module.
4. Power on the system:
   - The LCD will show the current credit balance.
   - If balance is sufficient, the load is switched ON.
   - The system alerts and turns OFF the load when credit runs out.
5. Send SMS in the predefined format to recharge credits.
---
## 📘 Documentation
Full report provided in `report.pdf` containing:
- Abstract
- Block Diagram
- Circuit Description
- Working Principle
- Code Explanation
- Results & Conclusion.
## 🖼️ Prepaid Energy Meter – Circuit Operation Flow (Step-by-Step)
Start
➡️ Initialize Arduino UNO
➡️ LCD Initialization
Displays "System Starting..."
➡️ GSM Module Initialization
Wait for GSM network response
➡️ Check Balance Stored in EEPROM
If balance is > 0, continue
Else, display "Recharge Required"
➡️ Relay is Turned ON
Power flows to load (e.g., fan, bulb)
➡️ Energy Meter Sends Pulses to Arduino
Based on power consumption
➡️ Arduino Calculates Units Consumed
1 pulse = 1 unit (based on meter type)
➡️ Deduct Cost per Unit from Balance
Display updated balance on LCD
➡️ If Balance < Minimum Limit
Send SMS alert via GSM: "Low Balance!"
➡️ If Balance = 0
Turn OFF Relay
Display "Power Disconnected"
Send SMS: "Balance Exhausted"
➡️ Wait for Recharge via SMS
Example SMS: #RECHARGE#100
➡️ Arduino Reads SMS
Parse the message, update EEPROM
➡️ Balance Updated
Relay turns ON
Display "Recharge Successful"
End / Loop
---
## 💡 Future Scope
- Integration with a mobile app for online recharge
- IoT-based remote monitoring using Wi-Fi
- Power theft detection feature
- Data logging on a web dashboard
---
