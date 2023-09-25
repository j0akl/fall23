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

# Sept 21

Cryptanalysis of the Caeser cipher:
- Trying all 25 keys is not that hard

Note: Sometimes brute force can be effective
- Key space needs to be large to prevent brute force attacks

## Monoalphabetic substitution cipher

Replace each letter X with pi(x) where x is a permutation
- Can be any letter, ex: A -> X, B -> C

Analysis:
- 26! combinations, can't brute force for humans
- Go to cipher for a long time
- was broken by frequency analysis

## Vigenere Cipher

Word: Cryptography
Key:  Luck
->    LUCKLUCKLUCK
Shift each letter in Cryptography by the index in the alphabet of the corrosponding key letter

Test:
C Y B E R S E C U R I T Y
L U C K Y L U C K Y L U C K Y
ngdoidyeeioaa this was wrong but chatgpt said so

Analysis
- Collection of shift ciphers
- Doesn't stop frequency analysis
- Broken by trying to guess the length of the key

## One Time Pad

Very long vigenere key

Analysis:
- achieves perfect secrecy
  - Ie there are no obvious patters visible
  - The ciphertext gives no information
- If you reuse the pad, frequency analysis is possible
- very difficult to distribute the pad


## Perfect Secrecy

If you have a ciphertext with length N, all plaintext strings
of length N are possible decodes

# Sept 25

## Project 2

- released by end of week
- Focus:
  - How do you use a crypto key to sign and validate messages?
  - symmetric and asymmetric encryption
  - supposed to be practical application of stuff learned in class
- due date ~two weeks from release
- need partners to sign keys
- TAs not allowed to sign keys

## Guest Lectures

- Ethics stuff, can probably skip
- Misinformation

## Project 3

Essay assignment, need partner

## Quiz Thursday if we finish cryptography unit

## Modern Symmetric Block Ciphers

- Algos that use a single key for encryption and decryption
  - algo is reversible
  - forall k forall m (Dk(Ek(m))) = m, where m is a message, k is a key, dk ek are decryption and encryption using key k
- Modern:
  - DES, 3DES, RC4, Blowfish, Twofish, AES
  - Most of these other than AES are known to be vulnerable

- Why block ciphers?
  - Defeats frequency analysis
  - encrypt by block instead of by letter

## DES (Data Encryption Standard)

- IBM, US standard from '77 to '01
- 64 bit block
- 56 bit key
- designed for fast hardware implementation
- keys too short, vulnerable to brute-force
- replaced by:

## AES

- '97, NIST
- Goal to replace DES
- Supports 128 bit block, 128, 192, 256 bit key
- 15 submissions for algo, selected Rijndael algo

- Features:
  - Designed to be efficient in software and hardware'
  - 128bit block
  - 128, 192, 256 bit key
  - *No known weaknesses at this time (128 bit key)*
  - People got through 11 rounds of encryption, but the algo has 14

AES example

Two parties have identical keys, one wants to send a message to the other

party 2 can decrypt the message because they have the key

## Block Cypher Modes

- A block cipher encrypts only one block
  - messages can be longer than that
- Need to extend to arbitrarily long messages
- Need to ensure if block cipher is secure, whole message is secure

## ECB Mode

- Message broken into blocks
- Each block encrypted separately
  - symmetric, same key used
- Don't use this in practice

## Cipher Block Chaining (CBC) Mode

- Use random init vector (random string of numbers)
- Take vector + first block of plaintext
- Use bitwise XOR with vector and plaintext
- Throw result into encryption, result is ciphertext
- Take ciphertext 1, use as init vector for block 2
- block *i* depends on block *i-1*
- Offers much more randomization

Analysis:
- Randomizes encryption
- need to protect integrity of IV
  - IV needed for decryption
  - Cannot let adversary control the IV
- Secure if block cipher is secure and IV is random and long

## Computational Complexity

Perfect secrecy is too computationally difficult to achieve in practice

Computational security relaxes in two ways:
- Security is preserved only against computationally bounded adversaries
  - No quantum computers, limit on computational power (heat death)
- Small probability of cracking is acceptable, becomes negligible (probably also heat death)

We want solutions to be verifiable in poly time or faster
- Cracking done in exponential or worse

Given finite computers, exponential time is safe

## IND-CPA Game

Ciphertext Indistinguishability under a Chosen-Plaintext Attack

Choose *k* and an encryption algo

Choose two plaintext messages (more in practice)

Choose a random binary number b

Encrypt the corrosponding message

Encrypt the message and return

Try to guess which message was chosen (b')

If you can guess correctly, does not fall under IND-CPA

If E is a perfectly secure algo, what is the probablity b=b'?
- should be 1/n where n is number of messages
- 1 if encryption is solved
- > 1/n if encryption is weak

If perfectly secure:
- given m1 m0
  - P(CT=c | Pm0) = P(CT=c | PT=m1)

Computational security means:
- P(CT=c | Pm0) ~= P(CT=c | PT=m1)
  - for a *computationally bounded adversary*

Need to be able to explain this for a quiz, seems easy enough


