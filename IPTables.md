# IPTables

Output config.
``iptables -L -v --line-numbers``

``iptables -I INPUT 1 -m state --state NEW -m tcp -p tcp --dport 80 -s 192.168.122.197 -j ACCEPT``

``iptables -D INPUT 1``

Tables are saved here.
``/etc/sysconfig/iptables``

Save tables. 
``iptables-save > /etc/sysconfig/iptables``

Block all traffic unless it's specifically allowed. Needs to be the last line.
``iptables -A INPUT -j DROP``

If you block all incoming traffic you will lose all outbound traffic from your server that the server initates unless you allow established traffic.
``iptables -I INPUT 1 -m conntrack --ctstate RELATED,ESTABLISHED -j ACCEPT``


