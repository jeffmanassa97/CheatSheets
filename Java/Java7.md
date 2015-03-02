# Java 7 Cheat Sheet
This is not a *getting started* guide, just a quick-reference for those that are a bit rusty in Java or that haven't coded in it recently (hence why I'm writing this).

## Summary
Java is a class-based **object-oriented** programming language. It is designed to let engineers *write once, run anywhere*. Java programs can be run on any system or platform that supports Java (*most* do), without needing to be recompiled. 

Java programs compile to **Java bytecode**, which can then run on any **Java Virtual Machine** (JVM). Much of Java, including its syntax, is based on **C** and **C++**. Java is **statically type**, which means that variables must be declared before they can be used.

## Hello World
filename: **HelloWorld.java**
```java
public class HelloWorld {
  public static void main(String[] args) {
    System.out.println("Hello world!");
  }
}
```

### Compilation
```sh
javac HelloWorld.java
```
creates a file named **HelloWorld.class**
### Run

```sh
java HelloWorld
```
output:
```
Hello world!
```

## Primitive Data Types
* **byte** - an 8-bit signed two's complement integer with range -128 to 127 inclusive (default = 0).
```java
byte b = 37;
```
* **short** - a 16-bit signed two's complement integer with range -32,768 to 32,767 inclusive (default = 0).
```java
short s = 2027;
```
* **int** - a 32-bit signed two's complement integer with range -2^31 to (2^31)-1 inclusive (default = 0).
```java
int number = 53617;
```
* **long** - a 64-bit signed two's complement integer with a range of -2^63 to (2^64)-1 inclusive (Java 8 supports it as unsigned as well) (default = 0L).
```java
int long = 104701;
```
* **float** - a single-precision 32-bit IEEE 754 floating point (note: in Java decimals default to the **double** type, hence the use of *f* to denote a float) (default = 0.0f).
```java
float f = 9.2f;
```
* **double** - a double-precision 64-bit IEEE 754 floating point (the default data type for decimals) (default = 0.0d).
```java
double pi = 3.14159;
```
* **boolean** - has only two possible values, **true** or **false** and represents 1-bit of data (default = false).
```java
boolean isAlive = true;
```
* **char** - a single 16-bit Unicode character with a minimum value of '\u0000' or 0 and a maximum value of 'u\ffff' or 65,535 inclusive (default = '\u0000').
```java
char c = 'a';
```

## Other Data Types
Some data types, such as strings, are represented as objects in Java.
```java
String sentence = "This is just a test of the Java string system.";
```

## Reference Data Types
Technically this refers to variables created using a defined constructor of their class, but here I'm just going over some more basic data types in Java that are not primitive data types.
* **Arrays** - a container object that holds a fixed number of values of a *single* type. Array indices are zero-based. Below is an integer array of size ten.
```java
int[] numbers = new int[10];
numbers[0] = 3;
numbers[1] = 29;
```
Here is a String array size 64.
```java
String[] words = new String[64];
words[0] = "Java";
```

## Object-Oriented
Java is a **class-based** object-oriented programming language. Each file represents a single class, and the filename and class name much match (i.e. filename=HelloWorld.java, classname=HelloWorld). Java **classes** are basically templates that describe the behavior and states that objects of its type support. Individual **objects** are instances of classes with specific states and behaviors. For instance, a robot might be stopped or in motion (state) and be able to move forward to go backwards (behavior). Each class can contain **methods** which correspond to behaviors (i.e. move forward). Classes also define **fields**, which can be used to store the state of objects of its type once instantiated.

Here is an example **Person.java**
```java
/**
 * Person.java
 */
public class Person {
    // Fields
    private int age;
    private String firstName;
    private String lastName;
    
    /**
     * A constructor for the Person class that accepts three parameters:
     * age, first name, last name.
     */
    public Person(int age, String firstName, String lastName) {
	  this.age = age;
	  this.firstName = firstName;
	  this.lastName = lastName;
    }

    /**
     * A getter method that returns the person's age.
     */
    public int getAge() {
	  return this.age;
    }

    /**
     * A setter method that sets our person's age.
     */
    public void setAge(int age) {
     this.age = age;
    }

    /**
     * A method that prints off the person's full name.
     */
    public void printFullName() {
	  System.out.println(this.firstName + " " + this.lastName);
    }

    /**
     * A method that prints off the person's age.
     */
    public void printAge() {
	  if(age == 1) {
	      System.out.println(this.firstName + " is 1 year old");
	  } else {
	      System.out.println(this.firstName + " is " + this.age + " years old");
	  }
    }

    /**
     * A method that increases the person's age by one.
     */
    public void increaseAge() {
	  this.age += 1;
    }

    /**
     * The main method executes only when this file is explicitly run,
     * i.e. 'java Person' from the terminal.
     */
    public static void main(String[] args) {
	  /* These variables will be used as arguments for our person.*/
	  int bobsAge = 52;
	  String bobsFirstName = "Bob";
	  String bobsLastName = "Smith";
	  
	  /* Here we create our new person object.*/
	  Person bob = new Person(bobsAge, bobsFirstName, bobsLastName);
	  
	  /* Now we print off Bob's full name */
	  bob.printFullName();
	  
	  /* Let's see how old Bob is. */
	  bob.printAge();
	  
	  /* Now we increase Bob's age. */
	  bob.increaseAge();
	  
	  /* And we'll see how old Bob is again. */
	  bob.printAge();
    }
}
```

## References

* [Java 7 API](http://docs.oracle.com/javase/7/docs/api/overview-summary.html)