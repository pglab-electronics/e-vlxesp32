# E-VLXESP32

<p align="center">
  <picture>
    <img width="1024" alt="E-VLXESP32" src="https://pglab-electronics.github.io/e-vlxesp32/evlxesp32.png" />
  </picture>
</p>

**E-VLXESP32** is an ESP32-based electronics module by **PG LAB Electronics** designed to control **VELUX®** motorized skylight windows using original **VELUX®** wall remotes.

## About

The **E-VLXESP32** is a compact electronics module featuring an integrated **temperature and humidity sensor**.

It connects to battery-powered **VELUX® wall remote controls** (models **KLI311, KLI312, KLI313**) and allows you to control **VELUX® motorized skylight windows** over your **local Wi-Fi network**.

This repository contains **ESPHome YAML configuration files** used to build and customize E-VLXESP32 firmware.

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

## Getting Started

### Requirements
- ESPHome installed
- E-VLXESP32 hardware module
- Supported VELUX® remote (KLI311, KLI312, KLI313)

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/your-repo/e-vlxesp32.git
   
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

### Pairing

Follow the standard **VELUX®** remote pairing procedure to link the remote (KLI311, KLI312, KLI313) with your window before using the **E-VLXESP32**.

## Repository Structure

- `evlxesp32.yaml` – Main ESPHome configuration
- `secrets.yaml` – Wi-Fi credentials, passwords, and keys
- `firmware` - Build of the last firmware

## Hardware

| Component | Description |
|-----------|-------------|
| MCU | ESP32-C3 (ESP32-C3-WROOM-02-N4) |
| Ambient Sensor | HDC1080 |
| Pogo Pins | for KLI311,KLI312, KLI313 connection |
| Programming Port | USB-C |
| AC-DC Module | IRM-01-5 |
| Power Input | 220AC, 60Hz screw terminal |


## Pinout

| GPIO | Function | Direction |
|------|----------|-----------|
| GPIO3 | I2C SDA | Input/Output |
| GPIO2 | I2C SCL | Output |
| GPIO1 | POGO PIN DOWN (shutter) | Output |
| GPIO7 | POGO PIN STOP (shutter)| Output |
| GPIO5 | POGO PIN UP (shutter)| Output |
| GPI10 | USER LED GREEN| Output |
| GPIO4 | POGO PIN UP (binary sensor) | Input |
| GPIO6 | POGO PIN STOP (binary sensor)| Input |
| GPIO0 | POGO PIN DOWN (binary sensor)| Input |

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

