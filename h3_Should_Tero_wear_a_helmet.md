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

## Shostack 2014: Chapter 1 - Dive In and Threat Model!

- Threat modeling is a skill that anyone can learn and is essential for security. </br>
- Threat modeling involves abstracting details to see the bigger security picture rather than focusing on code. </br>
- Threat modeling helps identify security issues in thing not yet built and prevents problems from occuring </br>
- Threat modeling is a practical discipline best learned through experience, similar to playing a musical instrument. </br>

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
> Define Data Flow over your DFD </br>
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

#### DREAD

> Define the impact and probability for each threat </br>
> Use DREAD formula: </br>
> </br>
> Damage - how bad would an attack be?
> Reproducibility - how easy it is to reproduce the attack?
> Exploitability - how much work is it to launch the attack?
> Affected users - how many people will be impacted?
> Discoverability - how easy it is to discover the threat?
> </br>
> Risk Value = (Damage + Affected users) x (Reproducibility + Exploitability + Discoverability) </br>

