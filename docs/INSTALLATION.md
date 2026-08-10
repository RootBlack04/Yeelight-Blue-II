# Installation / Usage

## Requirements

- Windows
- Google Chrome
- Bluetooth adapter
- Yeelight Blue II

## Steps

1. Enable Bluetooth in Windows.
2. Make sure the bulb is powered on.
3. Open `index.html` in Chrome.
4. Click **Connect**.
5. Select the Yeelight Blue II.
6. Accept the Bluetooth permission request.
7. Test ON/OFF first.
8. Then test RGB and brightness.
9. Test Color Flow after the basic controls work.

## Troubleshooting

### The bulb is not shown

Check:

- Bluetooth is enabled.
- The bulb is powered.
- The bulb is close to the computer.
- Another application is not actively controlling it.

Then try Connect again.

### Connection works but a command fails

Do not immediately change the BLE protocol.

First:

1. Disconnect.
2. Connect again.
3. Test ON/OFF.
4. Test RGB.
5. Check Developer / diagnostic information.
6. Export the session log if available.

### Refresh

A browser refresh creates a new Web Bluetooth page context.

The final application intentionally uses a normal **Connect** action after refresh instead of promising automatic BLE restoration.


## Open-source / AI-assisted project

This is an open-source project developed with an AI-assisted, vibe-coding workflow.
The distributed `index.html` is the actual controller build. Changes to the BLE layer should
always be tested against a real Yeelight Blue II.
