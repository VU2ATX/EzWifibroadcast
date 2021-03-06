## Welcome to the EZ-WifiBroadcast wiki!  
**Please read through this page and other sub-pages before you start asking questions on the forum.**

### Download
These are direct download links to images.


Release candidate: v1.6RC6 [EZ-Wifibroadcast-1.6RC6.zip on Google Drive](https://drive.google.com/open?id=1OgKU4dQoQWsV4T4tVOjq_XM0VrXMXaxs) or [from mirror on Freehoster (beware of ads)](https://www.file-upload.net/en/download-13063079/EZ-Wifibroadcast-1.6RC6.zip.html)

Release candidate: v1.6RC5 [EZ-Wifibroadcast-1.6RC5.zip on Google Drive](https://drive.google.com/file/d/18Q9vlwughGxd8plWHXzevAyhqgZdQ7SA/view?usp=sharing) or [from mirror on Freehoster (beware of ads)](https://www.file-upload.net/en/en/download-12976556/EZ-WifiBroadcast-1.6RC5.zip.html)

Release candidate: v1.6RC4 [EZ-Wifibroadcast-1.6RC4.zip on Google Drive](https://drive.google.com/open?id=1jg-V4uSFQtPljdrRjgkrIdidkTj8kHjm) or [from mirror on Freehoster (beware of ads)](https://en.file-upload.net/en/en/download-12976560/EZ-Wifibroadcast-1.6RC4.zip.html)

Release candidate: v1.6RC3 [EZ-Wifibroadcast-1.6RC3.zip on Google Drive](https://drive.google.com/open?id=1gcVUFHVF88LHg6KTvCBZtw5CV_btmbFg) or [from mirror on Freehoster (beware of ads)](https://www.file-upload.net/en/download-12889765/EZ-Wifibroadcast-1.6RC3.zip.html)

Release candidate: v1.6RC2 [EZ-Wifibroadcast-1.6RC2.zip on Google Drive](https://drive.google.com/uc?id=0B8ke2EKPqvORa1dhdGJQM3pfR28&export=download) or [from mirror on Freehoster (beware of ads)](https://en.file-upload.net/download-12774875/EZ-Wifibroadcast-1.6RC2.zip.html)

Release candidate: v1.6RC1 [ez16rc1.zip on Freehoster](https://en.file-upload.net/download-12769426/ez16rc1.zip.html)

Stable version: v1.5 [EZ-Wifibroadcast-1.5.zip on Gdrive](https://drive.google.com/uc?id=0B8ke2EKPqvORdDNkSTdwNDZQZnc&export=download) or [from mirror](https://1drv.ms/u/s!AICL89CL69nXhpsK)

Stable version: v1.4 [EZ-Wifibroadcast-1.4.zip](https://drive.google.com/open?id=0BxyIDQpjwq9YWk9mLWR1b0JENDg) or [from mirror](https://drive.google.com/uc?id=0B8ke2EKPqvORR0lXVGptSEhwOU0&export=download)

BETA version: v1.3 [EZ-Wifibroadcast-1.3beta.zip](https://docs.google.com/uc?id=0B8ke2EKPqvORazlSb3hxS0hOOTA&export=download)

Stable version: v1.2 [EZ-wifibroadcast-1.2.zip](https://drive.google.com/uc?id=0B8ke2EKPqvORRmdUenJ0WmtFc1U&export=download)

Stable version: v1.0 [ez-wifibroadcast-1.0.zip](https://docs.google.com/uc?id=0B8ke2EKPqvORQU5RYi1EbEpQMUE&export=download)


### Installation / Setup
- _**IMPORTANT: Read and follow the [wiring instructions](https://github.com/bortek/EZ-WifiBroadcast/wiki/Wiring)**_
- Download the sdcard image and unzip it
- Write it onto two (minimum 2GB) SD cards. One for transmitter Pi and another for Receiver Pi. See instructions on [this page](https://www.raspberrypi.org/documentation/installation/installing-images/) on how to write .img files on SD cards. Pi with the camera connected will act as a Tx an pi without camera will act as Rx. 
- Insert each SD card into each Raspberry Pi and boot them up.
- _**AGAIN: Read and follow the [wiring instructions](https://github.com/bortek/EZ-WifiBroadcast/wiki/Wiring)**_

### Configuration
- Put SD Card in Windows computer or anything that has a text editor (Tablet, Smartphone), edit wifibroadcast-1.txt and change frequency (`FREQ=`) to your needs.
- Do not change anything else for first tests
- If everything runs as intended, change configuration options in wifibroadcast-1.txt, osdconfig.txt and apconfig.txt
- See under [configuration options](https://github.com/bortek/EZ-WifiBroadcast/wiki/Configuration-options) and the [How-To section](https://github.com/bortek/EZ-WifiBroadcast/wiki/How-to's) for more info


### Features
(applicable to the latest release)
- Supports Pi A+, Pi1B+, Pi2B, Pi3B (NOT the new Pi3B+), Pi Zero, Pi Zero W, Odroid-W, Pi V1 and V2 cam (NOTE: RX Pi needs to be atleast a Pi2)
- max. possible resolutions (depending on cam used):
1280x720p 60fps
1296x972p 42fps
1640x922p 40fps
1920x1080p 30fps
- max. possible video bitrate about 12Mbit
- Latency ~125ms with 720p 48fps default settings, minimum possible latency roughly around 110ms
- Support for 2.3/2.4/2.5Ghz bands and 5.2Ghz to 5.8Ghz bands
- 2.4Ghz on 3dbi omni antennas: About 1-1.5km range with ~70mw wifi sticks, about 2-3km with ~300mW high-power cards (with default settings, about 50% higher range is possible with lower bitrate "longrange mode")
- 5Ghz on 3dbi omni antennas: ~250m range with 25mW wifi sticks, about 1km range with ~300mW high-power cards
- Configuration can be done from Windows, no Linux knowledge required
- Supports different configuration profiles selectable on the field via jumpers or DIP switches
- Forwarding of video stream and telemetry data to 2nd display via: USB Tethering, Wifi Hotspot, Ethernet, Wifibroadcast relay mode
- Bi-directional mavlink telemetry support (uplink not 100% compatible with all FCs yet)
- Support for video and telemetry inside Tower App, QGroundcontrol, Mission Planner
- Fully dynamic and automatic detection of 2nd display, just plug it in or connect via Hotspot and it'll work
- 2 wifi sticks transmit diversity on two different frequencies for bulletproof videolink
- 3 wifi sticks receive diversity support for Atheros, 5 wifi sticks receive diversity support for Ralink (or 2x Atheros and 2x Ralink)
- Integrated high resolution fully customizeable OSD with support for Mavlink, Frsky, LTM, Smartport telemetry
- .AVI Ground recording, PNG screenshots and telemetry data automatically saved to USB stick
- Automatic graphing of RSSI, packetloss, video bitrate and other data
- Quick startup, about 10 seconds until video is shown
- No issues as with standard wifi, no disconnection, video freeze etc, video will quickly recover
- Live and responsive RSSI display with defective blocks and packetloss display
- Handling similar to analog gear, just switch on and fly
- Smooth and stutter-free video (thanks, mmormota)
- Video reception is very stable even in difficult multipathing environments, no constant glitching as with analog
- OSD overlay rendered on the receiver will stay clear and functional even if video is too bad to fly
- SD card reliability and general robustness tweaks (read-only filesystem, syslogging to SD disabled, etc.)
- Debug logs and screenshot will be saved to sdcard in case of errors
- Low-latency/high update-rate RC over wifibroadcast via Joystick (Atheros only)


### Wifi cards and dongles
There is a list of Wifi cards and dongles on [this Wiki page](https://github.com/bortek/EZ-WifiBroadcast/wiki/List-of-Wifi-cards-and-doungles)

### Screens/Monitor
Virtually any screen/monitor connected to the HDMI port on your Pi will work. Besides that the following displays have been successfully tested:
 - Samsung 32 inch TV connected via HDMI to Pi.
 - Pi Official Screen connected to CSI port on your Pi. Resolution 800x480.
 - An LCD module from old 17 inch laptop with eBay driver [(for example this)](http://www.ebay.com/itm/HDMI-VGA-2AV-Lcd-controller-Board-VS-TY2662-V1-for-LCD-panel-Only-driver-board-/181596796562?hash=item2a48033692:g:TGEAAOSwQJhUdwFZ) using 1920x1080 to HDMI on Pi. Default FPS.
 - Goggles One (1920x1080) (set to fixed 1920x1080 resolution in config.txt!)
 - Headplay HD (1280x800)
 - Fatshark Base HD (1280x720)
 - Fatshark HDO (960x720)
 - Fatshark HD1/2/3 (800x600) (set to fixed 800x600 resolution in config.txt!)
 - Yuneec Skyview
 - Zeiss Cinemizer OLED

Please note that the monitor has to be connected and powered before the Pi is powered because the auto-detection only works at start-up. You can define your (custom) monitor resolution in config.txt statically though to be able to connect the monitor after the Pi is already running.

### Tested Raspberry Pi Hardware
- Pi1 B+, Pi 1A+, Pi2 B, Pi3 B, Pi Zero 1.3, Pi Zero W, Odroid-W
- Official Pi V1 Cam ("V1.3" on the PCB), official Pi V2 Cam ("V2.1" on the PCB)

Take a look [at the pictures](https://github.com/bortek/EZ-WifiBroadcast/wiki/Pictures) of the hardware and their weights.

### Notes
TX: The CPUs on the Raspberry Pi 1 and Pi Zero are around 75% maxxed out with standard settings (6Mbit bitrate, 8/4/1024 FEC). Two TX dongles and bitrates above about 9Mbit/s (depending on FEC settings etc.) will not be possible.

RX: Raspberry Pi1 and Pi Zero are not supported anymore from version 1.3 on. Use a Pi2 or Pi3.