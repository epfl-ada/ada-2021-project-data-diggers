
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

## Proposed additional datasets (if any): List the additional dataset(s) you want to use (if any), and some ideas on how you expect to get, manage, process, and enrich it/them. Show us that you’ve read the docs and some examples, and that you have a clear idea on what to expect. Discuss data size and format if relevant. It is your responsibility to check that what you propose is feasible.

In order to be able to find similarities between speakers, we will need more information about them, that’s why we will take advantage of the made available metadata about the speakers in the Quotebank dataset. 
In addition, with the aim of comparing the quotes classified as treating economics, we will make use of the Dow Jones Industrial Average. This will be done using a csv file containing indices for each day since 2013. 

<hr>

## Methods

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
The first major task will be to classify the quotes according to their theme using using Bertopic

<hr>

## Questions for TAs (optional): Add here any questions you have for us related to the proposed project.

Multi-gender?
