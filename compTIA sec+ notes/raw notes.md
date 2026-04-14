represent data as a short string of text a message digest a fingerprint

one way trip impossible to recover the original message from the digest used to store passwords confidentiality

verify a downloaded document is the same as the original integrity

SHA256 has is a 256 bits/64 hexadecimal characters

![](../../Pasted%20image%2020260414202851.png)

hash functions take an input of any size create a fixed size string message digest checksum

the has should be unique

md5 has a collision problem found in 1996 dont use md5 for anything important

![](../../Pasted%20image%2020260414203023.png)

verify a downloaded file hashes may be provided on the download site compare the downloaded file hash with the posted hash value
![](../../Pasted%20image%2020260414203054.png)

password storage instead of storing the password, store a salted hash compare hases during the authentication process nobody ever knows your actual password

salt random data added to a password when hashing

every user gets their ownrandom salt the salt is commonly stored with the password rainbow tables wont work with salted hashes additional random valueadded to the original password

this slows things down the brute force process it doesnt completely stop the reverse enginnering 

each user gets a different random hash the same password creates a different hash

![](../../Pasted%20image%2020260414203330.png)

prove the message was not changed integrity

prove the source of the message authentication

make sure the signature isnt fake non repudiatioin

sign with the private key the message doesnt need to be encrypted nobody else can sign this 

verify with the public any change in the message wil invalidate the signature

![](../../Pasted%20image%2020260414203617.png)

![](../../Pasted%20image%2020260414203717.png)

