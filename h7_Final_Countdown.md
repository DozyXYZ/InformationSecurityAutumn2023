# Task x) Homework Report Links

1) https://github.com/DozyXYZ/InformationSecurityAutumn2023/blob/main/h1_First_Steps.md
2) https://github.com/DozyXYZ/InformationSecurityAutumn2023/blob/main/h2_spiderwebs.md
3) https://github.com/DozyXYZ/InformationSecurityAutumn2023/blob/main/h3_Should_Tero_wear_a_helmet.md
4) https://github.com/DozyXYZ/InformationSecurityAutumn2023/blob/main/h4_ETAOIN.md
5) https://github.com/DozyXYZ/InformationSecurityAutumn2023/blob/main/h5_September2023!.md
6) https://github.com/DozyXYZ/InformationSecurityAutumn2023/blob/main/h6_A.Nynomous.md

# Task y) Presentation Cross Valuation
(Moodle)

# Task a) Install Firewall

Fig a1: Update System
* sudo get-apt update

![1 update debian](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/a49e7b65-f8d7-467a-b555-7347e9c92f5a)

Fig a2: Install Firewall, allowing SSH on Port 22 before enabling firewall
* sudo apt-get install ufw
* sudo ufw allow 22/tcp
* sudo ufw enable

![2 install firewall](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/43194e66-90d7-4d44-be02-7fac203558f6)

# Task b) SSH

Fig b1: Install SSH
* sudo apt-get install ssh

![3 install ssh](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/48f72278-bd60-4119-8da5-df589bb7e23d)

Fig b2: Ask for user name on the computer, start SSH, connect to SSH
* whoami
* sudo systemctl start ssh
* ssh username@localhost

![4 start ssh connect to ssh](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/948b466f-8e70-431a-aaf1-e680835146f3)

Fig b3: Create new user, never ever use bad password
* sudo adduser userx

![5 create new user](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/7290e34d-a537-4dd0-b020-451064456c9e)

Fig b4: Connect new user to the ssh server
* ssh userx@localhost

![6 connect users to the ssh server](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/797fc3fa-2f42-432e-91f3-8d3ba82c82d9)

Fig b5: Check how many users are in the server
* who -a

![7 user connected to servers](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/18ec884a-8750-4ad8-ac84-9fc497c7e497)

Fig b6: Ctrl + D to exit the server

![8 log out localhost](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/05185926-eac2-43f5-ba57-9b152e791ea8)
