# junos-vpn #

This is a simple [SLAX][1] script that when run, will display the current, active IPSec VPN tunnels on the device.

## Usage ##

* Copy/upload the file to the device:

    `scp vpn.slax user@device:/var/db/scripts/op/`

* Run the script from the local file system, in *_operational_* mode:

    `op url /var/db/scripts/op/vpn.slax`

* Configure the script so it can be run by using it's name:

    `set system scripts op file vpn.slax`

    Then in *_operationa_* mode, run:
    `op vpn`

[1]: http://code.google.com/p/libslax   "SLAX"
