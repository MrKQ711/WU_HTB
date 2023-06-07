# Content

- [Content](#content)
  - [Question 1](#question-1)
    - [The way to hack](#the-way-to-hack)
    - [Answer](#answer)
  
## Question 1

### The way to hack

- The above command is used to perform the check and determine the list of users available on the domain "inlanefreight.local" in the Microsoft Active Directory system environment.
- Here is an explanation of each part of the command:
  - kerbrute: this is the name of the tool used to perform Brute Force attacks on Kerberos systems. Kerberos is a widely used network authentication protocol in Windows environments.
  - userenum: this is an operating mode of the kerbrute engine to search for users in the system.
  - -d inlanefreight.local: this is the option to specify the specific domain that the user wants to check.
  - --dc 172.16.5.5: this is the option to specify the IP address of the domain controller server (Domain Controller) to which the kerbrute engine should send query requests.
  - /opt/jsmith.txt: this is the path to the file containing the list of user names (in this example, the file is "jsmith.txt"). The kerbrute tool will try the usernames in this file to determine if they exist in the system.

![Picture](../../Image/Sighting%20In,%20Hunting%20For%20A%20User/5.png)
![Picture](../../Image/Sighting%20In,%20Hunting%20For%20A%20User/6.png)

### Answer

![Picture](../../Image/Sighting%20In,%20Hunting%20For%20A%20User/7.png)