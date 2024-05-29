# BeerBot Temperature Monitor

This project uses an ESP32 microcontroller to monitor temperatures from multiple sensors and display the data on an OLED screen as well as a web interface. The web interface allows for configuration of Wi-Fi settings, InfluxDB integration, and sensor names. Additionally, the system can perform OTA (Over-The-Air) firmware updates and manage EEPROM data.

## Features

- **Temperature Monitoring**: Reads temperatures from up to 4 DS18B20 sensors.
- **OLED Display**: Displays IP address and temperatures in Fahrenheit.
- **Web Interface**: 
  - View live temperature data.
  - Configure Wi-Fi settings.
  - Configure InfluxDB settings for data logging.
  - Update sensor names.
  - Perform OTA firmware updates.
  - Manage EEPROM data.
- **Wi-Fi Configuration**: Auto-connects to the specified Wi-Fi network.
- **OTA Updates**: Supports updating firmware from a URL or manual upload.
- **EEPROM Management**: Allows downloading and uploading of EEPROM data.

## Components

- **ESP32**: The main microcontroller.
- **DS18B20 Sensors**: Up to 4 temperature sensors.
- **SSD1306 OLED Display**: 128x64 display for showing IP address and temperature readings.

## Schematic

### Connections

- **DS18B20 Sensors**:
  - Data pin connected to GPIO 4.
- **SSD1306 OLED Display**:
  - SDA pin connected to GPIO 21.
  - SCL pin connected to GPIO 22.

## Installation

### Prerequisites

- Arduino IDE installed with ESP32 board support.
- Required libraries installed:
  - OneWire
  - DallasTemperature
  - U8g2
  - WiFi
  - WebServer
  - WiFiManager
  - EEPROM
  - HTTPClient
  - Update

### Wiring

1. Connect the DS18B20 sensors to the ESP32:
   - Data pin to GPIO 4.
   - Power and ground to the respective 3.3V and GND pins on the ESP32.
2. Connect the SSD1306 OLED display to the ESP32:
   - SDA to GPIO 21.
   - SCL to GPIO 22.

### Uploading the Code

1. Open the Arduino IDE.
2. Load the provided code into the Arduino IDE.
3. Select the appropriate ESP32 board from the Tools menu.
4. Connect the ESP32 to your computer via USB.
5. Upload the code to the ESP32.

### Configuration

1. On first boot, the ESP32 will start an access point named `ESP32-Config`.
2. Connect to this access point and navigate to `http://192.168.4.1` in your web browser.
3. Follow the prompts to connect the ESP32 to your Wi-Fi network.

## Usage

### Web Interface

- **Home**: View live temperature readings and sensor names.
- **WiFi**: Configure Wi-Fi settings, including SSID, password, static IP, gateway, and subnet mask.
- **InfluxDB**: Configure InfluxDB server, database, username, and password for logging temperature data.
- **Sensor Names**: Update the names of the connected sensors.
- **System**: View system information, perform OTA updates, manage EEPROM data, and reboot the device.

### OLED Display

- Displays the IP address of the ESP32 and the temperature readings from each sensor in Fahrenheit.

### OTA Updates

- The device can check for updates at a specified URL and apply them automatically.
- Alternatively, firmware can be uploaded manually via the web interface.

## Contributing

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -am 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Create a new Pull Request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Thanks to the developers of the libraries used in this project.
- Inspired by the need to monitor temperatures in a home brewing setup.
