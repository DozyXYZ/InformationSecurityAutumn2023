# Task x: Summary

## 7 Things you should know about Tor
Source: https://www.eff.org/deeplinks/2014/07/7-things-you-should-know-about-tor

### 1. Tor's Effectiveness and Vulnerabilities
* Tor still provides anonymity but may have certain vulnerabilities.
* Exploits like browser bugs or user misconfigurations are the main ways it can be compromised.
* Traffic correlation attacks are a concern, but Tor remains cryptographically secure.

### 2. Tor's User Base
* Tor is not exclusively used by criminals; it has diverse users, including activists, the military, families, and journalists.
* Using Tor can actually protect against criminal tactics like identity theft and stalking.

### 3. Absence of a Military Backdoor
* Despite initial funding from the US Navy, there is no military backdoor in Tor.
* Independent audits and open-source nature confirm its integrity.
* Tor is developed by privacy-focused activists.

### 4. Legal Implications of Running Tor Relays
* No known prosecutions in the US for running a Tor relay.
* EFF believes running a Tor relay is legal.
* Using Tor for criminal activity can lead to problems and increased scrutiny.

### 5. Ease of Use
* Tor is user-friendly; the Tor Browser Bundle offers a pre-configured, secure browsing experience.
* Tails is another easy option, routing all internet traffic through Tor for enhanced privacy.

### 6. Tor's Speed
* Tor is slower than regular internet connections but has improved over time.
* Increasing the number of relays can help speed up the Tor network.

### 7. Limitations of Tor
* Tor is not foolproof; incorrect use can compromise anonymity.
* Using Tor with services like Google and Facebook can reveal your identity to them.
* Adversaries with access to both ends of your connection may perform statistical analysis to identify you.

## Shavers & Bair 2016: Hiding Behind the Keyboard: The Tor Browser

### Introduction
* Tor is an Internet browser modified from Firefox
* Tor hides the user's originating IP address when surfing website or sending email, attempt to trace or identify will need extraordinary efforts
* Tor = ease of use + anonymity
* Tor is one of the most simpliest to use and freely download. Anyone with internet connection and Tor browser can anonymously surf the internet and communicate without being identified

### History and Intended Use of the Onion Router
* Tor's intention is to allow unfettered and anonymous communication over the internet (connect to blocked websites, allow whistleblowers to communicate with officials, private conversation among businesses)
* Tor can be used to faciliate and commit crimes
* Tor was initially developed by the US govt in 2002 but is not (presently) controlled bu the US govt
* Tor is practically not controlled by anyone but rather open for improvements by virtually anyone with technical ability
* Tor receives input from privacy motivated experts to ensure it remains relevant and effective
* The US fovt try to deanonymize Tor's users

### How the Onion Router Works
* Tor directs the route of a user's internet traffic through random relays on the internet
> Data -> Elliptic curve cryptography -> First relay (entry) -> Strip 1 encryption layer -> Relays (middle) Strip 1 encryption layer -> Last relay (exit) -> Connect user's desire target with unencrypted connection </br>
> Exit relay does not know anthing of the traffic route other than the single previous relay -> extremely hard to track the traffic
* Ex: A wants to send a letter to B, but he put the letter in to an envelope with address of C, then put that envelope with address of D, then put that envelope with the address of E
> The envelope will be sent to E -> E opens -> E sends the envelope to D -> D opens -> D sends envelope to C -> C opens -> C sends to B </br>
> E knows the letter come from A and go to D </br>
> D knows the letter come from E and go to C </br>
> C knows the letter come from D and go to B

Fig x1: Tor Circuit (Book Illustration)
![Capture](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/4dfdac7a-db4d-480b-a2e0-48d3aa5f56f0)

* The Onion Router as sending data over Tor is like an onion, where a layer of encryption is peeled off as it goes throught the Tor nodes to its final destination
* Tor volunteer = remove outer envelope and forward the inner envelope -> extremely hard to identify the IP address (originals or nodes)
> As of 30/09/2023, the peak user of Tor is ~6.8m and 8000 nodes worldwide (Source: https://metrics.torproject.org/) 

### Tracking Criminals using Tor
* Most of the busted crimes in Tor was not due to Tor but big brothers exploit the errors made by suspects
* The biggest weakness of Tor is the user. It is extremely recommended that the users DO NOT change any settings of the browser because anyone setting can leak information out of Tor
* Never share geolocation, Never add plugins, Never allow scripts, java or any other website requests

* Theoretical methods of attacking Tor (common goald is obtaining the true IP address)
> Attack and disable large percentage of Tor network to identify users </br>
> Gain control as many entry and exit nodes as possible to correlate traffic and identify users
> Man-in-the-middle attack: interject a capture service between the Tor user and destination

It is the user's mistake, not Tor.

* Havard student made a mistake when he used Tor to email bomb threat to the school in order to avoid taking an exam. He used Tor on the Harvard school network in the time frame of the threat mail. The IT staff and FBI busted him. Tor worked but the user sucked.

* Drug Kingpin used personal email address on the open internet for some businesses. FBI linked him to his anonymous Dark Web identity. He got life sentence.

# Task a) Install and access Tor Browser

## Fig a1: Visit Torproject website, download Tor for your OS (Linux in this case)
![1 Download Tor](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/6d6affe5-f6ee-4600-95e5-1b4fc95240b1)

## Fig a2: Go to file location that has Tor folder, select start-tor-browser.desktop
![2 go to download location, select start tor](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/ed0ab319-6ad2-4744-ad72-2b0acfea9526)

## Fig a3: Connect to the Tor network
![3 connect to Tor](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/46c749b7-600a-4627-b5ac-6bdebe3e39a9)

## Fig a4: Tor browser interface
![4 Tor Browser Interface](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/9315e656-b945-4f0f-9be7-c5080333f1c7)

## Fig a5: The Hidden Wiki
* The URL in Tor contains 56 letters and numbers end with .onion, the address is convoluted and hard to remember. The hidden wiki lists the notable addresses. You can search more with different sources. </br>
> Hidden Wiki .onion address: http://6nhmgdpnyoljh5uzr5kwlatx2u3diou4ldeommfxjz3wkhalzgjqxzqd.onion/

![5 Hidden Wiki](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/86f96d97-35ee-463c-8d49-0fc441f1a8f4)

# Task b) Dark Net Surfing (SURF AT YOUR OWN RISK)

## Fig b1: Search Engine Ahmia and Haystak for Onion Sites
* You can search with normal terms like "hacker" or "cocaine", the search engines will return the .onion addresses
> Haystak: http://haystak5njsmn2hqkewecpaxetahtwhsbsa64jom2k22z5afxhnpxfid.onion/ </br>
> Ahmia: http://juhanurmihxlp77nkq76byazcldy2hlmovfu2epvl5ankdibsot4csyd.onion/

![6 haystak](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/3bfb0469-b448-4310-ab20-67d61ed32aea)
![6 ahmia](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/f9a1969e-ea4b-44e0-a458-f2dd698d8a6a)

## Fig b2: Tom & Jerry open a drug store, payment in BITCOIN - €420 equivalent for 10g High Quality Crack Cocaine
![11 tom jerry](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/254a68b8-1d57-4056-a5b1-9afdd8d474fc)
![11 tom jerry1](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/23715ae5-c414-47ee-863b-98662781dd90)

## Fig b3: Reddit Forum, to browse memes and mocking Americans
> Reddit: https://www.reddittorjg6rue252oqsxryoxengawnmo46qy4kyii5wtqnwfj4ooad.onion/?rdt=65486

![9 reddit](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/9d64b356-91cb-4728-8a53-e227bb548116)

## Fig b4: Mark Zuckerberg want to collect your information in the Dark Net as well
> Facebook: https://www.facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion/

![10 facebook](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/f9a3fa45-8526-4e96-a6d9-71442ba22ed7)




