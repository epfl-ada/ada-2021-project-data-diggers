
# Hierarchical study on American newspapers quotes and speakers’ features.

## Abstract: A 150 word description of the project idea and goals. What’s the motivation behind your project? What story would you like to tell, and why?

American newspapers cover all kinds of topics from politics to sports, business, environment, etc... At the highest level, one could ask which topics people are mostly interviewed about. One way to answer this question is by trying to infer the theme each citation of quotebank is treating in an unsupervised manner and draw a distribution over some labels/classes representing these themes. Once all citations are classified with a certain confidence probability, a lower-level question could be: for each class, is it possible to relate the quotes’ frequency with some real world event? For instance, could an increase of citations about economics forecast some variation in the American stock market? 
Using these classified quotes and using additional data on the authors characteristics, we would like to compare the features of the authors of a particular citation class and try to find recurrent attributes shared between them.

<hr>

## Research Questions: A list of research questions you would like to address during the project.

What are interviewed people mostly talking about in newspapers?
Are there subjects for which there are less citations? Why?
Can we correlate real world events with newspapers’ quotes? Can we predict real world events by looking at newspapers’ quotes ? Why or why not ?
What common characteristics do the authors of citations treating a certain topic have? Do they have recurrent features?

<hr>

## Proposed additional datasets

In order to be able to find similarities between speakers, we will need more information about them, that’s why we will take advantage of the made available metadata about the speakers in Quotebank dataset. 
In addition, with the aim of comparing the quotes classified as treating economics, we will make use of the Dow Jones Industrial Average. This will be done using a csv file containing indices for each day since 2013. 

<hr>

## Methods

To handle Quotebank in its size, we will use Dask which is an open library built to handle large dataset while keeping a low memory footprint. 
NLP to classify quotes (Bertopic?): resulting in probability distributions over the theme classes. 
Select quotes with highest confidence probability and remove others → filter dataset. 
Build as many datasets as classes and work on the new datasets separately (maybe select only a few of them).
For the datasets of interest, compare with real world events’ timeline. 
Enrich the dataset with wikidata on the authors.
For all authors, add a feature “cited in a quote about economics/not economics” (1/0) and proceed a regression analysis on the authors’ features to find correlation coefficients (can be done for all classes adding a feature “class/not class”).

<hr>

## Proposed timeline

3. December: Quotes classified + dataset filtered + metadata + real-life data processed
10. December: Analysis, quotes vs real life, authors attributes analysis
17. December : Milestone 3

<hr>

## Organization within the team: A list of internal milestones up until project Milestone 3.
- Manon: 
- Téo:
- Michael:
- Sébastien:

<hr>

## Questions for TAs (optional): Add here any questions you have for us related to the proposed project.

What should we do in terms of representation of the data? Should we include all the genders and nationalities?
# Hierarchical study on American newspapers quotes and speakers’ features.

## Abstract: A 150 word description of the project idea and goals. What’s the motivation behind your project? What story would you like to tell, and why?

American newspapers cover all kinds of topics from politics to sports, business, environment, etc... At the highest level, one could ask which topics people are mostly interviewed about. One way to answer this question is by trying to infer the theme each Quotebank citation is treating in an unsupervised manner and draw a distribution over some labels/classes representing these themes. Once all citations are classified with a certain confidence probability, a lower-level question could be: for each class, is it possible to relate the quotes’ frequency with some real world event? For instance, could an increase of citations about economics forecast some variation in the American stock market? 
In addition, using these classified quotes and using additional data on the authors characteristics, we would like to compare the features of the authors of a particular citation class and try to find recurrent attributes shared between them.

<hr>

## Research Questions: A list of research questions you would like to address during the project.

What are interviewed people mostly talking about in newspapers?
Are there subjects for which there are less citations? Why?
Can we correlate real world events with newspapers’ quotes? Why or why not ?
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
In order to handle Quotebank in its size, we make use of Dask which is an open library built to operate on large datasets while keeping a low memory footprint by performing lazy computation. This means that it does not compute tasks directly but saves the set of input and executes functions only on demand through the function .compute(). With the latter call, Dask executes the calculation cleverly while minimizing the data stored in memory and parallelizing tasks as much as possible.
We will use BERTopic to perform the classification of the quotes which will result in probability distributions over the theme classes. Subsequently, the quotes with highest label confidence level will be selected and the others removed ending up with a filtered dataset. 
We will then be able to separate the data according to their label and process them separately. 
For each of the new dataset of interest, we will report the frequency of citations and compare this frequency with real world event’s timeline, as for the already mentioned example the Dow Jones index.
Another axis of study consists in performing a regression analysis on the speakers’ features. We will first need to enrich quotebank with metadata on the authors of the quotes. After having stored these additional data in a dataframe, the idea is to add a column of binary variable representing whether or not the quote is labeled to a certain class. Performing a logistic regression, we will be able to define the most relevant features that make a speaker more or less likely to be quoted in a newspaper for a particular subject.

<hr>

## Organization
We have planned the following internal Milestone timeline:
3. December: Quotes classified + dataset filtered + metadata ready + real-life data processed
10. December: Analysis, quotes vs real life, authors attributes regression
17. December : Finalize the analysis, draw conclusions, redaction → Milestone 3

<hr>
## Questions for TAs (optional): Add here any questions you have for us related to the proposed project.
What should we do in terms of representation of the data? Should we include all the genders and nationalities?
