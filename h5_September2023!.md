# Task x) Summary

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

![7 Crack the hash](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/b01659c1-1b65-4635-8e2c-c2fe84ac0894)

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

