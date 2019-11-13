# Day 1

### Introduction 
* Java is a simple Language – No Pointers, Takes care of Memory Management, collect and destroy the unused objects.
* Java is a platform independent Language – Can be run on any machine as It us converted into an intermediate language called the bytecode and run on JVM(Java Virtual Machines) on any computer architecture.
* Java is an Object Oriented Language(OOP’s) – It can be used to bridge any data from one object to another.
* Java is a Robust Language – It is portable across many systems, have automatic memory management,  Strong type checking, Bugs, System Crashing bugs are rare.

### Java Environment
* JDK – JDK is intended for software developers and includes development tools such as Java Compiler, javadoc, jar
* JRE(Java Runtime Environment) – JRE contains the parts of the library required to run Java Programs and is for the end users
* JVM – It provides runtime environment in which java bytecode can be executed


### Compile a Basic Program
Create a Program
---
    # Store.java
    
    // Class Definitionpublic class Store {
       // main method
       // public – To make JVM to execute this method from anywhere
       // static  - It can be instantiated without requiring an instantiation of the class to which it belongs
       // void – It doesn’t return anything    public static void main(String[] args){         System.out.println("Hello World"); //System is a predefined class    }}
    Compile 
        javac Store.java //creates a Store.class
    Run 
        java Store
---

### Important Points 

All codes must reside inside the class
The name of the Class defined by the program is the same as the file
The name of the main class should match the name of the file that holds the program


### Classes & Objects

* Basic concepts of OOP’s revolved around life entities
* Classes are user defined blueprint 
* Class Name should begin with a Initial Letter capitalized by convention.
* A Class can only extend one parent(Superclass) – // Class ConvenienceStore extends Store
* A Class can implement more than one interface using a coma separated list // class File implements IStoreRead, IStoreWrite
* Class can be public or has default access - Scope Modifiers
* Classes and interfaces can have only two access specifiers

        * public
        * default - can be accessed within the class or a package
        
* Methods/Data Members has the following access specifiers
      
        * private 
        * Default – can be accessed within the class or a package
        * Protected
        * Public

* Object consists of state, Behavior, Identity

        * State – attributes of an object, properties of an object // Inventory
        * Behavior – methods of an object // Search, AddItem, UpdateItem
        * Identity – Unique name of an object // productName, Category, SubCategory, productId, skuId

They are other type of classes

    * Nested Classes // Show in Code		
    * Anonymous Classes // Show in Code
    * Lambda Expressions // Show in Code
    
---
    // Class is a member of another class
    class Outer {
        class Inner {
            public void show() { 
                System.out.println("In a nested class method"); 
            }    
         }
    }
    
    class Main { 
        public static void main(String[] args) { 
               Outer.Inner in = new Outer().new Inner();  
               in.show();
        }
     }

---


---
       // Can be abstract or Concrete
       interface Age {    
            void getAge();
       }
       
       class Main { 
          public static void main(String[] args) {
                Age age = new Age() {
                    public void getAge() {
                           System.out.println("Age is a number");         
                  }        
               };     
               age.getAge();  
          }
       }
---


---
        An Interface with single abstract method
        
        interface FuncInterface {
            // An Abstract function
            // Zero Parameter () 
            // Single Parameter (1) 
            // Multiple Parameters (p1, p2)   
             void abstractFunc(int x);
        }
           class Func {    
               public static void main(String[] args) {        
             
                   FuncInterface xObj = (int z) -> System.out.println(z * 4) ;  
                   xObj.abstractFunc(4);   
               }
        }
---

### Naming Conventions
* Class Names should be nouns, first letter of each internal word capitalized // Class Warehouse implements Depot
* Interface Name should be capitalized just like classes // interface Depot
* Methods should be verbs, first letter as lowercase and first letter of internal words capitalized // void updateTruckLocation(Truck truck)
* Variables names should be short & Meaningful
* Variables Should not start with Underscore(“_”) or Dollar Sign(‘$’) character
* Variable with single character should be avoided, except temporarily // int door = 5
* Constant variables should be ALL uppercase, separated by underscores // public static final int DEFAULT_DISTANCE = 10
* Packages should be all lowercase and should be one of the top level domain names like com, edu, net, org. 
* Package Subsequent name will be organization/username internal naming conventions //com.sainsburys.productlocator

### Packages

* Packages in Java to encapsulate a group of classes, sub packages and interfaces
* Prevent naming conflicts for different classes from different packages
* Protected member is accessible by classes in the same package and its subclasses
* A default member is accessible by classes in the same package only
* Packages are written on top of a file and saved it in a package directory
* Packages can have sub packages but sub packages with protected and default access can be access by sub packages only 

### OOPs concept in Java

Aim to relate real world entities like inheritance, hiding, polymorphism
It’s aim is bind together the data and the functions that operate on them so that no other part of the code can access

Characteristics of OOPs
 Encapsulation 
 Polymorphism
 Inheritance
 Abstraction

## Polymorphism 
Wrapping up of data into a single unit
* Binds together code and data it manipulates
* Protects from access by other objects - Data, variable is hidden

---

    import com.samjiks.models.*;
    public class Encapsulation {  
        public static void main(String[] args){  
              Customer c = new Customer();      
              BillingAddress billingAddress = new BillingAddress();       
              billingAddress.setCity("London");  
              billingAddress.setPostCode("EC1N2HT");    
              c.setBillingAddress(billingAddress);
              System.out.println("c = " + c.toString());   
        }
    }
---

Two types of Polymorphism
* Method overloading is in the same class, where more than one method have the same name but different signatures.
    
    void sum (int a , int b); 
    void sum (int a , int b, int c); 
    void sum (float a, double b);
    
* Method overriding is when one of the methods in the super class is redefined in the sub-class. In this case, the signature of the method remains the same.
   
--- 
    class X{   
        public int sum() { 
            // some code    
        }
   }
   class Y extends X {
       public int sum(){  
             //overridden method
             //signature is same    
       }
   }
--- 
### Inheritance
* It is mechanism in java by which one class is allow to inherit the features(fields and methods)
* Class can only extend one BaseClass(Base Class, Super Class)
* They are four types of inheritance

        Single Inheritance
        Multilevel Inheritance // Derived Class Intermediate Class -> Base Class
        Multiple Inheritance – through interfaces // Not Supported in Java
        Hierarchical Inheritance – One Class is inherited by many classes 


### Interfaces

* It is collection of abstract methods
* A class implements an interface
* Interface contains constants, default methods, static methods
* An Interface can contain any number of methods
* You can’t instantiate and interface
* An interface does not contain any constructor
* All of the method in an interface are abstract
* An interface can extend multiple interfaces
* Every method is an interface is also implicitly abstract
* Methods in an interface implicitly public 

### Abstract Classes
* Abstract classes may not contain abstract methods
* If a class has at least one abstract method, it must be declared abstract
* If a class is declared Abstract, it cannot be instantiated
* To use an abstract class, you have to inherit from another classes
* They are partial implementation for eg. Order, OrderDetails

abstract class CustomerLoyalCard implements ILoyaltyCard {    int points;    abstract void getCardDetails();    private void getCustomerProfile(){ }    public void convertVoucherToPoints(){ }}

### Abstract Classes vs Interface

* In Interfaces, all the methods will not have method implementation.
* The class which is implementing the interface should implement all the methods in that particular interface.
* Abstract classes can have abstract methods as well as normal concrete methods. Abstract methods don’t have an implementation.
* The class which is extending the abstract class should have the implementation for all the abstract methods in the abstract class.
* If the subclass doesn’t have enough information to implement the abstract methods, then the subclass should be declared as an abstract class.


