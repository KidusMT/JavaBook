# JavaBook ☕


## Static Methods and Default methods in Interface (Java +8)
  >> You cannot override the static method of the interface; you can just access them using the name of the interface. If you try to override a static method of an interface by defining a similar method in the implementing interface, it will be considered as another (static) method of the class.

## Functional Programming in Java
  - [Referential Transparency](https://www.sitepoint.com/what-is-referential-transparency/#referentialtransparencyinprogramming): any call to the program may be replaced with the corresponding return value without changing the result of the program (no side effects).
  
  below is referential transparent method
  ```java
  int add(int a, int b) {
    return a + b
  }
  ```
  below is NOT, referential transparent method because replacing the method with the result will change the result of the program since the message will no longer be printed.
  
  ```java
  int add(int a, int b) {
    int result = a + b;
    System.out.println("Returning " + result);
    return result;
  }
  ```
  - [Higher Order Function](http://tutorials.jenkov.com/java-functional-programming/index.html#higher-order-functions): function taking function as an argument and also can returning a function as well.
  - [First Class Citizen](https://stackoverflow.com/a/33695408/6021740): That means that you can create an "instance" of a function, as have a variable reference that function instance. Java doesn't support first class citizen but the closest we have is with lambda expressions (assigning them to variables). 
  - [First Class vs Higher order](https://stackoverflow.com/a/10141303/6021740)
  - `Covariant`, `Invariant`, `Contravariant`
  - 
## The Stream API
  - [State of the Lambda](https://cr.openjdk.java.net/~briangoetz/lambda/sotc3.html)

  ![image](https://user-images.githubusercontent.com/18373774/109812904-4384a280-7bf2-11eb-8422-b26764825e4f.png)
  
  *[javapapers] -> https://javapapers.com/java/java-stream-api/*
  
## Generics Programming
  - [Type Erasures](https://stackoverflow.com/questions/313584/what-is-the-concept-of-erasure-in-generics-in-java/313591#313591)
  - [Best Resource](http://www.angelikalanger.com/GenericsFAQ/JavaGenericsFAQ.html) from Angelika Langer
  - [Wildcards](https://stackoverflow.com/questions/12043874/java-generics-wildcard-capture-misunderstanding)
  - [Java generics, objects and wildcards differences & clarifications](https://stackoverflow.com/q/34993626/6021740)
  - Parameterized method
  - Raw Type
  - [Types of Method References](https://www.journaldev.com/32466/java-method-reference) from [Oracle doc](https://docs.oracle.com/javase/tutorial/java/javaOO/methodreferences.html)
    - `Class::StaticMethodName` : 
    - `Object::instanceMethodName`:
    - `Class::instanceMethodName`:
    - `Class::new`: 
## Java 8 Interfaces
  - `Default Methods` inside methods 
  - `Static Methods` inside methods 
## Java 8
  - [About the Lambda FAQ](http://www.lambdafaq.org/)
  - [Local Inner Classes](https://docs.oracle.com/javase/tutorial/java/javaOO/localclasses.html#local-classes-are-similar-to-inner-classes): is that even possible? 🤔 For [more examples](https://docs.oracle.com/javase/tutorial/displayCode.html?code=https://docs.oracle.com/javase/tutorial/java/javaOO/examples/LocalClassExample.java)
  ```java
   void display(){  
     class Local{  
         void msg(){System.out.println(data);}  
     }  
     Local l=new Local();  
     l.msg();  
   }  
  ```
  
### Diamond Problem from stackoverflow

       A
      / \
     B   C
      \ / 
       D

  - [Multiple Inheritance Ambiguity with Interface](https://stackoverflow.com/questions/29758213/multiple-inheritance-ambiguity-with-interface)
  - [Another solution from stackoverflow](https://stackoverflow.com/a/16788295/6021740)


## Java Jigsaw
  - [The primary objective of the Jigsaw project is to introduce the modularity concept to create a module in Java 9 and then applying the same to JDK.](https://www.tutorialspoint.com/what-is-project-jigsaw-in-java-9)
  - Benefits of Jigsaw(Modularity)
      - Strong Encapsulation
      - Clear Dependecies
      - Reliable

