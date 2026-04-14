
a public key certificate binds a public key with a digital signature and aother details about the key holder

a digital signature adds trust pki uses certificate authoritites for additional trust web of trust adds other users for additional trust

certificate creation can be built into the OS part of windows domain services many 3rd party options

![](../../Pasted%20image%2020260414205140.png)

everything associated with IT security requires trust a foundational characteristic

how to build trust from something unknown someone/something trustworthy provides their approval

refer to the root of trust an inherently trusted component hardware, software, firmware, or other components. HSM and etc

you connect to a random website do you trust it? need a good way to trust an unknown entity use a trusted third party an authority

certificate authory has digitally signed the website ceritificate you trsut the CA therefore you trust the website real time verification

built in to your browser any browser

purchase your web site certificate it will be trusted by everyone browser

CA is responsible for vetrting the request they will confirm the certificate owner additional verification information may be required by the CA

create a key pair then send the public key to the CA to be signed a certificate signing request CCSR

![](../../Pasted%20image%2020260414205545.png)

You are your own CA build it inhouse your devices must trust the internal CA

needed for medium to large organizations many web servers and privacy requirement

implement as part of your ove