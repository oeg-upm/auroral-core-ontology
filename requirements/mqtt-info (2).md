# Flood Sensor

## Event data

### Flood Sensor sends values on the following topics:

```
location-<location_id>/flood-<deviceid>/sensor/battery: battery level in %

location-<location_id>/flood-<deviceid>/sensor/flood: reports true when flood is detected, false otherwise

location-<location_id>/flood-<deviceid>/sensor/temperature: in °C or °F depending on configuration

location-<location_id>/flood-<deviceid>/sensor/error: if different from 0, there is an error with the sensor

location-<location_id>/flood-<deviceid>/sensor/act_reasons: list of reasons which woke up the device: battery, button, periodic, poweron, sensor, alarm
```

---

# Energy monitor

> ***Note***: `<i>` refers to phase and can accept values [0, 1, 2]

## Event data

### Energy monitor sends values on the following topics:
```
location-<location_id>/energy-<deviceid>/emeter/<i>/energy: energy counter in Watt-minute

location-<location_id>/energy-<deviceid>/emeter/<i>/returned_energy: energy returned to the grid in Watt-minute

location-<location_id>/energy-<deviceid>/emeter/<i>/total: total energy in Wh (accumulated in device's non-volatile memory)

location-<location_id>/energy-<deviceid>/emeter/<i>/total_returned: total energy returned to the grid in Wh (accumulated in device's non-volatile memory)

location-<location_id>/energy-<deviceid>/emeter/<i>/power: instantaneous active power in Watts

location-<location_id>/energy-<deviceid>/emeter/<i>/voltage: grid voltage in Volts

location-<location_id>/energy-<deviceid>/emeter/<i>/current: current in Amps

location-<location_id>/energy-<deviceid>/emeter/<i>/pf: power factor (dimensionless)

location-<location_id>/energy-<deviceid>/relay/0: reports status: on, off or overpower
```

## Write data

### Energy monitor accepts commands on the following topics:
```
location-<location_id>/energy-<deviceid>/relay/0/command: accepts on, off or toggle

location-<location_id>/energy-<deviceid>/emeter/<i>/command: accepts message reset_totals to reset total and total_returned energy counters to 0

location-<location_id>/energy-<deviceid>/command: accepts message reset_data to reset all device data
```

---

# Motion Sensor

## Event data

### Motion sensor sends values on the following topics:
```
location-<location_id>/motionsensor-<deviceid>/status: publishes a JSON payload in form:
 {
   "motion":false, // if motion is detected: boolean [true, false]
   "timestamp":0, // uint: device unix time
   "active":false, // if motion detection is actrive: boolean [true, false]
   "vibration":false, // if vibration is detected: boolean [true, false]
   "lux":0, // Illumination measure by the sensor in lux.
   "bat":0 // battery charge in percent
 }
```

---

# Temperature and humidity data

## Event data

### Temperature and humidity sensor sends values on the following topics:
```
location-<location_id>/htsensor-<deviceid>/sensor/temperature: in °C or °F depending on configuration
location-<location_id>/htsensor-<deviceid>/sensor/humidity: RH in %
location-<location_id>/htsensor-<deviceid>/sensor/battery: battery level in %
location-<location_id>/htsensor-<deviceid>/sensor/error: if different from 0, there is an error with the sensor
location-<location_id>/htsensor-<deviceid>/sensor/act_reasons: list of reasons which woke up the device: battery, button, periodic, poweron, sensor, alarm
location-<location_id>/htsensor-<deviceid>/sensor/ext_power: true, if the device is usb powered
```

---

# GPS emergency button

## Event data

### GPS emergency button sends values on the following topics:
```
location-<location_id>/gpsbtn-<deviceid>/status: : publishes a JSON payload in form:
 {
   "bat_level":32, // uint: battery level [%]
   "alarm_status": "on", // reports the alarm status: string ["on", "off"]
   "gps_latitude": 38.34, // WGS84 [degree]
   "gps_longitude": -7.54, // WGS84 [degree]
   "beacon_mac": "AABBCCDDEEFF", // Mac address of closest position beacon 0X000000000000-0XFFFFFF
   "x_axis_accel": 12.3, // X axis acceleration [g]
   "y_axis_accel": 12.3, // Y axis acceleration [g]
   "z_axis_accel": 12.3, // Z axis acceleration [g]
   "angular_unit": 14, // The angular relative to the X-axis and the Y-axis. [degree]
 }
```

---

# Water AMR data

## Event data

### Water AMR sensor sends values on the following topics:
```
location-<location_id>/water-amr-<deviceid>/status: publishes a JSON payload in form:
 {
   "iso_utc_time": "2020-10-23T15:58:21Z", // UTC time in ISO 8601 formatted timestamp: String
   "counter": 123456 // accumulated value in current timestamp: uint [m3]
 }
```




