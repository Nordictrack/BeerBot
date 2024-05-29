# BeerBot
ESP32 Based Dynamic Beer Monitoring 

This is a simple Temperature monitoring system for a home tap. Could be used for more than beer to be honest. Datacenter applications are very real here.


Hardware:
- ESP32
- SSD1306 OLED Display
- DS18B20 Temperature Sensor Kit

Current code includes:
- OLED with sensor readings
- Dynamic tempature sensor allocation
  - I don't know the limit, but I wouldn't bog it down lol.
- WiFi Setup w/ Static IP handling via WebGUI
- Web portal sensor readings with configuration
  - Ability to post to InfluxDB
  - Ability to rename all sensors
  - Ability to back-up EEPROM and upload EEPROM

Work in progress:
- OTA updates
- SSL Webpage
- Proper secrets hashing
