# Content

- [Content](#content)
  - [Question 1](#question-1)
    - [The way to hack](#the-way-to-hack)
    - [Answer](#answer)
  
## Question 1

### The way to hack

- I use DomainPasswordSpray tool to spraying the password.
- Payload:
  - Invoke-DomainPasswordSpray -Password Winter2022 -OutFile spray_success -ErrorAction SilentlyContinue
      - The "Invoke-DomainPasswordSpray" command in PowerShell performs a Domain Password Spray attack on a Windows Active Directory network.
      - In this attack, a single password (here, "Winter2022") is tried against many different user accounts in the domain. The goal of this attack is to find accounts with weak passwords to conduct security breaches or gain unauthorized access to the system.
      - Included parameters:
      - "-OutFile spray_success" allows specifying a file to record the accounts on which the attack succeeds.
      - "-ErrorAction SilentlyContinue" specifies that if an error occurs during the attack, PowerShell will not display the error message but continue to execute the next commands.

![Picture](../../Image/Spray%20Responsibly/4.png)

### Answer

![Picture](../../Image/Spray%20Responsibly/5.png)
