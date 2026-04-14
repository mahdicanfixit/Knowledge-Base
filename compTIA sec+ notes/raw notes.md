
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

implement as part of your overall computing strategy

internal certs dont need to be signed by a public CA your company is the only one going to use it no need to purchase trust for devicces that already trust you

build ur own CA issue ur own cert signed by ur own CA

install the CA certificate/trsuted chain on all devices they now trust any cert signed by ur internal CA works same as the one u bought

subject alternative name SAN extension to an x.509 cert lists additional indetification information allows a cert to support amanny different domains

![](../../Pasted%20image%2020260414205904.png)

wildcard domain certs are based on the name of the server a wildcard domain will apply to all server names in domain

Certificate revocation list maintained by the CA can contain many revocations in a large file

many different reasons changes all the time

april 2014 - cve2014 heartbleed OpenSSL flaw put the private key of affected web seervers at risk was patched and older certs were moved to the CRL

![](../../Pasted%20image%2020260414210058.png)

online certs status proocol provides scalability for OCSP checks

the CA is resposible for responding to all client OCSP requestss this may not scale well

instead have the cert holder verify their own status status information is stored on the certs holder server

ocsp status is stapled into the SSL tls handshake digitally signed by the CA

ocsp online cert status protocol the browser can check cert revocqation

messages usually sent to an OCSP respoinder via http

not all browsers apps support OCSP early internet exploere verisons and some support OCSP but dont bother chekcing 
