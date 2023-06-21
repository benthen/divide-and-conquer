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

* The time complexity of the TSP algorithm using a divide and conquer approach depends on the number of cities (n) and can be analysed as follows:

* The division step is done in a loop, iterating over n-1 cities. Hence, the time complexity is O(n).The conquer step recursively solves subproblems. For each subproblem, the algorithm considers (n-1) cities. The number of recursive calls in the conquer step can be represented by the factorial of (n-1), which is (n-1)!.The combination of solutions does not contribute significantly to the overall time complexity.Considering the above factors, the overall time complexity of the TSP algorithm using a divide and conquer approach is O(n * (n-1)!). As the number of cities increases, the time complexity grows exponentially due to the factorial term. Therefore, the algorithm becomes computationally expensive and inefficient for larger values of n.

* It's important to note that there exist more efficient algorithms, such as dynamic programming (e.g., the Held-Karp algorithm), that can solve the TSP with better time complexities, such as O(n^2 * 2^n). However, the divide and conquer approach still provides a conceptual understanding of the problem and can be used as a starting point for exploring more advanced techniques.
