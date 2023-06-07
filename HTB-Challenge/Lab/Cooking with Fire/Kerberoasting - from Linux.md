# Content

- [Content](#content)
  - [Question 1](#question-1)
    - [The way to hack](#the-way-to-hack)
    - [Answer](#answer)
  - [Question 2](#question-2)
    - [The way to hack](#the-way-to-hack-1)
    - [Answer](#answer-1)
  
## Question 1

### The way to hack

- I run command "[GetUserSPNs.py](http://getuserspns.py/) -dc-ip 172.16.5.5 INLANEFREIGHT.LOCAL/forend:Klmcargo2" is a command that is run to retrieve a user's Service Principal Name (SPN) information from a Domain Controller server.
- Specifically, this command uses the Impacket tool to connect to a Domain Controller server with an IP address of 172.16.5. It then asks to retrieve the SPN information of the user "INLANEFREIGHT.LOCAL/forend" with the password "Klmcargo2".
- SPN is a unique identifier for a service on the Windows network. Retrieving a user's SPN can provide information about the services the user has access to and uses on the network.
  ![Picture](../../Image/Cooking%20with%20Fire/1.png)
- Now I pull all TGS tickets for offline processing using the -request flag. The TGS tickets will be output in a format that can be readily provided to Hashcat or John the Ripper for offline password cracking attempts.
  ![Picture](../../Image/Cooking%20with%20Fire/2.png)
- Now I put the tgs into a file sap_tgs to hash.
  ![Picture](../../Image/Cooking%20with%20Fire/3.png)
- Now i use hashcat to get the password.
- The **`-m 13100`** in the command **`hashcat -m 13100 sap_tgs /usr/share/wordlists/rockyou.txt --force`** specifies the hash type that hashcat will be using. In this case, **`13100`** represents the hash mode for SAP TGS (Ticket-Granting Service) authentication hashes.
  ![Picture](../../Image/Cooking%20with%20Fire/4.png)
  ![Picture](../../Image/Cooking%20with%20Fire/5.png)

### Answer

![Picture](../../Image/Cooking%20with%20Fire/6.png)

## Question 2

### The way to hack

- Depend on the answer when run command.
  ![Picture](../../Image/Cooking%20with%20Fire/7.png)

### Answer

![Picture](../../Image/Cooking%20with%20Fire/8.png)