# JavaBook ☕
Everything(Something) about Java

## Functional Programming in Java
  - Referential Transparency: any call to the program may be replaced with the corresponding return value without changing the result of the program (no side effects).
  
  referential transparent method
  ```java
  int add(int a, int b) {
    return a + b
  }
  ```
  not, referential transparent method
  
  ```java
  int add(int a, int b) {
    int result = a + b;
    System.out.println("Returning " + result);
    return result;
  }
  ```
  - Type Erasures
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



