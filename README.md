# BeerBot Temperature Monitor (ESPHome Edition)

This project uses an Olimex ESP32-POE-ISO microcontroller running ESPHome to monitor temperatures from multiple DS18B20 sensors and display them on a 128x64 OLED screen. The device connects via Ethernet and exposes all readings natively to Home Assistant. An optional onboard web server allows viewing sensor values directly in a browser. Note this isn't just for beer, it could temp monitor anything really.

## Features

- **Temperature Monitoring**: Reads from up to 4 DS18B20 sensors on a 1-Wire bus (GPIO4).
- **OLED Display**: Displays device name, IP address, and all sensor temperatures in Fahrenheit.
- **Home Assistant Integration**: Native API support for use in automations and dashboards.
- **OTA Updates**: Firmware can be updated via Home Assistant.
- **Ethernet-Based**: Uses ESP32 LAN8720 interface, no Wi-Fi stack required.
- **Web Server**: Optional local web interface on port 80 for raw sensor viewing.

## Components

- **ESP32-POE-ISO**: Main microcontroller with built-in Ethernet. [Olimex ESP32-POE](https://www.mouser.com/ProductDetail/Olimex-Ltd/ESP32-POE-ISO-EA?qs=%252B6g0mu59x7KfK%2FIl1ERS8Q%3D%3D)
- **DS18B20 Sensors**: Up to 4 digital temperature sensors.
- **SSD1306 OLED**: 128x64 I2C display.

## Pin Assignments

| Component        | Pin         |
|------------------|-------------|
| DS18B20 Data     | GPIO4       |
| OLED SDA         | GPIO21      |
| OLED SCL         | GPIO22      |
| Ethernet MDC     | GPIO23      |
| Ethernet MDIO    | GPIO18      |
| Ethernet CLK     | GPIO17 (OUT)|
| Ethernet Power   | GPIO12      |

## Installation

1. Install Home Assistant with the ESPHome Add-on.
2. Use the ESPHome dashboard to add a new device with the following configuration:
   - Encryption Key
   - OTA Key
3. Flash via USB initially; future updates are handled OTA.

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
- Inspired by the need to monitor temperatures in a friends home brewing setup.
