# pfSense Training

## What is pfSense? The basics of Firewalls

According to pfSense website:

> "The pfSense project is a free network firewall distribution, based on the FreeBSD operating system with a custom kernel and including third party free software packages for additional functionality. pfSense software, with the help of the package system, is able to provide the same functionality or more of common commercial firewalls, without any of the artificial limitations..."

> pfSense software includes a web interface for the configuration of all included components. There is no need for any UNIX knowledge, no need to use the command line for anything, and no need to ever manually edit any rule sets. Users familiar with commercial firewalls catch on to the web interface quickly, though there can be a learning curve for users not familiar with commercial-grade firewalls.

In short pfSense is a Firewall/Router combo. A short baseline for each of these is laid out below.

### Firewalls

![image](https://user-images.githubusercontent.com/72173919/210431685-1e35d615-3b22-497e-8b05-cd61e6f5cf5b.png)

A **FIREWALL** is something that controls traffic *TO* a given network. It does this with simple/complex rules system. *Allow* this traffic and *deny* that traffic. Rules typically looks like this in raw form:

```EXAMPLE
TO              ACTION       FROM
-----------------------------------------
172.168.5.3/22  DENY         ANYWHERE
172.168.5.24    DENY         172.168.5.23
172.168.5.1     ALLOW        ANYWHERE
```


In the first example, we're saying to deny access (don't send packets) to the IP of 172.168.5.3 on port 22 from ANYWHERE (any IP address). Its important to understand that Firewalls don't typically stop traffic from getting **out** of your network or subdomain, but normally from getting **in**.

Three key concepts to understand with Firewalls:
1. Allow lets traffic (packets) pass to specified destination
2. Deny actually drops and destroys traffic (packets) that evaluate to true like the first and second example above
3. A **FIREWALL** doesn't ROUTE traffic. It isn't responsible for forwarding or sending packets to their desired endpoint, they simply evaluate if any rules are being broken and punishes the offending packets by destorying them (dropping them).

### Routers

You already know what this is! You have one at home most likely, which you've heard called a modem or router. In reality it's probably a Modem and Router combo! We won't talk about modems, but a router in concept is simple: route traffic from point A to point B and handle all the questions that come up like "Where exactly IS point B???". pfSense can also act as a router, building an understanding of what is where on your network and then forwarding traffic to the correct destinations.

![image](https://user-images.githubusercontent.com/72173919/210431866-68cf0095-da3f-4b4f-b06d-e64acbe9df02.png)

Routing large networks can be complicated but you'll need to understand a few aspects of routing:
1. VLANS
2. Zones/Broadcast domains
3. Areas

### VLANS
Virtual Local Area Network



