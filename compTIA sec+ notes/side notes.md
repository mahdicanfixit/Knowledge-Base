policies procedures hardware software people digital cert: create distribute manage store revoke

this is a big big endeavor lots of planning

also refers to the binding of public keys to people or devices the cert authority its all about trust

a single shared key encrypt with the key decrypt with the same key if it gets out youll need another key

secret key algorithm a shared secret

doesnt scale very well can be challenging to distribute

very fast to use less overhead than asymmetric encrypt often combined with asymmetric encryption

public key cryptography two or more mathmatically related keys

private key keep this private

public key anyone can see this key give it away

the private key is the only key that can decrypt data encrypted with the public key you cant derive the private key from the public key

![[Pasted image 20260411195922.png]]

asymmetric encryption public key cryptography 

key generation build both the public and private key at the same time lots of randomization large prime numbers and lots of math

everyone can have the public key only alice has the private key

![[Pasted image 20260411200147.png]]

someone else holds your decryption keys your private keys are in the ahnds of a 3rd party tthis may be within your own organization

this can be a ligitmate business arrangement a business might need access to employee information government ge