# Task x) OWASP 2021

## A03:2021 Injection
The overview presents statistics related to injection vulnerabilities in applications, where injection is a major security concern. Notably, 94% of tested applications exhibited some form of injection vulnerability, with a maximum incidence rate of 19%, an average incidence rate of 3%, and 274,000 occurrences. Common Weakness Enumerations (CWEs) associated with these vulnerabilities include CWE-79 (Cross-site Scripting), CWE-89 (SQL Injection), and CWE-73 (External Control of File Name or Path).

The description highlights conditions under which applications become vulnerable to injection attacks, such as insufficient data validation, unfiltered user input, and the use of dynamic queries without proper escaping. Various types of injections, including SQL, NoSQL, and Object-Relational Mapping (ORM) injections, are mentioned. It emphasizes the importance of source code review and automated testing as methods to identify and mitigate injection vulnerabilities. Incorporating security testing tools into the CI/CD pipeline is recommended.

Prevention strategies are outlined, emphasizing the separation of data from commands and queries. This can be achieved through safe APIs, parameterized interfaces, or the use of Object Relational Mapping Tools (ORMs). Server-side input validation is also encouraged, along with escaping special characters for dynamic queries. Additionally, limitations and controls within SQL queries are suggested to prevent data disclosure in the event of SQL injection.

## A05:2021 Security Misconfiguration
The document indicates a significant increase in the prominence of security vulnerabilities arising from misconfigurations is noted, rising from the 6th position in the prior edition. Around 90% of applications underwent testing for misconfigurations, yielding an average incidence rate of 4.%, with over 208,000 instances categorized under Common Weakness Enumeration (CWE) in this risk domain. Noteworthy CWEs within this category encompass CWE-16 Configuration and CWE-611 Improper Restriction of XML External Entity Reference.

Misconfigurations in applications present vulnerability risks when exhibiting traits such as inadequate security hardening, enabling superfluous features, retaining default accounts with unchanged passwords, disclosing excessive error information, or using outdated software.

To mitigate these risks, several proactive measures should be implemented. These include the establishment of a repeatable hardening process for consistent secure environment deployment, minimizing platform features, routine configuration updates, adoption of segmented application architectures, transmission of security directives to clients, and the use of automated processes to validate configuration effectiveness across all environments. These measures collectively aim to enhance application security by reducing the likelihood of misconfigurations leading to vulnerabilities.

## A06:2021 Vunerable and Outdated Components
The document discusses the significance of Vulnerable Components within the context of software security. It mentions that Vulnerable Components rank highly in community surveys and data analysis, despite the absence of Common Vulnerability and Exposures (CVEs) associated with them. Notable Common Weakness Enumerations (CWEs) in this category include CWE-1104 (Use of Unmaintained Third-Party Components) and others from previous lists.

There are several conditions that may render an organization vulnerable to such components. This includes not knowing the versions of software components, using outdated or unsupported software, neglecting regular vulnerability scans and security bulletins, failing to patch or upgrade software in a timely manner, not testing compatibility with updated libraries, and not securing component configurations.

Preventive measures emphasized the importance of a structured patch management process. These measures include removing unnecessary components, continuously monitoring and inventorying component versions, and vulnerabilities, obtaining components from official sources via secure links, and addressing issues with unmaintained or unpatched components through virtual patches. Additionally, organizations are encouraged to maintain a long-term plan for monitoring, triaging, and applying updates and configuration changes.

# Task a) Goat

## Prerequesites
Follow the instruction on https://terokarvinen.com/2020/install-webgoat-web-pentest-practice-target/ 

> make sure you are connected to the Internet </br>
> open Terminal on Linux </br>
> use command $ sudo apt-get update </br>
> confidently type your password, you will not see it when you type due to security reason </br>
> after finishing typing, press enter </br>
> install java using command $ sudo apt-get -y install openjdk-17-jre ufw wget bash-completion </br>
> enable firewall using command $ sudo ufw enable , if everything run correctly you should see the following pic on your screen </br>

Fig a1: Prerequesites Complete! </br>
![1 java firewall](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/20f713bc-d394-46a4-b182-13f502075545)

## Install and Run WebGoat
After enabling your firewall, I used the command recommended to download webgoat but run into some errors. Therefore, I could not download Webgoat

> The certificate of 'terokarvinen.com' is not trusted. </br>
> The certificate of 'terokarvinen.com' is not yet activated. </br>

I found a work around, however it is not recommended by the replier. (https://unix.stackexchange.com/questions/334905/how-do-i-fix-wget-on-an-http-url-not-trusted-errors-in-kali)

> download Webgoat using command $ wget --no-check-certificate https://terokarvinen.com/2020/install-webgoat-web-pentest-practice-target/webgoat-server-8.0.0.M26.jar </br>
> use command to run Webgoat on $ java -jar webgoat-server-8.0.0.M26.jar </br>

Fig a2: Workaround download </br>
![3 workaround and download](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/18066864-d7eb-4587-87c2-cd1669beca66)

Fig a3: Use Java to run Webgoat </br>
![a4](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/fbeb6dba-42a5-457e-b572-780b2e50cf97)

## Register
After successfully running Webgoat

> Open your browser and use the this link to access Webgoat: http://localhost:8080/WebGoat/ </br>
> If you get everything correctly, you will see a UI like Fig a4 </br>
> Register a new account! </br>

Fig a4: Register a new Webgoat account on Firefox browser </br>
![4 webgoat register](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/ad444573-d901-44a2-9d4e-0b29d38f3c10)

# Task b) Webgoat 8: General Developer Tools

> Login Webgoat account </br>
> Choose "General" tab </br>

Fig b1: Webgoat UI </br>
![b0](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/0bd1ab81-9752-4a78-b26b-591b421fa2e2)


> Follow the instruction on Step 1, 2, 3 to Inspect and view the elements and styles of Firefox Browser </br>

Fig b2: Firefox Dev Tools </br>
![b1 firefox, elements, styles](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/08760bcd-e2af-40bc-b012-47333e3b95b6)


> Go to Console tab, use command webgoat.customjs.phoneHome() to generate a phone number </br>
> Copy the number behind after "phoneHome Response is ..." and paste it in the box to check if it is a correct number </br>

Fig b3: Generate and check phoneHome
![b3 generate phoneHome on Webgoat tab](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/217ce664-802b-4a1b-8c9e-a44bdbcde9a5)
![b3 generate phoneHome correct](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/32c0bf45-ae30-4a4f-87c9-5d8bc89e94e3)


> Go to step 6 on Webgoat lesson </br>
> Go to Network tab on developer tools </br>
> Wait for it to generate all the requests </br>
> Do not close the developer tools, go to webgoat UI, click Go! button, you will see a new request appear on Network tab </br>
> Click on the request, you will see a number </br>

Fig b4: Generate and check a request  </br>
![b4 Found it](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/a0282112-bf70-4df9-b541-0eaff5b10d75)
![ba all done](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/de6cbda7-071d-4dc2-bcfc-92eb26d1e59e)

# Task c) Update OS and all applications


