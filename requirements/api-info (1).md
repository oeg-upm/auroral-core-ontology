# Energy load diagram

## Get load diagram

### Endpoint

/load-diagram/{device-id}/ /load-diagram/{device-id}/{from-timestamp} /load-diagram/{device-id}/{from-timestamp}/{to-timestamp}

### Parameters

device-id: The device identifier from-timestamp: UTC time in ISO 8601 formatted timestamp for when to get data FROM (default: 24h ago) to-timestamp: UTC time in ISO 8601 formatted timestamp for when to get data TO (default: now)

### Description

Returns the datapoints describing the load diagram for a monitoring device. Each datapoint is 15 min apart, unless there is data gaps.

### Example value:

```
[
  {
    "is_utc_timestamp": "String: UTC time in ISO 8601 formatted timestamp",
    "active_power": "float: instantaneous active power in Watts",
    "reactive_inductive_power": "float: instantaneous reactive inductive power in Watts",
    "reactive_capacitive_power": "float: instantaneous reactive capacitive power in Watts",
    "active_energy": "float: energy counter in kWh",
    "reactive_inductive_energy": "float: reactive inductive energy counter in kWh",
    "reactive_capacitive_energy": "float: reactive capacitive energy counter in kWh",
    "voltage": "int: rgrid voltage in Volts",
    "current": "float: current in Amps",
    "power_factor": "float: power factor (dimensionless)",
  }
]
```

---