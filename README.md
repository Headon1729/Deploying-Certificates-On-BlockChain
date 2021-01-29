# Deploying Certificates On BlockChain

model1.cto file contains the modelling of business ideas. It contains assets,participants and transactions.

logic.js contains the implementation of transactions

queries.qry contains the queries for searching seafarers according to their rank and experience

Shipping Industry- the invisible network that keeps the world running.  
In the shipping industry, someone holds the ownership of the ship while allowing someone else to send or receive their goods. As different ships are meant to carry various goods like an oil ship can't carry cargo, and vice-versa, one has to check if a particular vessel can carry the required goods. Like it, there are many things which need to be looked upon before starting a voyage like Export customs clearance for registration of cargo leaving the country. And all this management is done by ship management companies. Ship management company hire different seafarer depending on the work type, but they need to check the Authenticity of their certificates, which are then validated by the certification authority.  
 There are hundreds of certificates that the seafarer and the vessel have to maintain and renew. And it takes a lot of time to check the authenticity of them. If this whole network comprising of charter company, ship management company, certification authority, documents of vessel and seafarer are stored on a distributed ledger then it would maintain total transparency plus it would save a lot of time. So, this is the basic idea behind our project. 
 This documentation shows how to build a private business network using Hyperledger Fabric while highlighting on the different files which make up the network.


MODEL.cto
The Model file contains the assets, participants, concepts  which are neither assets nor participants and transaction. 

Certificates are the Assets; things which will be getting manipulated. They are the commodity whose ownership would be getting change. And each asset needs to be identified by a primary key. 
There is one Certificate class which holds the common attributes of all certificates and would be inherited by all the rest of certificate types.
There are 5 kinds of certificates-Training Certificate which is issued by training authority, Flag certificates, Medical Certificates, Seafarer/General Certificates and Vessel Certificates. 

Seafarer and vessel are the participants; they are the actors which will do the manipulation. Like assets, each participant needs to be identified by a primary key.
Besides this there are Training Institute , Ship Certification Authority and shipping Authority as participants.

Issue Certificate and Verify Certificate are the Transaction, which are the actual words that are going to be performed. There are 5 transactions referring to issuing 5 different kinds of certificates and 5 different transactions to verify these certificates .

Apart from this it contains concepts. Concepts are abstract classes that are not assets, participants or transactions. They are typically contained by an asset, participant or transaction.


LOGIC.js
The logic file contains different function, each of which corresponds to some transaction which is defined in the model file and tells how the operation would be performed. The functions are listed below -
1. issueTrainCertificate()
The function takes training certificate and seafarer as a parameter and issues the certificate by updating the certificate seafarer id to the id of seafarer.

2. issueMedicCertificate()
The function takes Medical certificate and seafarer as a parameter and issues the certificate by updating the certificate seafarer id to the id of seafarer.

3. issueGeneralCertificate()
The function takes general certificate and seafarer as a parameter and issues the certificate by updating the certificate seafarer id to the id of seafarer.

4. issueFlagCertificate()
The function takes training certificate and seafarer as a parameter and issues the certificate by updating the certificate seafarer id to the id of seafarer.

5. issueVesselCertificate()
The function takes vesselcertificate and vessel object as a parameter and issues the certificate by updating the certificate vessel id to the id of vessel.

6. viewAllCertificatesSeafarer()
This function returns all the certificates of the seafarer upon being called.

7. ViewAllCertificatesVessel()
This function returns all the certificates of the vessel upon being called.

8. verifyFlagCertificate()
This function takes flag certificate and certificate status (which is enum) as a parameter and changes the flag certificate status to the one that is passed.

9. verifyTrainingCertificate()
This function takes training certificate and certificate status (which is enum) as a parameter and changes the flag certificate status to the one that is passed.

10. verifySeafarerCertificate()
This function takes seafarer certificate and certificate status (which is enum) as a parameter and changes the flag certificate status to the one that is passed.

11. VerifyMedicalCertificate()
This function takes medical certificate and certificate status (which is enum) as a parameter and changes the flag certificate status to the one that is passed.

12. VerifyVesselCertificate()
This function takes vessel certificate and certificate status (which is enum) as a parameter and changes the flag certificate status to the one that is passed.

13. CertificateStatusSeafarer()
It returns CertificateId and CertificateStatus of all the certificates of the Seafarer.

14. CertificateStatusVessel()
It returns CertificateId and CertificateStatus of all the certificates of the Vessel.

15. SearchSeaFarerByParams()
This function takes the rank (string) of the seafarer as a parameter and returns all the seafarer fulfilling the requirement.

Query.qry
The query can filter results returned using criteria and can be invoked in transactions to perform operations, such as updating or removing assets on result sets. Queries are defined in a query file (.qry) in the parent directory of the business network definition. Queries contain a WHERE clause, which defines the criteria by which assets or participants are selected.
The file contains one query, this query finds the seafarers with desired rank and experience.

Access control (permission.acl)
This file contains the permission the user has i.e. what functionality or what transactions he can perform. For example a seafarer cannot issue a certificate, he can just upload them and so he only has the permission to read all kinds of certificates whereas rest of the participants training institute can read, create and update the assets, Shipping Authority can only read the certificates, Ship Certification Authority can do anything i.e. read, create and update .Vessel as a participant can also only read the certificates.


Resources

https://hyperledger.github.io/composer/v0.16/reference/cto_language.html

https://hyperledger.github.io/composer/v0.16/reference/acl_language.html

https://hyperledger.github.io/composer/v0.16/reference/js_scripts.html

https://hyperledger.github.io/composer/v0.19/tutorials/playground-tutorial.html

https://hyperledger.github.io/composer/v0.19/tutorials/developer-tutorial.html

https://hyperledger.github.io/composer/v0.19/tutorials/queries.html

https://hyperledger.github.io/composer/v0.19/api/runtime-assetregistry

https://hyperledger.github.io/composer/v0.16/api/runtime-participantregistry








# Deploying-Certificates-On-BlockChain
