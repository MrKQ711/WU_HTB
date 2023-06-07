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
    - [Answer](#answer-3)
  - [Question 5](#question-5)
    - [The way to hack](#the-way-to-hack-3)
    - [Answer](#answer-4)
  
## Question 1

### The way to hack

- If we run the function `Find-InterestingDomainAcl` we will receive a massive amount of information back that we would need to dig through to make any sense of:
  - Payload: `Find-InterestingDomainAcl`
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/5.png)  
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/5.1.png)
- But in this lab, we just focus into the username wley.
- Payload:
  - $sid = Convert-NameToSid wley
  - `Get-DomainObjectACL -Identity * | ? {$_.SecurityIdentifier -eq $sid}`
  - The "Get-DomainObjectACL -Identity * | ? {$_.SecurityIdentifier -eq $sid}" command is used in an Active Directory environment in PowerShell. This command is intended to retrieve a list of Access Control Lists (ACLs) of objects in an Active Directory domain and filter ACLs based on a specific Security Identifier (SID) value.
  - Specifically, the command uses "-Identity *" to retrieve all objects in the Active Directory domain, including users, groups, computers, etc.
  - The command then uses the "? {$_.SecurityIdentifier -eq $sid}" clause to filter ACLs based on the "SecurityIdentifier" attribute. The $sid variable in this command represents a specific SID value that you want to search for.
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/6.png)
- After i have the GUID of user wley, i perform a reverse search and map to a GUID value using -RéolveGUIDS Flag
- Payload:
  - `$guid= "00299570-246d-11d0-a768-00aa006e0529"`
  - `Get-DomainObjectACL -ResolveGUIDs -Identity * | ? {$_.SecurityIdentifier -eq $guid}`
  - The "Get-DomainObjectACL -ResolveGUIDs -Identity *" command is used in an Active Directory environment in PowerShell. This command is intended to retrieve a list of Access Control Lists (ACLs) of objects in an Active Directory domain.
  - Specifically, this command uses the "-ResolveGUIDs" and "-Identity *" options to retrieve all objects in the Active Directory domain and resolve the GUIDs (Global Unique Identifier) of these objects. . GUIDs are used to represent objects in Active Directory, and resolving them helps to display complete information about the objects in the results returned.
  - The command then uses the "? {$_.SecurityIdentifier -eq $sid}" clause to filter ACLs based on the "SecurityIdentifier" attribute. The $sid variable in this command represents a specific Security Identifier (SID) value that you want to search for.
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/7.png)

### Answer

![Picture](../../Image/An%20ACE%20in%20the%20Hole/8.png)

## Question 2

### The way to hack

![Picture](../../Image/An%20ACE%20in%20the%20Hole/9.png)

### Answer

![Picture](../../Image/An%20ACE%20in%20the%20Hole/10.png)

## Question 3

### The way to hack

- I get the sid of user damundsen and reverse it.
- Payload:
  - `$sid2 = Convert-NameToSid damundsen`
  - `Get-DomainObjectACL -ResolveGUIDs -Identity * | ? {$_.SecurityIdentifier -eq $sid2} -Verbose`
  - The "Get-DomainObjectACL -ResolveGUIDs -Identity * | ? {$_.SecurityIdentifier -eq $sid2} -Verbose" command is used in an Active Directory environment in PowerShell. This command is intended to retrieve and display a list of Access Control Lists (ACLs) of objects in an Active Directory domain, based on a specific Security Identifier (SID) value specified by the $sid2 variable. .
  - Specifically, the command uses the "-ResolveGUIDs" option to resolve the GUIDs (Global Unique Identifier) of objects in Active Directory. This helps to display complete information about the objects in the returned results.
  - The command then uses the "? {$_.SecurityIdentifier -eq $sid2}" clause to filter ACLs based on the "SecurityIdentifier" attribute. The $sid2 variable represents a specific SID value that you want to search for.
  - In addition, the "-Verbose" option is used to display detailed information about the command execution.
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/11.png)

### Answer

![Picture](../../Image/An%20ACE%20in%20the%20Hole/12.png)

## Question 4

### Answer

![Picture](../../Image/An%20ACE%20in%20the%20Hole/13.png)

## Question 5

### The way to hack

- I use the format.
- Payload:
  - Get-ADGroup -Filter {Name -like "GPO Management"}
  - $guid = "21fba9fd-1a6c-471f-9e7a-36af79c7146c"  # Thay đổi thành GUID chính xác của nhóm
  - $objectAceTypes = Get-DomainObjectACL -ResolveGUIDs -Identity $guid | Select-Object -ExpandProperty ObjectAceType
  - $filteredObjectAceTypes = $objectAceTypes | Where-Object { $_ -match '^[A-Z][a-zA-Z]+-[A-Z][a-zA-Z]+$' }
  - $filteredObjectAceTypes

### Answer

![Picture](../../Image/An%20ACE%20in%20the%20Hole/14.png)