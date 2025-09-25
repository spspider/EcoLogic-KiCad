# EcoLogic KiCad - ESP8266 Home Automation PCB

A professional-grade KiCad project for ESP8266-based home automation systems, designed for JLCPCB manufacturing and Home Assistant integration.

## 📋 Project Overview

This repository contains complete PCB designs for IoT home automation controllers using ESP8266 microcontrollers. The boards are optimized for controlling lights, home appliances, and other smart devices through Home Assistant.

### Key Features
- ESP8266-based design for WiFi connectivity
- Multiple relay outputs for appliance control
- JLCPCB-ready manufacturing files
- Home Assistant compatible
- Professional PCB layout with proper isolation
- SMD components for compact design

## 🖼️ Board Images

| Schematic | PCB Layout |
|-----------|------------|
| ![Schematic](IoTmanager/images/scheme.png) | ![PCB Top](IoTmanager/images/plate.png) |
| ![Schematic v2](IoTmanager/images/scheme2.png) | ![PCB Bottom](IoTmanager/images/plate2.png) |

## 📁 Repository Structure

```
EcoLogic-KiCad/
├── IoTmanager/                    # Main project directory
│   ├── BOM-CPL/                   # Bill of Materials & Component Placement
│   │   ├── BOM.csv               # JLCPCB Bill of Materials
│   │   ├── CPL.xlsx              # Component Placement List
│   │   └── *.csv                 # Position files
│   ├── gerber/                    # Manufacturing files
│   │   ├── gerber.zip            # Complete gerber package
│   │   ├── *.gbr                 # Individual gerber layers
│   │   └── *.drl                 # Drill files
│   ├── images/                    # PCB and schematic images
│   ├── LCPCB/                     # JLCPCB templates
│   └── *.kicad_*                 # KiCad project files
└── README.md                      # This file
```

## 🔧 Bill of Materials (BOM)

| Reference | Component | Quantity | Description |
|-----------|-----------|----------|-------------|
| U2 | ESP-12F | 1 | ESP8266 WiFi Module |
| U6 | AMS1117-3.3 | 1 | 3.3V Voltage Regulator |
| U12 | AMS1117-5.0 | 1 | 5.0V Voltage Regulator |
| U3 | DHT11 | 1 | Temperature & Humidity Sensor |
| U7 | DS18B20 | 1 | Temperature Sensor |
| U5 | PJ-320A | 1 | Audio Jack Connector |
| Q1,Q3,Q5,Q7 | MMBT5401 | 4 | PNP Transistors |
| Q2,Q4,Q6,Q8 | MMBT5551-npn | 4 | NPN Transistors |
| K3,K5,K6,K7 | ZC32F-012-HS3 | 4 | 12V Relays |
| D1 | LD271 | 1 | LED Indicator |
| D2,D3,D4,D5 | 1N4148 | 4 | Switching Diodes |
| C1,C2 | 1000µF | 2 | Polarized Capacitors |
| C4 | 10µF | 1 | Polarized Capacitor |
| C3 | 100nF | 1 | Ceramic Capacitor |
| R1,R5,R8,R11,R16 | 100Ω | 5 | Current Limiting Resistors |
| R3,R4,R12,R14-R19 | 1kΩ | 10 | Base Resistors |
| R2,R6,R9,R10,R13 | 10kΩ | 8 | Pull-up Resistors |
| R7 | 4.7kΩ | 1 | Pull-up Resistor |
| 33R1 | 33Ω | 1 | Current Limiting Resistor |
| J1 | Power Relay | 1 | Main Power Connector |
| J2,J3 | 12-Pin Connector | 2 | I/O Connectors |
| J4 | Flash Connector | 1 | Programming Interface |
| J5 | Reset Button | 1 | System Reset |
| SW1 | Push Button | 1 | 6mm Tactile Switch |
| Jumper-d5,d6,d7 | Jumpers | 3 | Configuration Jumpers |


## 🏭 JLCPCB Manufacturing Guide

### Step 1: Prepare Files
1. Download the complete `gerber.zip` from `IoTmanager/gerber/`
2. Get BOM file: `IoTmanager/BOM-CPL/BOM.csv`
3. Get CPL file: `IoTmanager/BOM-CPL/CPL.xlsx`

### Step 2: Upload to JLCPCB
1. Go to [JLCPCB.com](https://jlcpcb.com/)
2. Click "Add gerber file" and upload `gerber2.zip`
3. Review PCB specifications:
   - **Layers**: 2
   - **Thickness**: 1.6mm
   - **Color**: Green (recommended)
   - **Surface Finish**: HASL (lead-free)

### Step 3: SMT Assembly (Optional)
1. Enable "SMT Assembly"
2. Upload BOM file (`BOM.csv`)
3. Upload CPL file (`CPL.xlsx`)
4. Review component placement
5. Confirm parts availability

### Step 4: Order
- Minimum quantity: 5 pieces
- Typical lead time: 2-5 days (PCB only)
- SMT assembly adds 3-5 days



## ⚡ Power Requirements

| Parameter | Value | Notes |
|-----------|-------|-------|
| Input Voltage | 5V DC | Via USB or external supply |
| Current Consumption | 80-200mA | Depends on relay states |
| Relay Switching | 10A @ 250V AC | Per relay channel |
| Logic Level | 3.3V | ESP8266 native |


## 🛠️ Assembly Tips

### Soldering Guidelines
- Use lead-free solder (SAC305 recommended)
- Soldering iron: 350°C for SMD components
- Use flux for better joints
- Solder ESP8266 module first

### Testing Procedure
1. **Visual Inspection**: Check for shorts and proper alignment
2. **Power Test**: Apply 5V and measure 3.3V rail
3. **Programming Test**: Upload basic blink sketch
4. **Relay Test**: Verify relay switching with multimeter

## 🚨 Safety Warnings

⚠️ **HIGH VOLTAGE WARNING**
- Relays switch mains voltage (110V/220V AC)
- Always disconnect power before wiring
- Use proper electrical enclosure
- Follow local electrical codes

⚠️ **ESD Precautions**
- Use anti-static wrist strap during assembly
- Store boards in anti-static bags
- Ground yourself before handling

## 📝 Version History

| Version | Date | Changes |
|---------|------|---------|
| v2 | 2025-07 | Improved routing, added protection circuits |
| v1 | 2025-05 | Initial release |

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/improvement`)
3. Commit changes (`git commit -am 'Add improvement'`)
4. Push to branch (`git push origin feature/improvement`)
5. Create Pull Request

## 📄 License

This project is open-source hardware. Feel free to modify and distribute according to your needs.

## 🆘 Support & Donations

If this project helped you, consider supporting the development:

[![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-Support%20Development-orange?style=for-the-badge&logo=buy-me-a-coffee)](https://buymeacoffee.com/ecologic)

**Other ways to support:**
- ⭐ Star this repository
- 🐛 Report bugs and issues
- 💡 Suggest improvements
- 📖 Improve documentation
---

**Made with ❤️ for the Home Automation Community**