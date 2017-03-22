# Space Time and Runtime Complexities:

All interview conversations have been known to end with :

“Whats the time complexity of the solution ?”
“Can you improve the time complexity of your solution ?”

Time Complexity is running time of algorithm
- Depends on whether processor is single processor or multi processor.
- Depends on Read or write speed to memory
- Depends on 32/64 bit architecture of your machine
- Input --> MOST IMPORTANT - EVERYTHING ELSE DOESNT MATTER

During Time complexity, we dont care about any of those factors except for INPUT.

Model machine: single 32 bit processor that exequtes sequentially taking 1 unit of time for arithmatic/logical operations, assignments and returns.

Find: Rate of growth with respecto of the input:

E.G:
'''
sum(a,b){
return a + b;
}
'''
Time taken: 2 UNITS because 1 for return and 1 for addition.
this is a constant time algorithm. The time does not vary regardless of anything

E.G 2:

'''
sumoflist(A,n){
total = 0;            // Costs 1 unit and always runs once.
for i = 0 to n-1      // Costs 2 units - 1 for setting i to 0 and 1 for incrementing i and will run n+1 times where that extra time is                         // for the false condition
total = total + A[i]; // only this runs in the for loop - 2 units for addition and assignment and runs n times
return total          // costs 1 unit and only runs once when you're for loop is done
}
'''
Total = 1 + 2(n+1) + 2n + 1
which = 4n + 4 where n is the size of the array.

Rate of growth for quadratic functions is greater than that of linear functions which is greater than constants.

big-O notation. (definition) Definition: A theoretical measure of the execution of an algorithm, usually the time or memory needed, given the problem size n, which is usually the number of items

O(1) --> All the functions where time is equal to some constant belong to this set
O(n) --> All the functions where time is an equation of linearity
O(n^2) -->  All the functions where time is an equation of second order
O(N^x) --> All the functions where time is an equation of x order
big O --> Asymptotic Notation.

-----
Asymptotic Notations
-----

E.G: 
2 algorithms on a model machine
Alg 1 - T(n) = 5n^2 + 7
Alg 2 - T(n) = 17n^2 + 6n + 8
We analyze time complexity for really large input sizes. 
as n approaches infinity, the +7 and (6n + 8) become insignificant along with the 
coefficients of n^2 --> the 5 and 17.
So for very high values of n both functions essentially have the same rate of growth.
This is a quadtratic rate of growth. 
-----
The big O notation -->  O(g(n)) = {set of all functions f(n)  for which there exists some constant c and n0 --> f(n) <= cg(n) for n>= n0}

e.g:

function f(n) = 5n^2 + 2n + 1
---------g(n) = n^2

2n can never be greater than 2n^2 and 1 can never be greater than n^2
so c = (5 + 2 + 1) = 8 and n0 = 1
f(n) always <= 8n^2 for all n>= 1

f(n) set O(n^2)  --> f(n) always <= 8n^2 where 8n^2 is cg(n) for all n>=1
Big O notation gives the higher bound of the rate of growth of a function -- run time of algorithm in the worst case
-----
Omega Notations
-----

if we have a omega(g(n)) = {set of all functions f(n)  for which there exists some constant c and n0 --> cg(n)  <= f(n)  for n>= n0}

e.g:
function f(n) = 5n^2 + 2n + 1
---------g(n) = n^2

c = 5 and n0 = 0 as 5n^2 <= f(n)
so f(n) = omega(n^2)

omega notation gives the lower bound of the rate of growth of a function

-----
Theta Notations
-----

theta(g(n)) = {set of all functions f(n)  for which there exists some constant c1 and c2 and n0 --> c1g(n)  <= f(n) <= c2g(n)
for all n>= n0}

e.g:
function f(n) = 5n^2 + 2n + 1
---------g(n) = n^2

c2 = 8
c1 = 5 and n0 = 1
f(n) = theta(n^2)
theta notation best describes the rate of growth of the function since it gives us the tight bound instead of the lower and upper bound given by

graph of theta notation will show us f(n) bound by two functions c1g(n) and c2g(n) for all n >= n0
Theta notation is the best one to find in time complexity Analysis

Big O notation gives idea of run time in worst case

-----
-----
------
-------
--------
-------
------
-----
-----



