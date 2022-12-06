# ICT4HM103-3004
School course repo: ICT Security Basics from Trust to Blockchain


***
## Choose correct branch for viewing the homework
***

For example homework1 for the first week's homework.

![This is an instructional image](/pics/change_branch.JPG)


## Homework 6

### Shavers & Bair 2016: Hiding Behind the Keyboard: The Tor Browser[^torbook]

The onion router or thre Tor router allows people to browse the web anonymously. It anonymizes users in a way that makes tracking almost impossible. 

Tor has been modified from Firefox browser. The midifications hide the user's orginating IP address and this makes it hard to track down the user. The browser is easy to use and almost anyone can use it without technical knowledge. 

The need for Tor is to browse the web in a way that even if you are living in an oppressive nation you are able to do it. It can allow ie. whistleblowers to communicate with government officials anonymously. The bad side is, it can also be used for wrongdoings. 

It was originally created by US government but now it is open for improvements by anyone.

#### How the Onion router works

The term onion comes from the way the Tor browser works. Tor directs the user's internet traffic through "random relays" on the Internet. First the data is layered with elliptic cryptography (unbreakable by using brute force). Encrypted data enters the first relay called *entry* and one layer of encryption is stripped and sent to the *middle*. Then another layer is stripped of encryption and the data is sent to the *exit* layer. Finally user's connetion to the desired target is established with an unencrypted connection. So it is done like peeling an onion.

Similarly if you want to send a letter anonymously you could put your letter to an envelope and direct it to the correct recipent. Then you put that envelope another envelope and direct it to a random address, then you put that envelope to yet another envelope directed to a random address.

In theory if everyone only opens one layer the letter should arrive to its intended destination in secrecy.


#### Tracking criminals using Tor

Tor is basically unbreakable and the weakest link is usually the user. Installing scripts, plugins etc. to the browser may reveal the real user even if they use the Tor browser. Therefore you should always maintain the preconfigured settings and not add anything as a plugin or w/e. Other thing is also if you use Tor in a company network. Then the network admin may see the traffic and log suspicious behaviour. Like if you email your school of a bomb threat before an exam you don't want to take using Tor browser is not a good idea.

There are methods to try to find out criminals' IP addresses. For example if I am receiving threatning emails I may answer them and *seed* my answer. Then when the bad guy opens the message and the if the email allows HTML then the tracking script in the seed should work without alerting the bad guy. However, this is a risky way and if the bad guy is smart it won't work. More safe way would be to send an attachment with some code inside it that sends the correct address to the investigators when run on the bad guy's computer.

### Installing TOR browser

![installing tor](/pics/tor1.JPG)



[^torbook]: Shavers & Bair 2016: Hiding Behind the Keyboard: The Tor Browser