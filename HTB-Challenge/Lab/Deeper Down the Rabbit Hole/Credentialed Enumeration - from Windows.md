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
  - [Question 4](#question-4)
    - [The way to hack](#the-way-to-hack-3)
    - [Answer](#answer-3)
  
## Question 1

### The way to hack

- I use command Get-DomainUser -SPN -Properties samaccountname,ServicePrincipalName to get all account which have the inlanefreight.local.
  ![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/9.png)

### Answer

![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/10.png)

## Question 2

### The way to hack

- I use the function Test-AdminAccess.
  ![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/11.png)

### Answer

![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/12.png)

## Question 3

### The way to hack

- I use tool snaffler
- Payload:
  - `.\Snaffler.exe  -d INLANEFREIGHT.LOCAL -s -v data`
  - The ".\Snaffler.exe -d INLANEFREIGHT.LOCAL -s -v data" script is a command-line command to execute the Snaffler.exe program with the corresponding parameters and arguments. However, I do not have specific information about the Snaffler.exe program and the parameters used, so I cannot provide an exact description of the function of this command.
  - However, in this command there is some information that may help to better understand how the command is used:
      - ".\Snaffler.exe": This is the executable file name of the Snaffler program. The file name starts with "." refers to the current directory.
      - "-d INLANEFREIGHT.LOCAL": The "-d" parameter is used to specify the domain name or organizational unit name. Here, the value "INLANEFREIGHT.LOCAL" is provided for this parameter.
      - "-s": This can be an option to specify a specific action for the Snaffler.exe program. However, I don't know the specific action to be taken with this option.
      - "-v data": The "-v" argument can be another option, used to specify values or objects to be processed by the program. Here, the value "data" is provided for this argument.

![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/13.png)

### Answer

![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/14.png)

## Question 4

### The way to hack

- Run the command in question 3 and we also have the password.
  ![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/15.png)

### Answer

![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/16.png)