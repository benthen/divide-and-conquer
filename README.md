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
