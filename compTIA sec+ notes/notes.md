4.1
when using an app we need to see all the security around it

seeing the firewall settings. patch levels, os file verisons etc

integrity masurements check for secure basline

we need to create a baseline its mostly available from the manufacturer or OS manufacturer

many OS have extensive options there are over 3000 group policy settings

microsoft have security toolkit

now we have to deploy the baselines may require multiple deployment mechanisms 

automation is also very good here to have more than one device

maintain the baselines since new vulnerability will be discovered or a new os is installed

test and measure to avoid conflicts

---
4.1
no system is secure by default. you need to do that

hardening guides for software or platform

always connected mobile technologies need harderning 

updates can fix bugs and stuff

segmentation can protect data making ur company data away from the user data

control with an MDM mobile device manager.

we also need to hardern our desktops and latpotps seeing the updates for os application etc

automate the monthly patches

and remove whats not needed

we also need hardening in switches and routers. always change the configure authentication never use default

check the manufacturer for security updates and they are important

secure the cloud workstation too, least privilege access, all services network settings application rights and permissions

EDR which is detection and response

and backup as always c2c cloud to cloud

servers also need updates either its windows or linux, make a hard password and limit the accounts and also the network access to access the servers, and some kind of anti virus

SCADA/ICS that manage power generation refining manufacturing equipment facilities industrial energy logistics

real time information system control

there isnt no access from the ouside

embedded systems can be difficult to upgrade since they are designed for a speific function. and there is some kind of potential threats on these stuff and make sure to keep them up to date. and also make them in a certain network.

RTOS too like cars and stuff, isolate the system and prevent access from other areas

IoT devices are weak by default but changing the passwords and updates they gonna be secure. u can also segmentation

---
4.1
site surveys. determine existing wireless landscape seeing the access points. and work around the existing frequencies. and also plan for ongoing site surveys too

![](../../Pasted%20image%2020260427111149.png)

signal coverage potential interference and built in tools that u can use. and can use 3rd party tools like netspot. spectrum analyezer too can show all signals 

MDM aka mobile device management manages the company owned mobile devices/phones

u can set policies too when u enter the office the camera disable or such and when u leave its enabled.

manage access control froce screen locks and pins on these single devices

BYOD aka bring your own device or device

they have to meet company requirements so they can be managed by MDM

difficult to secure old ones. how is data protected and such

COPE corporate owned personally enabled they buy u the device and used both as a corporate and a personal device

and is protected using corporate policies 

CYOD choose your own device same as COPE but you can choose

cellular networks 4g, 5g

there is security concerns traffic monioring and location tracking 

wifi too since it has full access to the internet

encrypt ur data and use VPN to protect ur data

monitor the data from on path attack

bluetooth aka PAN connects ur mobile devices tgt like headsets headphones and etc

and do not ocnnect to a unknown device where you dont know where it is

---
4.1
an org wireless network can contain confidential information 

and authenticate the users before granting access to those networks

and ensure all communication is confidential encrypt the wireless data

and verify the integrity of all communication aka MIC

WPA2 has a brute force problem there is a four way handshake and capture the hash and when they take it offline they brute force it

once u have that key anyone can connect to it

WPA3 has GCMP ciper mode protocol a stronger from WPA2

WPA3 changes the PSK authentication process creates a shared session key to the device so no four way handshakes no hashes or brute force

gain access to a wireless network by temp users or mobile users

credentials they asking for the shared password which is PSK. its unsecure since its a password that can be shared

but u can use centralized authentication which makes u login instead of having a password only

if u using it at home there is WPA3-personal if its the company u can use WPA3-enterprise

identification who you claiming to be (username)

authentication can you prove who you say you are (password)

autheorztation based on your identification and authentication what access do yo have

accounting basically logging the login time, data sent and recvied and logout time of the user

![](../../Pasted%20image%2020260427112355.png)

RADIUS remote authentication dial in user service is available on almost any server OS

IEEE 802.1x NAC u cant get access to the network until you authenticate

EAP extensible authentication protocol an authentication framework 

supplicant the client authenticator the device that provides access authentication server validates the client credentials

---
4.1
secure coding concepts a balacne between time and quality

always test the quality assurance process

vulnerabilities will eventually be found and exploited so we patch

input validation what is the expected input 

docuemtn all input methods forms fields type

check and correct all input a zip code should be only X characters. fix any data with improper input

the fuzzers will find what you missed dont give them an opening 

secure your cookies they are ifnormation stored on your computer by the browser

tracks personalization and session management, it is a security risk unless someone gets access to them

senstitive information should not be saved in a cookie 

SAST static application security testing they put their code to see any secure risks 

dont rely on automation for those things

still have to verify each finding because false positives can be possible

an application is deployed users run application executable or scripts

has the application been modified can you confirm the application was written by a dev?

the application code can be ditially signed bny the develper

do sandboxing to isolate the threat

commonly used during development 

there is many things that can be sandboxing, VM mobile devices browser iframes windows uac

real time information view blocked attacks SQQL injection attempts patched vulnerabilites 

udit the logs find the information gathering and hidden attacks

---
4.2
every org has a purchasing process, start with getting from the user usualkly includes budgeting information and formal approvals

negotiate with suppliers terms and conditions 

once they done they do invoice and payment 

once they have the product they would do central asset tracking system

ownership once u give it to a person its gonna be in their name incase we need it again

classifciation type of asset hardware and software

monitoring the inventory and where it is and where its gonna be, associate a support ticket with a device make and model 

enumeration list all the asset, cpu memory storage keyboard and mouse

u can have an asset tag barcode RFID visible tracking number etc

media sanitization u may need to remove all the data so the data wont be seen by anybody

depending on the use cases, if we giving it to a employee we would do a one way trip and make sure its remove perm

if we want to make sure 100% we can use a drill. u can drill holes on the drive to remove it perm electromagnetic 

some orgs have alot of devices but dont have time to destory all of them there is 3rd parties where they can destory all the drives. they should have a cert of destorying

some orgs may need some emails to have and to use which is data retention keeping it just incase

---

4.3

vulnerability scanning scanning if there is any vulnerabilities 

port scan poke around and seeing whats open in a system

identify systems and devices

test from the outsdie and inside dont dismiss insder threats they also a thing

gather as much information as possible 

![](../../Pasted%20image%2020260427114349.png)

you can see the vulnerabilites and checking what can be need to be checked and what not

FUZZING SENDING RANDOM INPUT TO AN APPLICATION looking for something out of the dordinary like crahsing the application server error and etc

1988 project atthe univeristy they made a fuzzing generator 

many diferent fuzzing options platform specifics

CERT carnegie mellon computer emergency response team

package monitoring especially open ource, confirm the package is legitimate and if its a trusted source, checking the intergry of the package

see the safe package in a sandbox and if it is secure, then u can put it in ur enviorment

---

4.3 

always research the threats and the treat actors

see how the hackers tool used and etc 

make decisions based on this itelligence invest the best prevention

there are groups that can be seeing threats and how to understand them

OSINT open source, internet discussion groups social media and such

government data mostly do public hearings reports and websites

commercial data maps financial rpeorts databases

dsomeone else has already compiled the informationa nd you can buy it, basically third party intelligence

and if there is a threat they can tell you before it becomes known they always monitoring the threats and such

information sharing orgs public threat intelligence

private threat intelligences, data sharing the threats and such to work tgt

CTA cyber threat alliance sharing the threat tgt and do the intelligence

and source ytou can use is the dark web, you can see the hacking groups and services, and tools and credit card sales accounts and such

monitor forums to see if the org will pop up or what not

---

4.3

penetration testing aka pentest simulating an attack and seeing the process

national institute of standards and technology technical gudide to information securiy tewsting and assessment NST TST 

before any pentesting  we need to know the rules. the scope and reasonsing 

type of testing like on site breach, outside, normal working hours or after 6pm only

the rules like ip address emergency acontacts and how to handle the information and seeing the inscope and out of scope devices and applciations

try breaking into the system gain privilege escalation and be careful to not do a DoS or loss of data 

you might wanna try more than one thing like brute force social engineering database injections buffer overflows

youll be sure if ur vulnerable, then an attacker can get in

the process intial exploitation get into the netyrokr

persistence try getting in the system more than one way, make an account in the system and such

the pivot once u gain access u can try to access other devices. jumping to other systems and such

it takes some time to fix a vulnerability, software changes testing then deploy it etc

bug bounty programs is basically a person finding a bug or a vulnerability and gets a reward for making the bug public

---

4.3 

false positives are basically threats that are false. its differnet than a low severity vulnerability its real but may not be that high priority

false negatives is basically the opposite of false positives. a threat exists but u cant detect it

update the latest signatures 

work with the vulnerability detection manufactur for the latest threats

priortizting vulnerabilities from high medium and low depending on what is more imporntant and such

national vulnerability database nvd.nist.gov

CVSS common vulnerability scoring system each valunrbility has a score from 0 to 10, each scoring standards change over time  cvss 2.0 vs cvss 3 and etc

CVE the vulnerabiliteis can be cross referenced online national vulnerability database nvd.nist.gov/

CVE cve.mitre.org/cve/

microsfot security bulletins technet/security/current.aspx

the scanner gonna look for any vulnerabilite and it finds they gonna tell u the level of it. but before any scan you need the latast signatures. application scans web application scans and network scans too.

![](../../Pasted%20image%2020260428045345.png)

loss of value or business activity if the vulnerability is exploited.

a small DDos masy limit the access to the service can be 50% 

a buffer overflow may disable the whole service  would be 100%

understanding the enviroment your in. every environment is different from internal to external users. revenue generating application and the potential for exploit

some exploits have big consquences

2023 feb ransomeware closed for two weeks

power utilities back in march 2019 DDoS attacks from an unpatched known vulnerability

risk tolerance you cant fix all the threats u should have an amount of risk acceptable. the timing of security patches patching immediately doenst allow for proper testing

testing takes time, but there is a middle ground where u can take ur teime with testing but manage the security around it

---

4.3

the most common technique is patching

scheduled vulnerability and patch notices 

unscheduled patches are zero day and often urgent

the patches will always keep going

cybersecurity insurance coverage gives back the data that got lost. money lost to ph8ishing and privacy lawsuit costs

doesnt alwayscover everything

segmentation is limiting the scope of the threat, separate the devices into their own network, and limiting the attacker from attacking the other things

cant patch it? disconnect it and air gap might be required

use NGFWs 

you can use two switches they not connected with each other, and you can use virtual LAN or VlAN where it sepearte those two in one switch so blue talk to customer b and red talk to customer a. they all in the same router but they are split

compensating controls, optimal security methods mayt not be available

compensate in other ways disable the problematic service and revoke access to the application limit external access modify internal security contreols and software firewalls

provide coverage until a patch is around

removing the vulnerability is optimal but not always can be patched

u wanna have the uptime still on and provide the server but also protect the data and such

not all vulenerabilites share the same severity so the communite gonna decide if it needs to be patched or not

more than one person gonna see the vulnerability and then come to a conclusion

the vulnerability is now patched but did it stop the exploit? or patch all vulnerable systems?

rescan and see if it is deploied propely

audit everything just incase to see if it is installed propely

verifcation manually confirm the security

reporitng ongoing checks are required basically threat intellegence

continuous reporting seeing the number of identified vulnerabilites. system patched vs unpatched the new threat notifictions and the errors that come with it.

---
4.3

attackers never sleep they always gonna be around and awake so we need to copy

review account access firewall rulebaseand scanning 

seeing the status of the security posture

monitoring the computing resources

systems authentication logining in random places and time

server monitoring service activity backups software versions etc

applications availability uptime, data transfers if they are happening alot. security notifications to see what is the cause and such

how many employees vendors and guests. and see the firewall and ips reports

SIEM or SEM keep logs about database of servers firewalls vpn SANs cloud services

centralizing them in one place

correlation between diverse systems view authentication and access track application access and measure the data transfers

scanning constantly changing threat landscape so we need to be up to date with everything

computers dont move much but laptops phones and such does so they need to be more secure

actively check systems and devices operating systems types and verisons, drivers, applications and potential anomalies. 

gather the raw details so later u can do detail reports later

analyze the collected data. 

a report of maybe how many devices up to date. or in compliance. devices running older OS

then determine thee best steps. a new vulnerability is annoucned. and how much systems are vulnerable 

ad hoc information summaries prepare for the unknown

archiving it takes around 9months for a company to identify and contain a breach. IBM security report 2022.

access to data is really important you never know if the attacker in the network for months or years

may have a mandate

alerting real time notifcation when a security event happens. increase in authentication erorrs large file transfers

keep the right people informed if it is a traffic or an attack

notifcation methods using text. email or security console

when thre is an alarm u need to react asap. and quarantine the system and prevent it going to other devices. 

alert tuning bnalacning act. prevening false positives and negfatives

an alert should be accurate seeing the network and such

---
4.4
SCAP many automation protcols. weather its NGFW IPS or vulnerability scanner. they can all find a threat but different ways

managed by NIST https://scap.nist.gov

allow tools to identify and act  on the same vulnerability. confirm patch installs and such

using SCAP content can be shared between tools focused on configuartion compliance

really useful in large enviroments

when all ur security tools communtine and understand each other, it can be much easier to understand and automate the process of patching on those systems with less error. the processes can be automated and keep scanning for vulnearbilitys. notifcation and getting compliase.

apply security best practices to evverything OS cloud phones etc. its the bare mimimum for security settings

lets asay for phones. disabling screenshootingg. screen recording. preventing calls when locked. encrypt backups and such.

popular benchmark is CIS 

we check if the devices are in compliance and we use an agent to install it in a setup to check everything. its always on and always running to see if something goes wrong

an agentless runs without a formal install. it comes form the VPN and runs in the ram and if everything is good, it goes away. 

SIEM security information and event management logging the events and information in one place

real time inofmratin and put them in a long term storage

forensic analysis gather detai,s after an event

 antivirus and antimalware would prevent viruses and malwares. both terms can also be the same software in ur syste,m

DLP data loss prevention blocking the data that you dont want. aany data that u dont want u can block

stop the data before the attacker gets it

so many sources so many destinatinons weather its in the cloud or such

SNMP a database of data MIB maagnemtn information based poll devices over udp/161

request statstics from a device server firewall workstation switch router etc

![](../../Pasted%20image%2020260428081456.png)

this graph made by quering  firewall 

most snmp operations expect a poll. SNMP traps can be configured on the monitored device communicates over udp/162 it can alarm it

it can wait till the CRC errors increases by 5 send a trap that can monitor station react asap and putting the alarms on

Netflow gather traffic statistics from all traffic flows seeing what flowsd and such, many agents have netflow and such

netflow probe may be built in a switch or a router or a external probe. and connect  to a SPANand it connects the information and send it to netflow collector and see the traffic 
![](../../Pasted%20image%2020260428081746.png)

there is many details in the flow and such

vulnerability scanners usually minimally invasive unlike a pentest. port scan too and see what services are installed. u can identify systems and security devices in that range

we can do it in our own network. and outside as well. they can get alot of information but not accurate. so u need to verify it manually

---
4.5 

filter traffic by port number  traditional vs NGFW

encrypt the traffic vpn between sites

most firewalls can be layer 3 devices

most common firewall type is NGFW it analyse the traffic and make deiscion weather we let it in or not

requires some advanced decodes

ports and protocols make forwarding decisions based on protocol weather its TCP or UDP.

web server tcp/80, tcp/443 
ssh server tcp/22
microsoft RDP tcp/3389
DNS query udp/53
NTP udp/123


![](../../Pasted%20image%2020260429082619.png)

a logical path from top to bottom

very general or specific

implicit deny there is a deny at the bottom even if u didnt put one

ACL allowing or disallowing traffic. source IP destination IP port number time of day and application

![](../../Pasted%20image%2020260429083008.png)

most orgs put their firwall that sit between the internet and interanal network

there is also a screened subnet that dont contain any data 

IPS monitors traffic and seess if there is any malicious traffic

it uses a signature based

anomaly based build a basline of whats normal unusal traffic and such

you determine what happens when unwanted traffic appears

there is thousands of rules 

rules can be customized by groups. they seleteced automatically by the IPS or by urself

this can take some time to find the right balance between them

---

4.5

many control traffic based on the data within the content, corporate control of outbound and inbound data.

control the inappropriate content that is NSFW or parental controls

URL scanning also called URI uniform resource identifier. allow list block list

managed by the category auction hacking malware etc

can have limited control 

often integrated into an NGFW so single device can manage all of those

agent based. install cilent software on the user device itself

users can be located anywhere they can travel and anywhere they like

updates must be distributed tro all agents cloud updates and such

some use proxies they speak directly to the internet

so he asks for the website. and goes to proxy and then proxy sees if its okay to give him the link or not

some applications may need to know how to use the proxyexplicit 

some proxies are invisible so it called transparent

internal proxy both user and proxy are in the internal network  then it will check the data and sees if there is any malware then gives it to the user

u can set rules for example .professormesser.com: allow

there is 50 topics adult educational gambling gov etc

different dispostitions for example education: allow but gambling: block

filter URLs based on the risk. a good rep website is allowed a bad rep is blocked. risk like trustworthy low risk medium risk and high risk

automated reputation sites are scanned and assigned a reputation

there is also manual reputation

DNS filtering before connecting to a website, u get a ip address and perform a DNS lookup.

DNS is upated with real time threat intelligence both commercial and public lists

harmful sites are not resolved no IP no connection

this works for any DNS lookup not just web filtering

---

4.5

active directory has everything on the network. computers, user accounts, file sharing prints groups and etc. primarily windows based

mangage authentication users login using their AD credentials 

u can determine which users access what

group policy u can manage the computers or users with their own policy

a central console login scripts QoS

security patches for the linux kernel u can add mandatory access control MAC to linux

linux traaditionally uses DAC

limits application access least privilege a potential breach will have limited scope

and open source and can be installed in many linux distros

---

unencrypted network data making network traffic protect is needed

all traffic sent in the clear telnet, FTP, SMTP, IMAP

verify the packet capture

use a secure application protocol 

![](../../Pasted%20image%2020260429112100.png)

port can determine if something secure or not secure.

HTTP: port 80 HTTPS: port 443

different port number dont mean it is secured

![](../../Pasted%20image%2020260429112710.png)

transport method dont rely on the application 

802.11 wireless open access point

---

4.5 email securty

email spoofing happens all the time the email looks as if it originiated from james@professormesser.com but how do u know if that was him

reputable sender will configure email vaildation

the gakekeeper evaluates the source of inbound email messages block it at the gateway before it reaches the user on site or cloud based

spf protocol sender configures a list of all servers 

list of authorized mail servers are added to a DNS TXT record receiving mail servers perofmr a check to see if incoming mail really did come from an authrozied host

![](../../Pasted%20image%2020260503195548.png)

a mail server sign all outgoing mail 

its a signautre by the receiving mail servers

![](../../Pasted%20image%2020260503195704.png)

DMARC aka domain based message authentication reporting and conformance.

the domain owner decides what receiving email servers should do with emails not validating using SPF and DKIM

compliance reports are sent to the email administrator

![](../../Pasted%20image%2020260503195909.png)



---

4.5

FIM file intergrity monitroing some files change all the time some never do 

monitoring important OS and files, because some files change all the time but some never do for those who never do should be monitored.

windows SFC system file checker checks all the file and sees their dates and such

for linux we have tripwire

and many host based IPS options as well

DLP data loss prevention, for example social security numbers credit card numbers and such blocks the data before the attackers gets it 

many sources many destinations can be as software

DLP system on your computer data in use endpoint DLP

USB blocking back in nov 2008 a worm virus called agent.btz replicates using USB storage. they banned any removable flash media or storage devices

but got lifted in 2010 

cloud based DLP is also a thing

sees what is coming in and out 

blocks viruses and malware also

DLP need to block the email system it can look at sensteive emails that is inbound and outbound

fake wire transfers. and such

it can be blocked straight if the DLP is on

nov 2016 a employee spouse emails a spreadsheet to use a template

contained personal infomration of 36k employees

---

endpoint is the user stop the attackers that is inbound and outbound attacks

many different platforms mobile and desktops

protection is multi faceted we need layers

control at the edge, we use a firewall to manage the inside  and the outside network'

access control limits the access of the data who gets in and who doesnt. limit by user, or group, maybe location or application to use 

it can be removed anytime depending on the security posture

u cant really trust evveryone computer. so u do checks  and its called posture assessment. making sure the antivirus is in and such and the correct applications

before coonecting to the network. see the health check is the device trusted? is there anti virus etc

an agent monitors premanently installed onto a system and periodic updates may bbe required.

there is a dissolvable agnets where they not nee d to be installed. it just checks and terminates when no longer required aand everything is great

agentless NAC integrated with active directory checks if made when the user logs off

failing ur assessment? what happens if it fails?

quaranite network and notifying the admins

once resolved u can try again

EDR SIGNATURES ARENT THE ONLY DETECTION Ttool. sees the behavioral and analysis, machine learning and such, lightweight agent on the endpoint

investiage the threat root cause analyssi

respond to the threat, isolating the system, quaratine the threat and rollback to a good config, can be all automated.

XDR an evolution of EDR improves missed detections false positives and etc

where there is an virus infection it involves into more than one device

add network based detections 

XDR commonly includes user behavior analystics

watch for anything unusual, for the rules. pattern matching or statistical analysis

goal is to make it easy to stop the code before it becomes a larger problem

---

4.6 

applications are available anywhere

data located anywhere 

many application users and such

IAM identity and access managmenmt identify lifecycle managment. every entity gets a digital identiy

access control

authentication and authorization enetities must prove they are who they claim to be

identity governance tracing the resource access

provisioning, the user creation process and the account removal process

account deatils would be name attributes group permissions and etc

an important part of the IAM process nobody gets admin access and limit the users

permission assignments each entity gets limited permissions to do the job and not get any futher permissions. group azssignments are common

storage and files can be private to that user

no privileged access to the operating system to avoid the user to make changes to the OS

identity proofing i can be anyone

who the system thinks you are and such

validation something they know giving them quest ions only they know like dog or such

verification attestation, passport inperson meeting etc. automated verification also an option

![](../../Pasted%20image%2020260504142540.png)

SSO single sign on once u sign in u only do it once and get access to all available resources without requring to do it again

usually have a timer a single authentication can work for 24hours and such and when its expired u do it again

LDAP lightweight directory access protocol for reading and writing directories over an IP network

DAP was the original one but LDAP is lightweight

it can work with OS easily so it called LDAP

X.500 distinguished names

attribute=value pairs CN=WINDGETWEB, OU=MARKTING etc

![](../../Pasted%20image%2020260504142724.png)

its like a leaf every thing has its own purpose and permissions

SAML security assertion markup l;anguage 

open standard for authentication and authorization

it never designed for mobile apps

![](../../Pasted%20image%2020260504142921.png)

Oauth is authorization framework once u authorizate determines what resources a user will be able to access

created by twitter google and others

not an authentication protocol OpenID connect handles the single sign on authentication

![](../../Pasted%20image%2020260504143025.png)

federation provide network access to others not just employees, but partners suppliers customers etc

third parties can establish a federated network

![](../../Pasted%20image%2020260504143109.png)

the third parties must establish a trust relationship and the degree of trust

interoperability, many different ways to communicate with authentication server

often determined by what is at hand, u connect to a VPN concentrator that can talk to a LDAP server. we have an LDAP server

a new app uses Oauth need to allow an authenticationAPI access

the interoperability is dependt

access control authorization it forces the policies where allows or denys data. there is process of determining the rights of policy definition

users receive rights based on access control models

least privilege  rights and permissions set bare minimum

accoutns must be limited and if there is a virus the permissions are low so it wont attack as much

MAC mandatory access control OS limits and operation on an object

labeling of objects uses predefinied rules, 

DAC used in most OS 

u create a spreadsheet u the owner so u can control who has access to the spreadsheet and some only have read only

very flexible access control and very weak security tho since people can write on it 

RBAC you have a role in ur org, manager director team lead and project manager

admins provide access based on the role of the users. maangers have their own permissions director etc.

in windows use groups to provide role based access control

you are in shipping and receiving so u can use the shipping software

rule based access control, generic term for following rules

user dont have any permission to change the rules 

we first create a rule and associated with the object

rule examples lab access is only available between 9 and 5pm. only chrome browsers may complete this web form

more modern is ABAC attribute based access control

ABAC can consider many aprameters a next gen authorization model 

combine and evaluate, resource infomration ip address time of day desired action etc

time of day restrictions. almost all security devices include a time of day option

restrict access during certain times and days 

can be difficult to implement especially in a 24hr environment

time of day restrictions training room network is inaccessible between midnight and 6am, or conference room access after 8pm and etc

---

4.6

multifacotr prove who youa re use different methods,

factors are something you know have are and somwhere you are

password is the most common one , a pin or a pattern is things u know

something you have is smart card integrates with devices

usb security key has a certificate on the usb

hardware or software tokens generates a random authentication codes

your phone  using a SMS 

something you are like biometric authentication fingerprints face scan or voice print

usually stores a mathematical representation of ur biometric

difficult to change since u can change ur password but not ur fingerprint

used  in very specific situation not foolproof


somewhere you are provide a factor based on your location

IP address not perfect works with IPv4 but hard with IPv6

mobile device locations geolocations to a very speific area. and etc

---

4.6

password complexity and length making the password strong resist guessing and brute force attacks

to increase password entropy mixing upper and lower case letters numbers and special characters

least 8 characters or 12

once a password is set there is a age. 

a password can expire in 30 60 or 90 days. notifcations tell u that it will appear saying it got expired and you need to change

critical systems change more every 15 days or every week

password manager improtant to use different passwords for each account

encrypted protected in a single database

built in to many os and some browsers

enterprise password managers an org can have it

![](../../Pasted%20image%2020260504144850.png)

passwordless authentication many breaches due to poor password control

some apps authenticate without a password

you already be passwordless like phone ID or security key

it may not be the primary authentication method u may need to use a password but forward u can use passwordless

just in time permissions in many orgs it team is assigned administrator/root evelated account rights

grant admin access for a limited time but not permanent and it will time out normally

if it breaches a user account it wont have those permissions

a user would request a central clearinghouse

password vaulting account are temporary just in time process creates a time limited account admin receives ephemeral creditiaonals..

and it can be deleted when it is complete

---

4.6 

scripting and automation it something that does stuff for you instead of doing stuff manually

if a problem occurs it tend to do it instead of manually worryin g about it

automate mundane tasks

scripting saves time, no typgin required runs multiple times over and over

enforces baselines

missing important security patch and automatically installs when identified

standard infrastructure configurations

uses a script to build a default router config, adds firewall rules and such

secure scaling u adding new servers and databases

u scaling the security with it too u build the script with firewalls and devices along with it

employee retention automate the boring stuff

reaction time automation reacts much faster than you and doesnt need a wakeup call

since they run 24/7 allows the smart people to do smart work somewhere else

user and resource provisioning on boarding and off boarding assign access to specific resources

guard rails set automated validations limit behaviors and responses and reduce errors from users

security groups assign or remove group access, constant audits without human intervention

ticket creation automatically identify issues script email submissions into a ticket

escalation correct issues before a huan if issue cant resolved contact the oncall tech

automation can enable or disable access and services in a time frame it can enable a service or disables it

they can write code updates and pushes it automatically

automation can be used APIs interact with third party devices and services cloud services, firewalls, OS and talk their language

scripting has complexity many moving parts and have to reliably work together

and they cost it takes money to create the script, and money to implement the automation

Single point of failure what happens if it stops working, and can be a deal breaker

techical debt. patching problems may push the issue down the road, it going to be expensive to fix later

and someone should suppor tthe script and later on when u change the OS or something somebody gonna updat these scripts to the latest service

---

4.8

user clicks an email attachemtn and executes malware. malware communicates with the external servers

DDoS botnet attacks

confidential information got stolen and theif wants money basically ransomware

user installs peer to peer software and allows external access to interal access

NIST SP800-61 the incident reponse lifecycle preparation detection containment eradication and recovery and post indicent activity

ocmmunication methods phones and contact information of people u need to let them know

incident handling hardware and software, laptop removable mediaa forensic software, digtital camerass and etc

incident analysis resources documentation network diagrams baselines and critical file hash values

incident mitigation software clean OS or application images

detecting a security incident

many different detection sources. different levels of detail different levels of perception

a large amount of volume is the attack incoming all the time or is it a legitimate threats?

u should know what to do and etc

analysis an incident might occur in the future and its ur heads up

web server log vulnerability scanner in use

exploit announcement monthly microsoft patch release and etc

direct threats a hacker group doesnt like you they would tell u they coming

an attack is underway or an exploit is successful

a buffer overflow attempt identified by an intrustion detection

antivirus software identifies malware

host based monitor detects a configuration change

network traffic if there is a large increase the attacker trasfering a large amount of data

a generally bad idea to let things run their course u should act quiuckly

sandboxes is isolated OS run malware and analyze the results of it and clean out the sandbox when done

isolation can sometimes be problematic it can know if there is a VM and if it fines itself in that situation it deletes itself

recovery after an incident if there is bad software remove and keep the good oines

eradicate the bug remove malware and fiux vulernabilites

and if there is backups recover the system or rebuild it from scracth and replace the compromised files and tighetn down the perimeter

and once its done we do a reflection where there is a meeting and disscus the aattack and learn and improve

we should ask questions like what happened, timeline and such

how did your incident plans work

what would you do differently next time 

did we miss something or indicators would you watych next time

theres limited on the job training when a security event occurs its late to do the training 

train the team prior to an incident what happens to the response investigation plans incident reporitng and more

this can be an expensive endeavor even with larger repsonse teams

---

4.8

before an event occurs we should test yourselves before the real thing

if u planning to do testing u should do with test systems and not the ones u working 



