# ripple
Arduino Firmware for Ripple LoRa mesh

## Pre-requisites

You will need to install the Arduino IDE and add support for the following Boards:
 1. Adafruit Feather M0
 2. TTGO WiFi Lora 32, v1 to v2 (ESP32)
 2. Heltech WiFi Lora 32  (ESP32)
 3. Sparkfun Lora Gateway (ESP32)
 4. SParkfun Pro RF
 
Checkout the firmware bin(ary) images to your local machine, and from the command-line, use one of the following command incantations to flash the firmware to your board:

# Ver 2 firmware builds (with 'commander' app support)

## Adafruit Feather M0

### Repeater OR Messenger - 433 to 915MHz (configurable),  (USB-OTG only)

~/Library/Arduino15/packages/arduino/tools/bossac/1.7.0/bossac -i -d --port=cu.usbmodem14101 -U true -i -e -w -v Ripple-USB.Feather_m0.bin -R 

### GPS Tracker Node - Adafruit Feather M0 - 433 to 915MHz (configurable),  (only USB-OTG supported)

~/Library/Arduino15/packages/arduino/tools/bossac/1.7.0/bossac -i -d --port=cu.usbmodem14101 -U true -i -e -w -v RippleTracker-915-USB.feather_m0.bin -R 

### Sensor Node - Adafruit Feather M0 - 433 to 915MHz (configurable),  (only USB-OTG supported)

~/Library/Arduino15/packages/arduino/tools/bossac/1.7.0/bossac -i -d --port=cu.usbmodem14101 -U true -i -e -w -v RippleSensor-915-USB.feather_m0.bin -R 


## Sparkfun Pro RF

### Repeater OR Messenger - 433 to 915MHz (configurable),  (USB-OTG only)

~/Library/Arduino15/packages/arduino/tools/bossac/1.7.0-arduino3/bossac -i -d --port=cu.usbmodem14101 -U true -i -e -w -v Ripple-USB-Sparkfun-Pro.bin -R 


## TTGO/Heltech V1 boards

### Repeater OR Messenger - 433 to 915MHz (configurable),  (USB-OTG only)

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.4/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.4/tools/sdk/bin/bootloader_dio_80m.bin 0x10000 Ripple-USB.TTGO-V1.bin 0x8000 Ripple-USB.TTGO-V1.partitions.bin 

### Messenger - 433 to 915MHz (configurable),  (Bluetooth LE)

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.4/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.4/tools/sdk/bin/bootloader_dio_80m.bin 0x10000 Ripple-BLE.TTGO-V1.bin 0x8000 Ripple-BLE.TTGO-V1.partitions.bin 


## Heltech V2 boards

### Repeater OR Messenger - 433 to 915MHz (configurable),  (USB-OTG only)

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/sdk/bin/bootloader_qio_80m.bin 0x10000 Ripple-USB-heltech_v2.bin 0x8000 Ripple-USB-heltech_v2.partitions.bin

### Messenger - 433 to 915MHz (configurable),  (Bluetooth LE)

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.4/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.4/tools/sdk/bin/bootloader_qio_80m.bin 0x10000 Ripple-BLE.Heltech-v2.bin 0x8000 Ripple-BLE.Heltech-v2.partitions.bin

### Messenger - 433 to 915MHz (configurable),  (Bluetooth Classic)

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.4/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.4/tools/sdk/bin/bootloader_qio_80m.bin 0x10000 Ripple-915-Bluetooth.heltec_v2_wifi_lora_32.bin 0x8000 Ripple-915-Bluetooth.heltech_v2.partitions.bin


## Sparkfun Lora Gateway

### Repeater OR Messenger - 433 to 915MHz (configurable),  (USB-OTG only)

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/sdk/bin/bootloader_dio_80m.bin 0x10000 Ripple-USB-Sparkfun.bin 0x8000 Ripple-USB-Sparkfun.partitions.bin 

### Messenger - 433 to 915MHz (configurable),  (Bluetooth Classic)

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/sdk/bin/bootloader_qio_80m.bin 0x10000 Ripple-Bluetooth.Sparkfun.bin 0x8000 Ripple-Bluetooth.Sparkfun.partitions.bin 


## TTGO V1.6 to V2.1 boards

### Messenger - 433 to 915MHz (configurable),  (Bluetooth Classic)

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.4/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.4/tools/sdk/bin/bootloader_dio_80m.bin 0x10000 Ripple-Bluetooth.TTGOV2.bin 0x8000 Ripple-Bluetooth.TTGOV2.partitions.bin 

### Messenger - 433 to 915MHz (configurable),  (Bluetooth LE)

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.4/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.4/tools/sdk/bin/bootloader_dio_80m.bin 0x10000 Ripple-BLE.TTGOV2.bin 0x8000 Ripple-BLE.TTGOV2.partitions.bin 

### GeoPager Node - 433 to 915MHz (configurable), (only USB-OTG supported)

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.4/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.4/tools/sdk/bin/bootloader_dio_80m.bin 0x10000 Ripple-GeoPager-TTGOV2.bin 0x8000 Ripple-GeoPager-TTGOV2.partitions.bin 


# Ver 1 firmware builds (no longer supported)

## TTGO ESP32 LORA - 868MHz, for USB-OTG with handset

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 40m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/sdk/bin/bootloader_qio_40m.bin 0x10000 Ripple-868-USB.heltec_wifi_lora_32.bin 0x8000 Ripple-868-USB.partitions.bin 


## TTGO ESP32 LORA - 915MHz, for USB-OTG with handset

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 40m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/sdk/bin/bootloader_qio_40m.bin 0x10000 Ripple-915-USB.heltec_wifi_lora_32.bin 0x8000 Ripple-915-USB.partitions.bin 


## TTGO ESP32 LORA - 915MHz, for Bluetooth Classic with handset

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 40m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/sdk/bin/bootloader_qio_40m.bin 0x10000 Ripple-915-Bluetooth.heltec_wifi_lora_32.bin 0x8000 Ripple-915-Bluetooth.partitions.bin 


## Heltech ESP32 LORA V2 - 433MHz, for USB-OTH with handset

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.ESP32test-ESP32SPP --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/sdk/bin/bootloader_qio_80m.bin 0x10000 Ripple-433-USB.heltec_v2.bin 0x8000 Ripple-433-USB.partitions.bin 

## Heltech ESP32 LORA V2 - 433MHz, for Bluetooth Classic with handset

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.ESP32test-ESP32SPP --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/sdk/bin/bootloader_qio_80m.bin 0x10000 Ripple-433-Bluetooth.heltec_v2.bin 0x8000 Ripple-433-Bluetooth.partitions.bin 


# Experimental builds (still with known issues)

## TTGO ESP32 LORA - 915MHz, for Bluetooth LE with handset

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 40m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/sdk/bin/bootloader_qio_40m.bin 0x10000 Ripple-915-BLE.heltec_wifi_lora_32.bin 0x8000 Ripple-915-BLE.partitions.bin 

## Heltech ESP32 LORA V2 - 915MHz, for USB-OTG with handset

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/sdk/bin/bootloader_qio_80m.bin 0x10000 Ripple-915-USB.heltec_v2.bin 0x8000 Ripple-915-USB.heltech_v2.partitions.bin 

## GPS Tracker Node - TTGO T-Beam - 433 to 915MHz (configurable),  (only USB-OTG supported)

~/Library/Arduino15/packages/esp32/tools/esptool_py/2.6.1/esptool --chip esp32 --port /dev/cu.SLAB_USBtoUART --baud 921600 --before default_reset --after hard_reset write_flash -z --flash_mode dio --flash_freq 80m --flash_size detect 0xe000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/partitions/boot_app0.bin 0x1000 ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.2/tools/sdk/bin/bootloader_dio_80m.bin 0x10000 RippleTracker-915-USB.t-beam.bin 0x8000 RippleTracker-915-USB.t-beam.partitions.bin

