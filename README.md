# IT security summary
## Reasons for IT security
Security is becoming a massive industry within IT. As the capabilities of computers and networking grows, many more vulnerabilities are introduced. Security vulnarabilities could mean massive costs and in some cases can mean the end of a business. At this moment even governments have become vulnerable. We need to keep an eye on security to keep the IT industry healthy and safe.

### Loss of data
Loss of data could mean immense consequences. Imagine a bank losing records of all their mortgages, how would they be able to prove who their customers are? Imagine a government losing access to all personal identification information. How could you prove someone isn't a citizen of the country and how do you keep track of people under protected identity? You can see that IT security is something that is incredibly important to every person, government and industry.

# Information security as a process
Instead of seeing security as some sort of band-aid, where something went wrong and has already cause some sort of damage. Organisations are starting to implement security as a process. 

# Security vs. convenience
Having no security is very convenient for daily life. Not having to lock your car, entering your house without a key, starting up your computer without a password etc. For these conveniences, you'd have to trade security. You could see it as a scale where security is on one side and convenience is on the other.

It could be that security is too heavily implement. It would be inconvenient if it would take ten minutes to receive money from an ATM, because an employee of the bank would have to identify you through the ATM camera for instance.

**Some things require more security than others**

# C.I.A. triad
![CIA triad illustration](https://proxy.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.ibm.com%2Fblogs%2Fcloud-computing%2Fwp-content%2Fuploads%2F2018%2F01%2FTRIAD.png&f=1)
## Confidentiality
**Limiting access ot information.**

Access by rights or roles. Encryption or locked access can ensure confidentiality.

## Integrity
**Guaranteeing that information is not changed without consent or knowledge**

Measurements could be redundant storage (RAID), backups, checksums, storing data on read-only storage mediums, logging / version history.

## Availability
**Data should be available when it is needed.**

Failover (reduntant nodes in the data infrastructure),Load-balancing, disaster recovery.

# Components of Information Security

## Primitives
***"Cryptographic primitives"*** 
Basic concepts of cryptography based on mathmetics

"Any one who considers arithmetical methods of producing random digits is, of course, in a state of sin." ~ John von Neuman

### Entropy
The randomness collected by a operating system or application

## Encryption
Symetric encryption is by definition not less secure than asymmetric encryption. The security depends more key management than which technique is used.
### Substitution
The greek scytatale, ceasar cypher
### Transformation
Enigma machine
### Symetric
One key for both party, which is convenient and not complicated. Hard to keep the key safe.
### Asymetric
Two keys, one for encrypting and one for decrypting. More complicated but more secure.

### DES - Data Encryption Standard

### AES - Advanced Encryption Standard
Current standard for symmetric block encryption.

Three key lengths of 128, 192 and 256 bits respectively.

Iterations: 10, 12 or 14

One key is the private key and the other key is the public key.
### Block

### Stream

## Policies
Internal and external rules for organisations.

Laws, certifications, "common sense", company policy.

## Hashing
Ensure integrity and slightly ensure confidentiality.

### Hash collisions
When two differing inputs result into the same hash value or when a block has a pre-defined hash value.

The resilliance against hash collisions defines the integrity of a hash functions. 

### CRC
Cyclic Redundancy Check and error correction

### Checksums
Quick and computationally efficient way to verify file integrity.

### Crypto-hash
Is cryptographically secure, needs more processing power and time.
## Products
Implementations of Primivites and Policies. Software hardware and behaviour.

End goal is a safer organisation.

# Standards and certification

## Requirements
Every measurement needs a reason, these reasons are called "requirements".

There are three kinds of requirements:
- Requirements mandated by law
- Contractual requirements
- Risk analysis

## Industry specific standards

## ISO 27001
International standard for Information Security.

Defines how to establish and maintain an ISMS (Information Security Management System).

### Threat landscape


### Risk assesment
Part of ISO 27001 and PDCA, asses the risks in your organisation and describe how to act upon them.

When assessing risks, chance and impact are kept in mind.

### Plan
Plan how you wish to establish the measures described in the standard, define the scope and of the organization etc.
### Do
Implement solutions to problems, using new methods. 
### Check
Measure performance and compare the new methods with the old methods.
### Act
Look for the best solutions and integrate new methods organisation processes

### Identity and authentication management
#### Identity
Who you are
#### Authentication
How you prove your identity

#### Identity management
Starts with screening employees: Certificate of conduct, identity check etc.

#### Authentication management
By using several factors, for example:
- By what you know
- By what you have
- By what you are

#### Role/rights management
#### Access Control Lists (ACL)
Every object that needs security has its own list of authorized users and what they are allowed to do

**pro:** Simpel to understand and easy to implement

**con:** Decentralised, hard to maintain

#### Role Based Access Control (RBAC)
Every object that needs security is assigned one or multiple roles. Users are given these roles, when a user has the required role it is allowed access.

#### Attribute Based Access Control (ABAC)
Access control based on the context of the user
#### Graph Based Access Control (GBAC)
Access control based on a workflow

### Change management
Increasing security always causes more complexirt in an organisation

Timely communication and agreements prevent a lot of hassle.

# Products
The combination of primitives and policies.

"The only truly secure system is one that is powered off, cast in a block of concrete and sealed in a lead-lined room with armed guards." ~ Gene Spafford

A password is a product because it has policies to uphold to but it is also a primitive.

# TLS
Transport Layer Security

Uses asymmetric encryption to identify servers and exchange keys. Exchanged keys are used for a symmetricly encrypted session. 

Was called Secure Sockets Layer / SSL until 1999

## Certificates

## Public Key Infrastructure
1. User generates a keypair and adds identifying data to the public part. 
2. The private key remains on the computer, public key is sent to the CA as a "Certificate Signing Request".
3. The CA encrypts the CSR with the private key and sends this back. It is now a certificate.
4. User places the encrypted certificate on the website.
5. Website user downloads the certificate and decrypts it with the Operating Systems public key from the CA.

## VPN
Virtual Private Network

# Software 
## Secure coding principles

# PDCA cycle
Plan Do Check Act

