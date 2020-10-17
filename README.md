# mpd numpad

Use a numeric keypad to control a [MPD server](https://www.musicpd.org/).

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

# Prerequisites

- mpd server
- python3
- python3 mpd library

On a Raspberry Pi running Raspbian these can be installed by running
```
sudo apt install mpd python3 python3-mpd
```

# Installation

From within the repository run the following commands:
```
sudo -i
mkdir -p ~pi/bin
cp mpd-numpad ~pi/bin
adduser --disabled-password mpc
cp mpd-numpad.service /etc/systemd/system
systemctl start mpd-numpad
systemctl enable mpd-numpad
```

# ncmpcpp

`ncmpcpp` is a ncurses based (full screen text) mpd client.
`mpd-ncmpcpp.service` is a systemd service file which starts ncmpcpp on a
new virtual console (tty7 by default) on system boot. To install it run:
```
sudo -i
cp mpd-ncmpcpp.service /etc/systemd/system
# if not already present then add user:
adduser --disabled-password mpc 
apt install ncmpcpp
systemctl enable mpd-ncmpcpp
systemctl start mpd-ncmpcpp
systemctl status mpd-ncmpcpp
```
