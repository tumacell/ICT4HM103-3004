# ICT4HM103-3004
School course repo: ICT Security Basics from Trust to Blockchain


***
## Choose correct branch for viewing the homework
***

For example homework1 for the first week's homework.

![This is an instructional image](/pics/change_branch.JPG)


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

Enfilade and Strafer python based software. 
![Enfilade](/pics/db3.JPG)[^ransomware]
![Strafer](/pics/db4.JPG)[^ransomware]

[^tero]: https://terokarvinen.com/2022/trust-to-blockchain-2022-autumn/
[^ransomwaredb]: https://infocondb.org/con/hope/a-new-hope/combating-ransom-war-evolving-landscape-of-ransomware-infections-in-cloud-databases