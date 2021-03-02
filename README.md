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
  - `Type Erasures`
  - 
## The Stream API
## Generics Programming

## Java 8
  - [About the Lambda FAQ](http://www.lambdafaq.org/)
  
### Diamond Problem from stackoverflow

       A
      / \
     B   C
      \ / 
       D

  - [Multiple Inheritance Ambiguity with Interface](https://stackoverflow.com/questions/29758213/multiple-inheritance-ambiguity-with-interface)
  - [Another solution from stackoverflow](https://stackoverflow.com/a/16788295/6021740)



