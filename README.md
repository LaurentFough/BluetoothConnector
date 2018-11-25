# BluetoothConnector
Simple macOS CLI to connect/disconnect a Bluetooth device. I made it to easily connect my BeatsX earbuds (I thought the W1 chip would make the switch from my iPhone to my Mac seamless, but we're not there yet, apparently). There's probably a program that already does this but I didn't find it.

You can download a compiled version here: https://github.com/lapfelix/BluetoothConnector/releases
(or from here when AWS is down: https://www.dropbox.com/s/kxt8c5n3cgxfenh/BluetoothConnector.zip?dl=1)

If you have issues running the compiled binary (`permission denied` error), try running this command in Terminal:

`chmod +x /path/to/BluetoothConnector`

# Usage
#### Compiling, installing and then running from the command line
```
swift build
mv .build/release/BluetoothConnector /usr/local/bin/BluetoothConnector
./BluetoothConnector 00-00-00-00-00-00
```
Replace `00-00-00-00-00-00` is your device's MAC address. You can get it by alt-clicking the Bluetooth menu icon or by running BluetoothConnector without any arguments

#### With Automator to bind a shortcut to it (this is how I'm using it)
I included an Automator workflow service that calls BluetoothConnector from `/usr/local/bin` to make it easier to run BluetoothConnector with a keyboard workflow (this is how I'm using it).

Then open the Automator workflow and you should get a prompt to install it (don't forget to change the MAC address).
To bind a shortcut to the Automator service, launch System Preferences and Go to `Keyboard > Shortcuts > Services`, find your service and add a shortcut to it.
