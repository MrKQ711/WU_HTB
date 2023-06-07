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

- I run the command "sudo responder -I ens224 -wrf" is used to run Responder and provides some configuration options. Here is a description of the options in the command:
  - "sudo": Run command as root or sudo privileges to gain access and execute Responder related changes.
  - "responder": Responder program name.
  - "-I ens224": Specify the network interface to listen for and respond to requests.
  - "-wrf": Responder configuration options:
    - "w": Save the credentials (credentials) that Responder collects.
    - "r": Uses the malicious method (poisoning) mDNS/NBNS and generates spoofed responses to phishing and collects login information.
    - "f": Forward requests sent to Responder to maintain compatibility with network services.
    - In a nutshell, this command will run Responder on the ens224 network interface, listening for mDNS/NBNS requests and gathering credentials from those requests.
    ![Picture](../../Image/Sniffing%20out%20a%20Foothold/1.png)
  - After run, i get the hash of four account.
    ![Picture](../../Image/Sniffing%20out%20a%20Foothold/2.png)
    ![Picture](../../Image/Sniffing%20out%20a%20Foothold/3.png)
    ![Picture](../../Image/Sniffing%20out%20a%20Foothold/4.png)
    ![Picture](../../Image/Sniffing%20out%20a%20Foothold/5.png)

### Answer

![Picture](../../Image/Sniffing%20out%20a%20Foothold/6.png)

## Question 2

### The way to hack

- I run command to crack the hash of username backupagent
- The command "hashcat -m 5600 forend_ntlmv2 /usr/share/wordlists/rockyou.txt" is used to run Hashcat, a GPU or CPU based password cracking tool. Here is the description of the parameters in the command:
  - "hashcat": Hashcat program name.
  - "-m 5600": Specify the mode of the hash to recover. In this case, mode 5600 corresponds to NTLMv2.
  - "forend_ntlmv2": Filename (file) containing the hash to recover.
  - "/usr/share/wordlists/rockyou.txt": Path to the file containing the list of password words (wordlist) used to try the passwords.
  - In a nutshell, this command will use Hashcat to try passwords from the rockyou.txt list and attempt to recover the NTLMv2 hash contained in the forend_ntlmv2 file.
- I save the hash of username backupagent to a file and run command using this file.
![Picture](../../Image/Sniffing%20out%20a%20Foothold/7.png)
![Picture](../../Image/Sniffing%20out%20a%20Foothold/8.png)

### Answer

![Picture](../../Image/Sniffing%20out%20a%20Foothold/9.png)

## Question 3

### The way to hack

- Do step by step with the account backupagent, i also get the password of account wley.
![Picture](../../Image/Sniffing%20out%20a%20Foothold/10.png)
![Picture](../../Image/Sniffing%20out%20a%20Foothold/11.png)

### Answer

![Picture](../../Image/Sniffing%20out%20a%20Foothold/12.png)
