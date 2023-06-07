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

- We use nmap -A to get the commonName of host 172.16.5.5
  ![Picture](../../Image/Initial%20Enumeration/2.png)
  ![Picture](../../Image/Initial%20Enumeration/3.png)

### Answer

![Picture](../../Image/Initial%20Enumeration/4.png)

## Question 2

### The way to hack 

- We use ifconfig to identify the host. Then we use fping to know which ip is alive.
  ![Picture](../../Image/Initial%20Enumeration/5.png)
- We know that we have three ip alive. So i use nmap for each ip and get the ip 172.16.5.130.
  ![Picture](../../Image/Initial%20Enumeration/6.png)
  ![Picture](../../Image/Initial%20Enumeration/7.png)

### Answer

![Picture](../../Image/Initial%20Enumeration/8.png)
