#1.3 HOW LONG WILL THE FOR LOOP GET EXECUTED#
```C
#include<stdio.h>
int main()
{
    int i;
    for(;scanf("%d",&i);printf("%d\n",i));
    return 0;
}
```
#ANS: INFINITE OR UNTIL A CHARACTER IS NOT INSERTED.#

#WHICH OF THE FOLLOWING ARE DECLARATIONS AND WHICH ARE DEFINITIONS#

    extern int x;               //DECLARATION
    float y;                    //DEFINITION
    double pow(double,double);  //DECLARATION
    float square(float x);      //DEFINITION

*REDIFINITION IS AN ERROR WHEREAS REDECLARATION IS NOT AN ERROR*


#WHAT WILL BE THE CORRECT OUTPUT OF THE PROGRAM GIVEN BELOW#
```c
#include<stdio.h>
int main()
{
    extern int i;
    i=20;       //int i =20 ,must be present.
    printf("%d\n",sizeof(i));
    return 0;
}
```
#compilation error ,i is undefined .#

*A GLOBAL VARIABLE MAY HAVE SEVERAL DECLARATIONS BUT ONLY ONE DEFINITION*

#WHICH STATEMENT SHOULD BE ADDED IN THE GIVEN main() FUNCTION TO MAKE IT WORK#
```C
#include<stdio.h>
int main()
{
    printf("%d\n",z);
    return 0;
}
int z=25;
```
#ANS. extern int z;#

#P.1.33 POINT OUT THE ERROR IN THE FOLLOWING PROGRAM#
```C
#include<stdio.h>
int main()
{
    int (*p)()=fun;
    (*p)();
    return 0;
}
int fun()
{
    printf("loud and clear\n");
}```
#ANS. function fun() is not declared,i.e, int fun() must be mentioned above main()#

#1.37 WHAT ARE THE DIFFERENT TYPES OF LINKAGES #
#Three different types of linkages : #
#1.external  2.internal   3.none#

#1.38 WHICH OF THE FOLLOWING IS THE CORRECT OUTPUT FOR THE PROGRAM GIVEN BELOW#
```C
#include<stdio.h>
int main()
{
    int x=10,y=20,z=5,i;
    i=x<y<z;
    printf("%d\n",i);
    return 0;
}
```
#OUTPUT : 1#

*NOTE : We cannot obtain the remainder in floating point division*

#1.53 HOW WOULD YOU ROUND OFF A VALUE 1.66 TO 2.000000 AND TRUNCATE 1.75 TO 1.000000#
```C
#include<stdio.h>
#include<math.h>
int main()
{
    float x=1.66;
    float y=1.75;
    printf("%f %f\n",ceil(x),floor(y));
    return 0;
}
```

#2.2 IS THERE ANY ERROR IN THE GIVEN PROGRAM#
```C
#include<stdio.h>
int main()
{
    int i=1;
    for(;;)
    {
        printf("%d\n",i++);
        if(i>10)
            break;
    }
    return 0;
}
```
#ANS : NO ERROR#

#2.3 IS THERE ANY ERROR IN THE GIVEN PROGRAM#
```C
#include<stdio.h>
int main()
{
    int i=1;
    while()
    {
        printf("%d\n",i++);
        if(i>10)
            break;
    }
    return 0;
}
```
#ANS : Yes! ERROR !,there should be a condition inside a while loop#

#2.5 PREDICT THE OUTPUT : #
```C
#include<stdio.h>
int main()
{
    int x=10,y=20;
    if(!(!x)&&x)
        printf("x = %d\n",x);
    else
        printf("y = %d\n",y);
    return 0;
}```
#OUTPUT : x=10#

#PREDICT THE OUTPUT OF THE FOLLOWING : #
```C
#include<stdio.h>
int main()
{
    char i=0;
    for(i<=5&&i>=-1;++i;i>0)
        printf("%d\n",i);
    printf("\n");
    return 0;
}
```
#OUTPUT : 1 2 3.........126 127 -128 -127 ...-2 -1#

#2.8 PREDICT THE OUTPUT OF THE FOLLOWING CODE : #
```C
#include<stdio.h>
int main()
{
    char ch;
    if((ch=printf("")))     //we can also use \0 or """"
        printf("it matters\n");
    else
        printf("it doesn't matter\n");
    return 0;
}
```
#it doesn't matter #    ???

#2.9 PREDICT THE OUTPUT OF THE FOLLOWING CODE : # 
```C
#include<stdio.h>
int main()
{
    int i=1;
    switch(i++)         // WHAT IF switch(++i)???
    {
        printf("hello\n");
    case 1:
        printf("Hi\n");
        break;
    case 2:
        printf("bye\n");
        break;
    }
}

```
#OUTPUT : Hi#

#2.11 PREDICT THE OUTPUT :  #
```C
#include<stdio.h>
int main()
{
    int a=500,b=100,c;
    if(!a>=400)
        b=300;
    c=200;
    printf("b = %d c = %d\n",b,c);
    return 0;
}

```
# b=200 c=300#

#2.12 PREDICT THE OUTPUT : #
```C
#include<stdio.h>
int main()
{
    int x=10,y=100%90,i;
    for(i=1;i<=10;i++);
        if(x!=y);
            printf("x=%d y=%d\n",x,y);
    return 0;
}
```
#OUTPUT : x=10 y=10#

#2.13 POINT OUT THE ERROR : #
```C
#include<stdio.h>
int main()
{
    int i=4,j=2;
    switch(i)
    {
    case 1:
        printf("Hello");
        break;
    case j:
        printf("Hi");
        break;
    }
    return 0;
}
```
#ANS : constant expression should be used in second case instead of j #

#2.14 PREDICT THE OUTPUT : #
```C
#include<stdio.h>
int main()
{
    int i=5;
    while(i-->=0)printf("%i",i);
    i=5;
    printf("\n");
    while(i-->=0)printf("%i",i);
    printf("\n");
    while(i-->=0)printf("%d",i);
    return 0;
}
```
#OUTPUT : 4 3 2 1 0 -1 #
       #  4 3 2 1 0 -1 #

#2.15 INPUT : PREDICT THE OUTPUT : #
```C
#include<stdio.h>
int main()
{
    int i=0;
    for(i=0;i<=127;printf("%d\t",i++));
    return 0;
}
```

# OUTPUT : 0 1 2 3......126 127#

#2.16 INPUT : PREDICT THE OUTPUT #
```C
#include<stdio.h>
int main()
{
    char str[]="string";
    int a=5;
    printf(a>10?"%50s\n":"%s\n",str);
    return 0;
}
```
#OUTPUT : string#
#NOTE : switch statement can't be used to switch on strings#
#NOTE : continue can work only with loops not with switch#

#2.17 INPUT :#
```c
int a=1,b,dummy,val;
    val=a>10?b=20:b=10;
    printf("%d",val);
    return 0;
```
#ERROR : lvalue required in function main().#
#To avoid this (b=10) must be used in second assignment.#
#2.29 FIND THE OUTPUT OF THE GIVEN CODE : #
```C
#include<stdio.h>
int main()
{
    float a=0.7;
    if(0.7>a)
        printf("Hi\n");
    else
        printf("Hello\n");
    return 0;
}

```
#OUTPUT : Hi#
#       Because,0.7 is double by default and a is a float.When 0.7 is stored in a ,what get stored is a 32-bit binary equivalent of 0.7,The binary equivalent of 0.7 turns out to be a recurring number. This recurring number is teminated at 32 bits when it is stored in a. As against this,when 0.7 is treated as a dole the recurring binary equivalent of 0.7 is terminated at 64 bits. When the 64-bit recurring binary equivalent of 0.7 is compared with 32-bit recurring binary equivalent of 0.7,the 64-bit value turns out to be greater than the 32-bit value.Hence the condition turns out to be true. #

#FIND THE ERROR IN THE GIVEN CODE : #
```C
#include<stdio.h>
int main()
{
    int i=3;
    switch(i)
    {
    case 1:
        printf("Hello\n");
    case 2:
        printf("Hi\n");
        break;
    case 3:
        continue;
    default:
        printf("Bye\n");
    }
    return 0;
}
```
#ERROR : continue statement misplaced ,only used with loops#

#POINT OUT THE ERROR : #
```C
#include<stdio.h>
int main()
{
    char x;
    while(x=0;x<=255;x++);
        printf("abc\n");
    return 0;
}
```
#OUTPUT : syntax error,while loop written in the form of for loop#

#2.37 POINT OUT THE ERROR : #
```C
   int i=10,j=20;
    if(i==5)&&if(j==10)
        printf("have\n");
```
#ANS : syntax error ,it should be as : if((i==5)&&(j==10))#

#2.38 FIND THE OUTPUT : #
```C
#include<stdio.h>
int main()
{
    int n=0,y=1;
    y==1?(n=0):(n=1);
    if(n)
        printf("YES\n");
    else
        printf("NO\n");
    return 0;
}
```
#OUTPUT : NO#

#2.40 PREDICT THE RESULT OF THE GIVEN CODE : #
```C
#include<stdio.h>
#include<stdlib.h>
int main()
{
    int i=0;
    i++;
    if(i<=5)
    {
        printf("exit successfully");
        exit(0);
        main();
    }
    return 0;
}
```
#OUTPUT : exit successfully#
*The program prints 'exit successfully' once*
*The call to main() after exit(0) does'nt materialize*
#2.42 find the error : #
```c
#include<stdio.h>
int main()
{
    int i=10,j=15;
    if(i%2=j%3)
        printf("\nanswer");
    return 0;
}

```
#ANS : ERROR:lvalue required#

#PRINT THE CORRECT OUTPUT#
```C
#include<stdio.h>
int main()
{
    int a=0,b=1,c=3;
    *((a)?&b:&a)=a?b:c;
    printf("%d%d%d\n",a,b,c);
    return 0;
}
```
#OUTPUT : 313#
#2.44 PRINT THE OUTPUT : #
```C
#include<stdio.h>
int main()
{
    int i=0;
    for(;i<5;i++);  
    printf("%d\n",i);
    return 0;
}
```
#ANS : 5#

#2.45 PREDICT THE OUTPUT : #
```C

```

#2.46 PREDICT THE CORRECT OUTPUT : #
```C
#include<stdio.h>
int main()
{
    int x=1,y=1;
    for(;y;printf("%d%d\n",x,y))
        y=x++<=5;
}
```
#OUTPUT : 
21
31
41
51
61
70
#

#3.3 PRINT THE OUTPUT : #
```C
#include<stdio.h>
int main()
{static int a[20];
int i=1;
a[i]=i++;
printf("%d%d%d\n",a[0],a[1],i);
}
```
#OUTPUT : 001 in gcc while 011 in turbo compiler// #
