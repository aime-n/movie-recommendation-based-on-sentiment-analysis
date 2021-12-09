# Collaborative filtering methods
user-item interactions matrix
- system uses past interactions to sugest new recommendations
- predictions on estimated proximities between users and/or items

**Advantage** = doesn't require info about user or item, it uses only interactions. the more interactions, the more precise and effective the recommendation will be
**Desadvantages** = new users/items don't have interactions (cold start problem)

**Solutions**:
	- random strategy: recommend new things to random users
	- maximum expectation strategy: popular items to new users
	- exploratory strategy: various itens to new users or new item to various users
	- using a non collaborative filtering for new users/items

Collaborative filterings are divided in two categories:

1) Memory based
- recommentations based on similarities of observed interactions

2) Model based approaches
- recommendations learned from interaction matrix

## 1) Memory based
Works directly with past data, doesnt assume model. 
- ==Nearest neighbours search==
- large sparce vectors
ex = find closest users and sugest its popular items
- since it doesn't have a model, it uses only past interactions between users/items, it theoretically has a low bias (no model) and a high variance.


## 2)Model based approaches
tries to model a ==generative model on user-item interactions== to make new predictions.
small dense vectors
ex: matrix factorisation
- it has a latent model, so, theoretically it has a bigger bias (model per se)  and a lower variance

> The users and items latent representations extracted by the model have a mathematical meaning that can be hard to interpret for a human being. 
\- Towards Data Science



