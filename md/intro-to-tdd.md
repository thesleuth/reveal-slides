#Introduction to TDD



-
-
#3 laws of TDD

###First Law

You may not write production code until you have a written a failing corresponding unit test.

```
	public class Cow{
		public Cow(){}

		public String speak(){
			//BAD DOBBY
			return "Mooooow";
		}
	}

```

-
-
###First Law

You may not write production code until you have a written a failing corresponding unit test.

```
public class CowTest{

	@Test
	public void speakTest(){
		Cow cow = new Cow();
		String expected = "mooo";
		String actual = cow.speak();
		Assert.equals(expected, actual);
	}
}
```

-

```
public class Cow{
	public Cow(){}

	public String speak(){
		//Good DOBBY
		return null;
	}
}

```

-
#3 laws of TDD

###Second Law

You may not write more of a unit test than is needed to fail, and not compiling is failing.

```
public class CowTest{

	@Test
	public void speakTest(){
		Cow cow = new Cow();
		String expected = "mooo";
		String actual = cow.speak();
		Assert.equals(expected, actual);
	}
}
```

-
#3 laws of TDD

###Third Law

You may not write more production code than is sufficent to pass the current failing test.

```
public String speak(){
	String sound = "Mooooo";
	//BAD DOBBY!!!!
	String bucketsOfMilk = this.milkMe();
	return sound;
}
```

-
-

#Clean Code and Clean Test

A clean test is a readable Test

```
@Test
public void testFunction(){
//Bad Dobby
Unicorn unico = New Unicorn();
int x = 23;
int y = unico.saveThePrincess();
Assert.equals(x,y);
}

```

-
```
@Test
public void testCountToTwo(){
//Good Dobby
Unicorn unico = New Unicorn();
int expectedNumber = 2;
int actualNumber = unico.countToTwo();
Assert.equals(expectedNumber, actualNumber);
}
```
-
-
#One Assertion to Rule them All

A good unit test should have one assertion, which should also be quick and easy to understand. **SINGLE RESPONSIBLITY**

Single Concept per test

* Given (Sets the stage)
* When (Performs the action)
* Evaluate (Checks the results)

-
-
#F.I.R.S.T

* **F** is for **fast** - The test should be fast. If it's going to fail, let's get it over with
* **I** is for **Independent** - every test is an island, a "LONELY ISLAND". Executing it should not affect other test
* **R** is for **Repeatable** - every test should be able to run in any environment , local, QA, and Production
* **S** is for **Self-Validating** - every test should have one asserttion
* **T** is for **Timely** - test should be written FIRST... OR ELSE!!!
