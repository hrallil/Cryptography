## Agenda
- practical notes 
- motivation of cryptography 
- Kerck Hoff's Principle
- A primer on probability theory
- Perfect security


## Practical notes 
- 12 lectures, 
- 12 quizzes for each lecture. We have to pass 6 to be allowed to got to the exam
- Practical project at the end of the course. 
- Class is composed of alot of SVU? Computer Science Msc

## Motivation
The motivation of cryptography is to ensure that information sent from Alice to Bob, is not intercepted by a third party.

![[Pasted image 20240129123517.png]]
In the picture above, we see exactly such a scenario. Here there are many types of adversaries, this can be as simple as a listener.

In the picture, we see that the message $m$ has been encrypted with the key $k$, which is shown as $\{m\}_k$ . This is called the **CypherText**. This ensures that no third party can read the message without a key. 
When Bob has the same key $k$, we call this **symmetric crypto**. (will be used for the first 6 lectures).


## Kerck Hoff's Principle 

*A cryptosystems should be secure, even if everything about the system **Exept the key** is public knowledge*

Meaning, for many **Faulty** system, the more you share about the system, the more insecure the system can become. MitID is an example of this. 

Further more, keeping the key secure is highly important, in many cases the key will be secure by trusting a central person with it. However, this one person could be considered a security breach on its own. Once a key is out in the world (fx in a usb) it should be considered as public, even if its locked to the wrist of a *Trusted individual*.

## History of ciphers 

- ceasar's cipher. 
Here we will have 2 different functions, or ciphers: 
- $enc(m) = c$
- dec(c) = m
Here, if we have a message $m$, we find that the cipher message $c$ is defined as: 
$c_i = m_i + 3 \% 26$
and for decryption the oppossete: 
$c_i = m_i - 3 \% 26$

**Example**
enc(house) = krxvh 
dec(krxvh) = house

**This shows us that using a static key is not good**

## Using larger key spaces
Here, we use a mapping, where each letter maps to another (unused) letter in the alphabet. 
![[Pasted image 20240129131704.png]]
This is attackable through frequency attack. By simply looking at the frequency of each letter in the English language, and the frequency of each letter in the cyphertext, we can with confidence map them to eachother 


## Frequency analysis
This is a strategy to attack a cipher text. We can find the key by deducing based on frequency of values, and how frequent they normally are. In the English language  we alot of E's, meaning if we have a cypher text  which has alot of K's, then we can deduce that chances of the encryption going $E \rightarrow K$. If the encryption is symetric, then the decryption is the reverse of the encryption. 

## Viginer  cipher.
Here we use a key, which is not a number as the key. In the example below, the word *cafe* has been used.
![[Pasted image 20240129130551.png]]


To attack this cipher, we can use frequency analysis iteratively. Firstly we try every element, next we try on every other element, next every 3rd. 
By doing this, we will at some point get something which resembles English, and using that we can find the key word. 



## Thread model
There are many possible ways an attacker can try and break the encryption and decryption. 
In the picture below, we see 4 different increasingly smarter attackers. 
![[Pasted image 20240129132103.png]]
#### Attackers
- Ciphertext only attack.
- Known plaintext attack
- chosen paintext attack (CPA)
- Chosen ciphertext attack (CCA)


# A primer on probability Theory 

Probability is defined as: 
For an event $E$, we define the probability of the event happening as:
	 $0< P(E) < 1$
This can be described as:
	$P(E) = \frac{Observed}{Possible}$

Further more: 
- Compliment: $P(\bar{E}) = 1 - P(E)$
- Conjunction: $P(E_1 and E_2) = p(E_1) * P(E_2)$
- Disjunction: $P(E_1 V E_2) = p(E_1) + P(E_2)$
- Conditional probability: $P(E_1 | E_2) = \frac{P(E_1 and E_2)}{P(E_2)}$

#### Bayes and Lemune theorem



## Perfect security 
**Definition**: P(M=m | C=c) = P(M=m)





