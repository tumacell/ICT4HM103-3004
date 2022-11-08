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

Message authentication code (MAC or DAC / data authentication code) is one-way hash function that has a secret key. Only someone with the key can verify the hash value. 

## Linux command line basics

In my previous job I used to be responsible if overseeing Linux Oracle environment. This meant that I gave access to new users and sometimes for example gave diffrent premissions or rights to different files.[^linux] 

The Oracle environment is a bit different than the Debian environment (and I only used the console/terminal).
For example the command update the packages un your environment in Debian is
```
sudo apt-get update && upgrade 
```

wheras in the Oracle environment you would do
```
sudo yum update
```
In my opinion Linux is an environment where you can do professional stuff very efficicently. I like how convenient it is to 

```
nano newbashcript.sh
```
and then make it into a cronjob. And you can do them in your personal environment without root-privileges!
Too bad the UX is kind of sucky even in ubuntu envrionments (I have a laptop that has Ubuntu). And a lot of the time I may not be troubleshooting pre se, but I am trying to find out what thing or package i need to install or what config I need to modify in order to do something.
As an example was this week's homework. Since I do not understand Linux in-depth, during previous week I did not mirror something correctly and now I had to add some repos to some config file that I don't fully understand what it means.

Otherwise i really really like Linux.

## Cracking hashes and testing hashcat

I followed the instructions provided by the teacher[^instructions] and was able to intall hashid, hashcat and wget. But I had to do a lot of trouble shooting!

It turns out that when last week I installed the Debian 11 the OS installer set the DVD/ISO as the source for packages for mys system since I did not choose to scan for network mirrors.
Therefore when I tried the command 

```
sudo apt-get -y install hashid hashcat wget
```

I got messages like 
> E: Unable to locate package
or something like that.

After some intensive googling I found the reason for this. All I had to do was locate the correct repositories and add them to 

```
/etc/apt/sources.list
```

Simple! I sed the sources provided by itzgeek.com[^problem], although I tried to find some more official sources to solve the problem initially.

After that I was able to again follow the instructions.

You can check out [proof of doing the work in picture format](/pics/).

Some highlight for those who have to read through this:

- Originally I had some trouble installing the necessary packages:
![This is an image of problem when installing packages](/pics/hashcat1.JPG)
- I had to check the correct distro I was on (Bullseye) and then add the repos to the /etc/apt/sources.list
![This is an image of problem when installing packages2](/pics/hashcat2.JPG)
- The first problem to officially solve was 21232f297a57a5a743894a0e4a801fc3 and the answer was admin
![This is an image of solving hashes1](/pics/hashcat7.JPG)
- The NTLM hash was solveable after using the hashid and then using the correct mode 1000 with the hashcat. The correct mode was displayed in the hashid phase.
![This is an image of solving hashes2](/pics/hashcat10.JPG)


[^linux]: https://linuxhandbook.com/chmod-command/
[^instructions]: https://terokarvinen.com/2022/cracking-passwords-with-hashcat/
[^problem]: https://www.itzgeek.com/how-tos/linux/debian/setup-debian-11-official-repository-in-sources-list-etc-apt-sources-list.html