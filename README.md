# Yesoul_BLE

# Summary
This project uses an ESP32 board to receive data from a Yesoul S3 spin bike and rebroadcast it in a format that works with a Garmin Edge cycle computer or Garmin Watch that supports BLE sensors.

# Required Libraries
* [NimBLE-Arduino](https://github.com/h2zero/NimBLE-Arduino)
* Arduino

# Hardware
* ESP32 board of some type, no headers needed

# Details
The goal here is to allow the connection of an indoor bike (AKA spin bike, exercise bike) to a Garmin Edge Cyclings computer. While this should work with any indoor bike using 
This is needed as the Yesoul bike broadcasts under the [Fitness Machine Service](https://www.bluetooth.com/specifications/specs/fitness-machine-service-1-0/) and the Garmin Edge/watch will not receive this profile. So this project receives the Fitness Machine data converts the cadence and power data as needed and rebroadcasts this data under the [Cycling Power Service](https://www.bluetooth.com/specifications/specs/cycling-power-service-1-1/).

This solution is currently crafted to this one spin bike and if the bike is not broadcasting the exact same combination of data/flags it may not work. The proper solution to this would be to read the flags coming from the Yesoul and then knowing what data fields are present parse the incoming data correctly.

# Known Limitations
Currently this connects to the first device it sees with the Fitness Machine Service UUID (0x1826), and Indoor Bike characteristic UUID (0x2ad2). I'm not sure what would happen if there were two devices in range matching this.

# Future Goals
* Add speed data from spin bike. This will require adding the Cycling Speed and Cadence Service

# References
This is a great write up on understanding the Cycling Power Service, [Arduino BLE Cycling Power Service Blog Post](https://teaandtechtime.com/arduino-ble-cycling-power-service)