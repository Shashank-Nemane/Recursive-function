
Problem statement: 

Develop a C program to calculate the sum of the first 10 numbers using
recursive function calls and pointers. The program should define a recursive
function that takes a pointer to an integer as an argument and returns the
sum of the first 10 numbers. Within the function, recursion should be used
to compute the sum iteratively. Finally, the program should display the
calculated sum.

Research: 

Links: 

https://www.geeksforgeeks.org/dsa/introduction-to-recursion-2/

https://www.geeksforgeeks.org/dsa/program-calculate-value-ncr/

Recursion is the process in which a function calls itself directly or indirectly.

A recursive algorithm takes one step toward solution and then recursively calls itself to further move. The algorithm stops once we reach the solution.

Since the called function may further call itself, this process might continue forever. So it is important  to provide a base case to terminate this recursion process.

Steps for making a recursive function:

Step1 - Define a base case

Step2 - Define a recursive case

Step3 - Ensure the recursion terminates

Step4 - Combine the solutions

Recursive functions can be used in many different applications.

Here are more definitive, clear, and crisp points for the uses of recursive functions:


---

Uses of Recursive Functions (Clear & Definitive Points)

Used to solve problems that naturally reduce into smaller versions of the same problem.

Ideal for mathematical computations such as factorials, Fibonacci series, power calculations, GCD, and nCr.

Essential in divide-and-conquer algorithms like merge sort, quicksort, and binary search.

Helpful in navigating and processing hierarchical structures such as trees, graphs, and directory systems.

Provide clean and simple solutions for problems involving repetitive patterns or self-similar structures (e.g., fractals).

Useful for exploring all possible choices in decision-based problems (include/exclude logic).



Analysis:

Here I am using a recursive function for mathematical operation of nCr.


The recursive formula for nCr is based on a simple idea: 

While choosing r items from n items, we focus on one specific item and consider the two possible choices we have for it. 

Either we include this item in our selection, or we do not include it. If we include it, then we only need to choose the remaining r − 1 items from the remaining n − 1 items, which gives us the term nCr(n − 1, r − 1). 

If we do not include the item, then we must choose all r items from the remaining n − 1 items, which gives the term nCr(n − 1, r). 

Since these two cases cover every possible combination, we add them together to get the total number of ways. 

Therefore, the recursive relationship nCr = nCr(n − 1, r − 1) + nCr(n − 1, r) naturally arises from the idea of splitting the selection process into the “include” and “exclude” cases for one chosen item.

Ideate: Using recursive functions mathematical application in nCr .
Building a C program for calculating nCr using n and r as input from the user, while taking all cases in consideration and responding with appropriate messages.

Built:

#include<stdio.h>
int main()
{
int n,r;
start:
N:
printf("Enter n for nCr operation: ");
scanf("%d",&n);
if(n<0)
{
printf("Invalid input\n Enter valid input.\n");
goto N;
}
R:
printf("Enter r for nCr operation: ");
scanf("%d",&r);
if(r<0)
{
printf("Invalid input\n Enter valid input.\n");
goto R;
}
if(r>n)
{
printf("Invalid input\n Enter valid input.\n");
goto start;
}

printf("C(%d,%d) = %d",n,r,nCr(n,r));
return 0;
}
int nCr(int n,int r)
{
  if (n==r || r==0)
  {
    return 1;
  }
   return nCr(n-1,r-1) + nCr(n-1,r);
}

Test:

Case 1: n>r

Enter n for nCr operation: 5
Enter r for nCr operation: 3
C(5,3) = 10

Case 2: n<r

Enter n for nCr operation: 3
Enter r for nCr operation: 5
Invalid input
Enter valid input.
Enter n for nCr operation: 5
Enter r for nCr operation: 3
C(5,3) = 10

Case 3: n<0 or r<0

Enter n for nCr operation: -7
Invalid input
Enter valid input.
Enter n for nCr operation: 7
Enter r for nCr operation: -4
Invalid input
Enter valid input.
Enter r for nCr operation: 4
C(7,4) = 35





