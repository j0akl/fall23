# Cyber Notes

# Sept 7

## Housekeeping

First assignment released on monday

Potential attention checker next wednesday

## What is CyberSec? Why is it important?

## CIA Triad

Confidentiality
- protects information from prying eyes

Integrity
- protects data from being altered or deleted

Availability
- data needs to be available to those authorized to access

## History

### Information Assurance (IA)

- Confidentiality
- Integrity
- Authenticity
- Non-repudiation

These properties are often secured through cryptography

## History

1500BCE - encryption on mesopotamian tablets

600-400BCE cyphers

800AD - frequency analysis to break cyphers

Caesar Cypher

Enigma Machine - WWII propels us to modern cryptography - Leads to the creation of CompSci

Phone Phreaking - learning about the telephone network
- created group calls
- eventually used exploits for free phone calls

Hacker - someone who enjoys exploring computers

Exploration is legal, explotation is not

### ARPANET - 1969

Poor security warning in '73
- HS kid accessed the network
- '83 term virus was coined
- '83 TCP/IP instated

## CyberCrime

- Break-ins for profit
- caught by a *honeypot*

## CFAA

Current computer fraud and abuse act
- criminalizes 'unauthorized access' to systems

# Sept 11

First assignment released, due Friday
- setup linux and github repo
  - use personal github for this class
  - monorepo

Office hours are different, check the email for instructions on how to use them

Quiz (Wednesday after class):
- one question from previous lecture, one from this one, one from wednesday

## Threat Modeling

STRIDE/DREAD: Windows threat modeling software

Vulnerability:
- an identified weakness within a piece of software or hardware

Threat:
- a tactic or behavior that exploits a vulnerability which could result in damage to assets

Risk:
- the likelihood that your assets are lost, damaged, or destroyed

Ad Hoc Security Sucks
- we need to be thorough in securing systems

### Thread Modeling

The process of systematically identifying the threats faced by a system

- Identify things of value we want to protect
- enumerate the attack surfaces
- hypothesize attackers and map them to
  - things they want
  - their ability to target vulnerabilities
- Survey mitigations
- Balance cost/risk

Things of Value:
- data on the phone
- data that gets sent over a network
- personal security
- the device itself

### Application Threat Modeling

I'm designing an application. What could go wrong?

- When? Where? How?

Attack Surfaces:
- Physical Proximity
  - theft, direct connection
- Social Engineering
  - Trick the user into installing malware or giving up sensitive information
- Network
  - passive data collection
  - active network attacks
- Supply Chain
  - Backdoor OS
  - Backdoor the Device
  - Intercept and compromise the device in transit

# Sept 13

## Potential attackers
- theives
  - steal phones, connect to networks
  - mitigation: passwords, mfa, biometrics, full device encryption
  - likelihood: high
  - cost of mitigation: low
- law enforcement
  - legally compel you to do things
  - infect you with surveillance malware
  - mitigation: same things as theives (careful with obsruction of justice), stop using cloud services
  - likelihood: low
  - cost of mitigation: high
- eavesdroppers
  - observe network traffic
  - mitigation: use https (cant force this everywhere), use vpn
  - likelihood: medium
  - cost of mitigation: medium
- three letter agency
  - actively attack networks
  - mitigation: vpn (not really gonna work), use tor, disable js, no cloud
  - likelihood: high
  - cost of mitigation: high

# Sept 18 (Missed last class, check online slides)

Last class was just basic linux commands and scripting, didn't miss anything.

HW1 out, play some levels of a game and some other thing
- just screenshots need to be submitted
- Due sept 24

No class wednesday

## Cryptography

Cryptography
- mathematical techniques for creating "secrets"

Cryptanalysis
- mathematical techniques for breaking secrets

Cryptology
- the study of both above terms

Terminology:
- Plaintext
  - human readable text that is unmodified
  - cryptography is protecting the plaintext password
- Encryption
  - Uses a key to convert plaintext to ciphertext
- Ciphertext
  - encrypted text that in theory can only be decoded with a key
  - this is what is sent over the next
- Decryption
  - uses the decription key to view the plaintext on the receipient machine

Goals:
- Confidentiality
- Integrity
- Authenticity
- Non-repudiation

Additional Goals
- random number generation
- anonymity
- E-voting
- Secret Sharing
- Zero-knowledge proof
- secure multi-party computation
- computation over encrypted data

## Cryptographic Protocols

What are the attackers capable of? (Threat Modeling)

Kerchhoff's Principle
- A system should be secure, even if everything about the system *except* the key is pulic knowledge

Shannon's Maxim
- The enemy knows the system

Security through obscurity doesn't work

We can presume that attackers are computationally bounded, ie
they can't brute force something until heat death
- also no quantum computers (yet)
- only need to be a bit ahead of the limit of their computational power


