# Traveling Politician 

A politician hopes to become the president of the United States. Their campaign starts with the presidential primaries in the capital of Iowa. The politician then wants to visit the capital of every U.S. state to campaign before ending in the White House in the nation's capital of Washington, D.C. The politician does not want to visit any capital more than once. They would like to campaign in every capital one and only once. To be efficient and save on time and money, they would like to do this in as short a path as possible. The Traveling Politician Problem aims to find this shortest path. The map can be thought of as a graph with 51 points (the capitals of all 50 U.S. states, plus Washington, D.C.) and a set of distances between each of them. The starting point and ending point are already set (the capital of Iowa and Washington, D.C., respectively). This leaves 49 points to be visited in between the starting and ending points, this does not include the start and end points.

This problem is much harder than it may sound. The main solution to the problem is factorial time-that is, the time it takes to solve will be proportional to 49!. It is not 51! because the starting and ending cities are already set. After starting in Iowa, one of the 49 remaining capitals can be chosen as the first one to travel to. Now that one of the 49 has been chosen as the first, one of the remaining 48 capitals can be chosen as the second to travel to. Now there are 47 remaining capitals to choose as the third, and so on. The total number of paths to be compared will be 49x48x47x ... 3x2x1, which is 49! (49 factorial). This evaluates to around 6*10^62 different total paths to be compared. That's around a trillion trillion trillion trillion trillion.

One particular mistake is very easy to make here: why not just find the shortest path from the capital of Iowa to any other one state capital, then take the shortest path from there to any other one state capital, and then keep going until you wind up in D.C.? This could possibly give you a better solution than trillions of trillions of other solutions, but it's unlikely to give you the very best overall path to D.C. For example, let's say we only visit Texas and California in the middle: the distance from Iowa to Texas is shorter than the distance from Iowa to California, so you go to Texas first and then to California and then to D.C. This is around 5,300 miles. It's longer to go to California first than to Texas, but if you visit California first, then Texas, then D.C., you get around 4,900 miles, which is the shorter path. As you can see, finding the shortest distance from one capital to another at any given point is not necessarily going to give you the shortest overall path to visit each capital only once.

This problem is based on the "Traveling Salesman Problem", which is a well-known graph theory problem that has been heavily studied by mathematicians. Many resources are available to study this problem under the title "Traveling Salesman Problem".

https://en.wikipedia.org/wiki/Travelling_salesman_problem


## Getting Started

### Prerequisites

The Jupyter Notebook can be viewed in Github but if you wish to run Jupyter Notebook yourself, see the official installation guide [here](https://jupyter.org/install)

Package Requirements:
- pandas
- numpy
- geopy
- permutations from itertools
- maxsize from sys

To see how the state data was created, see [clean_capitals.ipynb](https://github.com/TDEN93/Traveling_Politician/blob/master/clean_capitals.ipynb)

Original solution can be found [here](https://github.com/VinnyDamiano/TravelingPolitician)  
Credit: **Vincent Damiano, Verbus Counts, Trent Rogers**

*This [solution](https://github.com/TDEN93/Traveling_Politician/blob/master/traveling_problem.ipynb) attempts to refactor the original solution above using pythonic methods and PEP 8 styling standards*

## Time
44.3 ms ± 261 µs per loop (mean ± std. dev. of 7 runs, 10 loops each)

## Note
The number of states can be changed by replacing "3" in:  
`middle = list(state_capitals.iloc[:3, 0].tolist())`  
### Warning
**Does not check for out of bounds values**

### TODO
- Verify and fix that D.C distance is not being considered
- Code clean up
- Neatly output results
- Generalize inputs
