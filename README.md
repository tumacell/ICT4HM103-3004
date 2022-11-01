# ICT4HM103-3004
School course repo: ICT Security Basics from Trust to Blockchain

## Homework 1: Adversial mindset

### Summary of Hutchins et al 2011[^summary]

#### Abstract and Intelligence-driven Computer Network Defense

- Long history for exploiting network vulnerabilities
- APT = Advanced persistent Threat
  - Meant for compromising data for economic or military advancement
  - Protection against the threats with best practices of enterprise level patching and hardening and reducing the most easily accessible vulnerabilities in nwtworked services
   - APT actors use advanced tools, malware and zero-day exploits
  - APT modelling is unique, but other phase based models to defensive and countermeasure strategies exist
   - ie. modelling IED attacks

- CND = Computer Network Defence
 - Base security decisions and measurements on understanding the adversary
 - Intelligence-driven CND is a risk management strategy 
   > that addresses the threat component of risk, incorporating analysis of adversaries, their capabilities, objectives, doctrine and limitations
 - The basic idea is that in a kill chain model just one mitigation may thwart the adversary -> repetition by adversary must be recognized and leveraged by the defender
 
#### Intrusion Kill Chain

- Kill chain phases
 1. Reconnaisance
  - Research identification and selecting the targets
  - Using crawling websites, mailing lists, social relationships etc.
  > Petteri's comment: as an example OSINT aka Open Source Intelligence[^osint]
 2. Weaponization
  - Remote acces trojan coupled with and exploit 
  - In example corrupted Office files, pdfs etc.
 3. Delivery
  - Delivering the weapon to the targeted environment
  - email attachments, websites, USB removable media
 4. Exploitation
  - Way of triggering the intruders' code
 5. Installation
  - Remote access trojan or backdoor on the victim's system
 6. Command and Control (C2)
  - APT malware requires usually manaul interaction bedore C2 channel is established. Once established, intruders have "hands on keyboard"
 7. Actions on objectives
  - After all the previous phases can intruders achieve their objectives
   - collecting, encrypting, extracting victim's data in the environment
 
#### Courses of Action
 
- Actions that can be used against every phase mentioned in the Intrusion Kill Chain
 1. Detect
 2. Deny
 3. Disrupt
 4. Degrade
 5. Deceive
 6. Destroy
 
### MITRE ATT&CK 

#### Tactic

- The reason for performing adversarial actions. For example hackers may want to achieve credential access

#### Techniques

- The way adversaries achieve their objectives. 

#### Procedure

- How specifically adversarial actions are implemented. For example using sudoers file to elevate privileges.

### Comparing Cyber Kill Chain and ATT&CK

Both frameworks have similarities although MITRE ATT&CK has phased the adversary actions into more phases. But for example both have Reconnaissance and Command and Control. And many of the other elements are very similar as well.

I believe ATT&CK as a more detailed overview is probably used in large enterprises or organizations like the military or other public sector organizations. Since it can be adopted as a tool for improving security and it has so much real-life information on malicious attacks, I think it may be the more comprehensive option.

### Summary of Darknet Diaries 

July 12th Episode (between eps 120 and 121.. did not realize it was actually a guest episode. Highly recommend this in any case).
<sub> Lapsu$, IBM punch cards, Australian sewage problems.... </sub>

#### Case Lapsu$
- Group of hackers had infiltrated Okta security firm's network (or so it was first reported and alleged initially)
- Screenshots posted by the hackers implicated that technical support engineer's account was compromised =>> in the worst case scenario hackers could change passwords, access restricted data etc.

#### Okta's response:
1. Figure out what was the technical impact
2. Get in front of customers and explain what had happened

- Okta traced the problem back to a hack of a third party vendor that they had thought they had already dealt with 
- They revisited the case and came to the conclusion that Okta had responded 100% like they should, but still the hackers claimed to have hacked their website

- Okta's team had been monitoring a hacker group called Lapsu$ 
 - Lapsu$' way of doing things (targetting big enterprises and claiming reputations) indicated that Okta may be a target
- Lapsu$ was very crafty and resourceful but seemed to be in the hacking business for the notoriety more than anything
- When studying logs afterwards of the third party hacking Ls movement was unconventional --> they did not exactly know how to leverage the data they received 
  - Another adversary may have been more methodical, but Ls strategy was adolescent

#### Aftermath

*** It was finally revealed that Lapsu$ actually had not cracked into Okta's support engineer's account or network. Only two of the client's account. It was very limited ***

- But the screenshots that the Lapsu$ provided (fake news about hacking) made a huge impact for Okta's reputation
  - How do you prepare yourself for these sort of attacks with little actual impact but huge impact if it is exaggerated to the public by the hackers wanting to become notorious
- Lapsu$ hackers left a huge digital trail 
- Their methods were more like that of script kiddies[^scriptkids] using social engineering, sim swapping rather than technical malware or coding skills.

#### Other topics

The episode also went over an IBM related hacking story from the 60s when punch-cards were still in use when using the computers. 
- Couple of school kids were able to figure out that changing one bit (adding one extra hole to a punch card) would disable rebooting the computer IBM were using at the time
- As a joke they added dozens of cards to the management console 
- As a result the computers were not able to reboot and it took some time for the engineers to figure out the problem
- One of the kids who was making the prank was interviewed for the podcast, he stated that he had not told IBM about the incident
 - He received a job from IBM five years later after the incident

In Australia a disgruntled ex-employee was able to hack into local sewage system using radio transmitters and their frequencies to acces pump stations remotely.
- The ex-employee was caught during the act and was sentenced to 2 years in prison.
- The sewage systems used SCADA[^scada] which is not connected to the internet, but sincce the ex-employee knew the configurations and correct frequencies, he was able to do some damage anyway.

### Installing Debian on Virtualbox

- I had already installed VirtualBox to fool around in Windows server environments since I do not have that much experience on it.
- I downloaded the xfce from [cdimage](https://cdimage.debian.org/images/unofficial/non-free/images-including-firmware/current-live/amd64/iso-hybrid/debian-live-11.5.0-amd64-xfce+nonfree.log).
- After downloading I used the steps provided by the [teacher](https://terokarvinen.com/2021/install-debian-on-virtualbox/) to install debian
 - For some reason I had to do some minor changes in the step "Insert Debian ISO Image as a Virtual CDROM", that I think was because of Windows environment
- You can check screenshots of the steps in the [pics folder](https://github.com/tumacell/ICT4HM103-3004/tree/homework1/pics)

![This is an image of Debain final phase](/pics/debian14.JPG)

| Question | Answer |
| --- | --- |
| Host OS | Windows10 |
| Physical computer used | School laptop |

[^summary]: https://lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf
[^osint]: https://osintframework.com/
[^scriptkids]: https://www.hypr.com/security-encyclopedia/script-kiddie
[^scada]: https://en.wikipedia.org/wiki/SCADA