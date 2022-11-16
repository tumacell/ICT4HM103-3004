# ICT4HM103-3004
School course repo: ICT Security Basics from Trust to Blockchain

## Homework 3 Public key

### SChneier 2015 Applied Cryptography

#### Terminology

**Sender and receiver**

**Messages and Encryption**

A *cleartext* message or a *plaintext* message can be disguised or its substance can be hidden via *encryption*. This disguised message is called *ciphertext* that can be turned in to plaintext via *decryption*. A message (M) can be a stream of digitized voice, video, image or w/e. Ciphertext (C) is also binary data and around the same size as the plaintext, if it is compressed it is smaller. The functionality of encryption in mathematical notation is 

>E(M) = C

Messages can be kept secure using *cryptography* by *cryptographers*. There is also people who do *cryptanalysis* (cryptanalysts). The branch of calculus including cryptography and cryptanalysis is *cryptology*.

Decryption (D) as a process is done to ciphertext so the notation:

>D(C) = M

**Authentication, Integrity and Nonrepudiation** 

*Authentication* is there so that the receiver of a message can be certain that the sender is who they say they are and that the origin is authenticated. 
*Integrity* in a message means that it has not been altered by an outside element.
*Nonrepudiation* means that a sender can not afterwards deny that they have sent a message.

**Algorithms and Keys**

*Cryptographic algorithms* is a mathematical function used in encryption and decryption. There can be secretive algorithms that are called *restricted* algorithms. They are not used today as much as previously because in changing environments they are not possible to be maintained.

In modern cryptgraphy *keys* are used to solve the restricted algo problems. 

**Symmetric Algorithms**

- Key-based algorithm, divulging the key makes the encryption useles
- Sometimes called conventional algorithm, secret-key algorithm, single-key algorithm or one-key algorithm
- Encryption key can be calculated from decryption key and vice versa --> most symmetric algorithms encryption & decryption key are the same 

**Public-key Algorithms**

- Also called asymmetric algorithms
- Key for encrypting is different for decrypting
- Key for encryption can be made public -> encryption can be made using this, but a spesific person with the decryption key can solve the encryption
- Key cannot be calculated from encryption -> decryption
- Encryption key = public key
- Decryption key = private key

#### Computer Algorithms

**DES = Data Encryption Standard**

Most popular computer encryption algorithm. Same key is used for encryption and decryption.

**RSA = Rivest, Shamar & Adleman**

Most public-key algorithm. Can be used for encryption and digital signatures.

**DSA = Digital Signature Algorithm**

Public-key algorithm. Only for digital signatures.

#### Large Numbers

Cool chapter on the scale of these things when it comes to cryptography.

#### Communications Using Public-Key Cryptography: from start to end of "Hybrid Cryptosystems"

Symmetric algorithm = safe / vault. Anyone with the combination can open it. Someone who does not have the correct combination can not open it and has to blow it up some other way.

Encrypting in the public-key way is easy the hard part is to decrypt messages. With current computational power it is almost impossible to get the private-key to decrypt messages or whatever it is encrypted.

*Process:*

- Person A and B agree on public-key cryptosystem
- A sends B the public key
- B encrypts a message using the public key and sends the encrypted message to A
- A decrypts the message using the private key

--> no prior arrangement are required, quick and easy

This same method can be used among network users where public-keys are published in a database.

**Hybrid Cryptosystems**

Criticism towards public-key algorithms: not a substitute for symmetric algorithms. 
Public-key algos are also slow, at least 1000 times slower than symmetric algorithms.
PK algorithms are vulnerable to chosen-plaintext attack.

#### Digital Signatures

**Digital Signature Trees**

Basic idea is a digital signature scheme based on secret-key cryptography that will produce an infinite number of one-time signatures using tree structure. The root is based on sume public file and authenticating it. Root then signs one message and authenticates the sub-nodes in the tree. Then each of these nodes sign one message and authenticates its sub-nodes.

**Signing Documents with Public-Key Cryptography**

This is pretty much the same process as the earlier example of person A and B sending encrypted messages and using the public key / private key.

- A encrypts a document with her private key -> signs the document
- B receives the signed document
- B decrypts the document with A's public key -> verification of the signature

1. The signature is authentic when message is decrypted with the public key.
2. Signature can't be forged
3. Signature can't be reused or transferred to any other document
4. Signed document can't be modified. If it is modified, then the same key is no longer valid
5. Signature can't repudiated.

### Encrypt and sign a message

I started out by checking if I already had gpg installed on my Debian:

![GPG installed](/pics/gpg1.JPG)

And it seemed to be already installed. SO next thing I did was try to check out some basic information form the manual using the command:

```
man gpg
```

![GPG manual](/pics/gpg2.JPG)

After that I made a folder where I could practice this the same way I did last week. I did the same commands as were instructed in the Tips section (there was one mistake in the tips).

```
gpg --gen-key
```

After which I was prompted some basic information for the key and also the secret. First time I was too slow and the key was not generated.

![GPG prompt](/pics/gpg3.JPG)

I then did the fingerprint command 

```
gpg --fingerprint Petteri
```

I made a .txt -file to be encrypted with 
```
nano encryptfile.txt
```

and then I simply encrypted the file:

![GPG encryptfirst](/pics/gpg7.JPG)

The command was a little bit different than in the tips, since I could not get it to work. 

```
gpg -r petteri.vaskin@haaga-helia.fi -e encryptfile.txt
```

And next i decrypted the file with 

```
gpgp -d encryptfile.txt.gpg
```

And it was succesful! Although I forgot to sign the thing so I made another file calld 
> encryptfile2
firgetting the .txt, but it does not matter in this case!

![GPG success](/pics/gpg8.JPG)

And in the end it states that it has "good signature" signaling that this worked well.