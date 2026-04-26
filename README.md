# SiFi View

SiFi View is the official desktop GUI for SiFi Labs biosensors. It provides a graphical user interface to scan, connect, configure, stream, visualize, and record biosignals from [BioPoint](https://sifilabs.com/product/biopoint/) and [SiFi Band](https://sifilabs.com/product/sifi-band/) devices.

SiFi View is built on top of [SiFi Bridge](https://github.com/SiFiLabs/sifi-bridge-pub), our cross-platform device communication tool. SiFi View is the recommended entry point for clinicians, researchers, and developers who want to evaluate the hardware and inspect data quality before integrating with their own pipeline.

## About

SiFi View is currently closed-source. The official releases are exposed on this repository in the [Releases](https://github.com/SiFiLabs/sifi-view-pub/releases) tab. This repository is used to host installers, track release notes, and centralize public issues and feedback.

If you are looking to integrate SiFi devices directly into your own software, you should instead look at:

- [SiFi Bridge](https://github.com/SiFiLabs/sifi-bridge-pub) — the underlying CLI/REPL device communication tool.
- [SiFi Bridge Python](https://github.com/SiFiLabs/sifi-bridge-py) — a Python wrapper around SiFi Bridge, also available on [PyPI](https://pypi.org/project/sifi-bridge-py/).

## Supported devices

| Device | Signals |
| --- | --- |
| BioPoint | EMG, ECG, PPG, EDA, IMU (accelerometer, gyroscope, quaternions), temperature |
| SiFi Band | EMG (8 channels), ECG, PPG, IMU (accelerometer, gyroscope, quaternions), temperature |

The exact set of available channels depends on the device firmware version. SiFi View detects the connected device and exposes only the modalities supported by that firmware.

## Installation

Download the installer for your platform from the latest [release](https://github.com/SiFiLabs/sifi-view-pub/releases/latest). BLE 5.x+ is required to connect to the devices.

### Windows
- Download the `.msi` (or `.exe`) installer.
- Run it and follow the prompts.

### macOS
- Download the `.dmg` matching your architecture (Apple Silicon or Intel).
- Open the disk image and drag SiFi View into your `Applications` folder.
- At first launch, you may see a popup stating that the developer cannot be verified. Right-click the application and select `Open` to bypass the warning, or allow it from `System Settings > Privacy & Security`.
- Grant Bluetooth permission when prompted.

### Linux
- Download the `.AppImage` (portable) or the `.deb` package.
- For the AppImage: `chmod +x SiFi-View-*.AppImage` and run it.
- For the .deb: `sudo apt install ./sifi-view_*.deb`.

## Getting started

1. Power on your BioPoint or SiFi Band.
2. Launch SiFi View.
3. Click `Scan` in the upper right corner to list nearby SiFi devices.
4. Select your device and click `Connect`.
5. Choose the signals you want to stream and start recording.

Recordings can be exported as HDF5 or CSV for offline analysis. For more advanced use cases (LSL streaming, UDP forwarding, custom Lua plugins, multi-device acquisition), use [SiFi Bridge](https://github.com/SiFiLabs/sifi-bridge-pub) directly.

## Known limitations

- Some Bluetooth adapters have known throughput issues with SiFi devices, in particular older Intel-based dongles. A short USB extension cable away from interference sources usually helps.
- M2/M3-based Macs may show lower BLE throughput than expected, leading to occasional dropped samples. This is a system-level limitation that affects all BLE peripherals.
- Some computers exhibit high latency when restarting the application. Toggling Bluetooth off and on resolves it.

## Issues and feedback

Bug reports and feature requests are very welcome. Please open an [issue](https://github.com/SiFiLabs/sifi-view-pub/issues) with:

- Your operating system and version.
- Your SiFi View version (visible in `Help > About`).
- The device model and firmware version.
- A clear description of the problem and steps to reproduce it.

For commercial support, partnerships, or hardware orders, please reach out to [contact@sifilabs.com](mailto:contact@sifilabs.com).

## License

SiFi View is distributed under a proprietary license. Use of the software is governed by the End User License Agreement bundled with the installer. The contents of this repository (release artifacts, documentation, and changelog) are made available for distribution purposes only.

© SiFi Labs Inc.
