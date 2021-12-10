[[Recommendation System]]

## Collaborative filtering methods
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





