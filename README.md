# CI2024_lab2

## TSP Solutions

### Overview

- I have tried implementing this problem using several different kind of algorithms. The goal was to find the shortest possible route that visits a set of cities and return to the orignal city. 

- My repository contains 4 different algorithms
 1. Brute Force Algorithm
 2. Genetic Algorithms
 3. Nearest Neighbour Algorithms
 4. 2-Opt Optimization

### Code Explanation
1. I have loaded the required data from csv file:
    ```python 
     data = pd.read_csv('cities/vanuatu.csv', header=None, names=['City', 'x', 'y'])

2. I have implemented two different function to calculate the distance
    a. **geodesic_distance(city1, city2)**: Calculates the geodesic distance (curved surface) between two geographical points.
    b. **euclidean_distance(city1, city2)**: Calculates the straight-line distance between two points in Cartesian coordinates.
    c. **calculate_total_distance(tour, country_coords)**: computes the total distance for a given tour of cities.

3. **algorithms Implementations**
    - a. Brute Force:-
       - This algorithms checks all possible permutatons of city tour to find the optimal tour with the minimum distance.
       - For n cities, it requires checkihn n! permutaions.
       - This approch is not effective when the no of cities grows due to the factorial complexity, it results in massive no, of steps.

    - b. Genetic Algorithm:- 
       - The genetic algorithm doesn’t evaluate every possible path; instead, it searches for an optimal or near-optimal solution by evolving a population of possible paths over multiple generations.
        - Each generation represent a step in a counter. Since in my code i am using 500 generations so the steps become 500.
    
    - c. Nearest Neighbour Algorithm
       - This heuristic algorithm is straightforward: starting from an initial city, it repeatedly moves to the nearest unvisited city until all cities are visited.
       - For 𝑛 n cities, this requires 𝑛−1 n−1 steps (moving from one city to the next closest one) plus a final step to return to the starting city.
       - This is the fastest in terms of step count but also more prone to producing suboptimal results because it only considers the immediate nearest city, not the overall shortest path.

    - d. 2-Opt Optimization
       - 2-Opt is a local optimization technique that iteratively improves a given route by swapping two cities at a time to reduce the total distance.

       - Each swap attempt counts as a step.

       - The 2-Opt algorithm requires far fewer steps than brute force or genetic algorithms but more than the nearest neighbor.

       - Its an improved implementation of nearest neighbor. 

