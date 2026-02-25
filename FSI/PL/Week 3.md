*2026-02-24 11:23:02*

1. ```bash
   iptables -F
   iptables -X
```
2. ```bash
   iptables -A INPUT -p icmp --icmp-type echo-request -j DROP
   ```
3. ```bash
   iptables -A INPUT -p tcp -s student.dei.uc.pt --dport ssh -j ACCEPT
   iptables -A INPUT -p tcp --dport imap -j ACCEPT
   iptables -A INPUT -p tcp --dport pop3 -j ACCEPT
   iptables -A INPUT -p tcp --syn -j REJECT # rejects only new connection not established ones
   ```
4. ```bash
   iptables -A OUTPUT -p tcp -d student.dei.uc.pt -m multiport --dports http,https -j ACCEPT
   iptables -A OUTPUT -p tcp --dport ssh -j ACCEPT
   iptables -A OUTPUT -p tcp --syn -j REJECT
   ```
5. ```bash
   iptables -F
   iptables -X   
   ```
6. ```bash
   iptables -A INPUT -p tcp -m multiport --sports ssh,http -j ACCEPT
   
   iptables -A OUTPUT -p tcp -m multiport --dports ssh,http,https -j ACCEPT
   
   iptables -A OUTPUT -p udp -d dns2.dei.uc.pt --dport domain -j ACCEPT
   iptables -A OUTPUT -p udp -d dns.dei.uc.pt --dport domain -j ACCEPT
   iptables -A INPUT -p udp -d dns2.dei.uc.pt --sport domain -j ACCEPT
   iptables -A INPUT -p udp -d dns.dei.uc.pt --sport domain -j ACCEPT
   
   iptables -A INPUT -p icmp --icmp-type echo-request -s student.dei.uc.pt -j ACCEPT
   iptables -A OUTPUT -p icmp --icmp-type echo-reply -d student.dei.uc.pt -j ACCEPT
   
   iptables -A INPUT -s 127.0.0.1 -i lo -j ACCEPT
   iptables -A OUTPUT -d 127.0.0.1 -o lo -j ACCEPT
   
   iptables -A OUTPUT -j DROP
   iptables -A INPUT -j DROP
   ```
7. ```bash
   iptables-save > /home/vboxuser/Desktop/rules1.iptables
   iptables-restore < /home/vboxuser/Desktop/rules1.iptables
      ```

cat /etc/services. has a list of ports to services
-j: ACCEPT, DROP(silently drops), REJECT(reject is like drop but notifies the sender that it was refused "Connection refused")