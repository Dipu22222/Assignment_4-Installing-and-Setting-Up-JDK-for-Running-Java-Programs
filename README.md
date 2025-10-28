# Assignment_4-Installing-and-Setting-Up-JDK-for-Running-Java-Programs
Name: Dipu Mondol;
<br>
ID: IT-24040;
<br>
Language: Java;
<br>
IDE: Command Line;
<br>
<br>
<br>
<br>
 README – JDK Installation and Setup
 Step 1: Install JDK

I downloaded and installed OpenJDK 25 (Temurin LTS) on my Windows 64-bit system.
The JDK was installed in:

C:\Program Files\Java\jdk-25

 Step 2: Set Environment Variables

Created a new system variable:

JAVA_HOME = C:\Program Files\Java\jdk-25


Added this to the Path variable:

%JAVA_HOME%\bin

 Step 3: Verify Installation

In Command Prompt, I ran:

java --version
javac --version


Output confirmed Java was installed and working properly.

 Step 4: Test Program

Created RainyDay.java:

public class RainyDay {
    public static void main(String[] args) {
        System.out.println("It's a rainy day!");
    }
}


Commands used:

javac RainyDay.java
java RainyDay


 Output:

It's a rainy day!
