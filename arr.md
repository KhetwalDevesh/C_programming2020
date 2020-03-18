# INPUT #
```c
#include<stdio.h>
int main()
{
    int arr[10],i,j,count=0;
    for(i=0;i<10;i++)
    {
        scanf("%d",&arr[i]);
        arr[i]=arr[i]/10;
    }
    for(i=0;i<10;i++)
    {
        printf("\t%d",arr[i]);
    }
    for(i=0;i<10;i++)
    {
        for(j=0;j<10;j++)
        {
            if(i==arr[j])
            {
                count+=1;
            }

        }
        printf("\nnumber\tcount");
        printf("\n%d\t%d",i,count);
        count=0;

    }
}
```              `
# P.2 FIND THE MEDIAN:
# INPUT #
```c
#include<stdio.h>
int main()
{
    float arr[10],median;
    int i,j,n;
    printf("enter the value of n : \n");
    scanf("%d",&n);
    printf("enter the array\n");
    for(i=0;i<n;i++)
    {
        scanf("%f",&arr[i]);
    }
    if(n%2==0)
    {
        median=(arr[n/2]+arr[n/2 + 1])/2;
    }
    else
    {
        median=arr[n/2 + 1];
    }
    printf("median = %f",median);
}
```
# P.3 inserting an element:
# P.4 INSERT A NUMBER IN AN ARRAY THAT IS ALREADY SORTED IN ASCENDING ORDER .
```c
#include<stdio.h>
int main()
{
    int n;
    printf("enter the length of the array : ");
    scanf("%d",&n);
    int arr[n],i,val,k;
    printf("\n enter the array : ");
    for(i=0;i<n;i++)
    {
        scanf("%d",&arr[i]);
    }
    printf("\nenter the position at which the value is to be inserted : ");
    scanf("%d",&k);
    printf("\nenter the value to be entered at position %d",k);
    scanf("%d",&val);

    n=n+1;
    for(i=n;i>k;i--)
    {
        arr[i]=arr[i-1];
    }
    arr[k]=val;
    printf("\nArray after the insertion of %d at %d is : ",val,k);
    for(i=0;i<n;i++)
    {
        printf("\n%d",arr[i]);
    }

}
```

# P.5 DELETE AN ELEMENT FROM AN ARRAY USING ITS INDEX:
```c
#include<stdio.h>
int main()
{
    int arr[10],i,pos,n;
    printf("enter the value of n : \n");
    scanf("%d",&n);
    printf("enter the array : ");
    for(i=0;i<n;i++)
    {
        scanf("%d",&arr[i]);
    }
    printf("\nenter  the position whose value is to be deleted : ");
    scanf("%d",&pos);
    for(i=0;i<n-1;i++)
    {
        if(i>=pos)
        {
            arr[i]=arr[i+1];
        }
    }
    n=n-1;
    for(i=0;i<n;i++)
    {
        printf("%d",arr[i]);
    }
}
```
# P.5 DELETE AN ELEMENT FROM A SORTED ARRAY :
```c
#include<stdio.h>
int main()
{   int n,i,num;
    printf("enter the value of n : \n");
    scanf("%d",&n);
    int arr[n];
    for(i=0;i<n;i++)
    {
        scanf("%d",&arr[i]);
    }
    printf("enter the value to be deleted : \n");
    scanf("%d",&num);
    for(i=0;i<n-1;i++)
    {
        if(arr[i]>=num)
        {
            arr[i]=arr[i+1];
        }
    }
    n=n-1;
    for(i=0;i<n;i++)
    {
        printf("%d",arr[i]);
    }
}
```
# P.5 WAP TO TO MERGE TWO UNSORTED ARRAY :
```c
#include<stdio.h>
int main()
{
    int n,m;
    printf("enter the length of first array : \n");
    scanf("%d",&n);
    printf("enter the length of second array : \n");
    scanf("%d",&m);
    int arr1[n],arr2[m],i;
    printf("\nenter first array : \n");
    for(i=0;i<n;i++)
    {
        scanf("%d",&arr1[i]);
    }
    printf("\narray 1 :\n");
    for(i=0;i<n;i++)
    {
        printf("%d\t",arr1[i]);
    }
    printf("\nenter second array : \n");
    for(i=0;i<m;i++)
    {
        scanf("%d",&arr2[i]);
    }
    printf("\narray 2 :\n");
    for(i=0;i<m;i++)
    {
        printf("%d\t",arr2[i]);
    }
    int o=m+n,arr3[o];
    for(i=0;i<o;i++)
    {
        if(i<n)
        {
            arr3[i]=arr1[i];
        }
        else
            arr3[i]=arr2[i-n];
    }
    printf("\nthird array : ");
    for(i=0;i<o;i++)
    {
        printf("%d\t",arr3[i]);
    }
}

```
# P.6 SORT AN ARRAY :
```c
#include<stdio.h>
int main()
{
int n,arr[10],i,temp,j;
printf("enter the value of n : ");
scanf("%d",&n);
printf("\nenter the array : ");
for(i=0;i<n;i++)
{
    scanf("%d",&arr[i]);
}
for(i=0;i<n-1;i++)
{
    for(j=i+1;j<n;j++)
   {
     if(arr[i]>arr[j])
    {
        temp=arr[i];
        arr[i]=arr[j];
        arr[j]=temp;
    }
   }

}

for(i=0;i<n;i++)
{
    printf("%d\t",arr[i]);
}
}
```
# P.7 WAP TO MERGE TWO SORTED ARRAY BY ABOVE SORTING METHOD :
```c
#include<stdio.h>
int main()
{
int n,m,i,temp,j;
printf("enter the value of n : ");
scanf("%d",&n);
printf("enter the value of m : ");
scanf("%d",&m);
int arr1[n],arr2[m];
printf("\nenter the first array : ");
for(i=0;i<n;i++)
{
    scanf("%d",&arr1[i]);
}
printf("\nenter the second array : ");
for(i=0;i<m;i++)
{
    scanf("%d",&arr2[i]);
}
int o=m+n,arr3[o];
for(i=0;i<o;i++)
{
    if(i<n)
   {
     arr3[i]=arr1[i];
   }
   else
   {
       arr3[i]=arr2[i-n];
   }
}
for(i=0;i<o;i++)
{
    printf("%d\t",arr3[i]);
}
for(i=0;i<o-1;i++)
{
    for(j=i+1;j<o;j++)
    {
        if(arr3[i]>arr3[j])
        {
            temp=arr3[i];
            arr3[i]=arr3[j];
            arr3[j]=temp;
        }
    }
}

for(i=0;i<o;i++)
{
    printf("%d\t",arr3[i]);
}
}
```
# P.8 WAP TO MERGE TWO SORTED ARRAYS :

# INPUT 
```c
#include<stdio.h>
int main()
{
    int n;
    printf("enter the value of n : ");
    scanf("%d",&n);
    int arr[10],i,val,dup=-1;
    printf("\nenter the array : ");
    for(i=0;i<n;i++)
    {
        scanf("%d",&arr[i]);
    }
    printf("\nenter the value to be searched : ");
    scanf("%d",&val);
    for(i=0;i<n;i++)
    {
    while(arr[i]==val)  // if(arr[i]==val)
    {printf("\n%d is found at %d",val,i);
    dup=i;
    break;
    }

    }
        if(dup==-1)
    {
        printf("\nout of range");
    }

}
```
# P.8 WAP TO IMPLEMENT LINEAR SEARCH.
```c
#include<stdio.h>
int main()
{
    int n,val;
    printf("enter the length of the array : ");
    scanf("%d",&n);
    int arr[n],i,j,count=0;
    printf("\nenter the array : ");
    for(i=0;i<n;i++)
    {
        scanf("%d",&arr[i]);
    }
    printf("\nenter the number to be searched : ");
    scanf("%d",&val);
    for(i=0;i<n;i++)
    {
        if(arr[i]==val)
        {count=count+1;
        printf("\nThe number is located at %d",i);}
    }
    if(count==0)
    {
        printf("\nOut of range");
    }

}

```
# P.9 WAP TO IMPLEMENT BINARY SEARCH.
# INPUT #
```c
#include<stdio.h>
int main()
{
    int n;
    printf("enter the length of the array : ");
    scanf("%d",&n);
    int arr[n],beg=0,end=n-1,mid,i,val;
    printf("\nenter the array : ");
    for(i=0;i<n;i++)
    {
     scanf("%d",&arr[i]);
    }
    printf("\nenter the value to be searched : ");
    scanf("%d",&val);
    mid=(end+beg)/2;
    while(arr[mid]!=val)
    {
    if(val>arr[mid])
    {
        beg=mid+1;
    }
    else if(val<arr[mid])
        {
            end=mid-1;
        }
    mid=(end+beg)/2;
    }
    printf("%d is at %d position",arr[mid],mid);
}
```
#P.10 WAP TO PRINT THE ELEMENTS OF A 2D ARRAY :
# INPUT - METHOD-1 : #
```c
#include<stdio.h>
int main()
{
    int arr[3][3]={1,2,3,4,5,6,7,8,9},i,j;
    for(i=0;i<3;i++)
    {
        for(j=0;j<3;j++)
        {
            printf("%d",arr[i][j]);
        }
        printf("\n");
    }
    }
    ```

# INPUT - METHOD-2 : #
```c
#include<stdio.h>
int main()
{
    int arr[3][3],i,j;
    printf("enter the array : ");
    for(i=0;i<3;i++)
        {
            for(j=0;j<3;j++)
            {
                scanf("%d",&arr[i][j]);
            }
        }
        for(i=0;i<3;i++)
        {
           for(j=0;j<3;j++)
           {printf("%d",arr[i][j]);}
            printf("\n");

        }

    }
```
# P.11 IN A SMALL COMPANY THERE ARE FIVE SALESMAN .EACH SALESMAN IS SUPPOSED TO SELL THREE PRODUCTS . WRITE A PROGRAM USING 2D ARRAY TO PRINT , 1:THE TOTAL SALES BY EACH SALESMAN 2:TOTAL SALES OF EACH ITEM .
 # INPUT #
 ```c
 #include<stdio.h>
int main()
{
    int i,j,arr[5][3],sum=0,tot=0;
    printf("enter the data : ");
    for(i=0;i<5;i++)
    {
        printf("\nenter the sales of three items by salesman %d\n",i);
        for(j=0;j<3;j++)
        {
         scanf("%d",&arr[i][j]);
        }
    }
    for(i=0;i<5;i++)
    {
        for(j=0;j<3;j++)
        {
            sum=sum+arr[i][j];
        }
        printf("\nTotal sales by salesman %d : %d",i,sum);
        sum=0;
    }
    printf("\n*********************************\n");
    for(j=0;j<3;j++)
    {
        for(i=0;i<5;i++)
        {
            tot=tot+arr[i][j];
        }
        printf("\nTotal sales of item %d is %d\n ",i,tot);
        tot=0;
    }

}
```
# P.12 WAP TO ADD THE ELEMENTS OF TWO MATRICES .
# INPUT 
```c
#include<stdio.h>
int main()
{
    int a[3][2],b[3][2],c[3][2],i,j;
    printf("Enter the elements of the first matrix : \n");
        for(i=0;i<3;i++)
        {
           for(j=0;j<2;j++)
           {scanf("%d",&a[i][j]);}
        }
    printf("Enter the elements of the second matrix : \n");
    for(i=0;i<3;i++)
    {
        for(j=0;j<2;j++)
        {
            scanf("%d",&b[i][j]);
        }
    }
    printf("The third array is : \n");
    for(i=0;i<3;i++)
    {
        for(j=0;j<2;j++)
        {
            c[i][j]=a[i][j]+b[i][j];
            printf("%d\t",c[i][j]);
        }
        printf("\n");
    }

    }
```
# WAP TO MULTIPLY TWO MATRICES.
```c
#include<stdio.h>
int main()
{
    int m,n,o;
    printf("enter m,n,o : ");
    scanf("%d,%d,%d",&m,&n,&o);
    int a[m][n],b[n][o],i,j;
    printf("\nenter first matrix : ");
    for(i=0;i<m;i++)
    {
    for(j=0;j<n;j++)
    {
        scanf("%d",&a[i][j]);
    }
    }
    printf("\nfirst matrix is : \n");
    {
        for(i=0;i<m;i++)
        {
            for(j=0;j<n;j++)
            {
                printf("%d\t",a[i][j]);
            }
            printf("\n");
        }
        printf("\nenter second matrix : ");
        for(i=0;i<n;i++)
        {
            for(j=0;j<o;j++)
            {
                scanf("%d",&b[i][j]);
            }
        }
        printf("\nsecond matrix is : \n");
        for(i=0;i<n;i++)
        {
            for(j=0;j<o;j++)
            {
                printf("%d\t",b[i][j]);
            }
            printf("\n");
        }
        int c[m][o],k,pro=0;
        for(i=0;i<m;i++)
        {
            for(j=0;j<n;j++)
            {
                for(k=0;k<n;k++)
                {
                    pro=pro+a[i][k]*b[k][j];
                }
                c[i][j]=pro;
                pro=0;
            }
        }
        printf("\nThe product is : \n");
        for(i=0;i<m;i++)
        {
            for(j=0;j<o;j++)
            {
                printf("%d\t",c[i][j]);
            }
            printf("\n");
        }

    }

}

```
#13. WAP TO COUNT THE NUMBERS GREATER THAN,LESS THAN AND EQUAL TO A NUMBER k IN AN ARRAY.
```c
#include<stdio.h>
int main()
/*{
    int m,n,i,j;
    printf("enter the no. of the rows : ");
    scanf("%d",&m);
    printf("enter the no. of columns : ");
    scanf("%d",&n);
    int a[m][n],b[m][n],c[m][n];
    printf("\nenter the elements of the first matrix : ");
    for(i=0;i<m;i++)
    {
        for(j=0;j<n;j++)
        {
         scanf("%d",&a[i][j]);
        }
    }
    printf("\nenter the elements of the second matrix : ");
    for(i=0;i<m;i++)
    {
        for(j=0;j<n;j++)
        {
            scanf("%d",&b[i][j]);
        }
    }
    for(i=0;i<m;i++)
    {
        for(j=0;j<n;j++)
        {
        c[i][j]=a[i][j]*b[j][i];
        printf("%d\t",c[i][j]);
        }
        printf("\n");
    }
}*/
{
    int n;
    printf("Enter the length of the array as n : ");
    scanf("%d",&n);
    int arr[n],i,k,co1=0,co2=0,co3=0;
    printf("\nenter the array : ");
    for(i=0;i<n;i++)
    {
        scanf("%d",&arr[i]);
    }
    printf("\nEnter k : ");
    scanf("%d",&k);
    for(i=0;i<n;i++)
    {
        if(arr[i]>k)
        {
            co1=co1+1;
        }
        else if(arr[i]<k)
        {
            co2=co2+1;
        }
        else
        {
            co3=co3+1;
        }
    }
    printf("\nThe count of numbers greater than %d is %d ",k,co1);
    printf("\nThe count of numbers smaller than %d is %d ",k,co2);
    printf("\nThe count of numbers equal to %d is %d ",k,co3);
}
```
