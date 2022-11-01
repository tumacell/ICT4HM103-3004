# ICT4HM103-3004
School course repo: ICT Security Basics from Trust to Blockchain

## Homework 1: Adversial mindset

### Summary of Hutchins et al 2011

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
 
- Actions against kill chain 
 1. Detect
 2. Deny
 3. Disrupt
 4. Degrade
 5. Deceive
 6. Destroy
 

### Summary of Darknet Diaries 

July 12th Episode (between eps 120 and 121.. did not realize it was actually a guest episode. Highly recommend this in any case).
> Lapsu$, IBM punch cards, Australian sewage problems....

Group of hackers had  infiltrated Okta security firm's network (or so it was first reported and alleged initially)
Screenshots implicated that technical support engineer's account was compromised
--> in the worst case scenario hackers could change passwords, access restricted data etc.

Okta's response:
1. Figure out what was the technical impact
2. Get in front of customers and explain what had happened

Traced it back to hack of a third party vendor
They had thought that they had already dealt with that scenario so at first they wanted to make sure their 
conclusions of that incident originally were correct
--> they had caught illegal password, failed mfa etc. and Okta had responded 100% like they should, but still the hackers claimed to have hacked their website.

Lapsu$
source-code Nvidia, Samsung etc.

Okta's team had been monitorign Lapsu$ and they had noticed them and came to the conclusion that their paths may cross

L was very crafty adn resourceful but seemed to be in the hacking business for the notoriety more than anything

When studying logs afterwards of the third party hacking Ls movement was unconventional --> they did not exactly know how to leverage the data they received when 
hacking in
Another adversary may have been more methodical, but Ls strategy was adolescent
They actually had not cracked into Okta's support engineer's account or network a single client's account. It was very limited

They wanted to be notorious and famous.

In the end they compromised two Okta accs.
But the screenshots that the Lapsu$ provided (fake news about hacking) made a huge impact
How do you prepare yourself for these sort of attack with little actual impact but huge impact if it is exaggerated to the public byt the hackers wanting to become notorious

Lapsu$ hackers left a huge digital trail and seemed to be more script kiddies using social engineering, sim swapping rather than technical malware or coding skills.
--> teenagers


The episode also went over an IBM related hacking story from the 60s when punch-cards were still in use when using the computers. 
- Couple of school kids were able to figure out that changing one bit (adding one extra hole to a punch card) would disable rebooting the computer IBM were using at the time
- As a joke they added dozens of cards to the management console 
- As a result 


Queensland sewage problems
Hard to map out what was the problem because of sparratic occurences
