# CAN Sniffer

[![PlatformIO](https://img.shields.io/badge/PlatformIO-Powered-orange?logo=platformio)](https://platformio.org/)
[![ESP32](https://img.shields.io/badge/ESP32-Based-blue?logo=espressif)](https://www.espressif.com/)
<!-- [![License](https://img.shields.io/badge/License-MIT-green)](LICENSE) -->

This project was developed for the course *C++ Programming for Embedded Systems* (EEL7323 — 20252) at UFSC.  
This repository contains the configuration for the PlatformIO IDE (or the PlatformIO VSCode extension) to compile and launch the application.

🔗 **Application repository:**  
[![Application](https://img.shields.io/badge/GitHub-CAN_Sniffer-blue?logo=github)](https://github.com/Rafael-Ramildes-Ferreira/CAN-Sniffer)

## Development Status
<!-- ![Version 0.5](https://img.shields.io/badge/Version-v0,5,0-blue?logo=gin) -->
![Version 0.5](https://img.shields.io/static/v1?label=Version&message=v0.5&color=blue?logo=gin
)
This version is for the halfway assignment submission. The classes interface are implemented as planned and code executes in Linux and in ESP32. Bluetooth is fully implemented and working.

### To Do
- Implement the application logic (code of the threads)
- SD card module code
- CAN module code
- Implement tests

## Objective

The goal of this project is to develop a CAN Sniffer using the ESP32 microcontroller.  
The system is responsible for reading frames from the CAN bus and storing them in an organized manner for later analysis, facilitating diagnostics and the development of embedded systems that use CAN communication.  
Additionally, the project aims to implement a modular design, allowing the storage or transmission medium to be replaced without requiring major changes to the code.

## Compilation

PlatformIO handles compilation and the download of all required libraries and the application.
Download the repositiry:

```bash
git clone https://github.com/Rafael-Ramildes-Ferreira/ESP-Core-Sniffer.git
```

Open in PlatformIO IDE or VSCode+PlatformIO extension, and hit build, or upload.

The application is automatically downloaded from the repository and appears at:

```
.pio/libdeps/nodemcu-32s/app
```

## Including libraries and porting for other platforms
The file `platformio.ini` is used to configure the environment. An environment called `nodemcu-32s` is already setup for deployment in ESP NodeMCU-32s. Unnamed envirement includes the libraries required by the application, including the application code. New enviroments and libraries can be configured by simply editing this file.

Other environments for additional boards may be configured as needed.  
Some configurations can be modified through PlatformIO’s menu interface:

```bash
pio run -e <environment_name> -t menuconfig
```

> [!IMPORTANT]
> Bluetooth support must be active, and hardware encryption (Mbed TLS AES) disabled.

The current configuration targets the NodeMCU-32S board.