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

![[Pas

