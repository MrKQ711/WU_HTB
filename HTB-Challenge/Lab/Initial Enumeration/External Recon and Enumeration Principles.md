# Content

- [Content](#content)
  - [Question 1](#question-1)
    - [The way to hack](#the-way-to-hack)
    - [Answer](#answer)
  
## Question 1

### The way to hack

- Check the DNS Record and the type of them.
  - The DNS server you are using does not support queries of type ANY for the domain [inlanefreight.com](http://inlanefreight.com/).
  - Instead of using the ANY query, you can try other query types like A (IP address record), CNAME (other domain record), MX (email record) and TXT (text record).
  ![Picture](../../Image/Initial%20Enumeration/External%20Recon%20and%20Enumeration%20Principles_1.png)
  ![Picture](../../Image/Initial%20Enumeration/Untitled.png)

### Answer

![Picture](../../Image/Initial%20Enumeration/Untitled1.png)
