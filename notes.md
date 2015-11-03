> Fair warning, this is my interpretation of the presentations. It is sometimes not copied verbatim.
> 
>  -- Zeb McCorkle

---

# Table of Contents

[TOC]

# Book: Java Software Solutions

## Chapter 1: Introduction

### Introduction

#### Focus of the Course

 - Object-Oriented Software Development
   - Problem solving
   - Program design, implementation, and testing
   - Object-oriented concepts
     - Classes
     - Objects
     - Encapsulation
     - Inheritance
     - Polymorphism
   - GUIs
   - The Java programming language

#### Introduction

 - We start with the fundamentals of computer processing
 - Chapter 1 focuses on:
	 - Components of a computer
	 - How computers store and manipulate information
	 - Computer networks
	 - The Internet and the WWW
	 - An introduction to Java
	 - An overview of OO concepts

### 1.1: Computer Processing

#### Hardware and Software

 - Hardware
	 - The physical, tangible parts of a computer
	 - Keyboard, monitor, disks, wires, chips, etc.
 - Software
	 - Programs and data
	 - A _program_ is a series of instructions
 - A computer requires both hardware and software
 - Each is essentially useless without the other

#### CPU and Main Memory

 - CPU (Central Processing Unit)
	 - IC that executes program commands
 - Main Memory (RAM)
	 - Primary storage area for programs and data that are in active use

#### I/O Devices

 - I/O devices facilitate user interaction
 - Examples include
	 - Monitor
	 - Keyboard
	 - Mouse
	 - Touchscreen

#### Secondary Memory Devices

 - Secondary memory devices provide long-term storage
 - Information is moved between main and secondary memory as needed

#### Software Categories

 - Operating System (Kernel-space)
	 - Controls all machine activities
	 - Provides the user interface to the computer
	 - Manages resources such as the CPU and memory
	 - NT Kernel, Mach Kernel, SysV Kernel, Linux Kernel
 - Application program (User-space)
	 - Generic term for any other kind of software
	 - Word processors, missile control systems, games
 - Most OSes and application programs have a _graphical user interface_ (GUI)

#### Analog vs. Digital

 - There are two basic ways to store and manage data:
	 - Analog
		 - Continuous, in direct proportion to the data represented
		 - Music on a record album - a needle rides on ridges in the grooves that are directly proportional to the voltages sent to the speaker
	 - Digital
	    - The information is broken down into pieces and each piece is represented separately
	    - _Sampling_ - Record discrete values of the analog representation
	    - Music on a CD - the disc stores numbers representing specific voltage levels sampled at specific times

#### Digital Information

 - Computers store all information digitally:
	 - numbers
	 - text
	 - graphics and images
	 - audio
	 - video
	 - program instructions
 - In some way, all information is _digitized_ - broken down into pieces and represented as numbers

#### Representing Text Digitally

 - For example, ever character is stored as a number, including spaces, digits, and punctuation
 - Corresponding upper and lower case letters are separate characters

#### Binary Numbers

 - Once information has been digitized, it is represented and stored in memory using the _binary number system_
 - A single _binary digit_ (0 or 1) is called a _bit_
 - Devices that store and move information are cheaper and more reliable if they have to represent only two states
 - A single bit can represent two possible states, like a light bulb that is either on (1) or off (0)
 - Permutations of bits are used to store values

#### Bit Permutations

|  1 bit  |  2 bits  |  3 bits  |  4 bits  |
|---------|----------|----------|----------|
| `0`     | `00`     | `000`    | `0000`   |
| `1`     | `01`     | `001`    | `0001`   |
|         | `10`     | `010`    | `0010`   |
|         | `11`     | `011`    | `0011`   |
|         |          | `100`    | `0100`   |
|         |          | `101`    | `0101`   |
|         |          | `110`    | `0110`   |
|         |          | `111`    | `0111`   |
|         |          |          | `1000`   |
|         |          |          | `1001`   |
|         |          |          | `1010`   |
|         |          |          | `1011`   |
|         |          |          | `1100`   |
|         |          |          | `1101`   |
|         |          |          | `1110`   |
|         |          |          | `1111`   |

 - Each permutation can represent a particular item
 - There are 2<sup>N</sup> permutations of N bits
 - Therefore, N bits are needed to represent 2<sup>N</sup> unique items

##### Moar!

###### 111010<sub>2</sub> to base 10
|1|1|1|0|1|0|<sub>2</sub>|
|-|-|-|-|-|-|-|
|32s|16s|8s|4s|2s|1s||
|32|16|8|0|2|0|<strong>= 58<sub>10</sub></strong>|

###### 10010101<sub>2</sub> to base 10
|1|0|0|1|0|1|0|1|<sub>2</sub>|
|-|-|-|-|-|-|-|-|-|
|128s|64s|32s|16s|8s|4s|2s|1s||
|128|0|0|16|0|4|0|1|<strong>= 149<sub>10</sub></strong>|

###### 18<sub>10</sub> to base 2

|1|0|0|1|0|<sub>2</sub>|
|-|-|-|-|-|-|-|-|-|
|16s|8s|4s|2s|1s||

### 1.2: Hardware Components

#### A Computer Specification

 - Consider the following specification for a personal computer:
	 - 3.07GHz Intel Core i7 processor
	 - 4GB RAM
	 - 750GB HDD
	 - 16x Blu-Ray/HD DVD-ROM & 16x DVD-R DVD Burner
	 - 17" Flat Screen Video Display with 1280 x 1024 resolution
	 - Networking card

#### Computer Architecture

    CPU ---+--- Main Memory
     +------+------+
     Disk  Video  etc
      Controller

#### Memory

 - Main memory is divided into many memory locations (or _cells_)
 - Each memory cell has a numeric _address_, which uniquely identifies it
 - Each memory cells stores a set number of bits (usually 8 bits, or one _byte_)
 - Large values are stored in consecutive memory locations
 - Main memory is _volatile_ - stored information is lost if the electric power is removed
 - Secondary memory devices are _nonvolatile_
 - Main memory and disks are _direct access_ devices - information can be reached directly
 - The terms _direct access_ and _random access_ often are used interchangeably
 - A magnetic tape is a _sequential access_ device since its data is arranged in a linear order - you must get by the intervening data in order to access other information

#### Storage Capacity

 - Every memory device has a _storage capacity_, indicating the number of bytes it can hold
 - Capacities are expressed in various units:
|  Unit  |Symbol|   Number of Bytes   |
|--------|------|---------------------|
|Kilobyte|  KB  |2<sup>10</sup> = 1024|
|Megabyte|  MB  |2<sup>20</sup>       |
|Gigabyte|  GB  |2<sup>30</sup>       |
|Terabyte|  TB  |2<sup>40</sup>       |
|Petabyte|  PB  |2<sup>50</sup>       |

#### Hard Disk Drive

 - Stacks of disks
 - Read/write heads

#### RAM vs ROM

 - _RAM_ - Random Access Memory (direct access)
 - _ROM_ - Read-Only Memory
 - The terms RAM and main memory are basically interchangeable
 - ROM could be a set of memory chips, or a separate device, such as a CD-ROM
 - Both RAM and ROM are random (direct) access devices
 - RAM probably should be called Read-Write Memory]

#### Compact Disks

 - A CD-ROM is portable read-only memory
 - A microscopic pit on a CD represents a binary 1 and a smooth area represents a binary 0
 - A low-intensity laser reflects strongly from a smooth area and weakly from a pit
 - A CD-Recordable (CD-R) drive can be used to write information to a CD once
 - A CD-Rewritable (CD-RW) can be erased and reused
 - The speed of a CD drive indicates how fast (max) it can read and write information to a CD

#### DVDs

 - A DVD is the same physical size as a CD, but can store much more information
 - The format of a DVD stores more bits per square inch
 - A CD can store 650MB, while a standard DVD can store 4.7GB
	 - A double sided DVD can store 9.4GB
	 - Other advanced techniques can bring the capacity up to 17GB
 - Like CDs, there are DVD-R and DVD-RW discs.

#### The CPU

 - A CPU is on a chip called a microprocessor
 - It continuously follows the _fetch-decode-execute cycle_
 - ALU (Arithmetic/Logic Unit) - Performs calculations and makes decisions
 - Control Unit - Coordinates processing steps
 - Registers - Small storage areas
 - The speed of a CPU is controlled by the _system clock_
 - The system clock generates an electric pulse at regular intervals
 - The pulses coordinate the activities of the CPU
 - The speed is usually measured in _gigahertz_ (GHz)

#### Monitor

 - The size of a monitor (e.g. 17") is measured diagonally, like a TV screen
 - A monitor has a certain maximum _resolution_, indicating the number of picture elements, called _pixels_, that it can display (such as 1280 by 1024 or 1920 by 1080)
 - High resolution (more pixels) produces sharper pictures

### 1.3: Networking

#### Networks

 - A _network_ is two or more computers that are connected so that data and resources can be shared
 - Most computers are connected to some kind of network
 - Each computer has its own _network address_ which uniquely identifies it among others
 - A _file server_ is a network computer dedicated to storing programs and data that are shared among network users

#### Network Connections

 - Each computer is a network could be directly connected to every other computer in the network
 - These are called _point-to-point_ connections
 - Adding a computer requires a new communication line for each computer already in the network
 - This technique is not practical for more than a few close machines
 - Most networks share a single communication line
 - Adding a new computer to the network is relatively easy
 - Network traffic must take turns using the line, which introduces delays
 - Often information is broken down in parts, called _packets_, which are sent to the receiving machine and then reassembled

#### Local-Area Networks

 - A _Local-Area Network_ (LAN) covers a small distance and a small number of computers

#### Wide-Area Networks

 - A _Wide-Area Network_ connects two or more LANs, often over long distances

#### The Internet

 - The _Internet_ is a WAN which spans the planet
 - The word Internet comes from the term _internetworking_
 - It started as a United States government project, sponsored by the Advanced Research Projects Agency (ARPA)
	 - originally it was called the ARPANET
 - The Internet grew quickly throughout the 1980s and 90s

#### TCP/IP

 - A protocol is a set of rules that determine how things communicate with each other
 - The software that manages Internet communication follows a suite of protocols called _TCP/IP_
 - The _Internet Protocol_ (IP) determines the format of the information as it is transferred
 - The _Transmission Control Protocol_ (TCP) dictates how messages are reassembled and handles lost information

#### IP and Internet Addresses

 - Each computer on the Internet has a unique _IP address_ such as:

        204.192.116.2

 - Most computers also have a unique Internet name, which is referred to as an _Internet address_:

        hector.vt.edu
        kant.gestalt-llc.com

 - The first part indicates a particular computer (`hector`)
 - The rest is the _domain name_, indicating the organization (`vt.edu`)

#### Domain Names (DNS)

 - The last part of a domain name, called a _top-level domain_ (TLD), supposedly indicates the type of organization:

    |TLD|For|
    |-|-|
    |edu|educational institution|
    |com|commercial entity|
    |org|non-profit organization|
    |net|network-based organization|
    
    Sometimes the suffix indicates the country:
    
    |TLD|Country|
    |-|-|
    |uk|United Kingdom|
    |au|Australia|
    |ca|Canada|
    |se|Sven|
    |no|Norge|

 - A domain name can have several parts
 - Unique domain names mean that multiple sites can have individual computers with the same local name
 - When used, an Internet address is translated to an IP address by software called the _Domain Name System_ (DNS)
 - There is **no** one-to-one correspondence between the sections of an IP address and the sections of an Internet address

#### The World Wide Web

 - The World Wide Web allows many different types of information to be accessed using a common interface
 - A _browser_ is a program which accesses network resources and presents them
	 - Popular browsers: Microsoft <strike>Internet Explorer</strike> Edge, Safari, Firefox
 - Rersources presented include:
	 - text, graphics, video, sound, audio, executable programs
 - A Web document usually contains _links_ to other Web documents, creating a _hypermedia_ environment
 - The term Web comes from the fact that information is not organized in a linear fashion
 - Web documents are often defined using the _HyperText Markup Language_ (HTML)
 - Information on the Web is found using a _Uniform Resource Locator_ (URL):

        http://www.cnn.com
        http://www.vt.edu/student_life/index.html
        ftp://java.sun.com/applets/animation.zip

 - A URL specifies a protocol (http), a domain, and possibly specific documents
        
### 1.4: The Java Programming Language

#### Java

 - The Java programming language was created by Sun Microsystems, Inc in 1995
 - It was introduced in 1995 and its popularity has grown quickly since
 - A _programming language_ specifies the words and symbols that we can use to write a program
 - A programming language employs a set of rules that dictate how the words and symbols can be put together to form valid _program statements_

#### Java Program Structure

 - In Java:
	 - A program is made up of one or more _classes_
	 - A class contains one or more _methods_
	 - A method contains program _statements_
 - These terms will be explored in detail throughout the course
 - A Java application always contains a method called `public static void main(String[] args)`
 - See `Lincoln.java`

   ```java
   // comments
   public class MyProgram { // class header
   	// class body
   	// comments about the method
   	public static void main(String[] args) { // method header
	   	// method body
	   }
   }
   ```

#### Comments

 - Comments should be included to explain the purpose of the program and describe processing steps
 - They do not affect how a program works
 - Java comments can take three forms:
   
   ```java
   // this comment runs to the end of the line
   /* this comment runs to the terminating
       symbol, even across line breaks */
   /** this is a <em>javadoc</em> comment */
   ```

#### Identifiers

 - _Identifiers_ are the "words" in a program
 - A Java identifier can be made up of letters, digits, the underscore character (_), and the dollar sign
 - Identifiers cannot begin with a digit
 - Java is _case sensitive_: `Total`, `total`, and `TOTAL` are different identifiers
 - By convention, programmers use different case styles for different types of identifiers, such as 
	 - _title case_ for class names - `Lincoln`
	 - _upper case_ for constants - `MAXIMUM`
 - Sometimes the programmer chooses the identifier (such as `Lincoln`)
 - Sometimes we are using another programmer's code, so we use the identifiers that he or she chose (such as `println`)
 - Often we use special identifiers called _reserved words_ that already have a predefined meaning in the language
 - A reserved word cannot be used in any other way

#### White Space

 - Spaces, blank lines, and tabs are called _white space_
 - White space is used to separate words and symbols in a program
 - Extra white space is ignored
 - A valid Java program can be formatted many ways
 - Programs should be formatted to enhance readability, using consistent indentation
 - See `Lincoln2.java` and `Lincoln3.java`

### 1.5: Program Development

#### Program Development

 - The mechanics of developing a program include several activities:
	 - Writing the program in a specific programming language (such as Java)
	 - Translating the program into a form that the computer can execute
	 - Investigating and fixing various types of errors that can occur
 - Software tools can be used to help with all parts of this process

#### Language Levels

 - There are four programming language levels:
	 - machine language
	 - assembly language
	 - high-level language
	 - fourth-generation language
 - Each type of CPU has its own specific _machine language_
 - The other levels were created to make it easier for a human being to read and write programs

#### Programming Language

 - Each type of CPU executes only a particular _machine language_
 - A program must be translated into machine language before it can be executed
 - A _compiler_ is a software tool which translates _source code_ into a specific target language
 - Sometimes, that target language is the machine language for a particular CPU type
 - The Java approach is somewhat different

#### Java Translation

 - The Java compiler translates Java source code into a special representation called _bytecode_
 - Java bytecode is not the machine language for any traditional CPU
 - Bytecode is executed by the _Java Virtual Machine_ (JVM)
 - Therefore Java bytecode is not tied to any particular machine
 - Java is considered to be _architecture-neutral_

#### Development Environments

 - There are many programs that support the development of Java software, including:
	 - Java Development Kit
	 - Eclipse
	 - NetBeans
	 - BlueJ
	 - jGRASP
	 - IntelliJ IDEA
 - Though the details of these environments differ, the basic compilation and execution process is essentially the same

#### Syntax and Semantics

 - The _syntax rules_ of a language define how we can put together symbols, reserved words, and identifiers to make a valid program
 - The _semantics_ of a program statement define what the statement means (its purpose or role in a program)
 - A program that is syntactically correct is not necessarily logically (semantically) correct
 - A program will always do what we tell it to do, not what we **meant** to tell it to do

#### Errors

 - A program can have three types of errors
 - The compiler will find syntax errors and other basic problems (_compile-time errors_)
	 - If compile-time errors exist, an executable version of the program is not created
 - A problem can occur during program execution, such as trying to divide by zero, which causes a program to terminate abnormally (_run-time errors_)
 - A program may run, but produce incorrect results, perhaps using an incorrect formula (_logical errors_ or _ID10T/IDIOT error_)

#### Problem Solving

 - The purpose of writing a program is to solve a problem
 - Solving a problem consists of multiple activities:
	 - understand the problem
	 - design a solution
	 - consider alternatives and refine the solution
	 - implement the solution
	 - test the solution
 - These activities are not purely linear -- they overlap and react
 - The key to designing a solution is breaking it down into manageable pieces
 - When writing software, we design separate pieces that are responsible for certain parts of the solution
 - An _object-oriented approach_ lends itself to this kind of solution decomposition
 - We will dissect our solutions into pieces called objects and classes

### 1.6: Object-Oriented Programming

#### Object-Oriented Programming

 - Java is an object-oriented programming language
 - As the term implies, an object is a fundamental entity in a Java program
 - Objects can be used effectively to represent real-world entities
 - For instance, an object might represent a particular employee in a company
 - Each employee object handles the processing and data management related to that employee

#### Objects

 - An object has
	 - _state_ - descriptive characteristics
	 - _behaviors_ - what it can do (or what can be done to it)
 - The state of a bank account includes its account number and its current balance
 - The behaviors associated with a bank account include the ability to make deposits and withdrawls
 - Note that the behavior of an object might change its state

#### Classes

 - An object is defined by a _class_
 - A class is the blueprint of an object
 - The class uses methods to define the behaviors of the object
 - The class that contains the main method of a Java program represents the entire program
 - A class represents a concept, and an object represents the embodiment of that concept
 - Multiple objects can be created from the same class

#### Inheritance

 - One class can be used to derive another via _inheritance_
 - Classes can be organized into hierarchies

## Chapter 2: Data and Expressions

### 2.1: Character Strings

#### Character Strings

 - A _string literal_ is represented by putting double quotes around the text
 - Examples:
   
        "This is a string literal."
        "123 Main Street"
        "X"
        ""
   
 - Every character string is an object in Java, defined by the `String` class
 - Every string literal represents a `String` object

#### The `println` Method

 - In the `Lincoln` program from Chapter 1, we invoked the `println` method to print a character string
 - The `System.out` object represents a destination (the monitor screen) to which we can send output

#### The `print` Method

 - The `System.out` object provides another service as well
 - The `print` method is similar to the `println` method, except that it does not advance to the next line
 - Therefore anything printed after a `print` statement will appear on the same line
 - See `Countdown.java`

#### String Concatenation

 - The _string concatenation operator_ (+) is used to append one string to the end of another

        "Peanut butter " + "and jelly"

 - It can also be used to append a number to a string
 - A string literal cannot be broken across two lines in a program
 - See `Facts.java`
 - The `+` operator is also used for arithmetic addition
 - The function that it performs depends on the type of the information on which it operates
 - If both operands are strings, or if one is a string and one is a number, it performs string concatenation
 - If both operands are numeric, it adds them
 - The `+` operator is evaluated L&rarr;R, but parentheses can be used to force the order
 - See `Addition.java`

#### Escape Sequences

 - What if we wanted to print the quote character?
 - The following line would confuse the compiler because it would interpret the second quote as the end of the string

   ```java
   System.out.println("I said "Hello" to you.");
   ```

 - An escape sequence is a series of characters that represents a special character
 - An escape sequence begins with a backslash character (\\)

   ```java
   System.out.println("I said \"Hello\" to you.");
   ```

 - Some Java escape sequences:
    
    \b: backspace
    \t: tab
    \n: newline
    \r: carriage return
    \": double quote
    \': single quote
    \\: backslash

 - See `Roses.java`

#### Quick Check

 - Write a single `println` statement that produces the following output:

   > "Thank you all for coming to my home tonight," he said mysteriously.

   ```java
   System.out.println("\"Thank you all for coming to my house tonight,\" he said mysteriously."); // OUTPUT: "Thank you all for coming to my house tonight," he said mysteriously\n
   ```

### 2.2: Variables and Declarations

#### Variables

 - A _variable_ is a name for a location in memory that holds a value
 - A _variable declaration_ specifies the variable's name and the type of information that it will hold
 - 

   ```java
   int sum;
   int base, max;
   ```

#### Variable Initialization

 - A variable can be given an initial value in the declaration
   
   ```java
   int sum = 0;
   int base = 32, max = 149;
   ```

 - When a variable is referenced in a program, its current value is used.
 - See `PianoKeys.java`

#### Assignment

 - An _assignment statement_ changes the value of a variable
 - The assignment operator is the `=` sign
   
   ```java
   total = 55;
   ```
   
 - The value that was in `total` is overwritten
 - You can only assign a value to a variable that is consistent with the variable's declared type
 - See `Geometry.java`

#### Constants

 - A _constant_ is an identifier that is similar to a variable except that it holds the same value during its entire existence
 - As the name implies, it is constant, not variable
 - The compiler will issue an error if you try to change the value of a constant
 - In Java, we use the `final` modifier to declare a constant
   
   ```java
   final int MIN_HEIGHT = 69;
   ```
   
 - Constants are useful for three important reasons
 - First, they give meaning to otherwise unclear literal values
	 - Example: `MAX_LOAD` means more than the literal 250
 - Second, they facilitate program maintenance
	 - If a constant is used in multiple places, its value need only be set in one place
 - Third, they formally establish that a value should not change, avoiding inadvertent errors by other programmers

### 2.3: Primitive Data Types

#### Primitive Data

 - There are eight primitive data types in Java
 - Four of them represent integers:
    - `byte`, `short`, `int`, `long`
 - Two of them represent floating point numbers:
    - `float`, `double`
 - One of them represents characters:
    - `char`
 - And one of them represents boolean values:
    - `boolean`
 - They actually store the value that you assign, as opposed to a reference.

#### Numeric Primitive Data

 - The difference between the numeric primitive types is their size and the values that they can store:
    
    | Type     | Storage | Min Value                               | Max Value   |
    |----------|---------|-----------------------------------------|-------------|
    | `byte`   | 8 bits  | -128                                    | 127         |
    | `short`  | 16 bits | -32768                                  | 32767       |
    | `int`    | 32 bits | -2147483648                             | 2147483647  |
    | `long`   | 64 bits | < -9 * 10^18                            | \> 9 * 10^18 |
    | `float`  | 32 bits | +/- 3.4*10^38 with 7 significant digits |             |
    | `double` |         | +/- 1.7*10^308 with 15 significant digits |             |

#### Characters

 - A `char` variable stores a single variable
 - Character literals are delimited by single quotes:

    ```java
    'a', 'X', '7', '$', ',', '\n'
    ```
    
 - Example declarations:

    ```java
    char topGrade = 'A';
    char terminator = ';', separator = ' ';
    ```

#### Character Set

 - A _character set_ is an ordered list of characters, with each character corresponding to a unique number
 - A `char` variable in Java can store any character from the _Unicode character set_
 - The Unicode character set uses sixteen bits per character, allowing for 65535 unique characters
 - It is an international character set, containing symbols and characters from many world languages
 - `'A'`: `65`
 - `'a'`: `97`
 - `'0'`: `48`

#### Characters

 - The _ASCII character set_ is older and smaller than Unicode, but is still quite popular
 - The ASCII characters are a subset of the Unicode character set, including:
    - uppercase letters
    - lowercase letters
    - punctuation
    - digits
    - special symbols
    - control characters

#### Boolean

 - A `boolean` value represents a true or false condition
 - The reserved words `true` and `false` are the only valid values for a boolean type
 -  

    ```java
    boolean done = false;
    ```

 - A `boolean` variable can also be used to represent any two states, such as a light bulb being on or off

#### Expressions

 - An _expression_ is a combination of one or more operators and operands
 - _Arithmetic expressions_ compute numeric results and make use of the arithmetic operators:

    | Operator           | Symbol |
    |--------------------|--------|
    | Addition           | `+`    |
    | Subtraction        | `-`    |
    | Multiplication     | `*`    |
    | Division           | `/`    |
    | Remainder (Modulo) | `%`    |

 - If either or both operands are floating point values, then the result is a floating point value

#### Division and Remainder

 - If both operands to the division operator (`/`) are integers, the result is an integer (the fractional part is discarded)

    ```java
    assert(14 / 3 == 4);
    assert(8 / 12 == 0);
    ```

 - The remainder operator (`%`) returns the remainder after dividing the first operand by the second

    ```java
    assert(14 % 3 == 2);
    assert(8 % 12 == 8);
    ```

#### Quick Check

What are the results of the following expressions?

| Expression   | Result |
|--------------|--------|
| `12 / 2`     | `6`    |
| `12.0 / 2.0` | `6.0`  |
| `10 / 4`     | `2`    |
| `10 / 4.0`   | `2.5`  |
| `4 / 10`     | `0`    |
| `4.0 / 10`   | `0.4`  |
| `12 % 3`     | `0`    |
| `10 % 3`     | `1`    |
| `3 % 10`     | `3`    |

#### Operator Precedence

 - Operators can be combined into larger expressions

    ```java
    result = total + count / max - offset;
    ```

 - Operators have a well-defined precedence which determines the order in which they are evaluated
 - Multiplication, division, and remainder are evaluated before addition, subtraction, and string concatenation
 - Arithmetic operators with the same precedence are evaluated from left to right, but parentheses can be used to force the evaluation order

> Written with [StackEdit](https://stackedit.io/).  
> Some (most?) content is copyright &copy; 2014 Pearson Education, Inc.