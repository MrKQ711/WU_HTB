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

- I use SharpHound to create file AA
  ![Picture](../../Image/Stacking%20The%20Deck/1.png)
- I open BloudHound and open file AA which i create already.
  ![Picture](../../Image/Stacking%20The%20Deck/2.png)
  ![Picture](../../Image/Stacking%20The%20Deck/3.png)
- In query, i use the query.
    `MATCH p1=shortestPath((u1:User)-[r1:CanPSRemote*1..]->(g1:Group)) MATCH p2=(u1)-[:SQLAdmin*1..]->(c:Computer) RETURN p2`

### Answer

![Picture](../../Image/Stacking%20The%20Deck/4.png)

## Question 2

### The way to hack

- The way in question 1 answer for question 2.

### Answer

![Picture](../../Image/Stacking%20The%20Deck/5.png)

## Question 3

### The way to hack

- I ssh to the machine linux.
  ![Picture](../../Image/Stacking%20The%20Deck/6.png)
- Then i use tool winrm.
  ![Picture](../../Image/Stacking%20The%20Deck/7.png)
  ![Picture](../../Image/Stacking%20The%20Deck/8.png)

### Answer

![Picture](../../Image/Stacking%20The%20Deck/9.png)