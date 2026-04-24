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

![](../../Pasted%20image%2020260422175645.png)

site to site VPNS are also a thing, where u have firewalls that act like vpn concentrator. sending traffic normally into site instead of adding it inthe devices

SD-wan is software defined networking in a wide area network a wan built for the cloud

the data center used to be in one place the cloud has changed everything

![](../../Pasted%20image%2020260422175838.png)

it would be a challange since they need to go to the data center then the cloud 

![](../../Pasted%20image%2020260422175926.png)

but now they can go straight to the cloud

SASE update secure access for cloud services 

SASE is a next gen vpn

security technologies are in the cloud located close to existing cloud services

![](../../Pasted%20image%2020260422180037.png)

selecting the right choice can be challendging so we use a hybrid

SD wan manage the network connectivity to the cloud 

sase a completel network and securitty solution

---

regulated managed by a third party government laws and statutes

trade secret an organization have a secret formulas have something unique

intellectual property 

legal information court records documents PII and other sensitive details

financial information internal company financial details customer financials

human readable some data types are clear and obvious

but some are non readbable enccoded data barcodes and images

some formats are a hybrid CSV XML etc

not all data has the same categorization license tag numbers vs health records

different levels require different security handling additiuonaal permissions and etc

proprietary  data that is the property of an organization

PII is data that has name birth mother maidenname etcv

PHI is health information

intellectual property PII PHI are sensitive 

confidential very sensitive 

public/unclassified 

private/classified sometimes require an NDA

data at rest is data resting make sure whole fisk encryption 

and apply controls

data in transit is the data in motion 

encrypting the data is also needed here since when its in transit u dont want an attacker to attack it 

nertwork based protection can be firewall, IPS

if u want extra security u can use TLS and IPsec

data is use is data that is being used, it is actively processing in memory

data is always decrypted otherwise we wont do anything with it

attackers can pick the decrypted information out of RAM

target corp. breach nov 2013 they got 110million credit cards

data at rest and data in transit both encrypted so they went for the data in use

data sovereignty is data in the country that depends on the laws of legal monitoring court orders etc.

like for example laws in the EU is data cllected on EU citizens must be stored in the EU

where is ur data stored 

geolocation loctaion details tracks the person

it can be many ways to determine location 802.11 or GPS

can be used to manage data access like netflix stopping u from watching something bc its not allowed in the country

limit admin tasks to see if they inside or outside the building

---

network location identify based on IP subnet 

geolocation determine a user location GPS is very accurate to see where a person is gonna be

802.11 wireless less accurate since its gonna see all the wireless datas around

ip address not very accurate 

geofencing automaticaslly allow or restrict access, when a person is outside they dont have access to the data or app unless your near the office

the primary job task is protecting the data otherwise the org gonna be out of business

weather its on storage drive, network, or CPU they all need to be protected

protecting the data encryption security policies

data permissions too asking those who will authorizae 

encryption information into unreadable data from plaintext to cipertext

the encrypted data is drastically different than the plaintext

hashing is like a fingerprint, to see if the message is the same. , we cant recreate the data since hashing is random

we store it mostly with passwords/confidentiality

verifying the download files comparing the app hashing numbers/integrity

can be a digital signature too, authentication or non repudiation and integrity

hopefully it wont be a collision since some hashing algormith did have collision which make the same hash erven tho two different words

obfuscate make something normally understandable but very difficult to understand

turn a readble code into nonsense

helps prevent the search for security holes make it difficult to figure out whats happening

data masking is a type of obfuscation hide some of the original data which protects ur PII and sensitive data

![](../../Pasted%20image%2020260422182450.png)

data couyld be in storage but control based on permissions

tokenization replace sensitive data with a non sensitive plaaceholder SSN 266-12-1112 is now 691-61-8539. its like a timer where it is temp that can be used one time and wont be able to replay the number

u wont have to worry about encryption or hashing its only a timed tokenization

![](../../Pasted%20image%2020260422182721.png)

segmentation many orgs use a single data source one large database thats why when an attacker gets inside these large databases the losses can be large too

separate the data basically making many databases so that it would be hard for the attacker

if there is sensitive data it should have even stronger security

permission restrictions control access to an account seeing the policies are best for an org

authentication process password policies and other considerations

---
high availability may need to be powered on manually so if one fails u can bring another componet to replace it

we can provide HA which is high availability always on and always there

having them always on tho they will be additional costs

combine two or more as one big server

easily increase capacity and availability 

![](../../Pasted%20image%2020260424033356.png)

load balancing is also a thing where it balances the load lets say a big GB file it would take from the servers if one fails the others will still be there

recovery site is prepped there will always be a backup 


