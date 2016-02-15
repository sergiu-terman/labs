# Laboratory work nr. 1

### Deadlines
Group 1: March 1st, 02:00 GMT+2

Group 2: March 7th, 02:00 GMT+2

### Grading system
- 1 problem  - 6
- 2 problems - 7
- 3 problems - 8
- 4 problems - 9
- 5 problems - 10

*The problem nr 5 coming soon*

Welcome young ones, to the first probability theory lab. Here you have the opportunity to tap into the ancient and sacred art of probability. By solving the following exercises you'll undergo a unique training that will open the door to new opportunities and adventures.

#### Note
The exercises will be solved using **Python** programming language. I know that most of you are accustomed only to **C**, but don't worry. **Python** is a high level language *(soon I'll give you some insight about high level languages)* that is really easy to learn. Using **Python** you can easily prototype solutions to your problems due to the fact that it's backed up by many libraries that cover a large spectrum of domains.

### Python environment setup
I assume that most of you runs a Windows machine that's why I *(strongly)*recommend installing **Anaconda** environment. It comes with a python interpreter *(more bout interpreting and compiling source code click [here](https://www.youtube.com/watch?v=qaj7nO1HUqA))* an editor and a REPL *(something that executes instantly every line of code that you type)* and also it has tons of useful libraries required by lab exercises. Here is the [official anaconda page](https://www.continuum.io/downloads) where you can download the application.

#### Note
When you'll google `"Python"`, you might stumble upon different versions of it. **Python 2.7** is the old one and **Python 3.x** is the new one. Of corse we'll be using the new one. They actually are two different programming languages (though might not look very different). Please do not mistake the python version.


##### Tip
Try to include the python version in your *Google query*, ex: `"I have some specific error python 3"`. This approach might help you to find faster the solution.

### A crash course to Python
[In this link](https://github.com/sergiu-terman/labs/blob/master/tpi/lab1/python_crash_course.md) is a long list of code snippets with explanatory comments. Please go thoroughly through them and try to understand most of them. After you succeed you will be ready to solve  the exercises. [Here you can find the original source](https://learnxinyminutes.com/docs/python3/) of code snippets, that is just in case the trimmed version was not enough for you. I strongly recommend not to go through it unless you're not a beginner to python, or you're accustomed to some other OOP (Object Oriented Programming) languages.

## Exercises
### 1. How much should I bet?
Are you in for some gambling? So these are the rules. A fair coin will be tossed until the first time it comes up heads. If this occurs on the jth toss you are paid 2 to power j dollars. You are sure to win at least 2 dollars so you should be willing to pay to play this game—but how much? Few people would pay as much as 10 dollars to play this game. See if you can decide, by simulation, a reasonable amount that you would be willing to pay, per game, if you will be allowed to make a large number of plays of the game. Does the amount that you would be willing to pay per game depend upon the number of plays that you will be allowed?

### 2. I bet my life on this one
Are you still in mood for gambling? Why don't we get more serious then! Let's roll old school and play some Russian roulette. Here's the deal. I have a revolver with a 6 slots barrel and only 2 bullets. Now i put the bullets into the revolver in **adjacent** slots, spin the barrel and hand you the gun. You point the gun to your head. You pull the trigger and ... Click! you're still alive. Congratulations but the game is not over yet. You have to pull the trigger one last time. Now you have two choices. 1 You spin the barrel afterwards you pull the trigger. 2 You pull the trigger without spinning. Luckily you also have a computer in front of you so you're allowed to simulate the current situation such that you can can make a better decision.

Your task is to find the probability for both cases. After you've computed the probability for the initial conditions please also find out what are the probabilities in case the bullets are not adjacent. After you're done with that, compute the same probabilities only when the gun has a 5 slots barrel and 2 bullets. At the end you have to present the result for 8 different outcomes. Good luck staying alive.

![](http://dailypicksandflicks.com/wp-content/uploads/2015/04/Sharon-Boswell-Obrien-Pie-Face.jpg)


### 3. Old crooked Seidenberg
Listen closer. I'm devising a new gambling game. The rules are straightforward. I have 3 dice. I have to roll them few times. If at least one of my rolled dice fulfills the special condition then I win otherwise the player wins. Special condition: **the sum of my dice has to be 14**. Now remains to solve a small issue that I'm dealing with. What is the number of times I have to roll the dice such that game would seem fair but at the same time would tip the odds in my favor (naturally). But you have to be very careful. If the number of rolls is too great then everybody will understand that the game is a sham hence nobody will play. But if the number of rolls is too small then I'll go bankrupt very soon.

Your task is to find the number rolls required to make the game playable but at the same time to bring profit (winning rate should be a tad smaller than 0.5). Try simulating the game for various number of roles. In order to convince me draw me a plot that shows the winning probability in relation to number of rolls. Remember that you'll obtain a higher probability convergence by increasing the number of simulations, around 10k should be enough.

### 4. Dangerous pixels
![](http://i.imgur.com/d3LvdUo.png)
This morning CIA faxed UTM the following map scan. The total captured surface is around 42 square miles (duh... this imperial metric). With red is marked the land that is mined by the guerrilla forces. Now CIA needs to evaluate the logistics required to defuse the deadly mines. But of course they do not have enough resources to compute the red area. Which is why they are playing their trump card, the brilliant engineers from FAF-151.

The stakes are very high, and lots of innocent lives can be spared. So please compute the mined area a.s.a.p., using Monte Carlo method.

##### Tip
The recommended python library for image processing is **pillow** (not the one you use to sleep).

#### 5. Let's get serious and crack something
This exercise aims to introduce you to very basic concept of hashing algorithms, how they work, why are they useful and what are their weaknesses. And along the way you'll pick up the principle behind the flaw of hashing functions.

Now you're face to face with **md5** hashing algorithm. Your task ahead is to find collisions for this algorithm, (only for the first 40 bits of the hash, aka first 10 hex characters). For that purpose you're going to use **birthday attack**, that is based on birthday paradox (duh).

You have to write a small program that would eventually find a collision for the first 40 bits generated generated by **md5** algorithm.

##### Tip
Cracking the first 40 bits usually takes few seconds (might get to to a duzen of seconds), hence I recommend for starters to find the colision only for first 20 bits. Once it is working you can increase the number.
