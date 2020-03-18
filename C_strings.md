```c
#include<stdio.h>
#include<string.h>
int main()
{
    int i=0;
    char ch[20];
    printf("enter your name : ");
    gets(ch);

    //char ch[5]={'d','e','v','e','s','h','\0'};
    //for(i=0;ch[i]!='\0';i++)
        //printf("%c",ch[i]);
    puts(ch);
}

```
#string related functions#
*strlen()*
*strrev()*
*strlwr()*
*strupr()*
*strcpy()*
*strcmp()*
*strcat()*

#P.1#
```c
#include<stdio.h>
int main()
{
    char str[]="Introduction to C";
    printf("\n|%s|",str);
    printf("\n|%20s|",str);
    printf("\n|%-20s|",str);
    printf("\n|%.4s|",str);
    printf("\n|%20.4s|",str);
    printf("\n|%-20.4s|",str);
}
```
#P.2 INPUT : #
```C
#include<stdio.h>
int main()
{
    char str[]="HELLO";
    for(int i=0;i<5;i++)
        printf("%-5.*s\n",i+1,str);
    for(int i=5;i>0;i--)
        printf("%-5.*s\n",i,str);
}
```
#OUTPUT : #
H
HE
HEL
HELL
HELLO
HELLO
HELL
HEL
HE
H

#P.2 INPUT #
```C
#include<stdio.h>
int main()
{
    char str[]="HELLO";
    for(int i=0;i<5;i++)
        printf("%5.*s\n",i+1,str);
    for(int i=5;i>0;i--)
        printf("%5.*s\n",i,str);
}
```

#OUTPUT#
    H
   HE
  HEL
 HELL
HELLO
HELLO
 HELL
  HEL
   HE
    H

#Use of sprintf() function#
    It is similar to printf() but the difference is that the formatted output is written to a memory area rather than directly to a standard output(screen).
    It is useful in situations when a formatted string in a memory has to be transmitted over a communication channel or to a special device.
    
    #INPUT#
 ```c
  #include<stdio.h>
int main()
{char s1[10],s2[]="c_programming";
sprintf(s1,"output = %s","hello");
puts(s1);
return 0;}
```
#OUTPUT#
output = hello     

#INPUT#
```C
#include<stdio.h>
int main()
{char s1[10],s2[]="c_programming";
sprintf(s1,"output = %s",s2);
puts(s1);
return 0;}
```
#OUTPUT#
output = c_programming 

#INPUT#
```C
#include<stdio.h>
int main()
{char a[100];
int n=10;
sprintf(a,"n =%d",n);
puts(a);}
```
#OUTPUT#
n =10

#Suppressing input#
#SCANSET : A scanset is used to define a set of characters which may be read and assigned to the corresponding string.A scanset is defined by placing the characters inside square brackets prefixed with a %, i.e, %["aeiou"]#

#Using scanf() also we can input space separated and various characters ,by using scanf("%[a-z]",str) .This implies that str can hold the values from a to z#
#If we want to enter the characters from the ascii value 32(i.e.space) and 126(i.e.tild ~) we can use following code snippets #
```c
char  str[100];
    printf("\nenter a string : ");
    scanf("%[ -~]",str);    // space to tild
    printf("\nthe string is : %s",str);
    return 0;
    ```
#If space is  entered inside the square of scanset,it helps us to overcome the problem of termination of string when entering a white space #
#The scanset may also terminate if a field width specification is included and the maximum number of characters that can be read has been reached.i.e, scanf("%10[aeiou]",str); will terminate if 10 characters are entered or a non-vowel character is entered#

    #The sscanf() Function #

    #CODE SNIPPETS from atcoder#
    ```c
    #include<stdio.h>
#include<string.h>
int main()
{char s1[100];
scanf("%s",s1);
//int l=strlen(s1);
for(int i=0;s1[i];i++)  //s[i] in condition ??
printf("x");
return 0;
}
```
        

#STRING CONCATENATION : #
```C
#include<stdio.h>
int main()
{
    char  s1[30],s2[20],s3[60];
    printf("\nenter string one : ");
    gets(s1);
    printf("\nenter string two : ");
    gets(s2);
    int i=0;
    while(s1[i]!='\0')
    {
        s3[i]=s1[i];
        i++;
    }
    int j=0;
    while(s2[j]!='\0')
    {
        s3[i]=s2[j];
        j++;
        i++;
    }
    for(int k=0;k<i;k++)
    {
        printf("%c",s3[k]);
    }
 return 0;
}```
#APPENDING STRINGS#
```C
#include<stdio.h>
int main()
{
    char  s1[30],s2[20],s3[60];
    printf("\nenter SOURCE string : ");
    gets(s2);
    printf("\nenter DESTINATION string : ");
    gets(s1);
    int i=0;
    while(s1[i]!='\0')
    {
        i++;
    }
    int j=0;
    while(s2[j]!='\0')
    {
        s1[i]=s2[j];
        j++;
        i++;
    }
    for(int k=0;k<i;k++)
    {
        printf("%c",s1[k]);
    }
 return 0;
}
```
#COMPARING TWO STRINGS #
```C
#include<stdio.h>
int main()
{
char s1[20],s2[20];
int i,c=0;
printf("enter string 1 : ");
scanf("%s",s1);
printf("\nenter string 2 : ");
scanf("%s",s2);
for(i=0;s1[i]!='\0';i++)
{
    if(s1[i]!=s2[i])
    {
        printf("not equal");
        break;
    }
    else
        c=1;
}
if(c==1)
    printf("equal");

}
```
#COMPARING TWO STRINGS USING USER DEFINED FUNCTION#
```C
#include<stdio.h>
int compare(char[] ,char[]);
int main()
{
    char str1[40],str2[40];
    int ans;
    printf("enter two strings to be compared : ");
    scanf("%s%s",str1,str2);
    ans=compare(str1,str2);
    if(ans==1)
        printf("equal strings");
    else
        printf("unequal strings");
}
int compare(char s1[],char s2[])
{
    int l1,l2,i,c;
    for(i=0;s1[i]!='\0';i++);
    l1=i;
    for(i=0;s2[i]!='\0';i++);
    l2=i;
    if(l1==l2)
    {
        i=0;
        while(s1[i]!='\0')
        {
            if(s1[i]==s2[i])
                c=1;
            else
            {
                return 0;
            }
            i++;
        }
        return 1;
    }
}
```
#EXTRACTING SUBSTRING FROM THE LEFT OF A STRING #
```C
#include<stdio.h>
int main()
{
    char s[20];
    printf("enter the string : ");
    gets(s);
    int n,i;
    printf("\nenter the length upto where the substring is needed : ");
    scanf("%d",&n);
    char sub_s[n];
    for(i=0;i<n;i++)
        sub_s[i]=s[i];
        sub_s[i]='\0';
        printf("\nthe substring required is : \n");
    puts(sub_s);

}
```
#EXTRACTING SUBSTRING FROM THE RIGHT OF A STRING #
```C
#include<stdio.h>
#include<string.h>
int main()
{
    char s[20];
    printf("enter the string : ");
    gets(s);
    int l,n;
    l=strlen(s);
    printf("\nenter the length of the substring required : ");
    scanf("%d",&n);
    char sub_s[n];
    int i=l-n,j=0;
    for(i=l-n;i<l;i++)
    {
        sub_s[j]=s[i];
        printf("\nsub [%d] = %c\n",j,sub_s[j]);
        j++;
    }
    sub_s[j]='\0';
    printf("the required substring is : ");
    puts(sub_s);
}
```
#EXTRACTING A SUBSTRING FROM THE MIDDLE OF A STRING #
```C
#include<stdio.h>
int main()
{
    char s[10];
    printf("enter the main string : ");
    gets(s);
    int f,n;
    printf("\nenter the position from which to start the substring : ");
    scanf("%d",&f);
    printf("\nenter the length of the substring : ");
    scanf("%d",&n);
    int i,j=0;
    char sub_s[n];
    for(i=f;i<f+n;i++)
    {
        sub_s[j]=s[i];
        j++;
    }
    sub_s[j]='\0';
    printf("\nthe required substring is : ");
    puts(sub_s);
}
```
#INSERTION OF A STRING INTO ANOTHER WITHOUT THE USE OF THIRD CHARACTER ARRAY #
```C
#include<stdio.h>
#include<string.h>
int main()
{
    char t[30],s[20];
    int pos,ls,lt;
    printf("enter the main text : ");
    gets(t);
    printf("\nenter the string to be inserted : ");
    gets(s);
    ls=strlen(s);
    lt=strlen(t);
    printf("\nenter the position at which the string has to be inserted : ");
    scanf("%d",&pos);
    int i,j=0;
    for(i=0;i<ls;i++)
    {
        for(j=ls;j>0;j--)
        {
            t[pos+i+j]=t[pos+i+j-1];
        }
    }
    t[lt+ls]='\0';
    printf("\nthe inserted string in the main string is : ");
    for(i=0;i<ls;i++)
    t[pos+i]=s[i];
    //t[pos+2*l]='\0';
    printf("\nthe required string is : ");
    puts(t);

}
```
#REVERSING A STRING USING SWAPPING #
```C

#include<stdio.h>
#include<string.h>
int main()
{char A[30];
printf("enter the string : ");
scanf("%[^\n]s",A);
int l=0,i=0,temp;
while(A[i]!='\0')
{l++;
i++;}
printf("length = %d\n",l);
int j=0;
while(j<l/2)
{
temp=A[j];
A[j]=A[l-1-j];
A[l-1-j]=temp;
j++;
}
printf("reversed string : ");
puts(A);
return 0;
}
```
#STRING MANIPULATION FUNCTIONS#
```C#include<stdio.h>
int main()
{
char str1[50]="programming";
char str2[20]="in c";
strcat(str1,str2);
printf("\n%s",str1);
}
```

#WAP TO READ A SENTENCE UNTIL AN * IS ENTERED AND DISPLAY THE NO. OF CHARACTERS ENTERED #
```C
#include<stdio.h>
#include<string.h>
int main()
{
    char str[100];
    int i=0,j;
    printf("enter a newline character to end : ");
    scanf("%c",&str[i]);
    while(str[i]!='*')
    {
        i++;
        scanf("%c",&str[i]);
    }
    str[i]='\0';
    i++;
    printf("\ntotal no's of characters entered are : %d",i);
    printf("\nthe text is : ");
    for(j=0;j<i;j++)
    {
        printf("%c",str[j]);
    }
}
```
#WAP TO READ MULTIPLE LINES IN A SENTENCE THEN COUNT THE NO. OF WORDS ENTERED#
```C#include<stdio.h>
#include<string.h>
int main()
{
    char str[100];
    int i=0,j,count=1;
    printf("enter a newline character to end : ");
    gets(str);
    i=0;
    while(str[i]!='\0')
    {
        if(str[i]==' '&&str[i+1]!=' ')
              count++;
              i++;
    }

    printf("\ntotal no's of characters entered are : %d",i);
    printf("\ntotal no's of words entered are : %d",count);
    printf("\nthe text is : ");
    puts(str);
}
```
#WAP TO COUNT THE NO. OF LINES ,WORDS AND CHARACTERS ENTERED #
```C
#include<stdio.h>
#include<string.h>
int main()
{
    char str[100];
    int i=0,j,count_line=1,count_words=1,count_char=1;
    printf("enter a * to end : ");
    scanf("%c",&str[i]);
    while(str[i]!='*')
    {
        i++;
        scanf("%c",&str[i]);
    }
    str[i]='\0';
    i=0;
    while(str[i]!='\0')
    {
        if(str[i]=='\n'||i==79)
        {
         count_line++;
         count_words++;
        }
        if(str[i]==' '&&str[i+1]!=' ')
            count_words++;
        count_char++;
        i++;
    }
    printf("\ntotal no's of characters entered are : %d",count_char);
    printf("\ntotal no's of words entered are : %d",count_words);
    printf("\ntotal no's of lines entered are : %d",count_line);
    printf("\nthe text is : ");
    puts(str);
}
```
*OR*
```C
#include<stdio.h>
int main()
{
    int i=0,co_ch=0,co_words=1,co_lines=1;
char str[100];
printf("enter . to stop : ");
scanf("%c",&str[i]);
while(str[i]!='.')
{
i++;
scanf("%c",&str[i]);
}
i=0;
while(str[i]!='.')
{
    if(str[i]!='\n')
co_ch++;
if((str[i]==' '||str[i]=='\n'))
co_words++;
if(str[i]=='\n')
co_lines++;
i++;
}

printf("\nthe total no. of characters in the above text are %d",co_ch);
printf("\nthe total no. of words in the above text are %d",co_words);
printf("\nthe total no. of lines in the above text are %d",co_lines);
}
```
#WAP TO COPY n CHARACTERS FROM mTH POSITION IN ANOTHER STRING#
```C
#include<stdio.h>
int main()
{
    char m_s[100],s_s[50];
    int m,n;
    //printf("enter the main string: ");
    //gets(m_s);
    printf("\nenter the string to be copied : ");
    gets(s_s);
    printf("\nenter the position from where the characters has to be copied : ");
    scanf("%d",&m);
    printf("\nenter the no. of characters to be copied : \n");
    scanf("%d",&n);
    int i=m,j=0;
    while(i<m+n)
    {
        m_s[j]=s_s[i];
        j++;
        i++;
           }
        m_s[j]='\0';
    printf("\nthe required string is : ");
    puts(m_s);
}
```
#WAP TO REPLACE COMMAS WITH A SEMICOLON#
```C
#include<stdio.h>
int main()
{
    char str[30];
    printf("enter the text : ");
    gets(str);
    int i=0;
    while(str[i]!='\0')
    {
        if(str[i]==',')
        str[i]=';';
        i++;
    }
    printf("\nthe required text is : ");
    puts(str);
}
```
#WAP TO ENTER A TEXT THAT CONTAINS MULTIPLE LINES. REWRITE THIS TEXT BY PRINTING LINE NUMBERS BEFORE THE TEXT OF THE LINE STARTS.#
```C#include<stdio.h>
int main()
{
    printf("enter * to end ");
    char s[100];
    int i=0,count_line=1;
    scanf("%c",&s[i]);
    while(s[i]!='*')
    {   i++;
        if(s[i-1]=='\n')
        {
            count_line++;
            s[i]=count_line;
            i++;
        }
        scanf("%c",&s[i]);
    }
    s[i]='\0';
    printf("1\t");
    i=0;
    while(s[i]!='\0')
    {
        if(s[i-1]=='\n')
        {
         printf("%d\t",s[i]);
         i++;
        }
        printf("%c",s[i]);
        i++;
    }
}
```

#WAP TO SORT THE STRINGS IN A STRING ARRAY #
```C
#include<stdio.h>
#include<string.h>
int main()
{
    int n,i,j;
    scanf("%d",&n);
    char str[n][10],temp[10];
    for(i=0;i<n;i++)
    {
        scanf("%s",str[i]);
    }
    for(i=0;i<n;i++)
    {
        for(j=0;j<n-1;j++)
        {
            if(strcmp(str[j],str[j+1])>0)
            {
                strcpy(temp,str[j]);
                strcpy(str[j],str[j+1]);
                strcpy(str[j+1],temp);
            }
        }
    }
    printf("\0sorted strings : ");
    for(i=0;i<n;i++)
        printf("%s\n",str[i]);
}
```

#WAP TO PRINT THE NO. OF OCCURENCES OF EACH CHARACTER IN A TEXT#
```C
#include<stdio.h>
int main()
{
    char str[100];
    int i=0,j,l,c=0;
    gets(str);
    l=strlen(str);
    while(str[i]!='\0')
    {
        if(str[i]==' ')
        {
            i++;
            continue;
        }
        for(j=0;j<l;j++)
        {
        if(str[j]==str[i])
        {
            if(i>j)
                break;
            else
                c++;
        }
        }
        if(c!=0)
        {
         printf("%c comes %d times\n",str[i],c);
        }
        c=0;
        i++;
        }
}
```