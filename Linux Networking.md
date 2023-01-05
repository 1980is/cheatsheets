# Linux Networking
Text that looks like this -> ``are commands for you to run``.

---

## See information for your NIC
 ``nmcli connection edit type ethernet``

Now you are in the nmcli interface. Type ``print`` to see detailed information for the connection named "ethernet". To see the name of all your connection, ``nmcli connection show``. 

### Display IP addresses
``ip ad``

### Display route information
``ip route``

Legacy command to see route information.
``netstat -rn`` or ``route -n``

### Display ARP table
``arp -a``

### Display the ARP default timeout
``cat cat /proc/sys/net/ipv4/neigh/default/gc_stale_time``

---

## Change settings for your NIC

### Assign IP address
Find the connection name, ``nmcli connection show``
Assign the IP address to the correct connection name.
``sudo nmcli connection modify "Wired connection 1" ipv4.addresses 192.168.1.21/24``

### Disabling and enabling an interface
- ``sudo ip link set ens33 down``
- ``sudo ip link set ens33 up``

### Changing the MTU for e.g., iSCSI
- ``sudo nmcli con mod ensp92 802-3-ethernet.mtu 9000``


## Debug

- ``tcpdump -i any port 2222``


---

## Distro Specific Stuff

### Ubuntu

### To run legacy commands like ifconfig
``sudo apt install net-tools``
The new commands are in the **iproute2** software package which should be installed.

### Fedora



