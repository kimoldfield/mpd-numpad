# mpd numpad

Use a numeric keypad to control a MPD server.

Written to allow a USB numeric keypad to be used to control mpd running on a headless Raspberry Pi.

# Testing

To test run
```
./mpd-numpad
```

mpd-numpad will connect to the local mpd server and print a list of key
mappings.

Pressing a key will perform the coresponding action.

Press "q" to exit.

# Installation

Run the following commands:
```
sudo -i
mkdir -p ~pi/bin
cp mpd-numpad ~pi/bin
adduser mpc
cp mpd-numpad.service /etc/systemd/system
systemctl start mpd-numpad
systemctl enable mpd-numpad
```
