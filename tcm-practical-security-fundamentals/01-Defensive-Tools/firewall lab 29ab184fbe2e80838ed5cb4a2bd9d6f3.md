# firewall lab

---

so i created a directory called firewall_lab and then made a file index.html in it and wrote hi firewall and saved it  then i setup a server by using pyton3 -m http.server on port 8080 

then i ip a in my terminal got my ip and ipconfig on host os and then i [http://localhost:8080](http://localhost:8080) and [http://my](http://my) vm ip :8080 and i was able to see the txt on web 

if firewall is disabled in terminal it will allow my host os ip to see the txt and if i enable it and can use my vm ip and connect so you gotta block the port 8080 now no matter who use the ip ad  it will block the external device using my vm ip address 

Now to block a specific ip address 

To block a specific IP address from accessing port 8080, use the following command:

```bash
sudo ufw deny from 192.168.1.21 to any port 8080 proto tcp
```

This will prevent the IP address 192.168.1.21 from accessing port 8080 using TCP protocol, even if they try to connect to your VM's IP address.

now 

sudo ufw status numbered this command will show acl in number wise because firewall will check rules from top to bottom and if any malicious ip want to log in it would let it if to top rules are not config properly so now it would show us 

|                        to  |                     action |                             from  |
| --- | --- | --- |
|  |  |  |
| 1] 8080/tcp | allow in  | anywhere  |
| 2] 8080/tcp | deny in  | 192.168.1.21  |
| 3] 8080/tcp | allow in  | anywhere (v6) |

so now the Ip we want to block can get in because the 1st rule lets any one using any Ip address in and the Ip address which as to be block in in number 2 so the malicious Ip address bypass the firewall block

**The fix - reorder rules:**

```bash
# Delete the rules in wrong order
sudo ufw delete 1
sudo ufw delete 1

# Add them in correct order
sudo ufw deny from 192.168.1.21 to any port 8080
sudo ufw allow 8080
```

**Now the ACL looks correct:**

1. `8080/tcp deny in 192.168.1.21` ← Block bad guy first
2. `8080/tcp allow in anywhere` ← Then allow everyone else

**This is why rule order is CRITICAL in firewalls!** Always put **specific deny rules ABOVE general allow rules**.