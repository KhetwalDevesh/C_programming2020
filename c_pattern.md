```c
#include<stdio.h>
int main()
{
    int a;
    scanf("%d",&a);
    int n;
    n=a*2-1;
    int i=n,j=n,l,m,small,large;
    for(l=0;l<n;l++)
    {
        for(m=0;m<n;m++)
        {
            if((l+m)<n)
            {
             small=l<m?l:m;
             printf("%d",a-small);
            }
            else
            {
                large=l>m?l:m;
                printf("%d",a-(n-1-large));
            }
        }
        printf("\n");
    }
}
```
#2.#
```c
#include<stdio.h>
int main()
{
    int n,i,j,k;
    scanf("%d",&n);
    for(i=0;i<n;i++)
    {
        for(j=0;j<n-i-1;j++)
            printf(" ");
        printf("*");
        if(i!=0)
        {
            for(k=0;k<2*i-1;k++)
                printf(" ");
            printf("*");
        }
        printf("\n");
    }
}
```
#2.SAME AS ABOVE BUT WITHOUT NESTED LOOP#
```c
#include<stdio.h>
int main()
{
    int n;
    printf("enter a number : ");
    scanf("%d",&n);
    char str[]="*";
    for(int i=0;i<n;i++)
    {
        int p=n-i;
        int q=i*2;
     printf("%*s",p,str);
     if(i!=0)
     {
         printf("%*s",q,str);
     }
     printf("\n");
    }

}
```
#3.#
```c
#include<stdio.h>
int main()
{
    int n;
    printf("enter a number : ");
    scanf("%d",&n);
    char str[]="*";
    for(int i=0;i<n;i++)
    {
        int p=n-i;
        int q=i*2;
     printf("%*d",p,i+1);
     if(i!=0)
     {
         printf("%*d",q,i+1);
     }
     printf("\n");
    }

}
```
