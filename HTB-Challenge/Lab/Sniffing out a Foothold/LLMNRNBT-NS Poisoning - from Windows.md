# Content

- [Content](#content)
  - [Question 1](#question-1)
    - [The way to hack](#the-way-to-hack)
    - [Answer](#answer)
  
## Question 1

### The way to hack

- We open powershell and  import-module .\Inveigh.ps1 with admin priviledge and use the tool Inveigh.
![Picture](../../Image/Sniffing%20out%20a%20Foothold/13.png)
- After that, we press Esc to stop and enter GET NTLMV2UNIQUE to get all of the username.
![Picture](../../Image/Sniffing%20out%20a%20Foothold/14.png)
- Then i copy the hash of username svc_qualys to the file and come to the Linux instance to start crack it.
![Picture](../../Image/Sniffing%20out%20a%20Foothold/16.png)
- Then i use hashcat to crack the hash.
- Payload: hashcat -m 5600 svc_qualys /usr/share/wordlists/rockyou.txt
![Picture](../../Image/Sniffing%20out%20a%20Foothold/17.png)

### Answer

![Picture](../../Image/Sniffing%20out%20a%20Foothold/18.png)





