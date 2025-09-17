![[Pasted image 20250916170407.png]]

why is data definition is hard?

![[Pasted image 20250916170313.png]]

![[Pasted image 20250916171043.png]]

data definition questions
- what is the input x?
   -  light? contrast? resolution?
   - what features to include?
- what is the target label y?
  - how can we ensure labelers give consistent labels?

![[Pasted image 20250916172125.png]]

unstrct
- may or may not have huge collection of unlabled examples x
- humans can lable more data
- data augmentation more likle to be helpful
struc
- may be difficult to obtain more data
- human labeling may not be possible

small <= 10000
- clean labels a critical
- can manualy look
- can get all the labels talk to each other
big >10000
- emphasis data process

![[Pasted image 20250916175707.png]]

![[Pasted image 20250916175929.png]]

big data problems can have small data challenges too
big dataset with long tail of rare events will have small data problems
- web search
- self driven car
- product recommendation system

Improving label consistency
- have multiple labelers label same example
- when disagreement have MLE, SME and/or discuss definition of y the reach agreement
- if labelers say x doesn't contain enough information change x
- literate until it is hard to significantly increase agreement

![[Pasted image 20250916180910.png]]

![[Pasted image 20250916181157.png]]

small data
- usually small number of labelers
- can ask labelers to discuss specific labels
big data
- get consistent definition with small group
- then send labeling instructions to labelers
- can consider having multiple labelers label every example and using voting or consensus labels for accuracy

why measure HPL

![[Pasted image 20250917132716.png]]

- in academia establish and beat a respectable benchmark to support publication
- hlp helps establish a reasonable target
- prove that ML system is superior to human doing the job and thus the business should adopt it (use with caution)

![[Pasted image 20250917133343.png]]

![[Pasted image 20250917133937.png]]

when HLP < 100% may indicate ambiguous labeling instruction

![[Pasted image 20250917134229.png]]

obtaining data

![[Pasted image 20250917134716.png]]

![[Pasted image 20250917135043.png]]

labeling data
- options: in-house vs outsourced vs crowdsourced
- having MLEs label data is expensive. But doing this for just a few days is usually fine
- why is qualified to label?
   - speech any fluent
   - factory inspection, medical diagnosis - SME
   - recommender system maybe impossible to label well
- don't increase data by more  than 10x at time

data pipeline

![[Pasted image 20250917161117.png]]

![[Pasted image 20250917163143.png]]

POC and production phases
POC (proof of concept)
- goal is to decide if the application is worcable and worth deploying
- focus on getting the prototype to work
- it is ok if pre-proccessing is manual. but take extensive notes/comments
Production phase
- after project utility is established, use more sophisticated tools to make sure the data pipline is replicable
- e.g. TensorFlow, Transform, Apache Beam, Airflow...

![[Pasted image 20250917164757.png]]

meta-data
examples: 
- manifacturing visual inspection: time, factory, line#, camera settings, phone model, inspector ID
- speech recognition: device type, labeler ID, VAD model ID
useful for
- error analysys, spotting unexpected effects
- keeping track of data provenance

![[Pasted image 20250917170503.png]]

https://csgaobb.github.io/Projects/DLDL.html

https://cs230.stanford.edu/blog/datapipeline/#best-practices

https://blog.tensorflow.org/2021/01/ml-metadata-version-control-for-ml.html

https://cloud.google.com/blog/products/ai-machine-learning/key-requirements-for-an-mlops-foundation

!git clone https://github.com/https-deeplearning-ai/MLEP-public.git

[[ML deployment]]
[[ML model]]
