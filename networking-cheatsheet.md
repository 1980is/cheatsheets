**See IP addresses**
- ``ip ad``

**See route information**
- ``ip route``
- Legacy command to see route information.
- ``netstat -rn`` or ``route -n``

**Assign IP address**\
\
Find the connection name, ``nmcli connection show`` \
Assign the IP address t the correct connection name.\
``sudo nmcli connection modify "Wired connection 1" ipv4.addresses 192.168.1.21/24``

# Distro specific stuff
---
## Ubuntu

## To run legacy commands like ifconfig
- ``sudo apt install net-tools``
	The new commands are in the **iproute2** software package.

## Fedora



