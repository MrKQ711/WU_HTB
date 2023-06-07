# Content

- [Content](#content)
  - [Question 1](#question-1)
    - [The way to hack](#the-way-to-hack)
    - [Answer](#answer)
  
## Question 1

### The way to hack

- I use command to get all of user that login into the host 172.16.5.5 and add list into the file valid_user.txt
- The command "enum4linux -U 172.16.5.5 | grep "user:" | cut -f2 -d"[" | cut -f1 -d"]"" is used to get the list of users from the SMB (Server Message Block) server ) has an IP address of 172.16.5.5 using the Enum4linux tool. Here is a description of the steps in the command:
  - "enum4linux": Program name Enum4linux, a tool used to enumerate and collect information from SMB servers.
  - "-U 172.16.5.5": Specify the IP address of the SMB server to perform the enumeration of user information.
  - "grep "user:"": Filters and displays only lines containing the word "user:" in the output of the enum4linux command.
  - "cut -f2 -d"["": Cuts and takes only the second word in each line with "[" as delimiter.
  - "cut -f1 -d"]"": Cuts and takes only the first word in each line with "]" as the delimiter.
  - In a nutshell, this command will run enum4linux on the SMB server with IP address 172.16.5.5, filter and extract the list of users from the results and display the usernames.

![Picture](../../Image/Spray%20Responsibly/1.png)

- After that, i use crackmapexec to try to login with the valid_user.txt. Finally, i displays only the result lines containing the "+" sign to identify user accounts that can be successfully logged in.
- The command "sudo crackmapexec smb 172.16.5.5 -u valid_users.txt -p Welcome1| grep +" is used to run the CrackMapExec tool to perform SMB (Server Message Block) attack on the server with IP address 172.16.5.5 . Here is a description of the steps in the command:
  - "sudo": Run command as root or sudo privileges to gain access and execute CrackMapExec related changes.
  - "crackmapexec": Program name CrackMapExec, a tool to attack and exploit vulnerabilities in the SMB protocol.
  - "smb 172.16.5.5": Specify the SMB server to perform the attack.
  - "-u valid_users.txt": Specifies a file containing a list of valid usernames to try to login.
  - "-p Welcome1": Specify the password ("Welcome1") to be used to attempt to login to the SMB server.
  - "| grep +": Filter and display only lines containing "+" in CrackMapExec command output.
  - In a nutshell, this command will run CrackMapExec to try to login to the SMB server with a list of valid users from the valid_users.txt file and the password Password123. The command then filters and displays only the result lines containing the "+" sign to identify user accounts that can be successfully logged in.
  ![Picture](../../Image/Spray%20Responsibly/2.png)

### Answer

![Picture](../../Image/Spray%20Responsibly/3.png)
