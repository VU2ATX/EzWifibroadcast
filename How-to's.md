# Setting up the OSD


## 1. configure general OSD and telemetry parameters in wifibroadcast-1.txt:

- Set `OSD=Y` in wifibroadcast-1.txt (already enabled by default)

- Set the Pi's serial port baudrate to the same baudrate as the serial telemetry data stream coming from the flight control. E.g. `OSD_BAUDRATE=57600` if your flightcontrol sends it's telemetry data using 57600 baud.

- For the onboard Pi serial port leave default `OSD_SERIALPORT=/dev/serial0`, if using an external USB2Serial adapter, set `OSD_SERIALPORT=/dev/ttyUSB0`

- If you want to connect your flight control to the TX Pi, leave `TELEMETRY_INPUT=tx`, if you have some other means of transmitting the telemetry to the ground (e.g. an LRS with telemetry downlink) choose `TELEMETRY_INPUT=rx` to receive the telemetry stream on the ground Pi serial port.

- In case you want to use the OSD included in the Android FP_VR app, also choose the appropriate UDP port to which the telemetry stream will be forwarded by setting e.g. `OSD_UDP_PORT=5002` (See in the FPV_VR settings which port is the right one for your telemetry protocol).



## 2. Configure telemetry protocol and OSD options in osdconfig.txt

- Remove the "//" characters in front of the `#OSD_RSSI` and `#OSD_RSSI_DETAILED` options to enable an RSSI and packets display for the OSD data in the upper right side of the screen. This way, you can see easily check if data is being received. E.g.: `#define OSD_RSSI` and `#define OSD_RSSI_DETAILED`

- Choose the telemetry protocol used, Frsky is default, other options supported are Mavlink, Lightweight telemetry (LTM), NMEA GPS. E.g.: `#define FRSKY`

- Choose graphical OSD options you would like to have enabled in osdconfig.txt. Should be self-explanatory.

- Chose an appropriate update interval for the OSD. 50ms = 20 updates per seconds should be okay for most, if you don't use the artificial horizon or other features that require a high update rate to be smooth, you can increase it. If you feel the OSD is not smooth enough, try decreasing it. Do not go below 20ms. E.g. `#define UPDATE_INTERVAL 30`

Generally, try to configure your flight control so that it does not send out unnecessary large amounts of data to keep the packet rate as low as possible.

Depending on the amount of data your flight control sends, you may want to increase `OSD_BLOCKLENGTH=64` to something larger like 256 to reduce the amount of telemetry packets. Compare the amount of packets of the video stream (on the upper left side) to the amount of packets of the telemetry stream (upper right) to get an idea. The number of OSD packets should not be more than 10% of the number of video packets.



### 3. 
Connect the serial port TX pin of your flight control to the serial port RX pin on the Raspberry. WARNING:**** The Pi uses 3.3V logic level on the serial ports, make sure your flight control also uses 3.3V. 5V might destroy the Pi serial port!

See https://pinout.xyz/ for pinout.