# junos-vpn #

This is a simple [1]SLAX script that when run, will display the current, active IPSec VPN tunnels on the device.

## Usage ##

There are few ways that you can run this script. One option is to upload it to the device, and run it from
there:

`scp vpn.slax user@device:/var/db/scripts/op/`

Once it is uploaded, you can run the following command from *operational* mode:

`op url /var/db/scripts/op/vpn.slax`

You can also enter in the following configuration:

`set system scripts op file vpn.slax`

...then you can just run `op vpn` from operational mode.

Another way is to run the script remotely, calling it via ftp, sftp, or scp. The latter two are preferred:

`op url scp://user:password@device/path/to/vpn.slax`

