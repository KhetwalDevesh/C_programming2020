#Pointers are variables that store address of another variable#
```c
#include<stdio.h>
int main()
{
    int a=10;
    int *p=&a;
    printf("%d\n",p);
printf("%d\n",*p);
//    printf("%d\n",*p);
}
```
```c
#include<stdio.h>
int main()
{
    int a=10;
    int *p=&a;
    printf("%d\n",p);
    p=p+2;
    printf("%d\n",p);
printf("%d\n",*p);
//    printf("%d\n",*p);
}
```
*pointers are not only used to store address they are used to dereferencing as  well.*

#WHY THERE IS A NEED TO TYPECAST THE ADDRESS OF A VARIABLE OR AN ARRAY WHILE ASSIGNING IT TO THE POINTER VARIABLE AS WE KNOW THE ADDRESS IS ALREADY IN INTEGER VALUE AND THE POINTER VARIABLE IS USED TO STORE THE  ADDRESS??#

#ANS. We can understand it well by analyzing the following code snippets#
```c
#include<stdio.h>
int main()
{
    int a=1025;
    int *p;
    p=&a;
    printf("size of integer is %d bytes",sizeof(int));
    printf("address = %d,value =%d",p,*p);
    char *p0;
    p0=(char*)p;
    printf("size of char is %d bytes\n",sizeof(char));
    printf("address = %d,value = %d\n",p0,*p0);     //1
    printf("Address = %d,value = %d\n",p0+1,*(p0+1));//4
```
1025 = 00000000 00000000 00000100 00000001
#It is the binary representation of 1025,since char data type has the capacity to store only 1 byte,therefore we need to typecast the address as well to assure that only 1 byte data would assign to the pointer and by doing so we can get rid of the error or the warning.#
#Therefore the last line of the code prints the value *(p0+1) as 4 which is exactly correct ,which we can analyze from the binary representation #

```c
#include<stdio.h>
int main()
{
    int x=5;
    int *p=&x;
    *p=6;
    int **q=&p;
    int ***r=&q;
    printf("%d\n",*p);  //6
    printf("%d\n",*q);  //address
    printf("%d\n",**q); //6
    printf("%d\n",**r); //address
    printf("%d\n",***r); //6
    ***r=10;
    printf("x= %d\n",x);    //10
    **q=*p+2;
    printf("x= %d\n",x);    //12


}
```

#APPLICATION'S MEMORY#
1.Heap
2.Stack
3.Global/static
4.code

#For the execution of the function call stack section of the memory is used#
```c
    int sumOfElements(int A[])
{
    int i,sum=0;
    int size=sizeof(A)/sizeof(A[0]);
    printf("size of A = %d  and the size of A[0] = %d\n",sizeof(A),sizeof(A[0]));
    for(i=0;i<size;i++)
    {
        sum+=A[i];
    }
    return sum;
}
int main()
{int A[]={1,2,3,4,5};
int total=sumOfElements(A);
printf("sum of elements = %d\n",total);
printf("size of A = %d  and the size of A[0] = %d\n",sizeof(A),sizeof(A[0]));}
```
#Here the sum is 1 because,the value of size is obtained as 1,this is because while calculating the value of the size,sizeof(A) is same as to sizeof(A[0]),this is because the compiler implicitily change A[] as *A in the formal argument and intepret it as a pointer which stores the address of the first element of the array currently,there its size is also 4 bytes in this condition.#
#To overcome the above issue we can pass the size of array to the function as well by calculating it in the calling function#
```c
int sumOfElements(int *A,int *size)
{
    int i,sum=0;
    printf("%d\n",*size);
    for(i=0;i<*size;i++)
    {
        sum+=A[i];
    }
    return sum;
}
int main()
{int A[]={1,2,3,4,5};
int size=sizeof(A)/sizeof(A[0]);
int total=sumOfElements(A,&size);
printf("sum of elements = %d\n",total);
printf("size of A = %d  and the size of A[0] = %d\n",sizeof(A),sizeof(A[0]));}

```
#CHARACTER ARRAYS AND POINTERS#
#1.How to store strings ?#
            #size of array>=no. of characters in string+1#
```c
#include<stdio.h>
void print(char *c)
{
    while(*c!='\0')
    {
        printf("%c",*(c));
        c++;
    }
    printf("\n");
}
int main()
{
    char c[20]="Hello";
    print(c);
}
```
#The above program will display Hello#
#We can modify the characters of the string using the following technique #
```c
#include<stdio.h>
void print(char *c)
{
    c[0]='A';
    while(*c!='\0')
    {
        printf("%c",*(c));
        c++;
    }
    printf("\n");
}
int main()
{
    char c[20]="Hello";
    print(c);
}
```
#The above program will print Aello#
#If we want our program to be read only and no modification would be successful,then we need to use 'const' in the argument#
```
#include<stdio.h>
void print(char *c)
{
    c[0]='A';
    while(*c!='\0')
    {
        printf("%c",*(c));
        c++;
    }
    printf("\n");
}
int main()
{
    char c[20]="Hello";
    print(const c);
}
```
#The above program will throw a compilation error .#

#NOTE : CHECK OUT THE BELOW TWO CODE SNIPPETS CAREFULLY#
```C
#include<stdio.h>
int main()
{
char *arr="hello";//Here string gets stored as compile time constant in the text segment of the memory.
arr[2]='a';
for(int i=0;*(arr+i)!='\0';i++)
    printf("%c\t",*(arr+i));
}```
VS
```C
#include<stdio.h>
int main()
{
char arr[]="hello";//Here string gets stored in the space for array in the stack
arr[2]='a';
for(int i=0;arr[i]!='\0';i++)
    printf("%c\t",arr[i]);
}```
#In the first case string literal gets stored in the address as a constant ,therefore we cant modify it,which we can observe by running the program .#
#While in the second snippet string is stored as an array which we can modify and obtain the required output#

#POINTERS AND 1-D ARRAYS#
 
 ```c
 #include<stdio.h>
int main()
{
    
    int A[]={1,2,3,4,5};
    int *p=A;
    for(int i=0;i<5;i++)
    printf("%d\t",*(p+i));
}
```
https://www.hackerrank.com/challenges/querying-the-document/problem
#ARRAYS AS FUNCTION ARGUMENTS#

```c
#include<stdio.h>
int sum_of_elements(int* A,int size);
int main()
{
    int A[5]={1,2,3,4,5};
    int size;
    size=sizeof(A)/sizeof(A[0]);
    sum_of_elements(A,size);
}
int sum_of_elements(int* A,int size)
{
    int i=0;
    while(i<5)
    {
        printf("%d\t",*(A+i));
        i++;
    }
}
```
#WRITE A PROGRAM TO COUNT THE CAPITAL AND SMALL LETTERS IN A GIVEN STRING#
```
#include<stdio.h>
int main()
{
    int cpc=0,smc=0;
    char str[100],*pstr=str;
    gets(str);
    while(*pstr!='\0')
    {
        if(*pstr>='A'&&*pstr<='Z')
        {
            cpc++;
        }
        if(*pstr>='a'&&*pstr<='z')
        {
            smc++;
        }
        pstr++;
    }
    printf("\ncount of capital letters in the above string is %d",cpc);
    printf("\ncount of small letters in the above string is %d",smc);
}


```