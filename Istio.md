
I have a new task, it sounds something like: # Introduce a virtual service for each hybris proxy microservice

so, to get a little of context, we have hybrus monolith and we are switching from monolith to microservices, but this hybrus is used as a database, or so, yet. 

 so, the task is that:
 ```
**Problem Statement:**

Our project has 20+ proxy microservices that call Hybris, the list can be found here: (I won't be posting the link here)

These hybris endpoints are called directly by microservices which doesn’t allow us to inject circuit breaking logic on demand.

**Goal:**

Add logic to the helm chart so that for each microservice listed here () that is calling hybris there is a virtual service created for hybris endpoints with circuit breaking enabled.

In order to be able to potentially handle throttling in future, there should be also one common virtual service before hybris that has a common circuit breaking configuration for all api specific hybris virtual services as depicted below.
```
So I start to decompose the task. Firstly, I need to 