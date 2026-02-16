# The Auditor - ESP32 Security Research Tool

A Flipper Zero-inspired security research and penetration testing tool built using ESP32 microcontroller. The Auditor is designed for educational purposes, security research, and authorized penetration testing.

## 🎯 Overview

The Auditor is a portable, ESP32-based multi-protocol security research device that brings together various wireless communication capabilities in a single compact package. Inspired by the Flipper Zero, this project leverages the powerful ESP32 microcontroller to provide a cost-effective alternative for security researchers and hobbyists.

## 🔧 Hardware Components

### Core Components
- **ESP32 Development Board** (ESP32-WROOM-32 or ESP32-S3)
  - Dual-core processor (up to 240 MHz)
  - Integrated WiFi (802.11 b/g/n)
  - Integrated Bluetooth (Classic + BLE)
  - 520 KB SRAM
  - Multiple GPIO pins for expansion

### Additional Modules
- **Display**: OLED display (128x64 or larger) for UI
- **Storage**: MicroSD card module for logging and storage
- **Input**: Buttons/Rotary encoder for navigation
- **Power**: LiPo battery with charging circuit
- **Antenna**: External antenna for improved range (optional)

### Expansion Capabilities
- **NFC Module**: PN532 or RC522 for NFC/RFID operations
- **Sub-GHz Radio**: CC1101 transceiver for additional frequency bands
- **IR Transmitter/Receiver**: For infrared communication
- **GPIO Header**: For custom modules and sensors

## ✨ Features

### WiFi Capabilities
- **Network Scanning**: Scan and identify nearby WiFi networks
- **Packet Monitoring**: Capture and analyze WiFi packets (monitor mode)
- **Deauthentication**: Send deauth frames for security testing
- **Evil Portal**: Create captive portals for security awareness training
- **Beacon Spamming**: Generate multiple fake access points
- **WPS Testing**: Test WiFi Protected Setup vulnerabilities

### Bluetooth/BLE Features
- **BLE Scanner**: Discover and enumerate Bluetooth Low Energy devices
- **Device Tracking**: Monitor BLE device presence and signal strength
- **Advertisement Spoofing**: Create custom BLE advertisements
- **Service Discovery**: Enumerate GATT services and characteristics
- **Classic Bluetooth**: Scan for classic Bluetooth devices

### RFID/NFC Operations
- **Card Reading**: Read various RFID/NFC card types (125kHz, 13.56MHz)
- **Card Emulation**: Emulate common access cards
- **Data Analysis**: Parse and analyze card data
- **Clone Detection**: Identify cloned or duplicated cards

### Infrared Functions
- **IR Learning**: Capture and store IR remote signals
- **IR Replay**: Transmit stored IR commands
- **Universal Remote**: Database of common device protocols

### Additional Tools
- **BadUSB**: Programmable USB HID attack payloads
- **GPIO Control**: Direct control of GPIO pins for testing
- **Serial Console**: UART communication for debugging
- **Data Logging**: Save captured data to SD card
- **Scripting**: Automate tasks with custom scripts

## 🚀 Getting Started

### Prerequisites
- ESP32 development board
- Arduino IDE or PlatformIO
- USB cable for programming
- Required libraries (see Installation)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/zoecyber001/the-auditor.git
   cd the-auditor
   ```

2. **Install Arduino IDE** (if not already installed)
   - Download from [arduino.cc](https://www.arduino.cc/en/software)
   - Install ESP32 board support via Board Manager

3. **Install required libraries**
   ```
   - ESP32 WiFi Library (built-in)
   - Adafruit GFX Library
   - Adafruit SSD1306 (for OLED display)
   - SD Library
   - BLE Library (built-in)
   - IRremote Library
   - MFRC522 (for RFID module)
   ```

4. **Configure settings**
   - Open `config.h` and adjust settings for your hardware
   - Set pin configurations for your specific setup

5. **Upload the code**
   - Connect your ESP32 via USB
   - Select the correct board and port in Arduino IDE
   - Click Upload

### Hardware Setup

1. **Connect the OLED display**
   - SDA → GPIO 21
   - SCL → GPIO 22
   - VCC → 3.3V
   - GND → GND

2. **Add SD card module** (optional)
   - MISO → GPIO 19
   - MOSI → GPIO 23
   - SCK → GPIO 18
   - CS → GPIO 5

3. **Connect buttons for navigation**
   - UP → GPIO 32
   - DOWN → GPIO 33
   - SELECT → GPIO 25
   - BACK → GPIO 26

## 📖 Usage

### Basic Navigation
- Use UP/DOWN buttons to navigate menus
- SELECT button to choose an option
- BACK button to return to previous menu

### WiFi Scanning
1. Navigate to WiFi → Scan
2. View list of discovered networks
3. Select a network for more details
4. Save results to SD card if needed

### Bluetooth Scanning
1. Navigate to Bluetooth → BLE Scan
2. Wait for devices to be discovered
3. View device names, addresses, and RSSI
4. Track specific devices over time

### RFID Operations
1. Connect RFID module (if not built-in)
2. Navigate to RFID → Read
3. Place card near reader
4. View and save card data

## 🏗️ Technical Architecture

### Software Stack
- **Framework**: Arduino/ESP-IDF
- **Core**: FreeRTOS for task management
- **Display**: Adafruit GFX for graphics rendering
- **Storage**: FAT32 filesystem on SD card
- **Networking**: lwIP stack for TCP/IP

### System Design
```
┌─────────────────────────────────────┐
│         User Interface Layer         │
│  (OLED Display + Button Input)      │
└─────────────────────────────────────┘
                 │
┌─────────────────────────────────────┐
│        Application Layer             │
│  (Menu System, Tools, Scripts)      │
└─────────────────────────────────────┘
                 │
┌─────────────────────────────────────┐
│         Protocol Handlers            │
│  (WiFi, BT, NFC, IR, USB)           │
└─────────────────────────────────────┘
                 │
┌─────────────────────────────────────┐
│         Hardware Abstraction         │
│  (ESP32 HAL, Driver Layer)          │
└─────────────────────────────────────┘
```

### Memory Management
- Efficient use of SRAM for real-time operations
- Flash storage for firmware and configurations
- SD card for logs and captured data
- Dynamic allocation for temporary buffers

## 🔒 Security & Legal Notice

**⚠️ IMPORTANT: This tool is designed for educational purposes and authorized security testing only.**

- **Only use on networks and devices you own or have explicit permission to test**
- **Unauthorized access to computer systems is illegal**
- **The developers are not responsible for misuse of this tool**
- **Always comply with local laws and regulations**

This project is intended to:
- Help security researchers understand wireless protocols
- Provide a learning platform for embedded systems
- Assist in authorized penetration testing
- Raise awareness about security vulnerabilities

## 📊 Project Status

### Current Features
- ✅ WiFi scanning and monitoring
- ✅ BLE device discovery
- ✅ Basic OLED display interface
- ✅ SD card logging
- ✅ Deauthentication attacks
- ✅ Beacon frame injection

### In Development
- 🔄 RFID/NFC support
- 🔄 IR remote functionality
- 🔄 BadUSB implementation
- 🔄 Advanced scripting engine
- 🔄 Web interface
- 🔄 Battery management

### Planned Features
- 📋 GPS module support
- 📋 LoRa communication
- 📋 Zigbee protocol support
- 📋 Mobile app companion
- 📋 Cloud sync capabilities
- 📋 Plugin system

## 🛠️ Development

### Building from Source
```bash
# Using PlatformIO
pio run

# Using Arduino IDE
# Open the .ino file and click Upload
```

### Contributing
Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

### Project Structure
```
the-auditor/
├── src/
│   ├── main.cpp           # Main application entry
│   ├── wifi_tools/        # WiFi-related functions
│   ├── ble_tools/         # Bluetooth tools
│   ├── rfid_tools/        # RFID/NFC functions
│   ├── ui/                # User interface code
│   └── utils/             # Utility functions
├── include/
│   └── config.h           # Configuration file
├── lib/                   # External libraries
├── data/                  # Data files (IR codes, etc.)
└── README.md
```

## 📚 Resources

### Documentation
- [ESP32 Documentation](https://docs.espressif.com/projects/esp-idf/)
- [Arduino ESP32 Core](https://github.com/espressif/arduino-esp32)
- [WiFi Protocol Specifications](https://www.wi-fi.org/)

### Learning Resources
- ESP32 Programming Tutorials
- Wireless Security Fundamentals
- RFID Technology Basics
- Bluetooth Low Energy Guide

### Similar Projects
- Flipper Zero
- WiFi Pineapple
- HackRF
- ESP32 Marauder
- WiFi Deauther

## 🤝 Community

### Support
- **Issues**: Report bugs on GitHub Issues
- **Discussions**: Join community discussions
- **Wiki**: Check the wiki for detailed guides

### Contact
- **GitHub**: [@zoecyber001](https://github.com/zoecyber001)
- **Project**: [the-auditor](https://github.com/zoecyber001/the-auditor)

## 📄 License

This project is open-source and available under the MIT License. See the LICENSE file for more details.

## 🙏 Acknowledgments

- Inspired by Flipper Zero and the amazing security research community
- Thanks to Espressif for the powerful ESP32 platform
- Built with contributions from the open-source community

## ⚡ Performance Notes

- **WiFi Range**: Up to 100m (line of sight) with external antenna
- **Battery Life**: 4-8 hours depending on usage
- **Boot Time**: ~2-3 seconds
- **Scan Speed**: ~500ms for WiFi networks, ~2s for BLE devices

## 🔧 Troubleshooting

### Common Issues

**Display not working**
- Check I2C connections (SDA/SCL)
- Verify display address (usually 0x3C or 0x3D)
- Test with I2C scanner sketch

**WiFi features not working**
- Ensure ESP32 supports monitor mode
- Check antenna connection
- Verify firmware version

**SD card not detected**
- Check wiring and connections
- Format SD card as FAT32
- Try a different SD card

**Low battery performance**
- Use quality LiPo battery (>1000mAh)
- Add proper voltage regulation
- Monitor battery voltage

## 🌟 Future Vision

The Auditor aims to become a comprehensive security research platform that combines:
- Multiple wireless protocols in one device
- User-friendly interface for beginners
- Advanced features for professionals
- Extensible architecture for custom tools
- Strong community support and contributions

---

**Built with ❤️ by the security research community**

*Remember: Use responsibly and ethically. Happy researching! 🔐*