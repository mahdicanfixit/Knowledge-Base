protect data on storage devices ssd hard drive usb drive cloud storage etc this is data at rest

full disk and partition volume encryption bitlocker filevault etc

file encryption EFS encrypting file system, third party utilities

protecting stored data and the transmission of that data

transparent encryption encrypt all database information with a symmetric key

record-level encryption encrypt individual columns

![[Pasted image 20260411200813.png]]

![[Pasted image 20260411200841.png]]

![[Pasted image 20260411200909.png]]

protect data traversing the network youre prob doing this now

encrypting in the application browsers can communicate using HTTPS 

vpn encrypts alll data transmitted over the network regardless of the app  cilent based using SSL tls 

site to site VPN using IPsec

there are many different ways to encrypt datga the proper formula must be used during encryption and decryption

both sides decide on the algorithm before encrypting the data the deatilsare often hidden from the end user

there are advantages and disadvantages between algorithms security lvl speed and complexity etc

![[Pasted image 20260411201141.png]]

theres very little that isnt known about the cryptographic process the algorithm is usually a knwon entity the only thing you dont know is the key

the key determines the output encrypted data hash value digital signature

keep your key private its the only thing protecting your data

larger keys tend to be more secure prevent brute force attacks attackers can try every possible key combination

symmetric encryption 128 bits or larger are common these numbers ger larger and larger as time goes on

asymmetric encryption complex calculations larger keys than symmetric

a weak key is a weak key by itself its not very secure

make a weak key stronger by performing multiple processes hash a password hash over and over strecthing the key

brute force attacks would require reversing each of those hashes