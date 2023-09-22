# Task x) Summary

# Task a) Hashcat and Cracking sample hash

## Install Hashcat

Fig a1: Install Hashcat
> $ sudo apt-get -y install hashid hashcat wget

![1 install Hashcat](https://github.com/DozyXYZ/InformationSecurityAutumn2023/assets/142783309/e1bb4b42-6769-44e0-978d-0bd11a82c4f9)

Fig a2: Create a new directory name 'hashed' and download the Rockyou dictionary as an archive file
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
