## select a model

![[Pasted image 20250915144642.png]]

AI system = Code + Data

model + hyperparameters + data => training => error analysis

1. doing well on training set (avg. training error)
2. doing well on dev/test set
3. doing well on business metrics/

___

performance on disproportionally important examples
performance on key slices of the dataset
rare classes

establish a baseline
![[Pasted image 20250915173833.png]]

unstructured/structured data
image             database
audio
text

* HLP
* Literature search for state-of-the-art/open source
* Quick-and-dirty implementation
* performance of older systems
Baseline helps to indicates what might be possible. In some cases (such as HLP) is also gives a sense of what is irreducible error/Bayes error


TIPS
start
* literature search to see what's possible (courses, blogs, open-source projects)
* find open-source implementation if available
* a reasonable algorithm with **good data** will often outperform a great algorithm with not so good data

should you take into account deployment constraints when picking a model?
- **Yes** if baseline is already established and goal is to build and deploy
- **No** (or not necessary), if purpose is to establish a baseline and determine what is possible and might be worth pursuing

sanity-check for code and alg
* try to overfit a small training dataset before training a large one

___
Error analysis

![[Pasted image 20250915180825.png]]

LandingLens

examine/tag example <=> purpose tags
* specific class labels |  user dempgrafic
* image properties    | product features/category
* other meta-data

useful metrics for tag
- what fracrion of errors has this tag
- of all data with that tag, what fraction is misclassified
- what fraction of old data uses this tag
- how much room for improvment for this tag 

prioritizing

![[Pasted image 20250915181711.png]]

- how much room for improvment
- how fricwently the category appeat
- how easy to improve 
- how important the category

to improve
- collect more data
- use augmentation to get more data
- improve lable accuracy/data quality


skewed datasets

![[Pasted image 20250915182241.png]]

![[Pasted image 20250915182652.png]]

![[Pasted image 20250915182826.png]]

![[Pasted image 20250915183019.png]]

![[Pasted image 20250915183407.png]]


Performance auditing

check for accuracy, fairness/bias, and other problems
1. brainstorm the ways the system might go wrong
   * performance on subset of data (ethnicity, gender)
   * how common are certain errors
   * performance on rare classes
1. establish metrics to access performance against these issues on appropriate slices of data
2. get business/product owner buy-in

data integration

model-centric view (take the data you have and develop a model that does as well as possible)

data-centric view (the quality of the data is paramount. the most models will perform well on good data)

data augmentation

![[Pasted image 20250915210510.png]]

![[Pasted image 20250915210823.png]]

create realistic examples that (i) the algorithm does poorly on, but (ii) humans (on other baseline) do well on
checklist:
- does it sound realistic
- is the x -> y mapping clear? (can human recognize )
- is algorithm currently doing poorly on?

model iteration

can adding data hurt?

for unstructured data problems if
- model is large (low bias)
- the mapping x -> y is clear (given only the input x, humans can make accurate predictions)
then adding data rarely hurts accuracy

adding features

![[Pasted image 20250916120934.png]]

other food delivery example
- only tea/coffee
- only pizza
what are the added features that can help make a decision?
product recommendation
collaborative filtering -> content based filtering

![[Pasted image 20250916121909.png]]

experiment tracking

what to track
- algorithm/code versioning
- dataset used
- hyperparameters
- result
tracking tools
- text files
- spreadsheet
- experiment tracking system
desirable features
- information needed to replicate results
- experiment results, ideally with summary metrics/analysis
- resource monitoring, visualization, model error analyses