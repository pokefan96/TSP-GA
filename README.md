# TSP-GA
# Genetic Algorithm for Traveling Salesman Problem

This code implements a genetic algorithm to solve the Traveling Salesman Problem (TSP). The TSP is a classic optimization problem that involves finding the shortest possible route that visits a set of cities and returns to the starting city. The algorithm evolves a population of candidate solutions over multiple generations to find the optimal solution.

## Usage
To run the code, ensure that you have Python installed. Simply execute the script, and it will output the best distance and best solution for each generation.

```
python tsp_genetic_algorithm.py
```

## Dependencies
The code requires the following dependencies:
- `random`: A Python module for generating random numbers.
- `math`: A Python module for mathematical operations.

## Functionality

### Generate_Cities(n, width, height)
This function generates a set of cities in a two-dimensional space. It takes three optional parameters:
- `n` (default: 25): The number of cities to generate.
- `width` (default: 200): The width of the solution space.
- `height` (default: 200): The height of the solution space.
It returns a list of tuples representing the coordinates of the generated cities.

### distance_formula(city1, city2)
This function calculates the Euclidean distance between two cities given their coordinates. It takes two parameters:
- `city1`: The coordinates of the first city as a tuple (x, y).
- `city2`: The coordinates of the second city as a tuple (x, y).
It returns the Euclidean distance between the two cities.

### initial_population(cities, population_size)
This function creates an initial population of candidate solutions. It takes two parameters:
- `cities`: The list of cities generated by `Generate_Cities`.
- `population_size`: The number of individuals in the population.
It returns a list of candidate solutions, where each solution is represented as a list of city indices.

### fitness(population, cities)
This function measures the fitness of each individual in the population. Fitness is defined as the total distance traveled in the TSP route for each individual. It takes two parameters:
- `population`: The list of candidate solutions.
- `cities`: The list of cities generated by `Generate_Cities`.
It returns a list of fitness values corresponding to each individual in the population.

### selection(population, fitness)
This function performs parent selection based on fitness. It selects two parents for crossover using a truncation selection strategy, where the top 50% of individuals are considered as potential parents. It takes two parameters:
- `population`: The list of candidate solutions.
- `fitness`: The list of fitness values for the population.
It returns two parent solutions.

### crossover(parent1, parent2)
This function performs crossover between two parent solutions to produce offspring. Crossover is done by selecting a random subset of genes from one parent and filling in the remaining genes with the genes from the other parent. It takes two parameters:
- `parent1`: The first parent solution.
- `parent2`: The second parent solution.
It returns a new solution as the offspring.

### breed_population(population, fitness)
This function creates a new population of offspring solutions through crossover and elitism. It uses the `selection` and `crossover` functions. It takes two parameters:
- `population`: The list of candidate solutions.
- `fitness`: The list of fitness values for the population.
It returns a new population of offspring solutions.

### mutate(population, mutation_rate)
This function applies mutation to the population. Mutation randomly swaps two genes within an individual with a probability defined by the `mutation_rate`. It takes two parameters:
- `population`: The list of candidate solutions.
- `mutation_rate`: The probability of mutation for each gene.
It returns the mutated population.

### evolution(population, mutation_rate, cities)
This function performs one evolution step, which includes creating a new population through crossover and mutation, as well as calculating the fitness of the new population. It takes three parameters:
- `population`: The list of candidate solutions.
- `mutation_rate`: The probability of mutation for each gene.
- `cities`: The list of cities generated by `Generate_Cities`.
It returns the new population, the best distance found in this generation, and the corresponding best solution.

### Main
The main part of the code sets the algorithm parameters, generates the initial population, and iterates through multiple generations of evolution. It prints the best distance and best solution for each generation.

## License
This code is released under the [MIT License](https://opensource.org/licenses/MIT).
