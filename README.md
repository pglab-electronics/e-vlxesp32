# E-VLXESP32

<img width="2550" height="1343" alt="evlxesp32_img" src="https://github.com/pglab-electronics/e-vlxesp32/blob/main/evlxesp32.png" />

**E-VLXESP32** is an ESP32-based electronics module by **PG LAB Electronics** designed to control **VELUX®** motorized skylight windows using original **VELUX®** wall remotes.

## About

The **E-VLXESP32** is a compact electronics module featuring an integrated **temperature and humidity sensor**.

It connects to battery-powered **VELUX®** wall remote controls (models **KLI311, KLI312, KLI313**) and allows you to control **VELUX®** motorized skylight windows over your **local Wi-Fi network**.

The E-VLXESP32 is available in two versions:

- Standard Version – Designed to fit standard 501 wall boxes and powered directly from the 220V AC mains supply for permanent installation.
- KIT Version - Powered exclusively via USB-C. This version requires user assembly and a 3D-printed enclosure using the provided design files.

This repository contains the ESPHome YAML configuration files used to build and customize the E-VLXESP32 firmware.

## Features

- Local Wi-Fi control of **VELUX® wall remotes**
- Full window control: open, close, or stop
- Powered by **ESPHome**
- Built-in **temperature** and **humidity** sensor
- No cloud needed
- Snap-fit design, no soldering required
- No batteries required
- Fits standard 501 wall boxes

## How It Works

The device interfaces with supported VELUX® wall remotes using pogo pins that make contact with the remote’s internal control pads. The ESP32 exposes these controls over Wi-Fi using ESPHome, allowing integration with systems like Home Assistant.

## Connect to Wi-Fi

Follow one of the methods below to connect your device to Wi-Fi.

### Method A — Hotspot (easiest, no app required)

1. Open Wi-Fi settings on your phone or computer.
2. Connect to the network “E-VLXESP32 Hotspot”.
3. A captive portal page should open automatically.
   If it doesn’t, open your browser and go to 192.168.4.1.
4. Enter your Wi-Fi name and password.
5. The device will connect, and the hotspot will disappear.

### Method B — Bluetooth via Home Assistant app

1. pen the Home Assistant mobile app (iOS or Android).
2. Go to Settings → Devices & Services.
3. Look for a “Discovered” banner at the top.
   If you don’t see it, make sure Bluetooth is enabled.
4. Tap E-VLXESP32 and follow the steps to enter your Wi-Fi credentials.

### Method C — USB-C serial

1. Connect the device to your computer using a USB-C cable.
2. Open the ESPHome dashboard.
3. Follow the prompts to provision the device via serial.

## Getting Started

If you want to flash the firmware directly from your computer and configure your Wi-Fi credentials and passwords.

### Requirements
- ESPHome installed
- E-VLXESP32 hardware module
- Supported VELUX® remote (KLI311, KLI312, KLI313)

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/pglab-electronics/e-vlxesp32.git
   
2. Open the YAML configuration in ESPHome

3. Update:
   - Wi-Fi credentials
   - Device name
   - Home Assistant API Encryption Key
   - Over The Air update Password
   - Optional sensor settings

4. Flash to the ESP32:
   ```bash
   esphome run evlxesp32.yaml

## Pairing

Before snap-fitting the E-VLXESP32, make sure you can operate your skylight window. Follow the standard **VELUX®** remote pairing procedure to link your remote (KLI311, KLI312, or KLI313) with the window before using the E-VLXESP32.

## Repository Structure

- `evlxesp32.yaml` – Main ESPHome configuration
- `secrets.yaml` – Wi-Fi credentials, passwords, and keys
- `firmware` - Build of the last firmware
  - `firmware.factory.bin` - Firmware ready to flash at offset 0x0
  - `firmware.ota.bin` - Firmware for over the air update
  - `firmware.md5` - Firmware md5 hash
- `stl` - 3D enclosure model

## Hardware

STANDARD VERSION

| Component | Description |
| ----------- | ------------- |
| MCU | ESP32-C3 (ESP32-C3-WROOM-02-N4) |
| Ambient Sensor | HDC1080 |
| Pogo Pins | for KLI311,KLI312, KLI313 connection |
| Programming Port | USB-C |
| AC-DC Module (*) | IRM-01-5 |
| Power Input (*) | 220AC, 60Hz screw terminal |
| Power Input USB (**) | 5 VDC, From USB-C port |
| Power Consumption (**) | 50 mA |

(*) Only for STANDARD VERSION

(**) Only for KIT VERSION

## Pinout

| GPIO | Function | Direction |
| ------ | ---------- | ----------- |
| GPIO3 | I2C SDA | Input/Output |
| GPIO2 | I2C SCL | Output |
| GPIO1 | POGO PIN DOWN (shutter) | Output |
| GPIO7 | POGO PIN STOP (shutter) | Output |
| GPIO5 | POGO PIN UP (shutter) | Output |
| GPI10 | USER LED GREEN | Output |
| GPIO4 | POGO PIN UP (binary sensor) | Input |
| GPIO6 | POGO PIN STOP (binary sensor) | Input |
| GPIO0 | POGO PIN DOWN (binary sensor) | Input |

## 3D Printing Guidelines KIT

For best results, print the kit version enclosure using **PETG** filament with a **0.2 mm** layer height and **30%** infill. **PETG** is recommended for its slight flexibility and durability, 
which helps achieve a reliable snap-fit assembly and long-term mechanical stability.

Supports are required for all parts to guarantee clean overhangs and a precise final geometry, ensuring the enclosure can snap-fit properly with the **VELUX®** remote cover.

The model is designed with tight tolerances for a precise fit. Depending on your printer calibration, you may need to slightly scale the enclosure up or down if the fit is too tight or too loose.

If the fit is too tight, avoid forcing the **VELUX®** cover onto the enclosure, as excessive pressure may damage or break the snap-fit mechanism.

## License

This project is licensed under the GNU GENERAL PUBLIC LICENSE 3.0 — see [LICENSE](LICENSE) for details.

The ESPHome configuration is open source and free to modify.

## Safety

⚠️ Ensure power is disconnected before installing the module. Incorrect installation may damage the device or connected equipment.

## Disclaimer

The **E-VLXESP32** is an independent third-party product developed and manufactured by PG LAB Electronics S.R.L.S. It is not affiliated with, endorsed by, or sponsored by VELUX A/S or any of its subsidiaries or affiliates.
**VELUX®** is a registered trademark of its respective owner. All references to VELUX® products, including compatible remote control models, are made solely for the purpose of indicating compatibility.
Compatibility is limited to specifically listed **VELUX®** remote control models (**KLI311, KLI312, KLI313**). We do not guarantee compatibility with any other devices or future product revisions.
This product is intended for installation by individuals with appropriate technical knowledge. Improper installation or use may result in damage to equipment or personal injury. The manufacturer assumes no liability for damages arising from incorrect installation or misuse.
By using this product, you acknowledge and accept these terms.