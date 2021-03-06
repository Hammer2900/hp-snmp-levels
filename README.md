hp-snmp-levels
==============

Get HP printer cartridge levels using SNMP

# Requirements

This utility requires python Net-SNMP bindings.

Debian like:
```
apt-get install python-pynetsnmp # Squeeze, Wheezy
apt-get install python-netsnmp # Jessie+
```

RHEL like:
```
yum install net-snmp-python
```

Tested with Python 2.7.8.

# Usage

```
usage: hp-snmp-levels.py [-h] host community

Get HP printer cartridge levels using SNMP

positional arguments:
  host        The IP address or hostname of the printer
  community   The SNMP community to use (often 'public')
```

# Example

```
$ ./hp-snmp-levels.py 192.168.1.1 public
This is a HP LaserJet CM1415fn printer, named NPIAD0001 and with serial no. 1337DEADBF, up since the 2014-10-07

Cartridge levels:
Black Cartridge HP CE320A has level 62%
Cyan Cartridge HP CE321A has level 63%
Magenta Cartridge HP CE323A has level 75%
Yellow Cartridge HP CE322A has level 63%

Please contact it@company.com for details.
```

# Supported printers

This utility has been tested with the following printer models:

* HP LaserJet CM1415fn

# Known issues

* Will not autodetect the number of cartridges yet (assumes 4 for now)
* Code lacks DRYness
