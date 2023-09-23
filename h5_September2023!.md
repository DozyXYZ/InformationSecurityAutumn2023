# Task x) Summary

## Applied Cryptography - Bruce Schneier

### One-way functions
* They are the fundamental buidling blocks for most of the public-key cryptography
* They are relative easy to compute but significant harder to reverse (take millions of year to reverse the functions)
* Example: breaking a plate is easy but put them back together is not easy
* A message encrypted with one-way function is not useful as no one could decrypt it
* Trapdoor one-way function is a special type of one-way function.
> It is easy to compute in one direction and hard to compute in the other direction </br>
> However, if you know a secret then you can compute from other direction easily </br>
> Example: it is easy to dissemble the watch, it is hard to assemble it again, but if you know the instruction or have the manual, it make the assembling task easier </br>

### One-way hash functions (aka ...
> Compression function, contraction function </br>
> Message digest, fingerprint, cryptography checksum </br>
> Message integrity check </br>
> Manipulation detection code)

* They are the fundamental for modern cryptography
* A hash function takes a variable-length input string (pre-image) and convert it to a fixed length output string (hash value)
* The point is to fingerprint the pre-image to produce a vale that indicates whether a candidate pre-image is likely to be the same as the real pre-image
* As there are infinite input but finite output, hash functions generally are many-to-one. 1 hash function possibly represent different inputs
* One-way hash function works the same way as one-way function: easy to generate the has value from the pre-image but it is hard to generate the pre-image that hashes to a particular value
* A good one-way hash function is collision free (it is hard to generate two pre-images with the same hash value)
* The security of a hash function is its one-wayness. The output is not dependent on the input and one tiny bit change will change the hash completely
* Given the hash value, it is unfeasible to compute a pre-image that hashes to that value
* Message Authentication Code MAC or Data Authentication Code DAC is a one-way hash function with the addition of a secret key:
> The hash value is a function of both the pre-image and the key </br>
> It works the same as hash function but only someone with the key can verify the hash value </br>
> You can create MAC out of a hash function or a block encryption algo.

## Phishing through email - Niklas Särökaari
Source: https://www.youtube.com/watch?v=m9YFJGSHYtY

### What is Phishing?
* Sending emails that appear to be from reputable sources to influence or gain personal information
* Email can contain a malicious attachment or link to an "seem legit" site to trick the victims provide their credentials

### Why people click phishing links?
* Out of curiosity
* Message fit their expectations
* Thought they might know the sender

### The goals of phishing - Engagement
* What are the points of the phishing campaign? Steal credentials, track and measure the number of clicks, or measure the reaction and report of employees to company

### Protection mechanisms and how to bypass them
* Sender Policy Framework (SPF): simple email validation system where the receiving mail server checks if the senders IP address is the expected one
> Before attacking, check if SPF of the victim is configured

* DomainKeys Identified Mail (DKIM): combat against spoofing an email. Sending mail server applies a digital signature, which can be validated by the recipient
* Domain Message Authentication, Reporting & Conformance (DMARC): policy to receive reports to detect possible abuse attempt
> Configured SPF and DKIM to makes your domain more reputable and legitimate in the victim's eyes

* Filtering: protection against malicious attachments, prevent poorly made phishing emails reaching its intended target. URL whitelisting / web filtering / greylisting are the techniques to counter phishing

* Site Cloning: Effective for targeted phishing campaigns where the goal is to steal creds
> always use fully qualified domain name FQDN and HTTPS

* IDN Homograph attack: register domains with foreign chars: gmail vs. gmäil

### What usually works in phishing?
* Package delivery message
* Mail from ServiceDesk / IT Department
* LinkedIn, Gmail, Dropbox, etc.
* Events that currently relevant to the company (IPOs, year end party, campaigns, etc.)
* Sharepoint like service

From Verizon 2013 Data Breach Investigation Reports, the inevitability of the click is around 16 emails, meaning if you send more than 16 emails, there is at least 1 victim click the email </br>
Clicking is not enough, the victim must provide their credentials </br>
Reconnaissance is an important step when conducting phishing campaign (study the victim)

### What to do?
* Implement SPF, DKIM, DMARC
* Keep your domain safe
* Educate and train users
* Secure your infrastructure
* Use phishing catcher such as x0rz to catch malicious phishing domains

# Task a) Hashcat and Cracking sample hash

## Install Hashcat

Fig a1: Install Hashcat
> $ sudo apt-get -y install hashid hashcat wget

![1 install Hashcat](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/e1bb4b42-6769-44e0-978d-0bd11a82c4f9)

Fig a2: Create a new directory name 'hashed', change the working directory to 'hashed', download the Rockyou dictionary as an archive file
> $ mkdir hashed </br>
> $ cd hashed </br>
> $ wget https://github.com/danielmiessler/SecLists/raw/master/Passwords/Leaked-Databases/rockyou.txt.tar.gz

![2 create a new directory and download a dictionary](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/d73e5a20-84c9-4149-8436-3c53716b3f35)

Fig a3: Extract the archive file, remove the archive, show the first few lines of the dictionary file  (.txt), count how many passwords stored in the files
> $ tar xf rockyou.txt.tar.gz </br>
> $ rm rockyou.txt.tar.gz </br>
> $ head rockyou.txt </br>
> $ wc -l rockyou.txt

![3 Extract, remove archive file, show the first few lines of the txt filesx](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/94e4cae6-c3a2-424b-944e-807bc3ec077c)

## Identify the Hash

Fig a4: Use -m parameter in hashid command to figure out the possibility of the sample hash 6b1628b016dff46e6fa35684be6acc96
> $ hashid -m 6b1628b016dff46e6fa35684be6acc96

![4 crack the sample hash](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/e320626c-0617-4129-ab1a-6038245cf23b)

## Crack the Hash

Fig a5: With hashcat, the password usually in the first 3 results. This sample choose MD5 (Hash type: 0)
> $ hashcat -m 0 '6b1628b016dff46e6fa35684be6acc96' rockyou.txt -o solved </br>
> -m 0 to select the hash type MD5 </br>
> rockyou.txt to select the dictionary </br>
> -o solved to send the output to a file name "solved" </br>

![5 command crack, save in a file](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/a61015e5-554b-48e7-97e2-f56a6a8dae55)

Fig a6: The output of the hashcat command
> Status: Cracked </br>
> Hash Type: MD5 (-m 0 parameter) </br>
> Hash Target: 6b1628b016dff46e6fa35684be6acc96 </br>
> Speed: 7882 H/s (7882 Hash per second) </br>

![6 output](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/a5a3633b-12bf-4d63-a819-aac808f05068)

Fig a7: The output Use cat command to display the content of the file 'solve', the password is 'summer'
> $ cat solved

![6 sample password](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/4fb70341-596e-4aa2-976b-c5f8b8c7fd68)

# Task b) Crack this hash: 8eb8e307a6d649bc7fb51443a06a216f

Fig b1: Use -m parameter in hashid command to figure out the possibility MD2, MD4, MD5 is the top results
> $ hashid -m 8eb8e307a6d649bc7fb51443a06a216f

![6 identify target hash](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/b4f3be7c-ad5d-4931-b505-a618265dfc23)

Fig b2: Try MD5 hash to crack the password (parameter -m 0)
> $ hashcat -m 0 '8eb8e307a6d649bc7fb51443a06a216f' rockyou.txt -o solved </br>

![7 Crack the hash](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/3d89ffee-0421-4345-bce2-4d12c0810c13)

Fig b3: The output of the hashcat command
> Status: Cracked </br>
> Hash Type: MD5 (-m 0 parameter) </br>
> Hash Target: 8eb8e307a6d649bc7fb51443a06a216f </br>
> Speed: 491.1 kH/s (491 100 Hash per second) </br>

![7 output](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/59e1a54f-823a-481e-81b6-77effaeaa345)

Fig b4: The output Use cat command to display the content of the file 'solve', the password is 'february'
> $ cat solved

![8 the hash is February](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/1043ecb8-3bed-4ae5-bbbb-c5957410214d)

# Task c) Phishing Email Scheme

## The email

From Iron Bank Anti Money Laundering Department
<mallory.remmacs@ibob-aml.bv>

Subject: Urgent: Account Verification Required

Dear Ms. Cersei Lannister,

We regret to inform you that your Iron Bank account has been temporarily suspended due to suspicious money laundering activities.
To protect your account and prevent unauthorized access, we kindly request that you verify your account information through the following link:

theironbankofbravos.com

Please note that failure to verify your account within 24 hours will result in permanent suspension.

Thank you for your prompt attention to this matter.

Sincerely,
Mallory Remmacs III
Head of Anti Money Laundering Department
The Iron Bank of Braavos, King's Landing Branch

## Analyze

The organization: The Iron Bank of Braavos, the most popular and prestigious bank in this fiction cashless society
The victims: People who have an account at the Iron Bank (middle to elite class)
The advisory: Broke-ass student who hope to phish some money to cover his daily needs

The goal of the phishing: Getting the credentials of the victims to control and empty the bank account

Technical tactics:
* Spoofed sender information: the advisory uses a fake name and email address of a well known and trusted bank
> mallory.remmacs@ibob-aml.bv - ibob: Iron Bank of Braavos, bv: Braavos same as fi: Finland

* Malicious Link: the link leads to a fake website to steal the credentials of the victims
> Fake website: theironbankofbravos.com </br>
> Real website: theironbankofbraavos.com

Psychological tactics:
* Urgency and Fear: this email create a sense of urgency and fear to pressure the recipients into taking immediate action. Bank account suspension can cause serious panic to people
* Authority and Trust: Head of the Anti Money Laundering Department gives the authority and look very legitimate in this situation
* Personalization: The email include the name of the victim to make the email look more authentic and personalized

Conclusion:
> In a cashless society, people have their money and even identity tight to the bank (Finnish ID -> Bank ID -> Make life easier in Finland). 
> So if the bank account has a problem, the account holder will have x100 problem.
> An email like this can cause people a short panic and anxiety moment.
> In a common sense, they will do verification immediately to avoid account suspension.
