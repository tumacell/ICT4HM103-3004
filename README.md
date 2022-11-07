# ICT4HM103-3004
School course repo: ICT Security Basics from Trust to Blockchain


***
## Choose correct branch for viewing the homework
***

## Homework 2

## Schneier 2015: Applied Cryptography: Chapter 2 - Protocol Building Blocks

Schneier (2015) talks about one-way functions which he considers to be central tp pub-key cryptography. They are not protocols but building blocks for protocols in cryptography.

Schneier uses a metaphor of plates as one-way functions: they are easy to break into pieces but not easy to fix back into a plate-form. He goes on that one-way functions alone are not practical for encryption for the same reason:
You can't write a message to a plate, smash it to million pieces and expect something to construct it back together.

As a solution Schneier presents trapdoor one-way function where you need a secret so that you can solve the encryption. Using another metaphor: disassembling a watch into hundreds of pieces and putting it back together is hard. However if you have secret (assembly instructions) it is possible to put the watch back together.

One-way hash functions have many names:
- compression function
- contraction function
- message diges
- fingerprint
- cryptographic checksum
- message integrity check (MIC)
- manipulation detection mode (MDC)

Like the one-way function this is also an essential building block for many protocols.

A hash function takes a variable-length input string (pre-image) and converts it to a fixed length output string  (hash value).

One-way hash function is easy to compute from pre-image but otehr way around (generating pre-image hashing to particular value) is hard.

Hash function is public and the security comes from the one-wayness. A single bit change in pre-image, hanges half of the bits in hash value. Also if given a hash value, it is almost impossible to find a pre-image that hashes to that value.

One way of understanding hash value is checking files between you and your friend. You want to find if your friend has the same files as you have. But you don't want them to send you anything. Asking for hash values and checking if they match will almost certainly verify that you have the same files.