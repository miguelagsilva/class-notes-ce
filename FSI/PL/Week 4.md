Client 1:
```bash
sudo ifconfig enp0s3 10.254.0.1 netmask 255.255.255.0 up
sudo ip route add default via 10.254.0.254
# Clear iptables
sudo iptables -F
sudo iptables -X
```

Client 2:
```bash
sudo ifconfig enp0s3 10.254.0.2 netmask 255.255.255.0 up
sudo ip route add default via 10.254.0.254
# Clear iptables
sudo iptables -F
sudo iptables -X
```

Router:
```bash
sudo ifconfig enp0s3 10.254.0.254 netmask 255.255.255.0 up
sudo ifconfig enp0s8 172.16.1.254 netmask 255.255.255.0 up
# Clear iptables
sudo iptables -F
sudo iptables -X
# Security policy
## internal -> external DNS and NTP direct
sudo iptables -A FORWARD -s 10.254.0.0/24 -d 172.16.1.0/24 -p udp -m multiport --dports domain,ntp -j ACCEPT
sudo iptables -A FORWARD -d 10.254.0.0/24 -s 172.16.1.0/24 -p udp -m multiport --sports domain,ntp -j ACCEPT
sudo iptables -A FORWARD -s 10.254.0.0/24 -p tcp -m multiport --dports 20,21 -j ACCEPT
sudo iptables -A FORWARD -d 10.254.0.0/24 -p tcp -m multiport --sports 20,21 -j ACCEPT
sudo iptables -P FORWARD DROP
## internal -> external SNAT
sudo iptables -t nat -A POSTROUTING -s 10.254.0.0/24 -d 172.16.1.0/24 -p tcp -m multiport --dports ssh,http,https -j SNAT --to-source 172.16.1.254
sudo iptables -A FORWARD -s 10.254.0.0/24 -d 172.16.1.0/24 -p tcp -m multiport --dports ssh,http,https -j ACCEPT
sudo iptables -A FORWARD -d 10.254.0.0/24 -s 172.16.1.0/24 -p tcp -m multiport --sports ssh,http,https -j ACCEPT
## external -> internal DNAT
sudo iptables -t nat -A PREROUTING -s 172.16.1.0/24 -d 172.16.1.254 -p tcp --dport ssh -j DNAT --to-destination 10.254.0.1
```

