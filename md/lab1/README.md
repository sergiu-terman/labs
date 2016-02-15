# Laboratory work nr. 1

### Deadlines
Group 1: March 14th, 02:00 GMT+2

Group 2: March 21th, 02:00 GMT+2

### Grading system
- 1 problem  - 6
- 2 problems - 7
- 3 problems - 8
- 4 problems - 9
- 5 problems - 10

*The problem nr 5 coming soon*

### 1. XNOR
Create a program that would ask for two boolean values (true or false, 0 or 1) and would output the result for the XNOR operation performed on them.
You're allowed to use only `and`, `or` and `not` operations

### 2. Truth table solver
You have to write a program that computes the truth table for various expressions. The set of expressions are limited to:

- and operation
- or operation
- not operation
- supports parenthesis

Your program has to receive an input string like `(!x + y) * z + (!z * y * k)` and print out

![](https://github.com/sergiu-terman/labs/blob/master/aux/truth_table.png/?raw=true)

Here are some examples of input that your program should support

```
x + y
!x * y
(!x + y) * x + y * !k
```

###### Note
I strongly recommend to use the python `eval` function. Inventing math operations and their execution priority is **not** the aim of this exercise.


### 3. Leibniz harmonic triangle
Write a program that prints the harmonic triangle for the depth `n`, where `n` is an input value. 


###### Tip
If you're using Python you might look into `fractions` module.

### 4. A game of life foreplay (aka [Elementary cellular automaton](https://en.wikipedia.org/wiki/Elementary_cellular_automaton))
In this problem we're going to take a look at elementary cellular automaton. Every cell is like a small micro organism with a few primitive rules. When combining with other cells they form interesting patterns. There also is an interesting [ted talk](https://www.youtube.com/watch?v=60P7717-XOQ) given by Stephen Wolfram that touches this topic.

Your task is to randomly generate a list (let's say of length 200, it's up to you in the end, just make sure to be long enough) containing only the numbers `0` and `1`. Then you start iterating over the list in order to compute the *next generation*. The rules that apply for the next generation are the following.

| 111   | 110   | 101   | 100   | 011   | 010    | 001 | 000 |
| ----- | :---: | :---: | :---: | :---: | :---:  | :---: | ----: |
| 0 | 1 | 1 | 0 | 1 | 1 | 1 | 0 |

For instance if the cells `1`, `2` and `3` have the value `1 1 0` the 2nd cell of the next generation will be  `1`.

###### Note
For computing the first and the last cell you can consider the missing parent to be `0`

Now you have to compute the next 100 generations and print the resulting matrix with color for value `1` and with white for value `1`. Once You've done that try to change the first generation from randomly generated numbers to all values to be `0` and the last element is `1`. Observe the result.

The rule applied above is called [rule 110](https://en.wikipedia.org/wiki/Rule_110), there is actually a [list of rules](https://en.wikipedia.org/wiki/Elementary_cellular_automaton) that renders quite interesting patterns.

Change arbitrary the initial rules and observe the difference.

*Maybe you can find a new interesting pattern for Bunica's covor*
