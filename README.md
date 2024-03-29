# JavaBook ☕


## Java Certifications
  - [Oracle Java Explorer](https://learn.oracle.com/ols/learning-path/java-explorer/40805/79726)
  - [Pluralsight IQ Skill Test for Java](https://www.pluralsight.com/role-iq/java-developer)


## Static Methods and Default methods in Interface (Java +8)
  > You cannot override the static method of the interface; you can just access them using the name of the interface. If you try to override a static method of an interface by defining a similar method in the implementing interface, it will be considered as another (static) method of the class (a.k.a method-hiding).
  > 
  - Default vs static method conflict from parent interfaces, which one wins? 
  ```java
  public interface Sup1 {
    static int myMethod() {
      return 1;
    }
  }
  public interface Sup2 {
      default int myMethod() {
          return 2;
      }
  }
  // when we implement both interfaces in the same class then the default method wins
  public class Impl implements Sup1, Sup2 {

    public static void main(String[] args) {
      Impl s = new Impl();
      int val = s.myMethod();
      System.out.println(val);
    }
  }
  
  //prints
  >> 2
  ```

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
  - [Functional Interfaces](https://docs.oracle.com/javase/8/docs/api/java/util/function/package-summary.html) (a.k.a [Single Abstract Method Interfaces or SAM Interfaces](https://www.javatpoint.com/java-8-functional-interfaces): `It can have any number of **default**, **static** methods but can contain **only one abstract method**. It can also declare methods of **object class**.`

      ```java
          @FunctionalInterface
          public interface MyFunctionalInterface {

              public abstract void execute();

              @Override
              String toString();

              default void beforeTask() {
                  System.out.println("beforeTask... ");
              }

              default void afterTask() {
                  System.out.println("afterTask... ");
              }
          }
      ```
       - `Consumer`: 	accept(T t), andThen(Consumer<? super T> after)
       - `Supplier`: 	get()
       - `Predicate`:  test(T t), and(Predicate<? super T> other), isEqual(Object targetRef), negate(), or(Predicate<? super T> other)
       - `Function`: 	apply(T t), identity(), compose(Function<? super V,? extends T> before), andThen(Function<? super R,? extends V> after)


## The Stream API
  - [State of the Lambda](https://cr.openjdk.java.net/~briangoetz/lambda/sotc3.html)

  ![image](https://user-images.githubusercontent.com/18373774/109812904-4384a280-7bf2-11eb-8422-b26764825e4f.png)
  
  *[javapapers] -> https://javapapers.com/java/java-stream-api/*
  - `peek` method is not stateful from the picture above
  
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
  - [Free Variables](https://www.informit.com/articles/article.aspx?p=2303960&seqNum=7)
    - not parameters inside lambda
    - not defined inside the block of code
    - not defined inside the right handside of the lambda expression 
    - [1. from stackoverflow](https://stackoverflow.com/a/43847137/6021740) 
    - [2. from stackoverflow](https://stackoverflow.com/a/25055561/6021740)
   
  for example: `text` and `count` are free variables
```java
public static void repeatMessage(String text, int count) {
    Runnable r = () -> {
        for (int i = 0; i < count; i++) {
            System.out.println(text);
        }
    };
    new Thread(r).start();
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

![image](https://user-images.githubusercontent.com/18373774/110223623-270b9300-7e9c-11eb-8950-ab97f63edcb0.png)



## Java Optional
  - [Gracefully handling NPE in java](https://www.geeksforgeeks.org/how-to-avoid-nullpointerexception-in-java-using-optional-class/)

```java
Optional.ofNullable(user);//Optional of Nullable value

Optional.of(notNullUserList);// Optional of Not Null value

return Optional.empty();// Empty Optional

// Consume if it is not Null
Optional<Address> optAddress = user.getAddress();
optAddress.ifPresent(System.out::println);

// Check if it is Not Null
Address address;
if(optAddress.isPresent){
    address = optAddress.get();
}

// Get if Object is Not Null, else return default
Address defaultAddress = new Address (....);
Optional<Address> optAddress = user.getAddress();
Address address = optAddress.orElse(defaultAddress);

// Get if Object is Not Null, else Throw Exception
Optional<Address> optAddress = user.getAddress();
Address address = optAddress.orElseThrow(UserNotFoundException::new)

// Get Value
Optional<Address> optAddress = user.getAddress();
Address address = optAddress.get();
```

## Important Notes
  - `Yield` vs `Return`: from [stackoverflow](https://stackoverflow.com/questions/58049131/what-does-the-new-keyword-yield-mean-in-java-13) : was included in Java 13 
  ![image](https://user-images.githubusercontent.com/18373774/110291244-53650380-7fb1-11eb-88e8-4d97bfcd168a.png)


## Java Notes:
  - [A method declared with the final keyword, then it is known as the final method. The final method can't be overridden. A final method declared in the Parent class cannot be overridden by a child class](https://javagoal.com/can-we-override-the-final-method-in-java/#:~:text=A%20method%20declared%20with%20the,overridden%20by%20a%20child%20class.)


## Order of Execution in Java


![image](https://user-images.githubusercontent.com/18373774/112776355-15358f80-9005-11eb-9946-e66538f00dbf.png)


```java
// static blocks
static int a;

static {
   a = 5;
   System.out.println("this is a static block");
}

// instance initialization block
int a;

{
    a = 5;
    System.out.println("this is instance initialization block");
}
```

# Random Topics
  - [Marker/Tagging Interfaces](https://www.baeldung.com/java-marker-interfaces): provides `run-time type` information about objects
```java
public interface FlyBehaviour{
   // no method in here - empty
}
```
   
  - [Formatting Currency]
```java
public class Solution {
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double payment = scanner.nextDouble();
        scanner.close();
        
        // Write your code here.
        
        String us = NumberFormat.getCurrencyInstance(Locale.US).format(payment);
        String india = NumberFormat.getCurrencyInstance(new Locale("en", "in")).format(payment);
        String china = NumberFormat.getCurrencyInstance(Locale.CHINA).format(payment);
        String france = NumberFormat.getCurrencyInstance(Locale.FRANCE).format(payment);
        
        System.out.println("US: " + us);
        System.out.println("India: " + india);
        System.out.println("China: " + china);
        System.out.println("France: " + france);
    }
}
```

## Final Keyword

- [Final vs Effectively Final](https://www.baeldung.com/java-effectively-final#:~:text=In%20simple%20terms%2C%20objects%20or,state%20of%20the%20referenced%20object.): An effectively final variable is a variable whose value is never changed, but it isn't declared with the final keyword. 
- [stackoverflow - best explanation with good example](https://stackoverflow.com/a/32123550/6021740)
- [stackoverflow](https://stackoverflow.com/a/4732617/6021740)
- [blank final](https://www.geeksforgeeks.org/blank-final-in-java/) : A blank final variable in Java is a final variable that is not initialized during declaration. Below is a simple example of blank final. `NOTE: Values must be assigned in constructor`, not elsewhere.
- [Final Static Methods](http://www.instanceofjava.com/2016/08/final-static-method-in-java-example.html)
![image](https://user-images.githubusercontent.com/18373774/113789293-7a276e80-9704-11eb-9633-2ff4f2b2af45.png)


### [Value Type vs Reference Type](http://net-informations.com/faq/general/valuetype-referencetype.htm#:~:text=A%20Value%20Type%20holds%20the,are%20stored%20in%20the%20stack.)

![image](https://user-images.githubusercontent.com/18373774/113783905-19933400-96fa-11eb-8aa0-e287f1216729.png)

- [Passing by Value vs. by Reference Visual Explanation](https://blog.penjee.com/passing-by-value-vs-by-reference-java-graphical/)

![image](https://blog.penjee.com/wp-content/uploads/2015/02/pass-by-reference-vs-pass-by-value-animation.gif)

- [Primitive and reference variables](https://java-programming.mooc.fi/part-5/3-primitive-and-reference-variables)


## Method Overriding vs Method Hidding 
- [From scientecheasy](https://www.scientecheasy.com/2020/08/method-hiding-in-java.html/)

![image](https://user-images.githubusercontent.com/18373774/113787592-eb652280-9700-11eb-8772-fe806a05bd6a.png)

- [stackoverflow](https://stackoverflow.com/a/10292034/6021740)
- [oracle - about classes and everything](https://docs.oracle.com/javase/specs/jls/se8/html/jls-8.html#jls-8.4.3.2)

## Java Monands
- [haskell](http://learnyouahaskell.com/a-fistful-of-monads#monad-laws)
- [youtube](https://www.youtube.com/watch?v=vePeILeSv4E)
- [gitst](https://gist.github.com/ms-tg/7420496#file-jdk8_optional_monad_laws-java)

## Comparator vs Comparable
- [GeeksForGeeks](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/)
> Unlike Comparable, Comparator is external to the element type we are comparing. It’s a separate class. We create multiple separate classes (that implement Comparator) to compare by different members.
- [Baeldung](https://www.baeldung.com/java-comparator-comparable)

## [About Amazon Corretto](https://aws.amazon.com/corretto/faqs/)

## Iterable to Collections
```java
ArrayList<E> list = new ArrayList<>();
iterable.forEach(list::add);
```

- [LinkedList vs ArrayList](https://stackabuse.com/difference-between-arraylist-and-linkedlist-in-java-code-and-performance/)
