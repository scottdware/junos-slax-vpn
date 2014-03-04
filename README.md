# junos-vpn #

This is a simple [SLAX][1] script that when run, will display the IKE and IPsec information for a given VPN
tunnel on your device.

## Installation ##

* Copy/upload the file to the device:

    `scp vpn.slax user@device:/var/db/scripts/op/`

* Run the script from the local file system, in *_operational_* mode:

    `op url /var/db/scripts/op/vpn.slax`

* Configure the script so it can be run by using it's name:

    `set system scripts op file vpn.slax`

## Usage ##
Once you have the script on your device or ready to run, there is one parameter that will need to be given:

* `tunnel`

You can specify this by issuing the following command from *_operational_* mode:

`op vpn tunnel <name>`

`<name>` can be one of two things:
* When the word `list` is given, it will display all of the current, active VPN's.

*  When the name of a VPN is given, it will display all information related to said VPN.

## Results ##

When you run the script with the `list` parameter, you get the following output:

```
admin@vpn-firewall> op vpn tunnel list
Name                      Status
--------------------------------------------------------------------------
Somebody                  UP
Vendor-ABC                UP
Another-Vendor            UP
Vendor-2                  UP
Home                      UP

Enter Name or "q" to quit: 
```

When run with the name of a VPN, you get the following:

```
admin@vpn-firewall> op vpn tunnel Vendor-ABC

--------------------------------------------------------------------------
Name: Vendor-ABC, Peer: 2.2.2.10, Total SA: 10
--------------------------------------------------------------------------
Flow      |SPI       |Index     |Life      |Port      |Encryption
--------------------------------------------------------------------------
<         |86c9382   |87        | 999999   |500       |ESP:3des/sha1
>         |6048e3fc  |87        | 999999   |500       |ESP:3des/sha1
<         |ec7fd5ea  |94        | 999865   |500       |ESP:3des/sha1
>         |af3987ad  |94        | 999865   |500       |ESP:3des/sha1
<         |5cf9a141  |95        | 999993   |500       |ESP:3des/sha1
>         |8d02e66a  |95        | 999993   |500       |ESP:3des/sha1
<         |fe1466e2  |97        | 990594   |500       |ESP:3des/sha1
>         |33c8e97e  |97        | 990594   |500       |ESP:3des/sha1
<         |ee108284  |105       | 995931   |500       |ESP:3des/sha1
>         |454d2e4d  |105       | 995931   |500       |ESP:3des/sha1
--------------------------------------------------------------------------
```

[1]: http://code.google.com/p/libslax   "SLAX"