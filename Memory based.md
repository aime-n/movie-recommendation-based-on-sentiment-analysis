[[Collaborative filtering methods]]

## 1) Memory based
Works directly with past data, doesnt assume model. 
- ==Nearest neighbours search==
- large sparce vectors
ex = find closest users and sugest its popular items
- since it doesn't have a model, it uses only past interactions between users/items, it theoretically has a low bias (no model) and a high variance.

Method | Resume
--- |---
User-user | find similar users and recommend its popular items
Item-item | find similar items

Complexity  of KNN algorithn = O(ndk)
- n users
- d items
- k neighbours

Dealing with complexity:
- sparsity of the interaction matrix
- ANN (approximate nearest neighbours method)



### User-user method
aka user-centred
Basically map users, their distances between each other and their interactions with items.

**Interaction matrix**: n users X m items

Row = users:
- the row shows the interactions of the user with each items
	- can be positive, neutral or negative

**knn finds similar users (row)**

Column = items:
- within the similar users, it finds the items to recommend

![[Pasted image 20211209153315.png]]

The interaction matrix can represent the interaction of a user with different items. We can use this interaction matrix of interest to find a similar user. The similarity is taken as closeness, especially if the have a lot of items in common \*. Then we can choose the K and recommend popular items in the group.

OBS: two users can have 1 item in common and in total and they can be 100% compatible. on the other side, two users can have 98/100 items in common and be less compatible (98%). So, we have to pay attention on the quantity of similar items.

### Item-item method
aka item-centred

> Two items are considered to be similar if most of the users that have interacted with both of them did it in a similar way.
\- Towards Data Science

It finds distances between items, and their similarities is proportional to the number of users in common that interacted with it the same way.

**Interaction matrix**:

- choose preferred item of a user
- represent the item as a vector of interaction with every user (column)
- knn searches for similar vector of interactions == 

![[Pasted image 20211209152911.png]]

Row = users:

Column = prefered items:

**knn finds prefered items (column)***

OBS: we can user the favorite item of a user, or n most liked items.

### User-centred vs Item-centred

||User-centred | Item-centred
---| --- | ---
search for | users with similar interactions with items | items with similar users interactions
advantage | personalized results | lots of interactions for each item
problem | few interactions with items for each user|  less personalized
variance | high, because it's sensitive to few interactions | low
bias | low, because the users are similar |  high
recommends | items that users neighbors like | items neighbors of the favorite user's item

