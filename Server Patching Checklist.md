# Server Patching Checklist

## Debian

### APT

Install **only** security updates.
``list=$(apt-get --just-print upgrade | grep -i security | awk '{print $2}' | awk '!seen[$0]++')``
``apt-get install --only-upgrade $list``

### Systemd

``systemctl status``

``sudo systemctl list-units --failed``
``sudo systemctl list-units --state failed``
``sudo systemctl list-units | grep -i failed``

### Journalctl

``journalctl | grep 'error'``

Show current boot messages.
``journalctl -b``

List boots of the system.
``journalctl --list-boots``

Select a specific boot from the list.
``journalctl -b -3``

## Red Hat

