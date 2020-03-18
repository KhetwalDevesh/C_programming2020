#P1. RETURN THE INDICES OF TWO ELEMENTS WHOSE SUM GIVES A SPECIFIC TARGET#
#SUPPOSE WE HAVE ELEMENTS 1,3,5,7,8 and OUR TARGET IS 8 .#
#CODE FOR nlogn TIME # #Although it can also be solved using n^2 approach but O(nlogn) is more optimized .so we should prefer it over the other.#
```c
#include<stdio.h>
int main()
{
    char arr[5]={1,3,5,7,8};
    int i=0,j=4,target=8,n=5;
    while(i<n)
    {
        while(j>=0)
        {
            if(arr[i]+arr[j]==target)
            {
                printf("i = %d\tj = %d",i,j);
                break;
            }
            else if(arr[i]+arr[j]>target)
                j--;
            else if(arr[i]+arr[j]<target)
                i++;
        }
        if(arr[i]+arr[j]==target)
            break;
    }
}
```
#P.2 MAX CONSECUTIVE ONES#