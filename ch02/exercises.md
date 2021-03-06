# Exercises

## Comprehension Check
1. Given the following lines of code as they might appear in a source file, how would you change them to use them directly in the REPL?

    **half x = x / 2**

    `let half x = x / 2`

    **square x = x * x**

    `let square x = x * x`

2. Write one function that can accept one argument and work for all the following expressions. Be sure to name the function.

    **3.14 * (5 * 5)  
    3.14 * (10 * 10)  
    3.14 * (2 * 2)  
    3.14 * (4 * 4)**

    `areaCircle r = 3.14 * square r`

3. There is a value in Prelude called pi. Rewrite your function to use pi instead of 3.14.

    `areaCircle' r = pi * square r`

## Parentheses and Association
Below are some pairs of functions that are alike except for parenthesization. Read them carefully and decide if the parentheses change the results of the function. Check your work in GHCi.

1. a) `8 + 7 * 9`

   b) `(8 + 7) * 9`

    parentheses change the results because (*) has a higher precedence than (+)

2. a) `perimeter x y = (x * 2) + (y * 2)`

   b) `perimeter x y = x * 2 + y * 2`

   parentheses do not change the results, same reason as above.

3. a) `f x = x / 2 + 9`

   b) `f x = x / (2 + 9)`

   parentheses change the results because (/) has a higher precedence than (+)

## Heal the Sick
The following code samples are broken and won’t compile. The first two are as you might enter into the REPL; the third is from a source f ile. Find the mistakes and fix them so that they will.
1. `let area x = 3. 14 * (x * x)`

   `let area x = 3.14 * (x * x)`

2. `let double x = b * 2`

   `let double x = x * 2`

3. ```
   x = 7
    y = 10
   f = x + y
   ```

    ```
   x = 7
   y = 10
   f = x + y
   ```

## Head Code
Determine in your head what the following expressions will return, then validate in the REPL:
1. `let x = 5 in x`

   `5`

2. `let x = 5 in x * x`

   `25`

3. `let x = 5; y = 6 in x * y`

   `30`

4. `let x = 3; y = 1000 in x + 3`

   `6`

_Rewrite with where clauses_:

1. `let x = 3; y = 1000 in x * 3 + y`

2. `let y = 10; x = 10 * 5 + y in x * 5`

3. `let x = 7; y = negate x; z = y * 10 in z / x + y`

## Chapter Exercises

### Parenthesization
Given what we know about the precedence of (*), (+), and (^), how can we parenthesize the following expressions more explicitly without changing their results?

1. `2 + 2 * 3 -1`

   `2 + (2 * 3) - 1`

2. `(^) 10 $ 1 + 1`

   `(10^) $ (1 + 1)`

3. `2 ^ 2 * 4 ^ 5 + 1`

   `(2 ^ 2) * (4 ^ 5) + 1`

### Equivalent expressions
Which of the following pairs of expressions will return the same result when evaluated?
1. 1 + 1

   2

   `1 + 1` will evaluate to `2`

2. 10 ^ 2

   10 + 9 * 10

   both expressions will evaluate to `100`

3. 400 - 37

   (-) 37 400

   first expression will evaluate to `363`, second will evaluate to `-363`

4. 100 `div` 3

   100 / 3

   first expression will perform an integer division and evaluate to `33`, the second will perform a fractional division and evaluate to `33.3...`

5. 2 * 5 + 18

   2 * (5 + 18)

   first expression will evaluate to `28`, multiplication will be performed first; second expression will evaluate to `46`, addition will be performed first.

### More fun with functions
Here is a bit of code as it might be entered into a source file. Remember that when you write code in a source file, the order is unimportant, but when writing code directly into the REPL the order does matter. Given that, look at this code and rewrite it such that it could be evaluated in the REPL (remember: you’ll need let when entering it directly into the REPL). Be sure to enter your code into the REPL to make sure it evaluates correctly.
```
z = 7
y = z + 8
x = y ^ 2
waxOn = x * 5
```
1. Now you have a value called waxOn in your REPL. What do you
think will happen if you enter:

    `10 + waxOn == 1135`

    `(+10) waxOn == 1135`

    `(-) 15 waxOn == -1110`

    `(-) waxOn 15 == 1110`

2. Earlier we looked at a function called triple. While your REPL has waxOn in session, re-enter the triple function at the prompt:

   `let triple x = x * 3`

3. Now, what will happen if we enter this at our GHCi prompt. Try to reason out what you think will happen first, considering what role waxOn is playing in this function call. Then enter it, see what does happen, and check your understanding:

   `triple waxOn`

4. Rewrite waxOn as an expression with a where clause

5. Evaluate `triple waxOn` again

6. Add a newfunction called `waxOff x = triple x`

7. a) What is the result of waxOff (-50)?

   b) Modify your waxOff to first triple the x value and then divide it by 10.