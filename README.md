# GGRA2

A parametrised Random City Generator

![alt text](https://github.com/micsche/RandomCity/blob/main/images/city-ex1.jpg)

Python generated Random city map

### Algorithm

The city is built on a very simple algorithm. The map consists of buildings, roads and freespaces. 

Each turn of the algorithm, the algorithm randomly chooses a freespace. It fills this space randomly with a random dwelling, after it checks that is fits in the freespace. The algorithm randomly selects if the new dwelling is a corner or not. 

With the new dwelling, new sites for new dwellings (or freespaces) are created. These are created at each side of the dwelling, unless the site is a corner, in which case the freespace is sited on only one side. In front, of the site a new road and also a new freespace are created. Before creating any new freespaces or roads the algorithm checks there is no pre-existing sites or roads.

![alt text](https://github.com/micsche/RandomCity/blob/main/images/algorithm.jpg)

### Parameters available for modification:
Random choices done by the algorithm are fully parametrised, and can be changed.
1. Sizes/shapes: The only available shapes for now are rectangular dwellings spaces. The user can choose the different rectangular shapes.
2. list_of_lists: The user can select the amount of small, medium and large dwellings he wants into the map. "list_of_lists" is an array of number of dwellings vs size wanted. The list is normalised and a probability distribution is created for each type of site size.
3. ROAD_SIZE : is user-selectable. This must be relative to the area size of the dwelling.
4. ANGLE_DEV_STD_DEV : Each dwelling is created twisted compared to the nearby sites. The variable is the standard deviation of the random angle change chosen. The smaller this value, the more straight the roads will be. 
5. PREFERENCE_STRAIGHT : This variable creates more freespaces along the road than freespaces. 
6. NO_OF_BUILDINGS: The number of dwellings in the final map.

### Drawbacks
1. Two roads intersect only when road corner is created. Two long roads cannot intersect at their ends.
2. Some freespaces are created that can never be filled in. Purging must be implemented.
3. As map grows larger, the algorithm finds it harder to place in dwellings.
4. Road sizes are fixed
