## Intro to Algebraic equations


-
-


###Basic Algebra

Algebra is about using letters in place of numbers. 

Sometimes it’s possible to work out
what the letter represents.

-
###Basic Algebra (continued)

If you were told that ```𝑥 + 7 = 15```, you can probably see deduce that ```𝑥 = 8```.

If you were told that ```𝑦 − 11 = 5```, you can probably see straight away that ```𝑦 = 17```.

These are examples of linear equations, which we’ll look at in more detail.

-

###Writing Algebraic Expressions

Writing an **algebraic expression** is like writing a sentence in a mathematical way. This is achieved by assigning letters to numbers. 

An **algebraic expression** is a set of instructions on
how to perform a calculation.

-
###Writing Algebraic Expressions (continued)
####Example:

Write the following as an algebraic expression:

- Five times a number minus three times another number.

-
###Writing Algebraic Expressions (continued)

First, I need to assign letters to the **‘unknown’** numbers. We'll call the first one ‘n’ and the
second one ‘m’ so that it is now:

- Five times **n** minus three times **m**.

-
###Writing Algebraic Expressions (continued)

Next, replace the words with mathematical symbols, leaving:

```
5 x n – 3 x m
```

which would be cleaned up to be: 

```
5n – 3m 
```

(notice that we don’t
need the multiplication sign as it is implied).

-

In JavaScript, however, the asterisk **(*)** is used to indicate multiplication,  so it would be would be represented as such: 

```
5*n - 3*m
```


-
###Writing Algebraic Expressions (continued)

A number divided by three: can be written as:

```
𝒙/𝟑
```

Half of a number plus quarter of another number: can be written as: 

```
𝒙/𝟐 + 𝒚/4
```

A number plus 5 all multiplied by 3 can be written as:

```
(𝒏 + 𝟓)𝟑
```

-

We usually put the number at the front so we could rewrite this as:

```
𝟑(𝒏 + 𝟓)
```

In Javascript, it would be written as: 

```
3 * (n+5)
```


When writing algebraic expressions, you may choose any letter, just make sure that different numbers are assigned to different letters.


(Notice that the first and second numbers are replaced with **‘n’** and **‘m’**).

-
-

##Simplifying Expressions:

Once you have an algebraic expression it can be simplified by collecting all the ‘like terms’
together (i.e. combining things that are the same letter or combination of letters). If an
expression includes brackets then you may need to multiply out the brackets first to see
what will combine.

Examples:


Simplify the following expression: 

```
𝟑𝒂 + 𝟕𝒃 – 𝟐𝒄 – 𝟒𝒃 – 𝟔𝒄 + 𝒂
```

-

###Collect together any letters that are the same

Look at the a’s: 

```
3𝑎 + 𝑎 = 4𝑎
```

Look at the b’s:

```
7𝑏 – 4𝑏 = 3𝑏
```

-
###Collect together any letters that are the same (continued)

Look at the c’s:

```
−2𝑐 – 6𝑐 = −8𝑐
```

-
###Collect together any letters that are the same (continued)

Put everything together and we have: 

```
𝟒𝒂 + 𝟑𝒃 – 𝟖𝒄
```

In Javascript, it would be written as:

```
(4 * a) + (3 * b) - (8 * c)
```

-
-

###Multiplying out Brackets:

Simplify the following: 

```
𝟑𝒂 (𝒃 – 𝒄) + 𝟓𝒂𝒃
```

-

###Multiplying out Brackets (continued)

First remove the bracket. To do this you need to multiply the bit (term) outside the bracket
by every bit (term) inside the bracket.

```
3𝑎 (𝑏 – 𝑐) + 5𝑎𝑏

3𝑎 × 𝑏 = 3𝑎𝑏

3𝑎 × – 𝑐 = − 3𝑎𝑐
```


-

###Multiplying out Brackets (continued)

So after multiplying out the brackets we have: 

```
3𝑎𝑏 − 3𝑎𝑐 + 5𝑎𝑏 = 𝟖𝒂𝒃 − 𝟑𝒂𝒄
```

-
###Multiplying out Brackets (continued)

Simplify the following: 
```
𝟑(𝟒𝒚 + 𝟐) − 𝟓𝒚 + 𝟏𝟐
```


-

###Multiplying out Brackets (continued)

First remove the bracket. To do this you need to multiply the bit (term) outside the bracket
by every bit (term) inside the bracket.

```
3 (4𝑦 + 2) − 5𝑦 + 12

3 × 4𝑦 = 12𝑦

3 × 2 = 6
```


-

###Multiplying out Brackets (continued)

So after multiplying out the brackets we have: 

```
12𝑦 + 6 − 5𝑦 + 12 = 𝟕𝒚 + 𝟏𝟖
```

In Javascript, it would be

```
𝟕*𝒚 + 𝟏𝟖
```

-
-

###Solving Equations with one Unknown

An equation which doesn’t have any squared, cubed, or higher powers is called a **linear equation.** E.g. ```3𝑥 + 2 = 14```.

When solving a linear equation you are trying to find the **value** of the letter in the equation.

To do this, you need to make the letter the **subject** of the equation (i.e. leave it on its own, at one side of the equation).

-
###Solving Equations with one Unknown (continued)

When rearranging equations, we follow this order: 

- Remove Brackets

- Add or subtract

- Multiply or divide

- Indices (powers)

Notice that apart from the Brackets still being first, this is BIDMAS in reverse, because we are ‘reversing’ or ‘undoing’ the equation.

-
###Solving Equations with one Unknown
#####Examples:

Solve the equation: 

```
5a = 15
```

-
###Solving Equations with one Unknown (continued)

Starting Equation has a multiplication: 

```
5a = 15
```

Divide each side by 5 to make ‘a’ the subject 

```
a = 3
```

We have solved this simple equation, and found the answer: 

```
a = 3.
```

-
###Solving Equations with one Unknown (continued)

Solve the equation: 

```
4b – 3 = 17
```
(Hint: collect b’s at one side, numbers at the other.)

Starting Equation: 

```
4b - 3 = 17
```

Add 3 to each side (to get rid of the -3):

```
4b – 3 + 3 = 17 + 3
```

Clean it up: 

```
4b = 20
```

Divide each side by 4 to leave ‘b’ on its own:

```
b = 5
```

-

###Solving Equations with one Unknown (continued)

Solve the equation: 

```
5y – 6 = 2y + 3
```
(collect y’s at one side, numbers at the other.)

Starting Equation. 

```
5y – 6 = 2y + 3
```

Add 6 to each side (to get rid of the -6):

```
5y – 6 + 6 = 2y + 3 + 6
```

-
###Solving Equations with one Unknown (continued)

Clean it up: 

```
5y = 2y + 9
```

Take 2y from each side (so y’s only on left):

```
5y – 2y = 2y – 2y + 9
```

Clean it up: 

```
3y = 9
```

Divide each side by 3 to leave ‘y’ on its own:

```
y = 3
```

-

###Solving Equations with one Unknown (continued)

Solve the equation: 

```
14 (m + 3) - 5 (2m + 6) = 44
```

-

###Solving Equations with one Unknown (continued)

First, multiply out the brackets, so that we can combine like terms.

Starting Equation: 

```
14(m + 3) - 5(2m + 6) = 44
```

Multiply out brackets: 

```
14m + 42 – 10m - 30 = 44
```

Collect like terms (m’s and numbers):

```
4m + 12 = 44
```

Take 12 from each side (to get rid of 12):

```
4m + 12 - 12 = 44 - 12
```

Clean it up:  

```
4m = 32
```

Divide each side by 4 to leave ‘m’ on its own: 

```
m = 8
```
-
###Solving Equations with one Unknown (continued)

A quick method:

- Look through the above examples again and notice that 
it looks like:

- When something moves to the other side of the equals sign it does the “opposite”. E.g. **+** becomes **-**, **x** becomes **÷** and vice versa.


-
###Solving Equations with one Unknown (continued)

Notice that in the second example, **-3** disappeared from the left and became **+3** on the right, in the third example, **2y** disappeared from the right and became **+2y** on the left etc.
