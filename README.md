# JavaBook ☕
Everything(Something) about Java

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
  - `Covariant`, `Invariant`, `Contravariant`
  - 
## The Stream API
## Generics Programming
  - `Type Erasures`
  - Parameterized method
  - Raw Type
  - [Types of Method References](https://www.journaldev.com/32466/java-method-reference) from [Oracle doc](https://docs.oracle.com/javase/tutorial/java/javaOO/methodreferences.html)
    - `Class::StaticMethodName` : 
    - `Object::instanceMethodName`:
    - `Class::instanceMethodName`:
    - `Class::new`: 
## Java 8 Interfaces
  - `Default Methods` inside methods 🤔
  - `Static Methods` inside methods 🤔
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



