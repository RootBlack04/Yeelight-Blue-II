# BLE Protocol Notes

These notes document only the behavior verified during the real-device testing used for the V14 release.

## Service

Primary service:

`0000fff0-0000-1000-8000-00805f9b34fb`

## Critical characteristics

### FFF1

`0000fff1-0000-1000-8000-00805f9b34fb`

Used for control writes.

### FFF5

`0000fff5-0000-1000-8000-00805f9b34fb`

Used for status/control interaction.

### FFF6

`0000fff6-0000-1000-8000-00805f9b34fb`

Notification characteristic for status responses.

### FFF7

`0000fff7-0000-1000-8000-00805f9b34fb`

Used by the verified Color Flow implementation.

## Status

The controller subscribes to FFF6 and uses the status response to update the UI.

A tested status response had the form:

```text
0,0,255,100,0,0,
```

## RGB

Tested control payloads include:

```text
255,0,0,100,...
0,255,0,100,...
0,0,255,100,...
255,255,255,100,...
```

## Color Flow

Tested flow commands use the FFF7 characteristic.

Start:

```text
CB
```

Stop:

```text
CE
```

Flow steps use comma-separated RGB/brightness/transition information.

## Safety rule

These notes are a record of the tested implementation, not a claim that every undocumented characteristic or command has been reverse-engineered.


## Development methodology

The protocol implementation was developed through iterative AI-assisted/vibe coding combined
with real-device observation and validation. These notes intentionally document verified behavior
rather than assumptions about undocumented Yeelight firmware.
