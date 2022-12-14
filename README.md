# ICT4HM103-3004
School course repo: ICT Security Basics from Trust to Blockchain

### Homework 7[^tero]


### Combating "Ransom-War:" Evolving Landscape of Ransomware Infections in Cloud Databases[^ransomwaredb]

This presentation was presented at *A New HOPE (2022)* on July 23rd 2022 by Aditya K. Sood.

How to combat ransomware especially in cloud databases. 
The presentation's agenda was:
- A look into modern application architecture
- Cloud databases used for modern applications
- Threats against cloud databases
- Cloud databases: infection root causes
- Real world examples of compromised cloud databases
- Introducing Enfilade and Strafer tools: demo
- Conclusion

#### Modern application architecture

As an overview in modern app development there a DevOps pipeline with code and code pipeline that are part of the CI/CD (continuous integration and coninuous delivery) pipeline. Then you have different networking elements for infrastructure, security and application. And this all "lives" in a (cloud) platform where there is also the most important part - the database. 

The database is money. That is where the data is so naturally that is where your attackers will try to attack!

#### Cloud databases used for modern applications

Relational:
- Oracle
- MySQL
- Microsoft DB

Non-relational:
- *MongoDB*
- CouchDB
- *Elasticsearch*
- Cassandra

Based on your choise the way attackers are chasing after the data changes as well. So you have to prepare based on your specific needs to an attack and build threat models based on that. For example if you have some of the data in a private cloud and some of the data in public cloud. 

#### Threats against cloud databases

Because data is the goal and the money lies in the data -> attacking the databases and using Ransomware attacks makes sense for the attackers.

Viper attacks -> Destroy the databases and affect the availability of the application. 

#### Cloud databases infections: root causes

- Exposed DB administrative interfaces
 - Restrict the privileges to a specific group
- Credential cracking: weak default passwords
 - Password policies
- Exploiting security vulnerabilities in DB software
 - For example most cloud based DBs have network associated interfaces and you can access them from anywhere
- Compromising end user system to infect cloud instances
 - Attacker may install an unsuspecting user with malware and infect the cloud DB
- Lateral movement in cloud infrastructure
 - Accessing one instance may open up other vulnerabilities in the IP address space. One VM compromised they can try to scan other VMs.
- Social engineering attacks to target cloud accounts (IaaS/PaaS/SaaS)

**How to detect ransomware?**

File integrity monitoring:
 - increase in rename of file on the disks
 - files with unknown file extensions

Scannin cloud DB
 - Checking potential ransom messages
 - Listing encrypted collections in non-sql DBs (document based)
 - Crreated DBs with suspicious behavior

Outbound connectivity
 - Data exfiltration from compromised systems
 - Communication with unauthorized locations on the Internet

Examine API calls

#### Real world examples of compromised cloud databases

The lecturer show some real-life examples of corrupted elasticsearch and mongodb databases. Basically lecturer showed how tha database was completely encrypted using some sort of ransomware called Meow. 

#### Introducing Enfilade and Strafer tools: demo

Strafer was designed to detect ransomware in the elasticsearch DBs and Enfilade in monodb DBs.

#### Conclusions

Ransomware attacks are causing serious disruptions and need to be handled proactively. Cloud databases need to be regularly assessed from security point-of-view. You should utilize ML/AI models to detect anomalies and use hardened sec configs. You can use open-source tools to detect exposed db network services. Kepp the patches updated to avoid exploitation.

Enfilade and Strafer python based software. 
![Enfilade](/pics/db3.JPG) [^ransomware]
![Strafer](/pics/db4.JPG) [^ransomware]


### Attacking Modern SaaS Companies[^saas]

This presentation was presented at *NolaCon 2017* on May 19th 2017 by Sean Cassidy.

SaaS is Software As A Service: Gmail, Salesforce, M365. Exponential growth since 2008.

> In 10 years there will be 3 major operating systems: AWS, GCP and Azure - Dino A. Dai Zovi

The lecrueer states that if an attacker gets access to a developer's laptop / build server / artifact server / config management / DB... / Anything, they will basically get access to everything.

How Saas development differs from others?
- Fast iterative development cycles of days or weeks rather than months // Linchpin servers (very strict and specific roles with these servers)
- Lots of automation // Usually not a lot of security monitoring
- Emopowered engineers with lots of credentials // No security strategy or planning
- Lots of new powerful tools // You can use those tools for bad things
- Lack of security culture // Little to no budget for security

![pipeline](/pics/saas1.JPG) [^saas]

CI pipeline
- Buil is triggered
- Source code is downloaded
- Source code is compiled
- Tests are run
- Software is packaged
- Uploaded to artifact server

- So if you run your attack code on Jenkins which is used in CI pipeline -> maybe for mining BTC

![pipelinehack](/pics/saas2.JPG) [^saas]

Basically if you are able to access jenkins then you have Read and Write access to the source code, credentials, secrets etc. 

Using containers especially in web development and other sw development includes several security tradeoffs:
- Easy patching
- Fits microservices very well
- Easy to automate building and deployment
- Containers are *not* security barrier
- Biggest danger is that they are fairly new

So when Kubernetes automates deployment of containers you can bypass SSH bastion host / fw 
    kubectl exec -ti pod-name /bin/bash

It is a convenient feature of Kubernetes that you need to be vary of!

Microservices are opposite of monolithic software. They are usually pieces that center around a business area. For example in a TODO list there could be a TODO service. They usually communicate via REST API (HTTPS) and JSON. They make development easier since you don't have to know the whole code base --> services can remain up partially even when something goes wrong in another service. On the other hand services tend to have complex interaction between each other. This complexity makes it possible to exploit potential security issues like service-to-service authentication.

It is important to focus on securing the APIs by for example not using too verbose URLs like todo-list-service.production.example.com because then an attacker can figure out other environments from the URL. Developers should be knowledgeable that every address / URL they make for the API advertises to outsiders what you are able to do with the application. 

Cloud 

For example access keys can be handled carelessly and ops teams / development teams can have very wide permissions. Sometimes developers make mistakses and actually push keys to the source code. When they notice the mistake they revert the commit, which does not delete the original commit rather only reverts it and an attacker can look for those secret keys. 

>The lecturer gave a very good source for figuring out kubernetes https://www.cncf.io/phippy/the-childrens-illustrated-guide-to-kubernetes/



[^tero]: https://terokarvinen.com/2022/trust-to-blockchain-2022-autumn/
[^ransomwaredb]: https://infocondb.org/con/hope/a-new-hope/combating-ransom-war-evolving-landscape-of-ransomware-infections-in-cloud-databases
[^saas]: https://infocondb.org/con/nolacon/nolacon-2017/attacking-modern-saas-companies