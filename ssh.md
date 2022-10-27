# SSH Cheatsheet
---

## Debug
- Received disconnect from 18.130.233.91 port 22:2: **Too many authentication failures**
	- Most likely you have five or more ssh keys loaded. Check how many keys you have with ``ssh-add -l``.
	- If you see five keys or more you are out of luck for now. Remove one of the keys you are not going to be needing soon.
	- ``ssh-add -L ~/.ssh/id_ed25519yourprivatekey``
	- Your ssh client will attempt to use all the keys from `ssh-agent` one by one before it gets to use the key you specified with `-i`. Yes, it's a bit counter-intuitive. Because each such attempt counts as an _authentication failure_ and **by default only 5 attempts are allowed** by the SSH server you are getting the error you see: **Too many authentication failures**.