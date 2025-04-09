# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

Find out the ip address of the attackers system
## NAME:N V MOHANA KRISHNA
## REG NO:212224100039
## OUTPUT:
![image](https://github.com/user-attachments/assets/a1112969-a0fc-4a6d-a61e-0ca3d7798e4d)



Invoke msfconsole:

## OUTPUT:
<img width="632" alt="image" src="https://github.com/user-attachments/assets/9339335e-3a3b-484a-9147-ed14657f93d5">




Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

<img width="710" alt="image" src="https://github.com/user-attachments/assets/9063654d-c07a-496a-879a-866b77da15c8">

Port Scanning:

Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000).
msf >  nmap -sT 192.168.29.175/24 -p1-1000

## OUTPUT:

<img width="700" alt="image" src="https://github.com/user-attachments/assets/9359a80c-eab2-41a0-b355-dd470a708606">

use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows.
msf > db_nmap 192.168.29.175/24

## OUTPUT:
<img width="681" alt="image" src="https://github.com/user-attachments/assets/06c2286a-9058-41da-af66-37d9e998e435">

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules.
cd /usr/share /metasploit-framework/modules/auxiliary
kali > ls -l

## OUTPUT:
<img width="680" alt="image" src="https://github.com/user-attachments/assets/c4c0f861-9d23-4602-b319-44d818c30af1">


Search is a powerful command in Metasploit that you can use to find what you want to locate. 
msf >search name:Microsoft type:exploit

## OUTPUT:

<img width="854" alt="image" src="https://github.com/user-attachments/assets/d282e8d6-27ae-4ad8-9e22-170089487e8d">

The info command provides information regarding a module or platform,

## OUTPUT:

<img width="836" alt="image" src="https://github.com/user-attachments/assets/21cb94ad-4423-4197-a3e5-9b46416b1fca">

## MYSQL ENUMERATION:
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

## OUTPUT:
<img width="773" alt="image" src="https://github.com/user-attachments/assets/bf2fa40c-2126-48b5-a372-4cabac84b4cb">

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

<img width="862" alt="image" src="https://github.com/user-attachments/assets/147a3e6f-2bc9-4df2-8679-0197e9a5a0ee">

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

<img width="860" alt="image" src="https://github.com/user-attachments/assets/21a71927-6410-4570-a4c8-ff6703d3ef73">

Use the set rhosts command to set the parameter and run the module, as follows

<img width="689" alt="image" src="https://github.com/user-attachments/assets/a3aaa3ef-8968-44cf-b66f-be0b24380e68">

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

<img width="778" alt="image" src="https://github.com/user-attachments/assets/f9cc1142-07e9-49c9-9f61-bf6d47aa7300">

et the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists:

set PASS_FILE /usr/share/wordlists/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS

Set BLANK_PASSWORDS to true in case there is no password set for the root account.

set BLANK_PASSWORDS true

<img width="735" alt="image" src="https://github.com/user-attachments/assets/5af9e9fe-1383-471d-83e3-315af66a9495">


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
