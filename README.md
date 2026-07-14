# Requirements
- 5V 1-16 Channel Relay
- ESP32-S3 N16R8 (16mb flash 8mb ram)
- DS3231 RTC Module (offline recommended)
- Female to Male Dupont Wires
- ESP32-S3 Expansion board
- Stabe Wifi Connection (opt. if no ds3231)
- 5V 2-5A Power Supply

`Optional`
- 5v UPS (Maintain Internal RTC time without DS3231 or NTP)

# Libraries
- ArduinoJson
- PubSubClient
- RTCLib 1.14.1

# Installation
### ESP32 Win/Linux Drivers
- CH340G: https://sparks.gogo.co.nz/ch340.html
- CP2102: https://www.silabs.com/software-and-tools/usb-to-uart-bridge-vcp-drivers?tab=downloads
- FT232: https://ftdichip.com/wp-content/uploads/2025/03/CDM-v2.12.36.20-Universal-Driver-for-x64-WHQL-Certified.zip
## Flasher
### Android (otg)
- https://play.google.com/store/apps/details?id=io.serialflow.espflash
### Android Termux
- https://github.com/7wp81x/Termux-ESP-Flasher
### Windows
- https://dl.espressif.com/public/flash_download_tool.zip
### Linux
```
esptool --port <PORT> write_flash 0x0 esp32-dump-0x0.bin
```
### Win/Linux Browser
- https://g3gg0.github.io/esp32_flasher/flasher.html
### Download the Firmware and Flash
- https://github.com/xiv3r/esp32s3-16channel-relay-automatic-timer-switch/releases/tag/esp32s3
- Flash Offset
```
esp32s3-dump-0x0.bin: 0x0
```

# Wifi Key
- Wifi Name:`ESP32S3_16CH_Timer_Switch`
- Password:`ESP32-admin`

# Setup
> online
- Go to `192.168.4.1 –> wifi` then connect to your Home Wifi to set rtc time automatically 

> offline
- Go to `192.168.4.1 -> Time` then tap sync browser to set the rtc time 

# Set Country Time
- Go to Time > GMT Offset and place your country gmt offset in seconds
- https://github.com/xiv3r/esp32s3-16channel-relay-automatic-timer-switch/blob/main/gmt-offsets-seconds.md

# Access
- mDNS:`esp32-s3-16ch-timer-switch.local`
- Captive Portal:`Auto redirect`
- Gateway:`192.168.4.1`
- WAN:`192.168.1.123`
- Global:`Enable esp32 s3 Port Forwarding on your router to access anywhere`

# Reset
- Hold BOOT button for 5 seconds

# 16 Channel GPIO Connection
```
16CH   |   ESP32-S3 N16R8
VCC  _____ 5V
IN1  _____ GPIO 4   Relay 1
IN2  _____ GPIO 5   Relay 2
IN3  _____ GPIO 6   Relay 3
IN4  _____ GPIO 7   Relay 4
IN5  _____ GPIO 11  Relay 5
IN6  _____ GPIO 12  Relay 6
IN7  _____ GPIO 13  Relay 7
IN8  _____ GPIO 14  Relay 8
IN9  _____ GPIO 1   Relay 9
IN10 _____ GPIO 2   Relay 10
IN11 _____ GPIO 42  Relay 11
IN12 _____ GPIO 41  Relay 12
IN13 _____ GPIO 47  Relay 13
IN14 _____ GPIO 21  Relay 14
IN15 _____ GPIO 20  Relay 15
IN16 _____ GPIO 19  Relay 16
GND  _____ GND
```

# DS3231 GPIO Connection
```
DS3231  |  ESP32-S3 N16R8 
   SDA  → GPIO 8
   SCL  → GPIO 9
   VCC  → 3.3V
   GND  → GND
```
<img src="https://github.com/xiv3r/esp32s3-16channel-relay-automatic-timer-switch/blob/main/libraries/s3-1.jpg">
<img src="https://github.com/xiv3r/esp32s3-16channel-relay-automatic-timer-switch/blob/main/libraries/s3-2.png">
<img src="https://github.com/xiv3r/esp32s3-16channel-relay-automatic-timer-switch/blob/main/libraries/s3-3.png">
<img src="https://github.com/xiv3r/esp32s3-16channel-relay-automatic-timer-switch/blob/main/libraries/s3-4.png">
<img src="https://github.com/xiv3r/esp32s3-16channel-relay-automatic-timer-switch/blob/main/libraries/s3-5.png">


