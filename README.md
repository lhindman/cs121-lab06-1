# Module 6 Lab Guide (part 1)
## Getting Started
[Lab Introduction Video](https://youtu.be/Gz_ZKspfhuE)  

### Code Style Requirements
Please review the [CS121 Style Guide](https://docs.google.com/document/d/1LWbGQBKkApnNAzzgwOSvRM03DmhYWx5yEfecT2WXfjI/edit?usp=sharing) and apply it in all lab activities and projects this semester. Coding Style will assessed as part of your lab and project grades.

### Code Quality Requirements
- Code must compile without warnings using openjdk11
- Code must run without errors or warnings on safe-path and edge test cases
- More to come as we learn about input validation and exception handling 

## Lab Warmup - FlowSampleEntry (required)
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
- double: dataReading
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
public double getDataReading()
public String getQualCode()
```

Add a toString() method that represents the FlowSample object as a nicely formatted String as shown below:

```
### <agency> - <siteNumber> ###
Time: <UTCTimeStamp>
Value: <dataReading>
```

Once the FlowSample class has been create, add code to FlowSampleEntry.java that users a Scanner object to prompt the user for each of the data values, creates a new FlowSample object, then calls each of the accessor methods and the toString method and displays the results in the console.

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
Reading: 3.60

```

### Implementation Guide
1. Expand the folder named FlowSampleEntry and open both FlowSample.java and FlowSampleEntry.java
2. Design a program to satisfy the requirements in the Problem Description and Program Design sections
3. Test the program using the sample user input and compare against the expected output. Carefully think about each of the different cases you'll need to test for to verify that the application is functioning properly.
4. Commit the changes to your local repository with a message stating that Lab Warmup is completed.
5. Push the changes from your local repository to the github classroom repository.

## Lab Activity 1 - FlowSampleParser
### Problem Description
The USGS provides FlowSample data in tab-delimited lines of text where each data field is separate by tabs. This is nearly the same situation that we learned about in the previous module with comma separated values, except here tabs are used to separate the fields instead of commas. For this activity we are going add functionality to the FlowSample class so that we can construct a new FlowSample from a single String value containing the required fields in tab-delimited format. Instead of prompting the user for each individual value, we will prompt the user for a single line of text that contains the tab-separated values as shown in the output below:

#### Expected Program Output (with sample user input)
```
---------------------
|    Data Entry     |
---------------------
Please enter the line of tab separated data:
USGS	13206000	2021-12-29 14:45	MST	3.60	P

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
Reading: 3.60

```
### Program Design
Add a second constructor to the FlowSample class that takes a single String value as a parameter as shown in the following header signature:
```
public FlowSample(String line)
```
The CSVParser example from the previous module is an excellent reference for how to use a Scanner to extract individual fields from a line of String data. In this case, the delimiter value will need to be changed from ',' to '\t'.  

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


## Coding Journal (Optional)
Keep a journal of your activities as you work on this lab. Many of the best engineers that I have worked with professionally have kept some sort of engineering journal. I personally packed notebooks around with me for nearly 8 years before I began keeping my notes electronically.   

Your journal can track ideas, bugs, cool links, code snippets, shell commands, rants, or simply a reflection on what worked well or not-so-well with this lab activity. I will not be grading the content of your journal, but I will expect at least two timestamped journal entries of at least a 75 to 150 words each added to the provided Journal.md file.  The purpose of this component is to help develop the habit of taking notes and creating documentation while you code. The more detail you provide the better as that will help you if you ever need to refer back to this project in the future.

## Markdown Resources
Markdown is a notation that is used to format text documents.  It is widely used in Software Development shops around the world, which is why we're asking you to use it in your lab documentation.  

Github provides a guide for getting started:  [Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
