#P.1. Overlapping subproblems property#
#FIBONACCI SERIES :  a series of numbers in which each number is the sum of the two preceding numbers.where fib(0)=0 and fib(1)=1 #
#It is a kind of overlapping subproblems,where every previous number is required for the computation of each next number.so it might take a long time for processing the preprocessed data . It might grow at exponential rate.#
#SOLUTION#
*remember the results .*
*do not solve the same problem again.just recall it from memory*
#TWO METHODS OF STORING THE RESULTS IN MEMORY : #
#1.Memoization(Top-Down)#
#2.Tabulation(Bottom-Up)#

#DYNAMIC PROGRAMMING : Dynamic Programming is an algorithm paradigm that solves a given complex problem by breaking it into subproblems and storing the results of subproblems to avoid the computing the same results again.#

#WHERE TO USE DYNAMIC PROGRAMMING ?#
#Following are the two main properties of a problem that suggest that the given problem can be solved using Dynamic programming#
#1.overlapping subproblems#
#2.optimal substructure#

#DYNAMIC PROGRAMMING VS.DIVIDE AND CONQUER#

#SIMILARITIEES : Both paradigms work by combining solutions to sub-problems. #
#DIFFERENCES : Dynamic programming is mainly used when the overlapping subproblems is satisfied.#
#EXAMPLES : Binary Search,fibonacci series#

#1.USING MEMOIZATION#
```C
#include<stdio.h>
#define NIL 0
#define MAX 100
int lookup[MAX];
void initialize()
{
    for(int i=0;i<MAX;i++)
        lookup[i]=NIL;
}
int fibo(int n)
{
    if(n<=1)
        lookup[n]=n;
    else
        lookup[n]=fibo(n-1)+fibo(n-2);
    return lookup[n];
}
int main()
{
for(int i=0;i<10;i++)
    printf("%d\t",fibo(i));
}
```
#USING TABULATION#
```C
#include<stdio.h>
int fib(int n)
{
    int fib[n+1],i;
    fib[0]=0,fib[1]=1;
    for(i=2;i<=n;i++)
        fib[i]=fib[i-1]+fib[i-2];
    return fib[n];
}
int main()
{
    int i,n;
    printf("enter n : ");
    scanf("%d",&n);
    for(i=0;i<=n;i++)
    {
        fib(i);
        printf("%d\t",fib(i));
    }
}
```

#SET 2,OPTIMAL SUBSTRUCTURE PROPERTY#

#A given problem is said to have the OPTIMAL SUBSTRUCTURE PROPERTY if an optimal solution of the given problem can be obtained by sing optimal solutions of its subproblems.After the subproblems becomes sufficiently small solving them becomes trivial,further these trivial solutions are used to solve the superproblem and arrive at the final result#

#LONGEST INCREASING SUBSEQUENCE#
# To find the length of the longest subsequence of a given sequence such that all elements of the subsequence are sorted in increasing order.  #
#For example :#
##