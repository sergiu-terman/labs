# Laboratory work nr. 2

### Deadlines
Group 1: May 2nd, 02:00 GMT+2

Group 2: May 2nd, 02:00 GMT+2

### Grading System

### What to do?
In this lab you have the opportunity to solve problems closer to real file. This implies that you have to combine your probability skills with **natural language processing** field, aka NLP. The dataset you are going to use is a list of tweets, found here [tweets.json](www.example.com).

Your task is divided in two topic.

In the first one you have to deal with word frequency and finding out the most popular and interesting words.

The second topic is about typing prediction. A good use case for typing prediction is a smartphone. While writting messages to your beloved friends is a cumbersome work to do (many many taps on you display), the phone operating systems usually comes with a typing prediction software. Now while you type your text a list of suggestion pops up at every keystroke. Your task would be to write programs that does something simmilar, naturally in a simplified version (no need to write mobile applications).

#### The NLP part
One of the main issue of text processing is breaking a text into words. At the first glance it seems to be an easy job. For instance you have the sentece `Today is a shiny day`. Easy enough you just use the python built in tool `sentence.split()` (where sentence is the string). Now you have a list of words. But as you know words in a text come hand in hand with characters like **. , ! ? "** and a bunch of other. So extracting words from a senence like **Now! Tell me what is your "problem"?** is suddenly more difficult. 

NLP libraries hold an extensive toolset for text processing. In this lab you'll be only scratching the surface of the whole potential of NLP. The word extraction problem mentioned above can be solved with a simple function call. For python you can use the `import nltk`.

#### The dataset
The data that you have in this laboratory work is a **JSON** string. It is a popular data format. One of the advantage is that it is easy to read. Also it's very easy to transpose the data into python primitives like lists dictionaries strings and integers. For that you have to import in your python script `import json` and you can use it like this `result = json.loads(input_string_you_read_from_file)`. In the `result` now you'll have either a python **list** or a **dictionary**. That's easy.

# Frequency 

### 1
Write a program that prints the first 10 most frequently used **words**, and the number of times it was mentioned.

### 2
Write a program that prints the first 10 most frequently used **nouns**, and the number of times it was mentioned.

### 3
Write a program that prints the first 10 most frequently used **proper nouns**, and the number of times it was mentioned.

### 4
Write a program that receives a word as an input and draws a frequency bar chart for the last 2 years. Every bar should represent the period of 2 months.

### 5
In our dataset we also have the number of likes and retweets for every message. This can give us some insight about the tweet popularity. Hence we can compute some sort of rating. The popularity of nouns is computed by the following formula `frequency * (1.4 + normRetweet) * (1.2 + normLikes)`. The values **normRetweet** and **normLikes** are the normalized values of likes and retweets for every word. To compute the number of likes and retweets for every word you just cumulatively collect the numbers from every tweet that the word was mention.

Ex: There are 2 tweets that mention the noun **program**. First tweet has **32** retweets and **87** likes. The second tweet has **42** retweets and **103** likes. The number of retweets the word **program** is **32 + 42** and the number of likes is **87 + 103**.

Write a program that prints the first 10 most popular **nouns**. The populartiy is defined by the computed rating discussed above.

# Typing prediction

#6
Write a pogram that receives as input an **unfinished word** and prints 3 word suggestions, followed by their frequency. The suggestions should be based on the initial dataset and sorted by the word frequency, computed in the first problem.

Ex. Input: `ap`, Output: `application (324), apple (164), appreciate (53)`. Where `application has the highest frequency, `apple` the second highest etc. 

Ex. Input: `pro`, Output: `programming (196), product (176), program (103)`. Again `programming` has the highest frequency.

#7
Write a program that receives as input a **word** and prints 3 word suggestions, followed by the **suggestion occurrences**.


The suggestions should be selected in the following way. You have to go through your tweets dataset and identify every occurrence of the input word. A every occurrence collect the word that follows the input word. That is the suggestion you are looking for. And also don't forget to count the number of times you got the same suggestions. Ex: input `like` and you find 5 occurrences of `like beer` and 2 occurrences of `love labs`. Your suggestion words would be `beer` and `labs`. But `beer` has a priority because it occured more times in your dataset. Your task it to select the most relevant suggestions as in the one that occured the most.

Ex. Input: `love`, Output: `programming (5), cars (2), beer(2)`

Ex. Input: `awesome`, Output: `party (10), language (4), framework (2)`
