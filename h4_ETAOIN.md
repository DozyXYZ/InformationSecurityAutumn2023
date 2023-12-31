# Task x) Applied Cryptocraphy, Chapter 1: Foundations

Cryptography is all about: </br>
* Authentication: the receiver of a message ascertain its origins.
* Integrity: the receiver of a message verify that it has not been modified in transit.
* Nonrepudiation: the sender should not be able to deny that he sent the message.

Cryptographic algorithm (cipher) is a mathematical function used for encryption and decryption. </br>
A cryptosystem is an algorithm, plus all possible plain text, ciphertexts and keys.

### Symmetric algorithms: the encryption key can be calculated from the decryption key and vice versa.
* Stream algorithms: algorithms operate on the plaintext a single bit or byte at a time.
* Block algorithms: algorithms operate on groups of bits.

Fig x1: Symmetric algorithms

![1 ED 1 key](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/bf86bee0-dccc-4c6e-a132-ecb6f3bda6a0)

### Public key algorithms (asymmetric algorithms): the encryption key is different from / cannot be calculated the decryption key. </br>
* Anyone can use the public (encryption) key to encrypt a message but only the specific person with the corresponding decryption (decryption) key can decrypt a message.

Fig x2: Public key algorithms

![1 ED 2 keys](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/060adc38-d9aa-4a66-b05b-fb5c71910e44)

### Cryptanalysis: the science of recovering the plaintext of a message without access to the key. An attempted crytanalysis is called an Attack.
* Ciphertext-only attack 
* Known-plaintext attack
* Chosen-plaintext attack
* Adaptive-chosen-plaintext attack
* Chosen-ciphertext attack
* Chosen-key attack
* Rubber-hose cryptanalysis / Purchase-key attack

### Security of algorithms
Different algorithms offer different degrees of security; depends on how hard they are to break. Lars Knudsen classified categories of breaking an algorithms in decreasing order of severity: </br>
* Total Break: the attacker finds the key
* Global Deduction: the attacker finds an alternate algorithm
* Instance (local) deduction: the attacker finds the plaintext of an intercepted ciphertext
* Information deduction: the attacker gains some information about the key or plaintext

Security:
* Unconditionally secure algorithm: no matter how much ciphertext the attacker has, there is not enough information to recover the plaintext
* Computationally secure algorithm: it cannot be broken with the current or future resources

Complexity of an attack:
* Data complexity: the amount of data needed as input to the attack
* Processing complexity: the time needed to perform the attack (work factor)
* Storage requirements: the amount of memory needed to do the attack

### Steganography: the science of hiding secret messages in other messages, such that the secret's very existence is concealed.

### Substitution Ciphers
* Simple (monoalphabetic) cipher: each character of plaintext is replaced with a corresponding character of ciphertext. Plaintext A -> Ciphertext N
> Caesar Cipher: 3 characters to the right in the English alphabet. A -> D, B -> E </br>
> ROT13: 13 characters to the right. A -> N, B -> O
* Homophonic substitution cipher: a single character of plaintext can map to one of several characters of ciphertext. Plaintext A -> Ciphertext 1, 12, 21, 
* Polygram substitution cipher: blocks of characters are encrypted in groups. Plaintext ABA -> Ciphertext RTQ
* Polyalphabetic substitution cipher: multiple simple substitution cipher used together.
> Running-key (book) cipher: one text is used to encrypt another cipher.

### Transposition Ciphers

The plaintext remains the same, but the order of characters is shuffled around </br>

Columar transposition cipher: https://www.youtube.com/watch?v=cPQXaYUMOjQ </br>

Fig x3: Columnar transposition cipher </br>
![Rotors](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/1753172e-b576-4eb0-a2d5-e759aa15b25b)

### XOR: exclusive-or operation, no-real security with simple XOR, trivial to break even without computer.

### One-time pad: a large nonrepeating set of truly random key letters, written on sheets of paper, and glued together in a pad.
Example: https://www.youtube.com/watch?v=6iYqHn3q8sY

### Computer algorithms
* DES - Data Encryption Standard: most popular computer encryption algorithm - symmetric
* RSA - Rivest, Shamir, Adleman - the creators: most popular public-key algorithm. used for both encryption and digital signature
* DSA - Digital Signature Algorithm, used as part of Digital signature standard, public-key algorithm but cannot be used for encryption but only for digital signatures.

# Task y) Frequency Distribution of letters in the Vietnamese Language

According to Stefan Trost Media's study of a Vietnamese text with 1 649 178 characters or 365 324 words, the 6 most common letters are:

* N: 11.01%
* H: 7.95%
* C: 6.71%
* T: 6.60%
* I: 5.71%
* A: 5.29%

Unlike other languages, the vowels a e o u i can add special characteristic and sound signs to create different pronunciation: </br>
For example: a -> ă â -> ằ ắ ẳ ẵ ặ ấ ầ ẩ ẫ ậ </br>
There are 29 letters in the Vietnamese alphabet but with special characteristics and sound signs, the maximum unique letters are 82.

Source: https://www.sttmedia.com/characterfrequency-vietnamese

# Task z) Bitwarden, Open Source Password Manager (https://github.com/bitwarden)

## What threats does it protect against?

* Password Theft: Bitwarden helps protect against password theft by securely storing and managing passwords in an encrypted vault, reducing the need for users to remember or write down passwords.
* Brute Force Attacks: Bitwarden encourages the use of strong, unique passwords for each account, making it difficult for attackers to guess passwords through brute force.
* Phishing: Bitwarden can help users avoid falling victim to phishing attacks by autofilling login credentials only on legitimate websites and not on phishing pages.
* Data Breaches: By storing passwords securely and enabling two-factor authentication (2FA), Bitwarden mitigates the impact of data breaches, as stolen passwords alone are insufficient to gain access to accounts.

## What information is encrypted, what not?

* Bitwarden encrypts various types of information, including passwords, secure notes, credit card information, and personal identity data. Essentially, any data you store within Bitwarden's vault is encrypted.</br>
* What's Not Encrypted: Bitwarden does not encrypt data that you do not explicitly store within its vault. For example, information stored outside Bitwarden, such as files on your computer or data in unsecured text files, is not automatically encrypted by Bitwarden.</br>

## What are the licenses?

* Bitwarden clients: The core password management code for individual password vaults, including Desktop, Web, Browser, Mobile, and CLI versions, is available under the GNU General Public License (GPL) 3.0 license.
* Bitwarden server: The main Bitwarden server code is licensed under the GNU Affero General Public License (AGPL) 3.0 license.

* Categorize: The GPL is a strong copyleft license, meaning that any modifications or derivative works must also be open source and share the same licensing terms. This promotes the continued openness and availability of the software.

Source: https://github.com/bitwarden/server/blob/master/LICENSE_FAQ.md

## Where is the data store?

* Bitwarden processes and stores all vault data securely in the Microsoft Azure Cloud in the US or EU using services that are managed by the team at Microsoft.

* Bitwarden Inc. is incorporated in the State of Delaware in the United States of America. 8bit Solutions LLC is wholly owned by Bitwarden Inc.

* The users and Bitwarden's agreement are governed by the federal laws of the United States of America and the laws of the State of California, without regard to conflict of law provisions. You and Bitwarden agree to submit to the exclusive jurisdiction and venue of the courts located in the State of California.

Source 1: https://bitwarden.com/terms/ </br>
Source 2: https://bitwarden.com/help/data-storage/#:~:text=Bitwarden%20processes%20and%20stores%20all%20vault%20data%20securely,is%20no%20server%20infrastructure%20to%20manage%20and%20maintain.

## How is the data protected?

* Open Source Code Base
* Zero-knowledge encryption: the company can't see the vault contents
* End-to-end encryption of the stored vault data
* Uses AES-CBC 256-bit to encrypt vault data, and PBKDF2 SHA-256 / Argon2id to derive user's encryption key from the entered password.
* Third-party independent application/code-library/network-infrastructure audits and bug bounty program

Source 1: https://bitwarden.com/help/is-bitwarden-audited/  </br>
Source 2: https://bitwarden.com/help/what-encryption-is-used/

# Task a) ETAOIN

HDMH'B TH. KWU'YI AWR WSSTOTMJJK M OWQINYIMLIY! MB KWU BII, BTGPJI BUNBHTHUHTWA OTPDIYB OMA NI NYWLIA RTHD SYIEUIAOK MAMJKBTB. BII KWU MH DHHP://HIYWLMYCTAIA.OWG </br>
THAT'S IT. YOU'RE NOW OFFICIALLY A CODEBREAKER! AS YOU SEE, SIMPLE SUBSTITUTION CIPHERS CAN BE BROKEN WITH FREQUENCY ANALYSIS. SEE YOU AT HTTP://TEROKARVINEN.COM

Fig a1: Original alphabet and substitution </br>
![Capture](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/0b855367-70f6-4845-b514-83ee10c7f2e8)

# Task b) Demonstrate the use of a password manager

## 1) Visit website: https://bitwarden.com/

## 2) Register a new account and verify your email

![1 register](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/903434b0-bd1b-4e9d-8e5b-23f5f729f8e2)
   
## 3) Add a new item to the vault

![2 UI](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/68e00eb7-b23b-41ed-9bdd-0170011f94d7)
![3 steam login item](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/178bf262-e95e-4478-aa28-c7a9f4018853)

## 4) Add extension on browser and login the extension

![4 add extension](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/9a3d44c9-d15a-40c3-93e9-9fb81a197cbc)
![5 Login into extension](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/da9e032c-fddf-4df2-b982-14c98a6dae60)

## 5) Go to webpage that you have in your password vault, click on extension, select login

![6 select autofill](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/5d55988e-a2c4-4fbd-aea1-0d9fb14618b8)
  
## 6) Complete!

![7 login complete](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/fee7fb68-4b3c-4086-ad08-121841e60b47)


# Task c) and m) Encrypt and decrypt a message

## 1) Update the system

![1 Update](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/fd6f4f2e-2d97-49e9-bcf3-32d671b9748b)

## 2) Install PGP, an encryption program that provides cryptography and authentication for data communication using a combination of public and private keys. It is recommended by Tero and many cybersecurity experts.

![2 instal pgp](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/c853e077-c2c5-413a-a866-abdf029f90a9)

## 3) Generate the keys for my email, I can send the public key to everyone I want to send a message to, I keep the private key to myself

![3 gen key](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/7783e2f2-dad9-4ab8-b527-2d842c9467de)

## 4) Export the public key to a file .asc

> -armor to change unreadable characters to readable characters </br>
> ls command to see the files in the folder </br>
> send the public key to others using email 

![4 export and ls](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/974222a3-fb62-419b-8bd9-a354d876996d)

## 5) Import the public key of the email of my friend ibrahim, he wanted to send me a message

![5 1 import](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/a927befb-b0a3-49a3-901e-1740977f154e)
![5 2 import2](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/26a9f7ce-7dac-4703-bc0a-8933de5ec1d7)

## 6) Ibrahim sent me his encrypted message via his email, I copied it to the terminal and decrypted the message

![6 decrypt](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/aa196b5e-6f52-4a14-9a2a-8fbce861555f)

## 7) Use -fingerprint to check it is the real Ibrahim and not Mallory

![7 use -fingerprint to check that it is really Ibrahim](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/05e9adaa-ea4f-4054-8244-810d4751d8a1)

## 8) I reply him back with an encrypted message

> check the Primary key fingerprint to ensure I sent to the real Ibrahim </br>
> copy the encrypted message and send to his email via my school email

![8 reply email](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/ebfba2b4-1c65-46d4-bc71-7c2c4c2f32b8)

# I had an issue with the time of the system

> use $ sudo timedatectl set-time "yyyy-mm-dd hh:mm" to set the time correctly

Reference: https://terokarvinen.com/2023/information-security-2023-autumn/#homework
