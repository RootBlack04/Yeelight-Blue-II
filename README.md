# Yeelight Blue II Web Controller

A local, browser-based controller for the **Yeelight Blue II** using **Bluetooth Low Energy (BLE)** and **Web Bluetooth**.

Designed for:

- Windows
- Google Chrome
- Yeelight Blue II
- Bluetooth Low Energy
- Local/offline use


## Open Source

This project is **open source**.

The goal is to make the Yeelight Blue II usable again through a transparent, local and community-friendly controller rather than depending on an old/unsupported mobile application.

You are free to:

- inspect the source code
- modify it
- experiment with the BLE protocol
- improve the UI
- add new effects
- fix bugs
- create pull requests
- fork the project

Contributions and experiments are welcome, especially when they are tested against real Yeelight Blue II hardware.

## Current status

**V14 Stable / Release Candidate**

The project has been tested against a real Yeelight Blue II.

Verified functionality includes:

- Connect / Disconnect
- Reconnect by normal Connect action
- RGB control
- Brightness
- ON / OFF
- Color Flow
- Custom Color Flow
- Effects
- Favorites CRUD
- Scenes CRUD
- Timer / Auto OFF
- Schedule
- Energy estimation
- Music Reactive mode
- Backup / Export / Import
- Developer / diagnostic information

The BLE core currently relies on the verified characteristics used during real-device testing:

| Characteristic | UUID | Main role |
|---|---|---|
| FFF1 | `0000fff1-0000-1000-8000-00805f9b34fb` | Control |
| FFF5 | `0000fff5-0000-1000-8000-00805f9b34fb` | Status query/control |
| FFF6 | `0000fff6-0000-1000-8000-00805f9b34fb` | Status notifications |
| FFF7 | `0000fff7-0000-1000-8000-00805f9b34fb` | Color Flow |

## Quick start

1. Use **Google Chrome on Windows**.
2. Make sure Bluetooth is enabled.
3. Open `index.html`.
4. Click **Connect**.
5. Select **Yeelight Blue II**.
6. Allow Bluetooth access.
7. Use the controller.

After a normal browser refresh, use **Connect** again. Automatic BLE restoration is intentionally not part of the final UX.


## Vibe Coding

This project was built using a **vibe-coding / AI-assisted development workflow**.

The development process combined:

- human testing and decisions
- AI-assisted coding
- iterative debugging
- real-device BLE testing
- protocol experimentation
- UI iteration
- feature-by-feature validation

AI was used as a development tool, not as a replacement for hardware verification.

In particular, BLE behavior was treated as **hardware-first**: a feature was considered verified only after it worked on the real Yeelight Blue II.

This means the repository is also an example of how **vibe coding + reverse engineering + real hardware testing** can be combined to build a useful open-source tool.

### Important

AI-generated code can contain mistakes.

Always test changes on the real device before considering a BLE/protocol change stable.
## Important

This is a **local Web Bluetooth application**.

It does not require:

- Wi-Fi
- Yeelight cloud
- an Android application
- a backend server
- an online account

The controller communicates directly with the bulb over BLE.

## Color Flow

The verified flow sequence uses FFF7.

A flow is composed of steps such as:

```text
index,R,G,B,brightness,mode,...
```

The tested controller sends the flow steps and then uses:

```text
CB
```

to start the flow and:

```text
CE
```

to stop it.

## Energy

Energy values are **estimates**, not measurements from an electrical power meter.

The estimate depends on the configured bulb power, brightness and usage duration.

## Backup

The application can export local data to JSON and import it again.

Backup data may include:

- Favorites
- Scenes
- History
- Energy history
- Timer
- Schedule
- Settings

Keep backup files private if they contain information you do not want to share.

## Limitations

### Browser / BLE

Web Bluetooth behavior depends on the browser and operating system.

The final version deliberately does not implement an automatic reconnect system after page refresh.

### Energy

The controller estimates consumption. It does not directly measure electrical current or wattage.

### Compatibility

The project is developed specifically around the tested Yeelight Blue II BLE behavior. Other Yeelight models may use different protocols or characteristics.

## Project structure

```text
yeelight-blue-ii-controller-v14/
├── index.html
├── README.md
├── LICENSE
└── docs/
    ├── INSTALLATION.md
    ├── TESTING.md
    └── PROTOCOL.md
```

## Development principle

The most important rule for this project:

> Do not change the verified BLE core unless a real-device test demonstrates a concrete problem.

UI improvements and local application features should remain separate from the working BLE protocol implementation.

## License

MIT — see `LICENSE`.
