#PROGRAM TO REMOVE DUPLICATE ELEMENTS FROM THE SORTED ARRAY#
```C
#include<stdio.h>
int main()
{
    int n,i,j=0;
    printf("enter n : ");
    scanf("%d",&n);
    int a[n],b[n];
    for(i=0;i<n;i++)
    {
        scanf("%d",&a[i]);
    }
    for(i=0;i<n-1;i++)
    {
        if(a[i]!=a[i+1])
        {
            b[j]=a[i];
            j++;
        }
    }
    b[j]=a[n-1];
    for(i=0;i<j+1;i++)
        printf("%d\t",b[i]);
}
```
#PROGRAM TO PRINT NON REPEATED ELEMENTS OF AN ARRAY : #
```C
#include<stdio.h>
int main()
{
    int n,i,j;
    printf("enter n : ");
    scanf("%d",&n);
    int arr[n],c=0,k;
    for(i=0;i<n;i++)
        scanf("%d",&arr[i]);
    for(i=0;i<n;i++)
    {
        c=0;
        for(j=i+1;j<n;j++)
        {
            if(arr[i]==arr[j])
            {
                c++;
                for(k=j+1;k<n;k++)
                {
                    arr[k-1]=arr[k];
                }
                j--;
                n--;
            }
        }
        if(c==0)
            printf("%d\t",arr[i]);
    }


}
               
```
#THE SIZE OF ALL THE POINTER VARIABLES IS SAME DEPENDENT ON THE COMPILER#
```C
#include<stdio.h>
int main()
{
    int *pnum;
    char *pch;
    float *pf;
    double *pd;
    long *pl;
    printf("\nthe size of integer pointer = %d",sizeof(pnum));
    printf("\nthe size of integer pointer = %d",sizeof(pch));
    printf("\nthe size of integer pointer = %d",sizeof(pf));
    printf("\nthe size of integer pointer = %d",sizeof(pd));
    printf("\nthe size of integer pointer = %d",sizeof(pl));
}

```
#PROGRAM TO REMOVE DUPLICATE ELEMENTS FROM THE UNSORTED ARRAY#
```C
#include<stdio.h>
int main()
{
    int n;
    printf("enter n : ");
    scanf("%d",&n);
    int a[n],i,j,k;
    for(i=0;i<n;i++)
    {
        scanf("%d",&a[i]);
    }
    for(i=0;i<n;i++)
    {
        for(j=i+1;j<n;j++)
        {
            if(a[i]==a[j])
            {
                for(k=j+1;k<n;k++)
                    a[k-1]=a[k];
                    j--;
                    n--;
            }
        }
    }
    for(i=0;i<n;i++)
        printf("%d",a[i]);
}

```
#INTERSECTION : 
```C
#include<stdio.h>
int main()
{
    int n,m;
    printf("enter n : ");
    scanf("%d",&n);
    printf("\nenter m : ");
    scanf("%d",&m);
    int i,j,k,y=0,a[n],b[m],d[n];
    for(i=0;i<n;i++)
    {
     scanf("%d",&a[i]);
    }
    for(i=0;i<m;i++)
    {
     scanf("%d",&b[i]);
    }

for(i=0;i<n;i++)
    {
        for(j=0;j<m;j++)
        {
            if(a[i]==b[j])
            {
                d[y]=a[i];
                y++;
            }
        }
    }
for(i=0;i<y;i++)
{
    for(j=i+1;j<y;j++)
    {
        if(d[i]==d[j])
        {
            for(k=j+1;k<y;k++)
                d[k-1]=d[k];
            j--;
            y--;
        }
    }
}
        printf("\nintersection : ");
    for(i=0;i<y;i++)
        printf("\t%d",d[i]);
}

```#

#WAP TO PRINT SECOND LARGEST ELEMENT OF AN ARRAY#
```C
#include <stdio.h>
#include <limits.h>

/* Function to print the second largest elements */
void print2largest(int arr[], int arr_size)
{
    int i, first, second;

    /* There should be atleast two elements */
    if (arr_size < 2)
    {
        printf(" Invalid Input ");
        return;
    }

    first = second = INT_MIN;
    for (i = 0; i < arr_size ; i ++)
    {
        /* If current element is greater than first
           then update both first and second */
        if (arr[i] > first)
        {
            second = first;
            first = arr[i];
        }

        /* If arr[i] is in between first and
           second then update second  */
        else if (arr[i] > second && arr[i] != first)
            second = arr[i];
    }
    if (second == INT_MIN)
        printf("There is no second largest element\n");
    else
        printf("The second largest element is %d\n", second);
}

/* Driver program to test above function */
int main()
{
    int n ;
    printf("enter n : ");
    scanf("%d",&n);
    int arr[n],i;
    for(i=0;i<n;i++)
        scanf("%d",&arr[i]);
    print2largest(arr, n);
    return 0;
}

```


#UNION#
```C
#include<stdio.h>
int main()
{
    int n,m;
    printf("enter n : ");
    scanf("%d",&n);
    printf("\nenter m : ");
    scanf("%d",&m);
    int a[n],b[m],c[m+n],z=0,i,j,k,y=0,d[n];
    for(i=0;i<n;i++)
    {
     scanf("%d",&a[i]);
     c[z]=a[i];
     z++;
    }
    for(i=0;i<m;i++)
    {
     scanf("%d",&b[i]);
     c[z]=b[i];
     z++;
    }

    for(i=0;i<z;i++)
    {
        for(j=i+1;j<z;j++)
        {
            if(c[i]==c[j])
            {
                for(k=j+1;k<z;k++)
                    c[k-1]=c[k];
                    j--;
                    z--;
            }
        }
    }


    printf("\nUnion : ");
    for(i=0;i<z;i++)
        printf("\t%d",c[i]);
}
```
#MERGED ARRAY TWO SORTED ARRAYS#
```C
#include<stdio.h>
int main()
{
    int n,m;
    printf("enter the size of array A : ");
    scanf("%d",&n);
    printf("\nenter the size of array B : ");
    scanf("%d",&m);
    int A[n],B[m],C[m+n],i,j,k=0,z=0;
    printf("\nenter the elements of array A : ");
    for(i=0;i<n;i++)
    {
        scanf("%d",&A[i]);
    }
    printf("\nenter the elements of array B : ");
    for(i=0;i<m;i++)
    {
        scanf("%d",&B[i]);
    }
    for(i=0;i<n;i++)
    {
        for(j=0;j<m;j++)
        {
            if(A[i]<B[j])
            {
                C[k]=A[i];
                k++;
                j--;
                i++;
            }
            else if(B[j]<A[i])
            {
                C[k]=B[j];
                k++;
            }
        }
    }
    printf("\nThe merged array is : ");
    for(i=0;i<k;i++)
    {
        printf("%d\t",C[i]);
    }

}

```

#LINEAR SEARCH#
```C
#include<stdio.h>
int main()
{
    int n,found=0;
    printf("enter the length of the array : ");
    scanf("%d",&n);
    int A[n],i,val;
    printf("\nenter the array : ");
    for(i=0;i<n;i++)
    {
        scanf("%d",&A[i]);
    }
    printf("\nenter the value to be searched : ");
    scanf("%d",&val);
    for(i=0;i<n;i++)
    {
        if(A[i]==val)
        {
         printf("%d exist at %d position in the array : ",val,i);
         found=1;
         break;
        }
    }
    if(found==0)
         printf("\n%d does not exist in the array ",val);

}
#BINARY SEARCH#
```C
#include<stdio.h>
int main()
{
    int n,found=0;
    printf("enter the value of n : ");
    scanf("%d",&n);
    int A[n],i,val,beg=0,end=n,mid;
    printf("\nenter the array : ");
    for(i=0;i<n;i++)
    {
        scanf("%d",&A[i]);
    }
    printf("\n enter the value to be searched : ");
    scanf("%d",&val);
    for(i=0;i<n;i++)
    {
        mid=(beg+end)/2;
        if(A[mid]==val)
        {
            printf("\nthe value to be searched is at %d position\n",mid);
            found=1;
            break;
        }
        if(val<A[mid])
        {
            end=mid;
        }
        else if(val>A[mid])
        {
            beg=mid;
        }
    }
    if(found==0)
        printf("\n%d does not exist in the array  ");
        }

```
#WAP TO READ AND DISPLAY THE OUTPUT OF N NUMBERS USING FUNCTION#
```C

#include<stdio.h>
void read(int arr[],int );
void display(int arr[],int);
int main()
{

    int arr[10],n;
    printf("enter the value of n : ");
    scanf("%d",&n);
    read(arr,n);
    display(arr,n);
    return 0;

}
void read(int arr[10],int n)
{
    int i;
    printf("enter the array : ");
    for(i=0;i<n;i++)
    scanf("%d",&arr[i]);
}
void display(int arr[10],int n)
{
    int i;
    printf("\nThe array is : ");
    for(i=0;i<n;i++)
        printf("%d\t",arr[i]);
}

```

#SMALLEST ELEMENT IN AN ARRAY USING FUNCTIONS#
```C
#include<stdio.h>
void read(int arr[],int);
int dis_small(int arr[],int);
int main()
{
    int n,ans;
    printf("enter the value of n : ");
    scanf("%d",&n);
    int arr[n];
    read(arr,n);
    ans=dis_small(arr,n);
    printf("\nsmallest element of the array is %d",ans);

}
void read(int arr[10],int n)
{
    int i;
    for(i=0;i<n;i++)
        scanf("%d",&arr[i]);
}
int dis_small(int arr[10],int n)
{
    int i,small=arr[0];
    for(i=0;i<n;i++)
    {
        if(arr[i]<small)
        {
            small=arr[i];
        }
    }
    return small;
}
```
#USING THE FUNCTIONS WAP TO INPUT,DISPLAY,MERGE TWO ARRAYS AND PRINT ITS INVERSE. 
```C
#include<stdio.h>
void read(int array[],int);
void display(int array[],int );
void merge(int array3[],int,int array2[],int ,int array1[],int);
void reverse(int array[],int);
int main()
{

    int n,arr1[10],m,arr2[10],arr3[20];
    printf("enter the length of the first array : ");
    scanf("%d",&n);
    read(arr1,n);
    printf("\nenter the length of the second array : ");
    scanf("%d",&m);
    read(arr2,m);
    int t=m+n;
    merge(arr3,t,arr1,n,arr2,m);
    printf("\nThe merged array is : ");
    display(arr3,t);
    printf("\nThe merged array in reversed order is : ");
    reverse(arr3,t);
    return 0;
}
void read(int arr[10],int n)
{
    int i;
    for(i=0;i<n;i++)
        scanf("%d",&arr[i]);
}
void merge(int arr3[],int t,int arr1[],int n,int arr2[],int m)
{
    int i,k=0;
    for(i=0;i<n;i++)
    {
        arr3[k]=arr1[i];
        k++;
    }
    for(i=0;i<m;i++)
    {
        arr3[k]=arr2[i];
        k++;
    }

}
void display(int arr3[],int t)
{
    int i;
    for(i=0;i<t;i++)
        printf("%d\t",arr3[i]);
}
void reverse(int arr3[],int t)
{
    int i;
    for(i=0;i<t;i++)
    {
        printf("%d\t",arr3[t-1-i]);
    }
}
```

#WRITE A MENU DRIVEN PROGRAM TO READ TWO ARRAYS ,FIND THEIR SUM AND PRODUCT#
```C
#include<stdio.h>
void read(int arr[2][2],int ,int);
void display(int arr[2][2],int,int);
void sum(int arr1[2][2],int arr2[2][2],int,int);
void mul(int arr1[2][2],int arr2[2][2],int,int);
int main()
{
    int opt,row,col;
    int arr1[2][2],arr2[2][2];
    do
    {
        printf("\n*****MAIN MENU*****\n");
        printf("1.Read the two matrices : \n");
        printf("2.Add the matrices : \n");
        printf("3.Multiply the matrices : \n");
        printf("4.exit : ");
        printf("\nEnter your option : ");
        scanf("%d",&opt);
        switch(opt)
        {
        case 1:
            {
                printf("\nenter the no. of rows and columns : ");
                scanf("%d%d",&row,&col);
                printf("\nenter the first matrix : ");
                read(arr1,row,col);
                printf("\nenter the second matrix : ");
                read(arr2,row,col);
                break;
            }
        case 2:
            {
                sum(arr1,arr2,row,col);
                break;
            }
        case 3:
            {
                mul(arr1,arr2,row,col);
                break;
            }
            }
    }
        while(opt!=4);
}
void read(int arr[2][2],int r,int c)
{
    int i,j;
    for(i=0;i<2;i++)
    {
        for(j=0;j<2;j++)
                scanf("%d",&arr[i][j]);
    }
}
void sum(int arr1[2][2],int arr2[2][2],int r,int c)
{
    int i,j,sum[2][2];
    for(i=0;i<2;i++)
    {
        for(j=0;j<2;j++)
            sum[i][j]=arr1[i][j]+arr2[i][j];
    }
    display(sum,r,c);
}
void mul(int arr1[2][2],int arr2[2][2],int r,int c)
{
    int i,j,k=0,pro[2][2],sum;
    for(i=0;i<2;i++)
    {
        for(j=0;j<2;j++)
        {
            sum=0;
            for(k=0;k<2;k++)
            {
             sum=sum+arr1[i][k]*arr2[k][j];
            }
            pro[i][j]=sum;
        }
    }
    display(pro,r,c);
}
void display(int arr[2][2],int r,int c)
{
    int i,j;
    for(i=0;i<r;i++)
    {
        for(j=0;j<c;j++)
                printf("%d\t",arr[i][j]);
        printf("\n");
    }

}

```