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
<sub> Lapsu$, IBM punch cards, Australian sewage problems.... </sub>

#### Case Lapsu$
- Group of hackers had  infiltrated Okta security firm's network (or so it was first reported and alleged initially)
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
- Their methods were more like that of script kiddies using social engineering, sim swapping rather than technical malware or coding skills.

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


[^scada]: https://en.wikipedia.org/wiki/SCADA