# Yesoul_BLE

Still a work in progress

This project uses an ESP32 board to receive data from a Yesoul S3 spin bike and rebroadcast it in a format that works with a Garmin Edge cycle computer or Garmin Watch that supports BLE sensors.

This is needed as the Yesoul bike broadcasts under the [Fitness Machine Service](https://www.bluetooth.com/specifications/specs/fitness-machine-service-1-0/) and the Garmin Edge/watch will not receive this profile. So this project receives the Fitness Machine data converts the cadence and power data as needed and rebroadcasts this data under the [Cycling Power Service](https://www.bluetooth.com/specifications/specs/cycling-power-service-1-1/).

This solution is currently crafted to this one spin bike and if the bike is not broadcasting the exact same combination of data/flags it may not work. The proper solution to this would be to read the flags coming from the Yesoul and then knowing what data fields are present parse the incoming data correctly.