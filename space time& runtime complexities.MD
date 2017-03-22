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
Techniques and rules to avoid doing all complex calculations and derive time complexity expression in terms of big O or theta notation

- We analyze time complexity for a:
  - Very large input size
  - Worst case scenario
E.G:
T(n) = n^3 + 3n^2 + 4n + 2
almost equal to n^3 for very large values of n (as n approaches infinity)
This will not grow any faster than an equation of 2n^3 

1) Drop all lower order terms
2) Drop the constant multipliers

e.g: 17n^4 + 3n^3 + 4n + 8
1) Drop lower order terms
--> 17n^4
2) Drop the constant multipliers
--> n^4
so bigO = (n^4)
-----

Running time in Algorithm can be calculated: SUMOF running time of all fragments in the program
look at running time for different fragments then then sum all the different fragments
BIGO is the the biggest OF expressions. 
-----

e.g 1: (these are known as simple statements)
if we have 
int a (initializing)
a = 5
a++
here the bigO(1)
------

e.g 2:  (these are known as single loops)
'''
for (i=0;i  < n ; i++) as this loop runs n times
{
[bunch of simple statements]
}
The total time taken is proportional to n so
bigO(n) for this fragment

--------

e.g 3: (This is known as a nested loop)
for (i=0;i  < n ; i++) as this loop runs n times
{
for (i=0;i  < n ; i++) as this loop runs n times{
[bunch of simple statements]
}
}
bigO(n^2)

-------
e.g 4:

'''
int a (initializing)
a = 5
a++
for (i=0;i  < n ; i++) as this loop runs n times
{
[bunch of simple statements]
}
for (i=0;i  < n ; i++) as this loop runs n times
{
for (i=0;i  < n ; i++) as this loop runs n times{
[bunch of simple statements]
}
}
'''

what is the bigO notation here?

running time of fragment 1 = O(1)
running time of fragment 2 = O(n)
running time of fragment 3 = O(n^2)

T(n) = O(1) + O(n) + O(n^2)
so for very large values of n only O(n^2) becomes significant
------

in any program, the fragment which has the maximum running time in the program decides the overall running time of the program

------
e.g 5:
'''
function() {

if (some condition) {
for (i=0;i  < n ; i++){ //as this loop runs n times
(simple statements)
}
else{
for (i=0;i  < n ; i++){ //as this loop runs n times
  for (i=0;i  < n ; i++){ //as this loop runs n times
  (simple statements)
  }
 }
}
}
'''
--------
In this case, single loop has O(n) if condition is true and O(n^2) if condition is not true.
We always analyze the time complexity in the worst case so the complexity for this particular program
is O(n^2) because this is how it is in the worst case scenario. We dont add up the fragments or average them.
we pick up the maximum of the 2. 
--------

## Space Complexity
###### Space complexity is a measure of how efficient your code is in terms of memory used.
###### Space complexity analysis happens almost in the same way time complexity analysis happens.

For example, consider the following code :
'''
vector<int> V;
for (int i = 0; i < N; i++) V.push_back(i);
'''
vector<int> V;
for (int i = 0; i < N; i++) V.push_back(i);
'''

