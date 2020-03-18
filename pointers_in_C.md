#POINTERS : variables that store address of another variable.#
```c
#include<stdio.h>
int main()
{
    int a;
    int *p;
    p=&a;
    a=5;
    printf("%d",p);     //2686748(address of a)
    printf("\n%d",a);   //5 (value of a)
    printf("\n%d",&a);  //2686748
    printf("\n%d",&p);  //2686744(address of p)
    printf("\n%d",*p);  //5(value of pointer p)
    a=8;
    printf("\n%d",a);   //8(updated value of a)
    printf("\n%d",*p);  //8(*p updated as well)
}
```
```c
 int a=5;
    int *p;
    p=&a;
    printf("address of p is %d",p);//2686744
    printf("\naddress p+1 is %d",p+1);//2686748
    printf("\naddress p+2 is %d",p+2);//2686752
    printf("\nvalue at address p is %d",*p);//5
    printf("\nvalue at address p+1 is %d",*(p+1));//garbage

```
#Pointer variables are not only used to store the address of a variable,rather these are used to dereference these addresses so that we can access and modify the values in these addresses . #
```c
 int a=1025;
    int *p;
    p=&a;
    printf("size of integer is %d bytes\n",sizeof(int));    //4 
    printf("Address = %d,value = %d\n",p,*p);               //2686740,1025
    char *p0;                                               
    p0=(char*);                                                                
    printf("size of char is %d bytes \n",sizeof(char));     //1    
    printf("Address = %d,value = %d\n",p0,*p0);             //2686740,1
    printf("Address = %d,value = %d\n",(p0+1),(*p0+1));;    //2686741,garbage
```
```c
//void pointer - generic pointer
    void *p1;
    p1=p;
    printf("Address = %d ",p1);
```
#CALL BY REFERENCE : #
```C
#include<stdio.h>
void  increment(int);
int main()
{
int a;
a=10;
increment(&a);
printf("\nAddress = %d,value of a in the main function %d",&a,a);
}
increment(int *a)
{
    *a=*a+1;
    printf("Address = %d,value of a in the incre function %d",&*a,*a);
}
```
#INPUT,DISPLAY AND SORT AN ARRAY USING POINTER FUNCTIONS#
```C
#include<stdio.h>
void input(int *p)
{
    int i;
    printf("enter the array : \n");
    for(i=0;i<=4;i++)
        scanf("%d",p+i);
}
void display(int *p)
{
    int i;
    for(i=0;i<=4;i++)
        printf("%d\t",*(p+i));
}
void sort(int *p)
{
    int i,j,t;
    for(i=1;i<=4;i++)
    {
        for(j=0;j<4;j++)
        {
            if(*(p+j)>*(p+j+1))
            {
                t=*(p+j);
                *(p+j)=*(p+j+1);
                *(p+j+1)=t;
            }
        }
    }
}
int main()
{
    int a[5];
    input(a);
    sort(a);
    display(a);
}

```
#EXTENDED CONCEPT OF POINTERS#
#nO. OF astericks in the pointer tells the level of indirection of the pointer.
and it can hold only the address of its previous variable.#
#***r it means r is a pointer to a pointer to a pointer to an int#
#it is the way to read pointers.#
```c
#include<stdio.h>
int main()
{
    int x=5,*p,**q,***r;
    p=&x;
    q=&p;
    r=&q;
    ***r=7;
    printf("*p = %d",*p);
    printf("*q = %d",*q);
    printf("*r = %d",*r);
}
```
#POINTER ARITHMETIC#
#we cannot add,multiply or divide two addresses(subtraction if possible)#
#we cannot multiply an integer to an address and cannot divide address with an integer value#
#WE CAN SUBTRACT TWO ADDRESSES THUS WE WILL GET ANSWER IN BYTE#
*i.e. pointer-n=pointer -sizeof(type of pointer)*n
#WE CAN ADD AN INTEGER TO AN ADDRESS#
*i.e. pointer+n=pointer +sizeof(type of pointer)*n
```C
#include<stdio.h>
int main()
{
   int a=5,b=10;
   int *p,*q;
   p=&a;
   q=&b;
   printf("ADD AN INTEGER TO ADDRESS : %d",p+1);
   printf("SUBTRACT TWO ADDRESSES : %d",p-q);}
```
#p+1 means address_of_a + size_of_datatype*1#
#p-q means (address_of_a - address_of_b)/datasize_of_pointers#
#CODE SNIPPETS #
```c
int x=5;
    int  *p;
    p=&x;
    printf("\n%d",p);   //2686748
    printf("\n%d",&p);  //2686744
    printf("\n%d",p+1); //2686752
```
vs
```c
    char x=5;
    char  *p;
    p=&x;
    printf("\n%d",p);  //2686748
    printf("\n%d",&p); //2686744
    printf("\n%d",p+1);//2686749
    ```
```c
#include<stdio.h>
int main()
{
int i=3,*x=&i;
float j=1.5,*y=&j;
char k='c',*z=&k;
printf("\n%u\t%d",x,*x);
printf("\n%u\t%f",y,*y);
printf("\n%u\t%c",z,*z);
x++;
y++;
z++;
printf("\n%u\t%d",x,*x);
printf("\n%u\t%f",y,*y);
printf("\n%u\t%c",z,*z);
}
```

    ```c
    #include<stdio.h>
int main()
{
    int *p;
    int x=10;
    p=&x;
    printf("%d\n",*p);
    printf("%p\n%p",&p,&x);//%p prints the address in hexadecimal.
}```
```c
#include<stdio.h>
int main()
{
    int *p,*s;
    int x=10;
    p=&x;
    s=&*p;
    printf("%u",p);
      printf("\n%d",(s));
}
```
#ASSIGNMENT OPERATORS IN POINTERS #
```C
#include<stdio.h>
int main()
{
    int x=5,y=10,*px=&x,*py=&y;
    *px=*py;
    printf("%d",*px);
}
```
*An object is a named region of storage; an lvalue is an expression referring to an object.*

#WAP TO READ AND DISPLAY AN ARRAY OF n INTEGERS#
```C
#include<stdio.h>
int main()
{
    int n;
    printf("enter the number of elements : ");
    scanf("%d",&n);
    int arr[n],i,*parr=arr;
    printf("\nenter the array : ");
    for(i=0;i<n;i++)
    {
        scanf("%d",parr+i);
    }
    printf("\nThe array is : ");
    for(i=0;i<n;i++)
        printf("%d",*parr+i);
}
```
#WAP TO READ,DISPLAY AND PRINT THE SMALLEST ELEMENT OF AN ARRAY AND ITS POSITION USING FUNCTION#
```C
#include<stdio.h>
void read(int *arr,int *n);
void display(int *arr,int *n);
void smst(int *arr,int *n,int *small);
int main()
{
    int n;
    printf("enter the length of the array : ");
    scanf("%d",&n);
    int arr[n];
    read(arr,&n);
    display(arr,&n);
    smst(arr,&n,arr);
}
void read(int *arr,int *n)
{
    int i=0;
    printf("\nenter the array : ");
    while(i<*n)
    {
        scanf("%d",arr+i);
        i++;
    }
}
void display(int *arr,int *n)
{
    int i=0;
    printf("\nentered array is : ");
    while(i<*n)
    {
        printf("%d\t",*(arr+i));
        i++;
    }
}
void smst(int *arr,int *n,int *small)
{
    int i=0,pos=i;
    while(i<*n)
    {
        if(*(arr+i)<*small)
        {
         *small=*(arr+i);
         pos=i;
        }
            i++;
    }
    printf("\nThe smallest element is %d and its position is %d",*small,pos);
}

```
#CALCULATE AREA OF CIRCLE USING POINTER#
```C
#include<stdio.h>
int main()
{
    int r,*x=&r;
    scanf("%d",&r);
    float ar,*par=&ar;
    *par=3.14**x**x;
    printf("%.2f",*par);
}
```
#TO DETERMINE A CHARACTER IS VOWEL OR NOT #
```C
#include<stdio.h>
int main()
{
    char ch,*pch=&ch;
    scanf("%c",&ch);
    if(*pch=='a'||*pch=='e'||*pch=='o'||*pch=='i'||*pch=='o'||*pch=='u')
            printf("vowel");
    else
        printf("not a vowel");

}
```
#TO INPUT THE CHARACTERS UNTIL * IS NOT ENTERED AND DISPLAY EACH CHARACTER BY CHANGING ITS CASE#
```C
#include<stdio.h>
int main()
{
    char ch,*pch=&ch;
    int upper=0,lower=0;
    printf("enter a character : ");
    scanf("%c",pch);
    while(*pch!='*')
    {
        if(*pch>='A'&&*pch<='Z')
        {
            *pch+=32;
            upper++;
        }
        if(*pch>='a'&&*pch<='z')
        {
            *pch-=32;
            lower++;
        }
        printf("\t%c\n",*pch);
        fflush(stdin);
        printf("enter a character : ");
        scanf("%c",pch);
    }
    printf("\ntotal no. of uppercase characters = %d",upper);
    printf("\ntotal no of lowercase characters = %d",lower);
}
```
#WAP TO DISPLAY SUM AND AVERAGE OF THE NUMBERS FROM M TO N#
```C
#include<stdio.h>
int main()
{
    int n,m,*pn=&n,*pm=&m,l=0,sum=0,*psum=&sum;
    float avg,*pavg=&avg;
    printf("enter n and m : ");
    scanf("%d%d",&n,&m);
    while(*pn<=*pm)
    {
        sum+=*pn;
        (*pn)++;
        l++;
    }
    avg=(float)sum/l;
    printf("sum = %d",*psum);
    printf("\naverage = %f",*pavg);
}
```
#WAP TO PRINT ALL EVEN AND ODD NUMBERS BETWEEN m AND n#
```c
#include<stdio.h>
int main()
{
    int m,n,*pm=&m,*pn=&n,i;
    printf("enter the limits : ");
    scanf("%d%d",pm,pn);
    while(*pm<=*pn)
    {
        if(*pm%2==0)
            printf("%d is even\n",*pm);
        else
            printf("%d is odd\n",*pm);
        (*pm)++;
    }
}
```
#WAP TO READ NO.S UNTIL -1 IS ENTERED AND DISPLAY WHETHER THE NUMBER IS PRIME OR COMPOSITE#
```C
#include<stdio.h>
int main()
{
    int n,*pn=&n,flag=0,i;
    printf("enter any number : ");
    scanf("%d",pn);
    while(*pn!=-1)
    {
        if(*pn==1)
            printf("nor prime neither composite\n");
        else if(*pn==2)
            printf("prime\n");
        else
        {
            for(i=2;i<=*pn/2;i++)
            {
                if(*pn%i==0)
                {
                 flag=1;
                 break;
                }
            }
            if(flag==0)
                printf("\nprime");
            else
                printf("\nnot prime");
                flag=0;
        }
        printf("\nenter any number : ");
        scanf("%d",pn);
    }
}
```
#GENERIC POINTERS : #
```C
#include<stdio.h>
int main()
{
    int x=10;
    char ch='A';
    void *gp;
    gp=&x;
    printf("generic pointer to the integer value = %d",*(int*)gp);
    gp=&ch;
    printf("\ngeneric pointer to the character %c",*(char*)gp);
    return 0;
}
#PASSING ARGUMENTS TO FUNCTION USING POINTERS #
#WAP TO ADD TWO NUMBERS : #
```C
#include<stdio.h>
int sum(int *,int *,int *);
int main()
{
    int a,b,c;
    printf("enter the numbers to be added : ");
    scanf("%d%d",&a,&b);
    sum(&a,&b,&c);
    printf("The sum is : %d",c);
}
int sum(int *a,int *b,int *c)
{
    *c=*a+*b;
}

#WAP TO FIND THE AREA OF THE TRIANGLE ,GIVEN THE BASE AND THE HEIGHT OF THE TRIANGLE#
```C
#include<stdio.h>
void read(float *b,float *h);
void t_area(float *b,float *h,float *a);
int main()
{
    float base,height,area;
    read(&base,&height);
    t_area(&base,&height,&area);
    printf("\narea of the triangle is : %f",area);

}
void read(float *b,float *h)
{
        printf("enter the base of the triangle : ");
        scanf("%f",b);
        printf("\nenter the height of the triangle : ");
        scanf("%f",h);
}
void t_area(float *b,float *h,float *a)
{
    *a=0.5**b**h;
}
```
#WAP TO PRINT THE LARGEST OF THE THREE NUMBERS : #
```C
#include<stdio.h>
void read(int *a,int *b,int *c);
void compare(int *a,int *b,int *c,int *big);
int main()
{
    int a,b,c,large;
    read(&a,&b,&c);
    compare(&a,&b,&c,&large);
    printf("The biggest of the three numbers is %d",large);
}
void read(int *a,int *b,int *c)
{
    printf("enter the numbers to be compared :");
    scanf("%d%d%d",a,b,c);
}
void compare(int *a,int *b,int*c,int *big)
{
    if((*a>*b)&&(*a>*c))
        *big=*a;
    else if((*b>*c)&&(*b>*a))
        *big=*b;
    else if((*c>*a)&&(*c>*b))
        *big=*c;
    else
        *big=*a;
}
```


```
    #POINTERS AND ARRAYS #
    ```C
        int A[5]={1,2,3,4};
    int *p;
    p=A;
    printf("%d",p);       //2686728
    printf("\n%d",&A[0]); //2686728
    printf("\n%d",*p);    //1
    printf("\n%d",A[0]);  //1
    printf("\n%d",p+1);   //2686732
    printf("\n%d",&A[1]); //2686732
    printf("\n%d",*(p+1));//2
    printf("\n%d",A[1]);  //2
    ```
    #POINTERS AND FUNCTIONS#
    
    ```c
    #include<stdio.h>
int sum_of_elements(int A[],int n);
int main()
{
    int i,size,ans;
  int A[]={6,2,3,4,0};
size=sizeof(A)/sizeof(A[0]);
sum_of_elements(A,size);
for(i=0;i<size;i++)
{
    printf("%d\t",A[i]);
}

}
int sum_of_elements(int * A,int n)
{
    int sum=0,i;
    for(i=0;i<n;i++)
    {
        A[i]=2*A[i];
    }
    return (A,n);
}
```
#PRINT THE OUTPUT #
```C
{
    int arr[]={1,2,3,4,5};
    int *ptr,i;
    ptr=&arr[2];
    *ptr=-1;
    *(ptr+1)=0;
    *(ptr-1)=1;
    printf("\nArray is : ");
    for(i=0;i<5;i++)
        printf("%d\t",*(arr+i));
}

```
#OUTPUT : 1 1 -1 0 5#

```c
{
    int arr[]={1,2,3,4,5,6,7,8,9};
    int *ptr1,*ptr2;
    ptr1=arr;
    ptr2=&arr[8];
    while(ptr1<=ptr2)
    {
        printf("%d",*ptr1);
        ptr1++;
    }
}
```
#OUTPUT : 123456789#
#CHARACTER ARRAYS AND POINTERS #
#character arrays#
```C
#include<stdio.h>
#include<string.h>
int main()
{
    char c[20];
    c[0]='j';
    c[1]='o';
    c[2]='h';
    c[3]='n';
    c[4]='\0';
    int len =strlen(c);
  printf("%d\n",len);
    printf("%s",c);
}

```
or
```c
  char c[5]="john";
    //scanf("%s",&c);
    int len =strlen(c);
  printf("%d\n",len);
    printf("%s",c);
```
```c
#include<stdio.h>
#include<string.h>
void print(char* C);
int main()
{
    char C[20]="hello";
    printf(C);
}
void print(char* C)
{
    int i;
    while(C[i]!='\0')
    {
     printf("%c",C[i]);
     i++;
    }
}


```
#ARITHMETC OPERATORS WITH POINTERS#
```C
#include<stdio.h>
int main()
{
int num1=2,num2=3,sum=0,mul=0,div=1;
int *ptr1,*ptr2;
ptr1=&num1;
ptr2=&num2;
sum=*ptr1+*ptr2;
mul=sum**ptr1;
*ptr2+=1;
div=9+*ptr1/ *ptr2-30;
printf("sum = %d",sum);
printf("\nmul = %d",mul);
printf("\ndiv = %d",div);
}

```
#POINTERS AND STRINGS #
#WAP TO INPUT AND DISPLAY STRINGS USING POINTERS#
```C
#include<stdio.h>
int main()
{
    char str[30],*pstr=str;
    gets(pstr);
    while(*pstr!='\0')
    {
        printf("%c",*pstr);
        pstr++;
    }

}
```

#WAP TO READ A STRING AND COUNT THE NO. OF UPPER AND LOWER CASE CHARACTERS IN THE STRING#
```#include<stdio.h>
int main()
{
    char str[30],*pstr=str;
    gets(str);
    int i=0,lower=0,upper=0;
    while(*pstr!='\0')
    {

        if(*pstr>'a'&&*pstr<'z')
            {lower++;
            pstr++;
        }

        else if(*pstr>'A'&&*pstr<'Z')
            {upper++;
            i++;
            pstr++;
            }
        else
        {
            pstr++;
        }
    }
    printf("Total no. of uppercase characters are %d",upper);
    printf("\ntotal no. of lower case characters are %d",lower);
}
```
#WAP TO COPY A STRING TO ANOTHER USING POINTERS#
```C
#include<stdio.h>
int main()
{
    int i;
    char str[100],cpy_str[100];
    char *pstr,*pcpy_str;
    pstr=str;
    pcpy_str=cpy_str;
    printf("enter the string : ");
    gets(str);
    while(*pstr!='\0')
    {
        *pcpy_str=*pstr;
        pcpy_str++,pstr++;
    }
    *pcpy_str='\0';
    printf("\nthe copied text is : ");
    pcpy_str=cpy_str;
    while(*pcpy_str!='\0')
    {
        printf("%c",*pcpy_str);
        pcpy_str++;
    }
}
```
#WAP TO COPY n CHARACTERS FROM THE mth position from an array to another#
```c
#include<stdio.h>
int main()
{
    int i,m,n;
    char str[100],cpy_str[100];
    char *pstr,*pcpy_str;
    pstr=str;
    pcpy_str=cpy_str;
    printf("enter the text : \n");
    gets(pstr);
    printf("enter the value of m : ");
    scanf("%d",&m);
    printf("\nenter the value of n : ");
    scanf("%d",&n);
    pstr=pstr+m;
    i=0;
    while(i<n)
    {
        *pcpy_str=*pstr;
        pcpy_str++;pstr++;
        i++;
    }
    *pcpy_str='\0';
    printf("\nthe copied text is : ");
    pcpy_str=cpy_str;
    while(*pcpy_str!='\0')
    {
        printf("%c",*pcpy_str);
        pcpy_str++;
    }
}
```
#WAP TO PRINT THE LAST m CHARACTERS OF A CHARACTER ARRAY : #
```
#include<stdio.h>
int main()
{
    int i,m,l;
    char str[100],*pstr=str;
    printf("enter the string : ");
    gets(str);
    l=strlen(str);
    printf("enter the no. of characters to be printed from the last : ");
    scanf("%d",&m);
    i=l-m;
    pstr=str+i;
    while(*pstr!='\0')
    {
        printf("%c",*pstr);
        pstr++;
    }
   // *pstr='\0';
}
```
#WAP TO PRINT HELLO WORLD USING POINTERS#
```C
#include<stdio.h>
int main()
{
    char *ch="Hello World";
    printf("%s",ch);
}

```
#WAP TO ADD TWO FLOATING NUMBERS #
```C
#include<stdio.h>
int main()
{
    float num1,num2,sum;
    float * pnum1=&num1,* pnum2=&num2,*psum=&sum;
    printf("enter two floating numbers : ");
    scanf("%f%f",*pnum1,*pnum2);
    *psum=*pnum1+*pnum2;
    printf("sum = %.2f",*psum);

}
```
#WAP TO FIND THE AREA OF THE CIRCLE#
```C
#include<stdio.h>
int main()
{
    double r,ar;
    double *pr=&r;
    double *par=&ar;
    printf("enter the radius : ");
    scanf("%lf",pr);
    *par=3.14*(*pr)*(*pr);
    printf("area of circle = %f",*par);
}

```
#WAP TO CONVERT A FLOATING POINT NUMBER INTO AN INTEGER#
```C
#include<stdio.h>
int main()
{
    float num;
    float *pnum=&num;
    scanf("%f",pnum);
    printf("%d",(int)*pnum);    //without (int) what will be the output??? 
}
```
#WAP TO PRINT THE LARGEST OF THE THREE NUMBERS #
```C
#include<stdio.h>
int main()
{
    int a,b,c,ans;
    int *pa=&a,*pb=&b,*pc=&c;
    printf("enter the three numbers : ");
    scanf("%d%d%d",pa,pb,pc);
    ans=*pa>*pb?(*pa>*pc?*pa:*pc):(*pb>*pc?*pb:*pc);
    printf("\nlargest of the three no's is %d",ans);
}
```
#WAP TO PRINT A CHARACTER ,WRITE ITS ASCII VALUE AND WRITE IT IN UPPER CASE#
```C
#include<stdio.h>
int main()
{
    char ch,*pch=&ch;
    printf("enter the character : ");
    scanf("%c",pch);
    printf("entered character is %c",*pch);
    printf("\nits ascii value is : %d",*pch);
    printf("\nupper case is : %c",*pch-32);
}
```
#WAP TO REVERSE A STRING #
```C
#include<stdio.h>
char *reverse(char *p)
{
    int l,i;
    char t;
    for(l=0;*(p+l)!='\0';l++);
    for(i=0;i<l/2;i++)
    {
        t=*(p+i);
        *(p+i)=*(p+l-1-i);
        *(p+l-1-i)=t;
    }
    return p;
}
int main()
{
    char a[10]="string";
    reverse(a);
    printf("%s",a);
}
```
#WAP TO PRINT THE LENGTH AND REVERSE OF AN ARRAY#
```C
#include<stdio.h>
int length(char *p)
{
    int l;
    for(l=0;*(p+l)!='\0';l++);
    return l;
}
char * reverse(char *p)
{
    int l,i;
    char t;
    for(l=0;*(p+l)!='\0';l++);
    for(i=0;i<l/2;i++)
    {`
            t=*(p+i);
            *(p+i)=*(p+l-1-i);
            *(p+l-1-i)=t;
        }
            return p;
    }
    int main()
    {
        char    A[10]="SWAPPING";
        printf("%d",length("computer"));
        printf("%s",reverse(A));
    }
    
    ```
