# Eye 360

This document outlines the tools and steps needed to debug the connectivity of Eye 360 devices and test cameras on a Raspberry Pi.

## Tools Required

- **bluetoothctl**: CLI tool for connecting to Bluetooth devices. 
  - For more information, run: `man bluetoothctl`
  - *Tip*: Make sure to include steps for pairing devices.

- **pavucontrol**: GUI tool for managing audio device volume.
  - *Tip*: Use it to set specific devices as the output.

- **nmap**: Network scanning tool to check IPs on a network.
  - Use the command: `nmap -sP [ip]/24`
  - *Tip*: Look for expected output containing `esp-*` to identify cameras.

- **ifconfig**: Displays network interfaces.
  - Check the two interfaces on this device: `wlan0` and `eth0`.

## PI Hotspot

- **SSID**: `raspi-webgui`
- **Password**: `ChangeMe`
- The web interface can be accessed at `http://[ip]:80`
  - **Username**: `admin`
  - **Password**: `secret`

## Testing Cameras 
- Testing script can be found in ~ or home dir
- Activate the virtual env : `source myenv/bin/activate`
- `python test-camera.py`

*Note*: be sure that the **IP** still valid so please run `nmap` first

### Connection to the PI:

using ssh and by adding **-X** you will be able to run GUI apps
- `ssh -X abb@[ip]` 
- **password** = password
- *Tip:* feel free to add your ssh public key later on to the PI.

### final notes:

- The pi will be connected to some access point and then access point will be connected to the internet and your device will be connected to this access point too, and the hotspot already set from the PI will be used only for cameras can be also used if you want to connect your device to it.