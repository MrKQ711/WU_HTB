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
  
## Question 1

### The way to hack

- I use Get-MpComputerStatus to get all information about host’s security configuration.
![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/17.png)

### Answer

![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/18.png)

## Question 2

### The way to hack

- I use net localgroup Administrators to get the information about a groups (admins)
  ![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/19.png)

### Answer

![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/20.png)

## Question 3

- I use command dsquery * -filter "(&(objectCategory=person)(objectClass=user)(userAccountControl:1.2.840.113556.1.4.803:=2))" -attr distinguishedNam
    ![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/21.png)
- I use net user /domain bross (Betty Ross = bross)
    ![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/22.png)

### The way to hack

![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/23.png)