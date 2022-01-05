# Lab06 Guide
## Getting Started
[Lab Introduction Video](https://youtu.be/Gz_ZKspfhuE)  
- Please clone the [Mod06 Code Examples](https://github.com/lhindman/cs121-mod06-examples.git).
- Please watch the [Activity 4 Walkthough Videos](https://www.youtube.com/playlist?list=PLbxWwkW_BhyB9fHkeDHCyzfbV6MB4IeNU).  


### Code Style Requirements
Please review the [CS121 Style Guide](https://docs.google.com/document/d/1LWbGQBKkApnNAzzgwOSvRM03DmhYWx5yEfecT2WXfjI/edit?usp=sharing) and apply it in all lab activities and projects this semester. Coding Style will assessed as part of your lab and project grades.

### Code Quality Requirements
- Code must compile without warnings using openjdk11
- Code must run without errors or warnings on safe-path and edge test cases
- More to come as we learn about input validation and exception handling 
## Activity 1 - CountFlips
### Problem Description
Revise the Coin class, found in the Module 6 examples, such that its state is represented internally using a boolean variable.  Test the new versions of the class as part of the CountFlips and FlipRace programs.
### Implementation Guide
1. Open the Module 6 code examples and copy Coin.java, FlipRace.java and CountFlips.java from the CountFlips folder into the folder named A1-CountFlips
2. Modify Coin.java as described in the Problem Description
3. Test the program using both the CountFlips driver class
4. Commit the changes to your local repository with a message stating that Activity 1 is completed.
5. Push the changes from your local repository to the github classroom repository.

## Activity 2 - Kennel
### Problem Description
Design and implement a class called *Dog* that contains instance data that represent the dog's name and age. Define the *Dog* constructor to accept and initialize instance data. Include getter and setter methods for the name and age. Include a method to compute and return the age of the dog in "person years" (seven times the dog's age). Include a *toString* method that returns a one-line description of the dog. Create a driver class called *Kennel*, whose *main* method instantiates and updates several *Dog* objects.

### Implementation Guide
1. Expand the folder named A2-Kennel and create two new files named Dog.java and Kennel.java respectively
2. Design a program to satisfy the requirements in the Problem Description and enter the program code in Dog.java and the driver code in Kennel.java
3. Test the program using the run link above the main method. Carefully think about each of the different cases you'll need to test for to verify that the application is functioning properly.
4. Commit the changes to your local repository with a message stating that Activity 2 is completed.
5. Push the changes from your local repository to the github classroom repository.

## Activity 3 - Bookshelf
### Problem Description
Design and implement a class called *Book* that contains instance data for the title, author, publisher, and copyright date. Define the *Book* constructor to accept and initialize these data. Include setter and getter methods for all instance data. Include a *toString* method that returns a nicely formatted, multiline description of the book. Create a driver class called *Bookshelf*, whose *main* method instantiates and updates several *Book* objects.

### Implementation Guide
1. Expand the folder named A3-Bookshelf and create two new files named Book.java and Bookshelf.java respectively
2. Design a program to satisfy the requirements in the Problem Description and enter the program code in Book.java and the driver code in Bookshelf.java
3. Test the program using the run link above the main method. Carefully think about each of the different cases you'll need to test for to verify that the application is functioning properly.
4. Commit the changes to your local repository with a message stating that Activity 3 is completed.
5. Push the changes from your local repository to the github classroom repository


## Activity 4 - SnakeEyes
### Problem Description
Using the *Die* class from the SnakeEyes folder in the Module 6 examples, design and implement a class called *PairOfDice*, composed of two *Die* objects. Include methods to set and get the individual die values, a method to roll the dice, and a method that returns the current sum of the two die values. Rewrite the *SnakeEyes* program using a *PairOfDice* object.

### Implementation Guide
1. Open the Module 6 code examples and copy Die.java and SnakeEyes.java from the SnakeEyes folder into the A4-SnakeEyes folder.
2. Design a program to satisfy the requirements in the Problem Description and implement it in a file named PairOfDice.java
3. Test the program using the modified version of the SnakeEyes program. Carefully think about each of the different cases you'll need to test for to verify that the application is functioning properly.
4. Commit the changes to your local repository with a message stating that Activity 4 is completed.
5. Push the changes from your local repository to the github classroom repository

## Activity 5 - GameOfPig
### Problem Description
Using the *PairOfDice* class from Activity 4, design and implement a class to play a game called Pig. In this game, the user competes against the computer. On each turn, the current player rolls a pair of dice and accumulates points. The goal is to reach 100 points before your opponent does. If, on any turn, the player rolls a 1 (on either die), all points accumulated for that round are forfeited, and control of the dice moves to the other player.  

If the player rolls two 1's in one turn, the player loses all points accumulated thus far in the game and loses control of the dice. Therefore, the player must decide either to roll again (be a pig) and risk losing points or to relinquish control of the dice, possibly allowing the other player to win. Implement the computer player such that it always relinquishes the dice after accumulating 20 or more points in any given round.

### Implementation Guide
1. Copy Die.java and PairOfDice.java from A4-SnakeEyes into the A5-GameOfPig folder.
2. Design a program to satisfy the requirements in the Problem Description and implement it in a file named GameOfPig.java
3. Test the program using the GameOfPig driver program. Carefully think about each of the different cases you'll need to test for to verify that the application is functioning properly.
4. Commit the changes to your local repository with a message stating that Activity 5 is completed.
5. Push the changes from your local repository to the github classroom repository
