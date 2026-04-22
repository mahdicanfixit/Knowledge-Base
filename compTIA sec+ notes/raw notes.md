IPS prevents a traffic and IDS detects it

we wish to have 100% uptime but it isnt realistic something will break at some point

fail open is when a system fails but data still flowing

fail closed is a system and data stop working
![](../../Pasted%20image%2020260422000208.png)

![](../../Pasted%20image%2020260422000317.png)

if ur in a network its easy to manage the devices but if ur outside u can do a jump server it should be secure to not compromise the jump server since it has connections with the inside

applications may need to know how to use the proxy explicit and there is also a transparent proxies that are invisible

most common one is NAT. most preoxies use application proxies too

there is multipurpose proxies too 

there is a internal proxy aka forward proxy ![](../../Pasted%20image%2020260422000810.png)

reverse proxy  its the proxy from the internal network that manages the response ![](../../Pasted%20image%2020260422000904.png)

open proxy is a third party uncontrolled proxy which is security concerning that third party we have no idea from

load balacing gets a big load and baalnce it 



![](../../Pasted%20image%2020260422001112.png)

it can also TCP offload protocol overhead

all these servers are working and gets a bit from everyone

and load balancer does all the encrypting where a reponse can be encrypted in the load balancer

and it can do caching and prioritization

they also can do content switching application centric balancing 

some servers are active and some are on standby

if one of them fails they would know and send requests from the ones that are online

sensors and collectors are a thing u can control and do informating managment with it

IPS firewall logs authenticatioin logts web server access logs and database logs email etc

collectors it is proprietary consoles IPS and firwall 

SIEM is also a thing u can use many siems includ all the things u need to log

port security is a chalnnage. 

port security is basically using a username and password giving authenticion on wireless networks

EAP esxtensible authentication protcol is a framwork 

many different ways to authenticate based on rfc standards

most EAP integrates with 802.1x it is a wireless protocol

aka IEEE 802.1x port based network access control u dont get access until u authenticate

EAP integrates with 802.1x

---


we be using firewalls at home office and in ur OS

controlling the flow of what comes in and out

firewalls control inappropriate content

it protects against attackers

firewall has 7 layers OSI layer 4 vs OSI layer 7 it uses vpn and etc

all in one security appliance UTM unified threat management.

URL filter and content inspection picking what website u want to filter

malware inspection watching if malware is getting in

spam filter where emails be spamming 

router and switch too and IDS/IPS

bandwidth shaper too

it can also use as a VPN

they mostly oprate at layer 4 

NGFW next gen firewall the OSI application layer all dayta is every packet

they can be called application layer gateway

requires some advanced decodes every packet gonna be analyzed and make security decisions 

NGFW u can allow or restrict people using youtube, can view twitter but tweet. and etc

it can be used as IPS too identify the application and see the vulnerability signature to the traffic

URL filters like gambling sites, or yahoo.com

WAF is not like a normal firewall it applies rules to HTTP/HTTPS converstations

SQL injection add your own commands to an application sql query

its a major focus of PCI payment 

---

VPN is a encrypted data traversing a public network

concentrator encrypt and decrypt access device 

used with client software sometimes built in the OS

keep data private across the public network encryption is the reason we keeping it private

![](../../Pasted%20image%2020260422175303.png)

we encrypt the data we wanna send and add new headers 

common protocols are SSL/TLS tcp/443 firewalls have no issues in these protocols

no big vpn clients usually remote access communication

authenticate users no requirement for digital ceritifcates or shared passwords

