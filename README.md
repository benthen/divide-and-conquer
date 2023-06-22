# Pseudocode of Divide and Conquer Algorithm to solve Travelling Salesperson Problem

1. Start
2. function main()
   1. Start
   2. Declare cityDistance, cityNum, and minDistance
   3. Read the number of cities (cityNum) from the user
   4. Initialize cityDistance matrix of size cityNum x cityNum
   5. Read cityDistance matrix from the user
   6. Initialize minDistance to infinity
   7. Create an array of cities from 0 to cityNum-1
   8. Call function divideAndConquer(cities, 0, cityNum-1)
   9. Print minDistance
  10. End

3. function divideAndConquer(cities, start, end)
   1. Start
   2. if start == end 
         1. cost = calculateCost(cities)
         2. if cost < minDistance 
            1. then minDistance = cost
   3. for i = start to end 
         1. swap(cities[start], cities[i])
         2. divideAndConquer(cities, start + 1, end)
         3. swap(cities[start], cities[i])
   4. End

4. function calculateCost(cities)
   1. Start
   2. totalCost = 0
   3. for i = 0 to cityNum-2 
         1. totalCost += cityDistance[cities[i]][cities[i+1]]
   4. totalCost += cityDistance[cities[cityNum-1]][cities[0]]  
   5. return totalCost
   6. End

5. function swap(a, b)
   1. temp = a
   2. a = b
   3. b = temp

6. End

# Example of input
![image](https://github.com/benthen/divide-and-conquer/assets/111986781/874af583-45cd-4615-bb8f-fa22839eb383)

# Example of outpupt
![image](https://github.com/benthen/divide-and-conquer/assets/111986781/1923ce20-c4d4-4270-9157-6d71f0c5eb5c)

# Analysis of Divide and Conquer Algorithm

### The time complexity of the TSP algorithm using a divide and conquer approach depends on the number of cities (n) and can be analysed as follows:

* The division step is done in a loop, iterating over n-1 cities. Hence, the time complexity is O(n). The conquer step recursively solves subproblems. For each subproblem, the algorithm considers (n-1) cities. The number of recursive calls in the conquer step can be represented by the factorial of (n-1), which is (n-1)!. The combination of solutions does not contribute significantly to the overall time complexity. 
* Considering the above factors, the overall time complexity of the TSP algorithm using a divide and conquer approach is O(n * (n-1)!).
> As the number of cities increases, the time complexity grows exponentially due to the factorial term. Therefore, the algorithm becomes computationally expensive and inefficient for larger values of n.

### The correctness of the Travelling Salesman Problem (TSP) algorithm using a divide and conquer approach can be analysed as follows:

* In the divide step of the algorithm, the problem is divided into smaller subproblems by permuting the cities. Each subproblem represents finding the shortest path for a subset of cities. The correctness of the algorithm depends on the correctness of solving these subproblems.
> The base case occurs when there is only one city left. In this case, the algorithm directly calculates the cost of the single city tour, which is correct by definition.
  
* In the combine step, the algorithm combines the solutions of the subproblems to find the overall solution. It selects the minimum distance among the solutions obtained from different permutations of cities. This step ensures that the algorithm returns the correct solution by considering all possible city tours. The divide and conquer approach systematically explores all possible permutations of cities, ensuring that no potential solution is overlooked.
> By checking all permutations, the algorithm guarantees finding the optimal solution, which is the shortest distance required to visit all cities and return to the starting city.

