**See detailed information for your nic**
- ``nmcli connection edit type ethernet``
- Type ``print`` to see detailed information.

**See IP addresses**
- ``ip ad``

**See route information**
- ``ip route``
- Legacy command to see route information.
- ``netstat -rn`` or ``route -n``

**Assign IP address**
- Find the connection name, ``nmcli connection show``
- Assign the IP address to the correct connection name.
- ``sudo nmcli connection modify "Wired connection 1" ipv4.addresses 192.168.1.21/24``

**Disabling and enabling an interface**
- ``sudo ip link set ens33 down``
- ``sudo ip link set ens33 up``

**Changing the MTU for e.g., iSCSI**
- ``sudo nmcli con mod ensp92 802-3-ethernet.mtu 9000``

# Distro Specific Stuff
---
## Ubuntu

## To run legacy commands like ifconfig
- ``sudo apt install net-tools``
	The new commands are in the **iproute2** software package.

## Fedora



