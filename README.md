# ICT4HM103-3004
School course repo: ICT Security Basics from Trust to Blockchain


***
## Choose correct branch for viewing the homework
***

For example homework1 for the first week's homework.

![This is an instructional image](/pics/change_branch.JPG)

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