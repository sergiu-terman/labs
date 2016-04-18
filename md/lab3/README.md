# Laboratory work nr. 3

### Deadlines
Group 1: May 16nd, 02:00 GMT+2

Group 2: May 16nd, 02:00 GMT+2

### Grading System
Add the accumulated score to 4 to obtain your grade:
- 1: 0.5
- 2: 1
- 3: 0.5
- 4: 2
- 5: 2

##### Note
In case you accumulated a mark in form of `x.5` (ex: `8.5`) the mark will strongly depend on your report. If you did a lousy job on your report the mark will be floored `$ echo "from math import floor; print(floor(8.5))" | python`.


#### The dataset
The dataset is a text file where every line reprents a JSON object that describes a tweet ([tweets.txt](https://github.com/sergiu-terman/labs/blob/master/aux/tweets.txt/?raw=true)). It was fetched using twitter stream API, hence we're dealing with real life data (yay).

## 1
Write a program that prints on the screen 10 most popular #hashtags followed by the number of occurrences of the #hashtag.

## 2
Let's do some emotional analyses.

In this file [AFINN-111.txt](https://github.com/sergiu-terman/labs/blob/master/aux/AFINN-111.txt/?raw=true) you'll find an emotion dictionary for English words. Every word mentioned in the dictionary is followed by a numerical value in the range of -5 to 5. The numerical value describes the word emotional impact where -5 is the most negative and 5 is the most positive.

Your task is to find the emotional value for every tweet. First step would be to extract every word from the tweet body. I recommend using an `nltk tokenizer` (similar to TPI Lab 3). Then you find out the emotional value for every word (if it has one). You finish by summing the emotion rating.

Write a program that will store the computed result in a text file. Every line should represent the tweet id followed by the computed emotional value.

## 3
Write a program that prints on the screen 10 most positive tweets and 10 most negative tweets.

# Let's visualize some data
For data visualization we're going to use Gephi. You can download it from [here](https://gephi.org/). Gephi is a tool for drawing graphs and various graph manipulations that can help you extract valuable conclusions out of it. [Here](https://www.youtube.com/watch?v=kbLFMObmLNQ) you can find a neat tutorial on how to use Gephi, it's a bit outdated but it should shed some light on the tool potential.

#### Loading the graphs in Gephi
A major part of your job is to create a file that can be fed to Gephi. [Here](https://gephi.org/users/supported-graph-formats/) is the list of the entire range of formats supported by Gephi. The more descriptive XML based formats allow a more detailed graph customization. But in our case a CSV (comma separated values) formatted file should suffice. You can google more details about CSV format, once you're done you can find out [here](https://gephi.org/users/supported-graph-formats/csv-format/) how to format your file in order to be able to load it to Gephi.

## 4

Firstly you have to select 200 tweets from the initial dataset. From every tweet message text you have to extract the words (you guessed right, using a tokenizer). Every word should represent a graph node. The graph edges represent the connection between words in every tweet message.

Example: tweet 1: "What a sunny day", tweet 2: "This day is awful"

The words have to be connected in the following way:

```
What -> a, sunny, day
a -> What, sunny, day
day -> What, a, sunny, This, is, awful
This -> day, is, awful
is -> This, day, awful
awful -> This, day, is
```

#### First step
Write a program that will generate a CSV file that represent the word connection in the selected 200 tweets.

#### Second step
- Load the generated CSV file to Gephi
- Apply the ForceAtlas layout
- Apply text labels for the nodes (resize them if needed)
- Apply the modularity colors for the obtained clusters
- Set the different node size depending on the number of connections it has with other nodes
(Everything just like in the video tutorial mentioned above)

### ACHTUNG!! IMPORTANT!! TWEET SELECTION!!
In the current dataset are 10K tweets. In order to select your 200 tweets you have to do the following. Compute `value = 200 * numărul_meu_din_catalog` (from the big list 1..~30) and start reading the tweets from the line number equal to `value`.

Example: `Sergiu Terman, numărul_meu_catalog = 23, value = 23 * 200 = 4600`. So I select my 200 tweets from the dataset starting the line `4600`.

## 5
Let's clean a bit the data. Once you finished the exercise 4 you can be able to distinguish the noise in your data. Nodes that have lots of connections like `a`, `t`, `http`, and other irrelevant nodes that does not bring any value, more than that it only pollutes our graph.

Your task is to select a list of handpicked words (of the size at least 15) that you consider to be most irrelevant for your current graph (usually the big unimportant nodes). The second step is to patch your script from exercise 4 such that when you will generate the CSV it will not include the nodes from your list of selected words.

Once you've generated the new CSV repeat the **second step** from exercise 4.

Enjoy your last lab ;)
