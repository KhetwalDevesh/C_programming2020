#1.INPUT #
```c

#include<stdio.h>
int main()
{
    if(printf("hello world")){}
}
```
#2.INPUT #
```c
#include<stdio.h>
int main()
{
    int a=0;
    a=a++ + a++ - a++ ;// + ++a;
    printf("%d\n",a);
}
```
#INPUT #
```c
#include<stdio.h>
int main()
{int flag =0,flag1=0,n;
char s;
flag=scanf("%d",&n);
flag1=scanf("%d",&s);
printf("value of flag is %d",flag);
printf("\nvalue of flag is %d ",flag1);
}
```
#4.INPUT#
```c
#include<stdio.h>
void main()
{

    printf(8+"first year");
}
```
#INPUT#
```c
#include<stdio.h>
void main()
{

    int i,j=5,k,x;
    for(i=1;i<=5;i++)
    {
        for(k=1;k<=j;k++)
        {
            printf("");
        }
        for(x=1;x<=i;x++)
        {
            printf("%d",i);
            printf(" ");
        }
        printf("\n");
        j=j-1;
    }
}
```
#viva : INPUT#
```c
#include<stdio.h>
int main()
{
    int x=-1,i,count=0;
    for(i=0;i<=70000;i++)
   {
     printf("%d",x);
    count=count+1;
   }
   printf("%d",count);
}
```
#INPUT#
```c
#include<stdio.h>
int main()
{
    int x;
    x=3*5/4+1*4/3+1/4;
    printf("%d",x);
}
```
# viva : INPUT : Write a program to print the given series upto n=100000 : 1+1/5+1/10+-----------+1/n   #
```c
#include<stdio.h>
int main()
{
    float i,n,s=1;
    printf("enter n : ");
    scanf("%f",&n);
    if(n<100000)
    {
    for(i=1;i*5<=n;i++)
    {
        s=s+1/(5*i);
    }
    printf("%f",s);
    }
}


```
# INPUT #
```c
#include<stdio.h>
int main()
{
    printf(";"      ";"     ";");
    printf(";"";"";");
    printf(";""   "";""   "";");
    printf("""""""");
v
}
```
# INPUT # >>> # OUTPUT -- 'INFINITY LOOP'#
```c

#include<stdio.h>
int main()
{
    char x='a',i,count=0;
    for(i=0;i<=129;i++)
   {
     printf("%c",x);
    count=count+1;
   }
   printf("%d",count);
}
```
# INPUT # >>> OUTPUT --- 'a will be printed 130 times' #
```c

#include<stdio.h>
int main()
{
    unsigned char x='a',i,count=0;
    for(i=0;i<=129;i++)
   {
     printf("%c",x);
    count=count+1;
   }
   printf("%d",count);
}
```

# INPUT >>>> OUTPUT -- compilation error..#
```c
#include<stdio.h>
int main()
{
    int x;
    x=3.0%5.2;
    printf("%d",x);
}
```
#INPUT#
```c
#include<stdio.h>
int main()
{
    printf("hello"),printf("world"),printf("\tcprogramming");}
```
#INPUT#
```c
#include<stdio.h>
int main()
{
    printf("%c",'hello'),printf("world"),printf("\tcprogramming");}
```
#15.INPUT#
```c#include<stdio.h>
int main()
{
    int i=(5,8,9);
    int j;
    j=11,4,1;
    printf("%d%d",i,j);
    return 0;
}
```
#16.INPUT #
```c
#include<stdio.h>
int main()
{
    int a=300,b=0,c=0;
    if(a>=400);
    b=300;
    c=200;
    printf("%d%d",b,c);
    return 0;
}```
# 17.INPUT #
```c
#include<stdio.h>
int main()
{
    char ch='A';
    switch(ch)
    {
        case'A':
        case'B':ch++;
        case'C':ch++;
    }
    printf("%c",ch);
    return 0;
}
```
#18.INPUT#
```c
#include<stdio.h>
int main()
{
    int x=4,y=0,z;
    while(x>=0)
    {
        if(x--==y++)
            break;
        else
            printf("\n%d%d",x,y);
    }
    return 0;
}
```
#19.INPUT#
```c
#include<stdio.h>
int main()
{
    int x=4,y=0,z;
    while(x>=0)
    {
        if(--x==++y)
            break;
        else
            printf("\n%d%d",x,y);
    }
    return 0;
}
```
#20.INPUT#
```c
#include<stdio.h>
int func(int);
int main()
{
    int k=97;
    k=func(k=func(k=func(k)));
    printf("%d",k);
}
int func(int x)
{
    x++;
    return x;
}
```
#21.INPUT#
```C
#include<stdio.h>
int main()
{
    int i;
    for(i=1;i<=5;printf("\n%d",i));         ANSWER : infinity LOOP
    i++;
    return 0;
}
```
#22.INPUT#
```C
#include<stdio.h>
int main()
{
    int arr[4],i=0;
    while(i<4)
        arr[i]=++i;
    for(i=0;i<4;i++)
        printf("%d",arr[i]);
    return 0;
}
```
#23.INPUT#
```C
#include<stdio.h>
int main()
{
    int i=10;
    while(i=20)
        printf("\nsunrise");       : INFINITY LOOP
    return 0;
}
```
#24.INPUT#
```c
#include<stdio.h>
int main()
{
    char c[2]="A";
    printf("\n%c",c[0]);
    printf("\n%s",c);
    return 0;
}
```
#25.INPUT#
```c
#include<stdio.h>
int reset1();
int reset2();
int main()
{
    auto int i=0;
        printf("%d\n",reset1());
        printf("%d\n",reset2());
        printf("%d\n",reset1());
        printf("%d\n",reset2());
    return 0;
}
int reset1()
{
    int j=0;
    j++;
    return(j);
}
int reset2()
{
    static int i=10;
    i+=1;
    return(i);
}
```
#26.INPUT#
```c
#include<stdio.h>
int main()
{
    int a=2,b=3,c=4;
    if(c!=100)
        a=10;
    else
        b=10;
    if(a+b>10)
        c=12;
    a=20;
    b=++c;
    printf("\n a = %d \t b = %d \t c = %d",a,b,c);
    return 0;
}
```
#27.INPUT#
```c
#include<stdio.h>
int main()
{
    char ch=321;   //321-256=65
    printf("%d",ch);// 65
    printf("\n%c",ch); //A
}

```
#28. INPUT#
```C
char str[10];
    printf("\nenter a string : ");
    scanf("%",str);         // OR scanf("s",str);
    printf("\nther string is : %s",str);
```
#output : garbage#

#29.INPUT#
```C
#include<stdio.h>
int main()
{
    int i;
    char a[]="\0";
    if(printf("%s",a))
        printf("non empty");
    else
        printf("\nempty");
}
```
#output : empty#
#INPUT#
```C
#include<stdio.h>
int main()
{
    int i;
    char a[]="a\0";
    if(printf("%s",a))
        printf("non empty");
    else
        printf("\nempty");
```
#output : non empty#
```c
#include<stdio.h>
int main()
{
    int i;
    char a[]="a\0";
    if(printf("%s",a[0])) //don't gives output at runtime
        printf("non empty");
    else
        printf("\nempty");
```
```c
#include<stdio.h>
int main()
{
    int i;
    char a[]="a\0";
    if(printf("%s",a[1]))   
        printf("non empty");
    else
        printf("\nempty");
```
#output : <null>empty#

```c
while(A[j]!='\0')
{if(j<=l/2)
{temp=A[j];
A[j]=A[l-1-j];
A[l-1-j]=temp;
j++;            //doesnt works
}        //j++ should be after the end of if block.
}
```

```c
#include<stdio.h>
int main()
{

    printf("%%%%%%");
}
```
#output : %%%#

#INPUT#
```C
#include<stdio.h>
int main()
{
    char a=316,b=5;
    char ch=a+b;
    printf("enter a character : ");
    //scanf("%c",&ch);
    printf("\nascii value is : %c",ch);

}
```
#INPUT : #
```c
printf("enter . to stop : ");
scanf("%c",&str[i]);
while(str[i]!='.')
{
    //i++;  //     CORRECT
scanf("%c",&str[i]);
i++;        //ERROR
}
```
#while inputting a multiline text the thing needed to keep in mind is that the increment of the index must be done before the scanf present in the loop otherwise it will never stop taking the input.# 

#INPUT#
```C
#include<stdio.h>
int main()
{
    int arr[5],i;
    *arr=5;
//    arr++;(ERROR) //array is not an lvalue.
    *(arr+1)=0;
    printf("%d",*(arr+1));
}
```