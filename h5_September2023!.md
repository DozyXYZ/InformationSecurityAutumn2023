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

## Identify Hash

Fig a4: Use -m parameter in hashid command to figure out the possibility of the sample hash 6b1628b016dff46e6fa35684be6acc96
> $ hashid -m 6b1628b016dff46e6fa35684be6acc96

![4 crack the sample hash](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/e320626c-0617-4129-ab1a-6038245cf23b)

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

![7 output](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/39a14e05-1dab-4587-874c-a84fef148004)

Fig a6: The output Use cat command to display the content of the file 'solve', the password is 'summer'
> $ cat solved

![6 sample password](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/4fb70341-596e-4aa2-976b-c5f8b8c7fd68)
