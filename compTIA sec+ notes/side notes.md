a logistical challenge how do you share an encryption key across an insecure medium without physically transferring the key?

out of band key exchange dont send the symmetric key over the net telephone, couriser, inperson etc.

inband key exchange its on the network protect the key with additional encryption use asymmetric encryption to deliver a symmetric key

theres a need for fast security without compromising the securtiy part

share a symmetric session key using assymmetric encryption cilent encrypts a random symmetric key with a server public key the server decrypts it and uses it to encrypt data this i