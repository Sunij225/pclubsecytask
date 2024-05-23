# Sorting
You have an array a consisting of n integers. Each integer from 1 to n appears exactly once in this array.

You can swap i-th integer and j-th integer if their gcd(i,j) is strictly greater than 1 . You have to tell whether the array gets sorted or not in ascending order . There is no limit on the number of times you swap .

NOTE :- We assume indexing from 1 to n .

## INPUT 
The first line contains a single integer t (1<=t<=10000) — the number of test cases.

The first line of each test case contains a number n (1<=n<=100000) - denoting the number of integer in the array .

The second line of each test case contains n numbers a1,a2,a3.....an (1<=ai<=n).

## OUTPUT 
For each test case,if it is possible to sort the array in ascending order using the swaps you are allowed to make, print YES. Otherwise, print NO.
