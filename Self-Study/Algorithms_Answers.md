# Analysis of Algorithms

## Exercise I

<br/><br/>
a) In our loop, we are iterating while a is less than n^3 so that would suggest runtime complexity of O(n^3) at first glance. However, the value of a is getting updated by about n^2 during every iteration. This means that our loop is running while n^2 < n^3. The difference between those two values is n, so our runtime complexity should be O(n).
<br/><br/>
b) Our outermost loop has runtime complexity O(n). The next two loops down also have runtime complexity O(n) if we drop the constants in each range. The final loop should also have runtime complexity O(n) because k is being derived from a loop that iterates n times. This suggests that our algorithm has overall complexity of O(n^4).
<br/><br/>
c) The best-case runtime for this solution is O(1) if the bunnies argument is 0. If bunnies > 0, this algorithm will break as currently written. This suggests undefined runtime complexity. If we assume the typo is fixed (bunnieEars vs. bunnyEars), the algorithm will have runtime complexity O(n) (where bunnies = n) because it reduces the count of bunnies by 1 every time it recurses.
<br/><br/>
<br/><br/>

## Exercise II

<br/><br/>
I will proceed to describe the answer in plain English.
<br/><br/>
Let us first try to solve the problem in a very naive way. Given n floors, we can drop an egg starting at the ground floor and working our way up to the critical floor f (the floor at which an egg first breaks). If the critical floor f is actually floor n, this naive algorithm would have runtime O(n). This is not good.
<br/><br/>
A better way to do this might be binary search. With this approach, we can divide our building into two subsets at floor n/2. If the egg breaks at n/2, we can repeat the process with the lower subset; if it does not, try the higher subset. Some complexity may arise when it comes to verifying that the selected floor is the critical floor; on any floor that the egg breaks on, we should check whether it breaks on the floor right beneath. If it doesn't, we've found the critical floor. Binary search by itself has runtime complexity of O(log n). Considering that this implies log n verification checks, we can say that this binary search variation will have runtime complexity O((log n)^2)
