# Task x) 

## Braiterman et al 2020: Threat modeling manifesto 

- Threat Modeling Manifesto is a guide to develop or refine methodologies. It emphasizes VALUES and PRINCIPLES like Agile Manifesto. </br>
- These values and principles aid in effective threat modeling and secure system development. </br>
- Threat modeling is about analyzing system representations to identify security and privacy concerns. </br>
- Threat modeling helps recognize system systems vulnerabilities and design flaws for early or ongoing mitigation. </br>
- 4 Questions Framwork guide threat modeling: </br>
> What are we working on? </br>
> What can go wrong? </br>
> What are we going to do about it? </br>
> Did we do a good job? </br>
- Its output - threats - informs decisions during design, development, testing, and post-deployment phases. </br>
- Anyone concerned about system privacy and security should use threat modeling. </br>

Source: https://www.threatmodelingmanifesto.org/

## Shostack 2022: Welcome to the Worlds Shortest Threat Modeling Course

The author discussed why we do threat modeling and the 4 Questions Framework

Why threat modeling? </br>
> We anticipate the problem when they're inexpensive to deal with them. </br>
> Think about threats before building anything so we have more approaches to handle. </br>

4 Questions Framework: Answer these questions to have a structure and add more details with consistency and precise.

1) What are we working on? </br>
> Collaborate to get everyone on the same table and add their ideas. </br>
> Sketch or structure the projects so that people can engage and respond. It is an imperfect start but will get better over time. </br>
> Record or document the process so we can look back, add more details, and learn new things. </br>
> Data flow diagrams with 5 entities: Processes, External Entities, Boundaries, Data Flow, Data Stores. </br>
> More details: https://github.com/adamshostack/DFD3/ </br>

2) What can go wrong? </br>
> Models such as STRIDE or cyber kill chain help us consistently think about threats, structure them, and find the answers. </br>
> - STRIDE: Spoofing, Tampering, Repediation, Information Disclosure, Denial of Service, Elevation of Privileges </br>
> - Cyber Kill Chain: Reconnaissance, Weaponization, Delivery, Exploitation, Installation, Command and Control, Actions on Objectives </br>

3) What are we going to do? </br>
> Track and treat the problems as development items in the backlog in the design process. </br>
> Make sure you do something about it. </br>
> Threat modeling informs risk management to quantify the probability or the impact to make the right decisions. </br>

4) Did we do a good job? </br>
> Would you recommend the solution to your colleague? </br>
> - Yes -> you did a good one </br>
> - No -> you have not done a good job yet. Try again :D </br>

Source: https://www.youtube.com/playlist?list=PLCVhBqLDKoOOZqKt74QI4pbDUnXSQo0nf

## OWASP CheatSheets Series Team 2021

- Threat modeling is a structured approach for identifying and prioritizing potential threats to a system and assessing the effectiveness of mitigations. </br>
- It is recommended for all developers, designers, and architects to incorporate threat modeling into their software development process. </br>
- Early threat modeling can save resources by identifying and addressing potential threats during the design phase. </br>
- When creating a threat model, one should document data flows, potential threats, and security controls to enhance system security. </br>

### Getting Started

- Define Business Objectives help you to evaluate the impact of any threat you find during the risk analysis process. </br>
- Identify application design </br>
- Create design documents </br>

### Decompose and Model the System

- To gain an understanding of how the system works to perform a threat model, it is important to understand how the system works and interacts with its ecosystem. </br>
> Define and Evaluate your Assets </br>
> Create an information flow diagram </br>
> Define Data Flow over your Data Flow Diagram </br>
> Define Truste Boundaries </br>
> Define applications user roles and trust levels </br>
> Highlight Authorization per user role over the DFD </br>
> Define Applications Entry Points </br>

### Identify Threat Agents

> Define all possible threats </br>
> Map Threat agents to application Entry points </br>
> Draw attack vectors and attacks tree </br>
> Mapping Abuse Cases to Use Cases </br>
> Re-define attack vectors </br>

### Write your Threat traceability matrix
 
> Define the impact and probability for each threat </br>

> Use DREAD to  evaluate each existing vulnerability using a mathematical formula to retrieve the vulnerability’s corresponding risk. </br>
> </br>
> Damage - how bad would an attack be? </br>
> Reproducibility - how easy it is to reproduce the attack? </br>
> Exploitability - how much work is it to launch the attack? </br>
> Affected users - how many people will be impacted? </br>
> Discoverability - how easy it is to discover the threat? </br>
> </br>
> Risk Value = (Damage + Affected users) x (Reproducibility + Exploitability + Discoverability) </br>

> Use PASTA to build a complete risk analysis and evaluation procedures that you can follow to evaluate the risk for each of the identified threat.

Fig x1: PASTA </br>
![Capture](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/94700ffc-8a99-458a-947d-edb58b2c97ad)

Sources: https://owasp.org/www-pdf-archive/AppSecEU2012_PASTA.pdf

> Use Rank Risks to build a risks matrix from most severe to least severe based on Means, Motive, and Opportunity </br>

Fig x2: Rank Risks </br>
![dbaca7bc05dbf4e08575d6e9cabae596](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/8d758444-418d-4770-8a35-c030f4435599)

Sources: https://i.pinimg.com/originals/db/ac/a7/dbaca7bc05dbf4e08575d6e9cabae596.gif

### Determine countermeasures and mitigation

> Identify risk owners </br>
> Agree on risk mitigation with risk owners and stakeholders </br>
> Build your risk treatment strategy </br>
> </br>
> - Reduce: code upgrades, specific design choices, or configuration adjustments during deployment </br>
> - Transfer: outsource development or deployment to 3rd parties who assume responsibility, and perform appropriate testing </br>
> - Avoid: disable specific functions or features in the application </br>
> - Accept: when threats fall within predefined acceptable criteria set by the risk owner </br>
> </br>
> Select appropriate controls to mitigate risks </br>
> Test risk treatment to verify remediation </br>
> Reduce risk in risk log for verified treat risk </br>
> Periodically retest risk </br>

Source: https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html

## Shostack 2014: Chapter 1 - Dive In and Threat Model!

Tips for Identifying Threats </br>
* Start with external entities: go in STRIDE order, look for spoofing then tampering on web browser. You can also start with business logic if you know the component of the process </br>
* Never ignore a threat because it's not what you're looking right now: When you come up with some threats, write them down and come back to them </br>
* Focus on feasible threats: there exists real possibilities but the likelihood that these threats occur is very low. Spend your resources to patch exploits that are common and have relatively high impact </br>

Source 1: https://www.oreilly.com/library/view/threat-modeling-designing/9781118810057/9781118810057c01.xhtml#c1
Source 2: https://libguides.haaga-helia.fi/az.php (Find Ebook Central - Require Haaga Helia Library Access)

# Task a) Security Hygiene

Use Strong Passwords </br>
> Create complex passwords with a mix of upper and lower case letters, numbers, and symbols </br>
> Use different passwords for different accounts </br>

Keep Software and Application Updated </br>
> Regularly update your operating system, web browsers, and software applications. Updates often include security patches </br>

Regular Backups </br>
> Back up important data regularly to an external hard drive or cloud storage. This can help recover your data in case of ransomware or hardware failure </br>

** Keep sensitive and private information out of your social media </br>
> The adversaries can use those to phish your networks </br> 

** Beware of the Peripherals you connect to your personal / work devices </br>
> Those can be tampered with chips that can do scary things and cost you time, money and (maybe) your jobs . </br>

** Stay alert, read carefully, control your temptation </br>
> YOU are the first line of defense and the most effective one!! </br>

# Task b) Make-belief boogie-man - a threat model for imaginary company

