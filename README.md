# A hierarchical study of American newspaper quotes and speaker characteristics.

## Abstract

American newspapers cover all kinds of topics from politics to sports, business, environment, etc... At the highest level, one could ask which topics people are mostly interviewed about. One way to answer this question is by trying to infer the theme each Quotebank citation is treating in an unsupervised manner and draw a distribution over some labels/classes representing these themes. Once all citations are classified with a certain confidence probability, a lower-level question could be: for each class, is it possible to relate the quotes’ frequency with some real world event? For instance, could an increase of citations about economics forecast some variation in the American stock market? 
In addition, using these classified quotes combined with additional data on the authors characteristics, we would like to compare the features of the authors of a particular citation class and try to find recurrent attributes or relevant features.

<hr>

## Research Questions

What are interviewed people mostly talking about in newspapers?
Are there subjects for which there are less quotes? Why?
Can we correlate real world events with newspapers’ quotes?
What common characteristics do the authors of citations treating a certain topic have? Do they have recurrent features?

<hr>

## Proposed additional datasets
For the purpose of trying to find similarities between speakers, we will need more information about them, that’s why we will take advantage of the made available metadata about the speakers of the Quotebank dataset. 
In addition, with the aim of comparing the quotes classified as treating economics, we will make use of the Dow Jones Industrial Average. This will be done using a csv file containing indices for each day since 2013. 
Additional libraries used:
Pandas
Numpy
BERTopic
bz2
Dask
Json
<hr>

## Methods
In order to handle Quotebank in its size, we make use of Dask which is an open library built to operate on large datasets while keeping a low memory footprint by performing lazy computation. This means that it does not compute tasks directly but saves the set of input and executes functions only on demand through the function .compute(). With the latter call, Dask executes the calculation cleverly while minimizing the amount of data stored in memory and parallelizing tasks as much as possible.
We will use BERTopic to perform the classification of the quotes which will result in probability distributions over the theme classes. Subsequently, the quotes with highest label confidence level will be selected and the others removed ending up with a filtered dataset. 
We will then be able to separate the data according to their label and process them separately. 
For each of the new dataset of interest, we will report the frequency of citations and compare this frequency with real world event’s timeline, as for the already mentioned example with the Dow Jones index.
Another axis of study consists in performing a regression analysis on the speakers’ features. We will first need to enrich quotebank with metadata on the authors of the quotes. After having stored these additional data in a dataframe, the idea is to add a column containing a binary variable representing whether or not the quote is labeled to a certain class. Performing a logistic regression will allow us to determine the most relevant features that make a speaker more or less likely to be quoted in a newspaper for a particular subject.

<hr>

## Organization
We have planned the following internal Milestone timeline:
3. December: Quotes classified + dataset filtered + metadata ready + real-life data processed
10. December: Analysis, quotes vs real life, authors attributes regression
17. December : Finalize the analysis, draw conclusions, redaction → Milestone 3

<hr>

## Repo structure
![Diagram of our different notebooks and datasest](ADA project structure.pdf)
