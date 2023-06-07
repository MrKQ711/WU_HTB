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

- The command "rpcclient -U "" -N 172.16.5.5" is used to establish a connection to a destination server via the RPC (Remote Procedure Call) protocol.
- Here is an explanation of each part of the command:
  - rpcclient: this is the name of the tool used to interact with services that use the RPC protocol in the Windows system environment.
  - -U "": this is the option to define user credentials. In this case, empty quotation marks ("") are used to specify that no username is provided.
  - -N: this is the option to bypass the user password request. In this case, no password is provided.
  - 172.16.5.5: this is the IP address of the destination server that you want to establish an RPC connection to.
  - In a nutshell, the above statement is used to establish an RPC connection to a specific destination server, without requiring a user login or password. The rpcclient tool can be used to perform interactive operations with RPC services on the target server.
  ![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/1.png)
  - I convert 1170 from dec to hex.
  ![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/2.png)
  - Find in the list and i have.
    ![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/3.png)

### Answer

![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/4.png)

## Question 2

### The way to hack

- The command "sudo crackmapexec smb 172.16.5.5 -u forend -p Klmcargo2 --groups" is used to perform a password sniffing attack on the SMB (Server Message Block) service on a target server.
- Here is an explanation of each part of the command:
  - sudo: this is the command to execute the command with user "root" or administrator privileges, depending on the system.
  - crackmapexec: this is the name of the tool used to perform password detection attacks on services.
  - smb: this is the option to specify the SMB protocol.
  - 172.16.5.5: this is the IP address of the target server you want to attack.
  - -u forend: this is the option to define the username (in this example, the username is "forend") to use when performing the attack.
  - -p Klmcargo2: this is the option to specify the password (in this example, the password is "Klmcargo2") to use when performing the attack.
  - --groups: this is an option to tell the crackmapexec tool to list the user groups to which the provided user belongs.
  - To summarize, the above command is used to perform a password sniffing attack on the SMB service on a specific target server, using the crackmapexec tool. The user and password are provided to attempt to login to the target server and the "--groups" option is used to request listing of the user groups of the provided user.
  ![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/5.png)
  ![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/6.png)
  ![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/7.png)

### Answer

![Picture](../../Image/Deeper%20Down%20the%20Rabbit%20Hole/8.png)

