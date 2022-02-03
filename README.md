# Yesoul_BLE

Still a work in progress

# Summary
This project uses an ESP32 board to receive data from a Yesoul S3 spin bike and rebroadcast it in a format that works with a Garmin Edge cycle computer or Garmin Watch that supports BLE sensors.

# Required Libraries
* 
* 

# Hardware
* ESP32 board of some type, no headers needed

# Details
This is needed as the Yesoul bike broadcasts under the [Fitness Machine Service](https://www.bluetooth.com/specifications/specs/fitness-machine-service-1-0/) and the Garmin Edge/watch will not receive this profile. So this project receives the Fitness Machine data converts the cadence and power data as needed and rebroadcasts this data under the [Cycling Power Service](https://www.bluetooth.com/specifications/specs/cycling-power-service-1-1/).

This solution is currently crafted to this one spin bike and if the bike is not broadcasting the exact same combination of data/flags it may not work. The proper solution to this would be to read the flags coming from the Yesoul and then knowing what data fields are present parse the incoming data correctly.

# Future Goals
* Add speed data from spin bike. This will require adding the Cycling Speed and Cadence Service

# References
This is a great write up on understanding the Cycling Power Service, [Arduino BLE Cycling Power Service Blog Post](https://teaandtechtime.com/arduino-ble-cycling-power-service)