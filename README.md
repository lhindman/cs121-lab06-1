# Module 6 Lab Guide (part 1)
## Getting Started
[Lab Introduction Video](https://youtu.be/Gz_ZKspfhuE)  

### Code Style Requirements
Please review the [CS121 Style Guide](https://docs.google.com/document/d/1LWbGQBKkApnNAzzgwOSvRM03DmhYWx5yEfecT2WXfjI/edit?usp=sharing) and apply it in all lab activities and projects this semester. Coding Style will assessed as part of your lab and project grades.

### Code Quality Requirements
- Code must compile without warnings using openjdk11
- Code must run without errors or warnings on safe-path and edge test cases
- More to come as we learn about input validation and exception handling 

## Lab Warmup - FlowSample (required)
### Problem Description
Create a class called FlowSample that represents a single, point-in-time snapshot, of USGS river flow water data. For this lab we will be using data collected from the [Boise River at the Glenwood Bridge](https://waterdata.usgs.gov/monitoring-location/13206000/#parameterCode=00065&period=P7D). A sample data file containing 7 days worth of samples has been included. Detailed information on the format of this information can be found on the [USGS NWIS Help Site](http://help.waterdata.usgs.gov/faq/about-tab-delimited-output). 

Each sample contains the following values:
- Agency
- SiteNumber
- Timestamp
- TimeZone
- GageHeight (water level) in feet
- QualificationCode (P means provisional value, subject to change)

### Program Design
The FlowSample class will represent a single sample of data.  It should contain private instance variables for each of the above sample values with data types as follows:
- String: agency, siteNumber, timeZone and qualCode
- double: data
- DataTime: timestamp

The constructor for FlowSample should be an initial value constructor with the following header signature:
```
public FlowSample(String agency, String siteNumber, String timeZone, String qualCode, String timestamp, double data)
```

Once created, a sample should not be able to be modified, so no mutator (setter) methods should be created. However accessor (getter) methods should be created for each of the instance variables except time zone. Two accessor methods should be implemented for the timestamp data, one that shows the local time formatted as a String and a second that shows UTC time formated as a String. The following lists the expected accessor methods for the FlowSample class
```
public String getAgency()
public String getSiteNumber()
public String getLocalTimestamp()
public String getUTCTimestamp()
public double getData()
public String getQualCode()
```

Add a toString() method that represents the FlowSample object as a nicely formatted String as shown below:

```
### <agency> - <siteNumber> ###
Time: <UTCTimeStamp>
Value: <data>
```

Once the FlowSample class has been create, add code to FlowSampleDriver.java that users a Scanner object to prompt the user for each of the data values, creates a new FlowSample object, then calls each of the accessor methods and the toString method and displays the results in the console.

#### Expected Program Output (with sample user input)
```
---------------------
|    Data Entry     |
---------------------
Please enter the following sample data values
Agency: USGS
Site Number: 13206000
Timestamp: 2021-12-29 14:45
Time Zone: MST
Gage Height: 3.60
Qualification Code: P

---------------------
| Data Confirmation |
---------------------
You entered the following:
Agency: USGS
Site Number: 13206000
Local Timestamp: 2021-12-29 14:45
UTC Timestamp: 2021-12-29 14:45
Gage Height: 3.60
Qualification Code: P

---------------------
|  Sample Summary   |
---------------------
### USGS - 13206000 ###
Time: 2021-12-29 14:45
Value: 3.60

```

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
