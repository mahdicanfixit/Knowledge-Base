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

segmentation is limiting the scope of the threat, separate the d
