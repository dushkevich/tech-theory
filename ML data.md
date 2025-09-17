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
