
# Lambdas


## What is it?
* Lambda expressions are used to perform computation based on function abstraction and application.
* Lambda expressions denote _method-invokation deference_.

-
## What is the purpose?
* Lambda expression can be passed as a parameter in a method.
* We treat code in Lambda expressions as data.
	* This piece of code can be passed to other objects and methods.


-
## What is a `FunctionalInterface`?
* A functional interface is an interface that contains only one abstract method.
* Lambda expressions can be used to represent the instance of a functional interface.
* The `@FunctionalInterface` annotation explicitly denotes that
	* this interface can only declare a single method-signature
	* this interface can be expressed as a lambda.

-
## Types of Functional Interfaces
<table>
  <tr>
    <th>Name<br></th>
    <th>Has First Argument<br></th>
    <th>Has Second Argument</th>
    <th>Has Return-Type</th>
  </tr>
  <tr>
    <td>Runnable<br></td>
    <td>no<br></td>
    <td>no</td>
    <td>no</td>
  </tr>
  <tr>
    <td>Consumer<br></td>
    <td>yes<br></td>
    <td>no<br></td>
    <td>no</td>
  </tr>
  <tr>
    <td>BiConsumer<br></td>
    <td>yes<br></td>
    <td>yes<br></td>
    <td>no<br></td>
  </tr>
  <tr>
    <td>Supplier</td>
    <td>no</td>
    <td>no</td>
    <td>yes</td>
  </tr>
  <tr>
    <td>Function</td>
    <td>yes</td>
    <td>no</td>
    <td>yes</td>
  </tr>
  <tr>
    <td>BiFunction</td>
    <td>yes</td>
    <td>yes</td>
    <td>yes</td>
  </tr>
</table>

-
## Runnable
* Takes no arguments
* Return nothing
* An expression which performs a mutation and returns nothing

-
-
## Runnable Syntax (Lambda)
```java
public static void myMethod() {
	Runnable r = () -> System.out.println("Hello world");
	r.run(); // invoke the method
}
```

## Runnable Syntax (Method Reference)

```java
public class MyClass {
	public static void main(String[] args) {
		Runnable r = MyClass::myMethod;
		r.run();
	}

	public static void myMethod() {
		System.out.println("Hello world");
	}
}
```

-
## Consumer
* Takes a single argument
* Returns nothing
* An expression which takes a single argument and returns nothing

-
-
## Consumer Syntax
```java
Consumer<String> c = (str) -> System.out.println(str);
```



-
## Biconsumer
* Takes two arguments
* Returns nothing
* An expression which takes a single argument and returns nothing

-
-
## BiConsumer Syntax
```java
BiConsumer<String, Integer> c = (str, intVal) -> System.out.println(str + intVal);
```

-
-
## Supplier
```java
Supplier<Double> s = () -> Math.random();
```

-
-
## Function

-
-
## BiFunction




## Syntax
<img src = "https://cdncontribute.geeksforgeeks.org/wp-content/uploads/lambda-expression.jpg>
