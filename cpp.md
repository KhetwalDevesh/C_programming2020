# First c++ program #
```c++
include<iostream>
int main()
{
	std::cout<<"hello world\n";
	return 0;
}
```
# C++ Data types#
* PRIMITIVE : These data types are built-in or predefined data types and can be used directly by the user to declare variables.e.g.:int ,char,float,bool,etc.
* ABSTRACT : These data types are defined by user itself.Like,defining a class in C++ or a structure.
# PRIMITIVE DATA TYPES #
* Int : Keyword used for integer data types is int.Integers typically requires 4 bytes of memory space and ranges from -2147483648 to 2147483647.
* Char : character data types is used for storing characters.
* Boolean : boolean data type is used for storing boolean or logical value.
* Float : Floating point data type is used for storing single precision floating point values or decimal values.
* Void : Void means not any value ,void datatype represents a valueless entity .Void data type is used for those function which does not returns a value.

# DATATYPE MODIFIERS #
# They are used with the built-in data types to modify the length of data that a particular data type can hold. Data type modifiers available in C++ are : #
## 1.Signed ##
## 2.Unsigned ##
## 3.Short ##
## 4.Long ##

# We can find their size using the following code snippets in c++#
```c++
//#include<bits/stdc++.h>
#include<iostream>
using namespace std;
int main()
{
    cout<<"size of char is "<<sizeof(char)<<" bytes\n";
    cout<<"size of long int is "<<sizeof(long int)<<" bytes\n";
    cout<<"size of short int is "<<sizeof(short int)<<" bytes\n";
    return 0;
}
```
# OUTPUT #
 	size of char is 1 bytes
 	size of long int is 4 bytes 
 	size of short int is 2 bytes
 * <h2 using namespace > is used to avoid the practice of using <h2 std::cout>
 	
 # BASIC I/P AND O/P FOR C++#
 <h1 HEADER FILES >
 <h2 * iostream ,iomanip,fstream >
 	```c++
 	#include<iostream>
using namespace std;
int main()
{
    int age;
    cout<<"enter your age : ";
    cin>>age;
    cout<<"the age is "<<age<<"";
    return 0;
}
```
 
```c++
#include<iostream>
using namespace std;
int main()
{
    cerr<<"it shows unbuffered error";
    clog<<"\nit shows buffered error";
    return 0;
}
```
* cerr : standard unbuffered stream,used for instantly displaying the error .It does'nt have any buffer to store the error message and display later.
* clog : standard buffered stream,unlike cerr the error is first inserted into a buffer and  is stored in the buffer until it is not fully filled.

<h1 OPERATORS IN C++>
	*ARITHMETIC OPERATORS
		* Unary : ++,--
        * Binary : +,-,/,*
        ```c++
        #include<iostream>
using namespace std;
int main()
{
    int a=1,b=2;
    a++;
    cout<<"The value of a is increased to "<<a<<"";
    b--;
    cout<<"\nThe value of b is decreased to "<<b<<"";
    cout<<"\nSum of a and b is "<<a+b<<"";
    return 0;
}
```
    * RELATIONAL OPERATORS
        [==,<=,>=,<,>]
        ```c++
        #include<iostream>
        using namespace std;
        int main()
        {
            int a=1,b=2,c=1;
            cout<<"is a equal to b : "<<(a==b)<<"";
            cout<<"\nis a equal to c : "<<(a==c)<<"";
        }
```
    * LOGICAL OPERATORS
        [and,or,not]
        ```c++
        #include<iostream>
using namespace std;
int main()
{
    bool a=true,b=false;
    cout<<"a and b is : "<<(a&&b)<<"\n";
    cout<<"a or b is : "<<(a||b)<<"";
    return 0;
}
```
    * ASSIGNMENT OPERATORS
        [=,+=,-=,/=,*=]

<h1 LOOPS IN C++ >
    1.while loop(entry control)
        ```c++
        #include<iostream>
using namespace std;
int main()
{
    int a=1;
    while(a<=10)
    {
        cout<<"hello!\n";
        a++;
    }
    return 0;
}
```
    2.for loop(entry control)
     ```c++
     #include<iostream>
using namespace std;
int main()
{
    int a;
    for(a=1;a<=10;a++)
    {
        cout<<"hello!\n";
    }
    return 0;
}
```
    3.do-while loop
    ```c++
    #include<iostream>
using namespace std;
int main()
{
    int a=2;
    do
    {
        cout<<"hello!\n";
        a++;
    }
    while(a<=1);
    return 0;
}
```
<h1 DECISION STATEMENTS >
    1.if(condition)
    ```c++
    #include<iostream>
using namespace std;
int main()
{
    int a=1;
        if(a<3)
        {
        cout<<"hello!\n";
        }
    return 0;
    }

```
    2.else(condition)
    ```c++
    #include<iostream>
using namespace std;
int main()
{
    int a=1;
        if(a<3)
        {
        cout<<"hello!\n";
        }
        else
        {
        cout<<"hello world";
        }
    return 0;
    }

```

        <h1 SWITCH STATEMENTS IN C++>
```c++
#include<iostream>
using namespace std;
int main()
{
    int a=1,b=2,ch;
    cin>>ch;
    switch(ch)
    {
     case(1):
     cout<<(a+b)<<"";
     break;
     case(2):
     cout<<(a-b)<<"";
     break;
     case(3):
     cout<<(a*b)<<"";
     break;
     default:
     cout<<"exit";
    }
    return 0;
    }

```
    < h1 FUNCTIONS IN C++>
```c++
#include<iostream>
using namespace std;
int fun(int,int);
int main()
{
    int n1,n2,var;
    cout<<"enter the no's : \n";
    cin>>n1;
    cin>>n2;
    var=fun(n1,n2);
    if(var==0)
    {
        cout<<n1;
    }
    else
    {
        cout<<n2;
    }
}
fun(int a,int b)
{
    if(a>b)
        return 0;
    else
        return 1;
}

```


