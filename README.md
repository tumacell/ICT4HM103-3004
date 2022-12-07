# ICT4HM103-3004
School course repo: ICT Security Basics from Trust to Blockchain

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

Installing Tor for windows10 was very easy. I just downloaded according to the instructions[^instructions] from https://www.torproject.org/download/ the windows version. And then installed the browser.

I roleplayed someone who is not at all familiar with computers (surprisingly easy :( ) and still was able to use the browser fine.

Installing the browser: 

![installing tor](/pics/tor1.JPG)

I put the settings so that it always connects to the Tor network automatically:

![installing tor](/pics/tor4.JPG)

From about tor (in the browser) I was able to connect to .onion version of duckduckgo

![installing tor](/pics/tor6.JPG)

![installing tor](/pics/tor7.JPG)

![installing tor](/pics/tor8.JPG)

### Browsing the Tor  network

I did not understand this part of the assignment. I thought regular browsing with Tor browser was clunky and not very user-friendly. The browser crashed multiple times and I was not able to achieve all taht much using it during a very short period of time. I will probably stay using Firefox at least for now. It was however interesting to see how the circuits changed periodically.

![installing tor](/pics/tor9.JPG)

### How does anonymity work in TOR?[^torsite], [^torwork]

Most of the questions were answered in the section How the Onion browser works. T

>Tor uses a variety of different keys, with three goals in mind: 1) encryption to ensure privacy of data within the Tor network, 2) authentication so clients know they're talking to the relays they meant to talk to, and 3) signatures to make sure all clients know the same set of relays. All the connections in Tor use TLS link encryption[^torsite]

Tor is not completely decentralized, but the idea is somewhat similar. In the first phase of this assignment I explained how sending a message in Tor works: how the different nodes peel encryption layers and how the final or exit node knows the message and where it's finally going, but does not know the origin. Sending banck a message is kind of similar: message is sent to the predecessors without knowing the whole chain and only knowing the one needed step. And in the return Tor adds again the layers of encryption in every step. And lastly the original node receives a fully encrypted response (like go to Facebook for example --> Facebook respond). And because the orgin node has both keys to decrypt the message it can understands the mssage.[^torwork] 

### What kind of the treath models could TOR fit?[^instructions]

This part of the assignment I was not able to answer. I read a couple of forum posts in stackexchange.com[^threat1] and int torprojects gitlab[^threat2]. Admittedly I ran out of time this time around.

[^torbook]: Shavers & Bair 2016: Hiding Behind the Keyboard: The Tor Browser
[^torsite]: https://support.torproject.org/about/key-management/
[^torwork]: https://medium.com/hackernoon/how-does-tor-really-work-c3242844e11f
[^instructions]: https://terokarvinen.com/2022/trust-to-blockchain-2022-autumn/
[^threat1]: https://tor.stackexchange.com/questions/27/how-does-tors-threat-model-differ-from-i2ps-threat-model
[^threat2]: https://gitlab.torproject.org/legacy/trac/-/wikis/doc/UserThreatModels