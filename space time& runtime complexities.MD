# space time and runtime complexities:

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


