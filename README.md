# Micro Deck Firmware Releases

This public repository distributes signed firmware binaries and OTA manifests for the Micro Deck ESP32-C3 device.

## What is published here

- Firmware binary assets attached to GitHub Releases
- A signed `manifest.txt` used by the device's updater

Project source code and the Windows editor source are not published in this repository.

## Update security

Each manifest is signed with the project's ECDSA P-256 release key. The ESP32 firmware embeds only the public key and verifies the manifest signature, device target, firmware version, image size, release URL, and SHA-256 digest before finalizing an OTA update.

OTA is user-triggered from the Micro Deck Windows application. Wi-Fi is not used during normal BLE macro operation. USB flashing remains the recovery path.

## Device compatibility

- Target: ESP32-C3
- Flash layout: custom 4 MB partition table with two 1.5 MiB OTA app slots and 896 KiB LittleFS
- USB serial build option: `CDCOnBoot=cdc`
- Do not use Erase All Flash for normal updates.
