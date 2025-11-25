# Power-Consumption-Safety-Monitoring-System
Design an loT-based Power Consumption and Safety Monitoring System using Raspberry Pi Pico for real-time tracking of electrical usage. Also help detect fire hazards due to short circuits. Ensure remote reporting, and quick response to hazards.
# Scope of the Solution
Measure electrical power usage using the INA219 sensor and monitor safety parameters such as flame detection and short-circuit indicators. Display real-time voltage, current, and power readings on the Serial monitor. Trigger buzzer and LED alerts when abnormal conditions or fire hazards are detected. Send all sensor data to ThingSpeak for remote visualization and continuous data logging. Access the online dashboard remotely for campus-wide electrical safety monitoring and early hazard detection.
# Hardware Requirements :
- NodeMCU ESP8266
- INA219 current & voltage sensor
- Flame sensor
- Buzzer
- LED (used as load)
- 5V power supply

# Software Requirements:
- Arduino IDE
- ESP8266 board package
- ThingSpeak account
- Required libraries (WiFi, HTTP, INA219)
- 
- # Code Logic Implementation (Power Consumption & Safety Monitoring System)


- Initialization:
The program imports necessary libraries, initializes the INA219 current/voltage sensor, sets up the flame sensor input pin, and configures the LED and buzzer used for safety alerts. WiFi credentials and the ThingSpeak API key are also loaded.
- WiFi Connection:
The system attempts to connect to the configured WiFi network. If connected, it will be able to upload data to ThingSpeak; if not, it will continue monitoring locally.
- Sensor Reading:
The program continuously reads the flame sensor (to detect fire hazards) and retrieves voltage, current, and power measurements from the INA219 sensor for real-time power consumption monitoring.
- Safety Alerts:
Based on readings:
If flame is detected → buzzer turns ON and LED indicates a hazard.
If no flame is detected → buzzer and LED remain in their normal state.
(This provides immediate local safety response.)
- Cloud Upload (ThingSpeak):
Every 15 seconds, if WiFi is connected, the system uploads the current, power, voltage, and flame status to ThingSpeak, allowing remote monitoring and logging of power usage and safety events.
- Continuous Loop:
The device repeatedly performs the cycle of:
read sensors → check safety → update LED/buzzer → upload to ThingSpeak (if time) → repeat, providing real-time power tracking and fire-hazard monitoring.
