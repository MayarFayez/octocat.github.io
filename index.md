List all possible usage of const keyword:

const keyword is attached with any method(),variable,pointer variable,and with the object of a class it prevents that 
specific object / method() / variable to modify its data items value.

1)constant variables:

rules for declaration and initialization of the constant variables:

const  datatype  name = value ;

Example:
```
// C++ program to demonstrate the
// the above concept
#include <iostream>
using namespace std;

// Driver Code
int main()
{

    // const int x;  CTE error
    // x = 9;   CTE error
    const int y = 10;
    cout << y;
}
```
```ruby
output: 10
```

2)const keyword with pointer variables:

there are 3 possible ways to use  const keyword with pointer

a)when the pointer variable point to a const value:

syntax: const datatype* var_name ;

Example:
```
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int x=10 ;
    char y= 'M' ;

    const int* i = &x;
    const char* j = &y;
 
    // Value of x and y can be altered,
    // they are not constant variables
    x = 9;
    y = 'A';
 
    // Change of constant values because,
    // i and j are pointing to const-int
    // & const-char type value
    // *i = 6;
    // *j = 7;
 
    cout << *i << " " << *j;
}
```
```ruby
output: 9 A
```

b)when the const pointer variable point to the value:

syntax: datatype* const var_name ;

Example:
```
#include <iostream>
using namespace std;

// Driver Code
int main()
{
// x and z non-const var
int x = 5;
int z = 6;

    // y and p non-const var
    char y = 'A';
    char p = 'C';
 
    // const pointer(i) pointing
    // to the var x's location
    int* const i = &x;
 
    // const pointer(j) pointing
    // to the var y's location
    char* const j = &y;
 
 
    // The values that is stored at the memory location can modified
    // even if we modify it through the pointer itself
    // No CTE error
    *i = 10;
    *j = 'D';
 
    // CTE because pointer variable
    // is const type so the address
    // pointed by the pointer variables
    // can't be changed
    // *i = &z;
    // *j = &p;
 
    cout << *i << " and " << *j
        << endl;
    cout << i << " and " << j;

}
```
```ruby
output:
9 and M
0x7ffd1ff8f830 and MC
```
c)when const pointer pointing to const variable:

syntax: const datatype* const var_name ;

Example:
```
#include <iostream>
using namespace std;

// Driver code
int main()
{
int x= 9 ;

    const int* const i = &x;
   
    // *i=10;  
    // The above statement will give CTE
    // Once Ptr(*i) value is
    // assigned, later it can't
    // be modified(Error)
 
    char y{ 'A' };
 
    const char* const j = &y;
   
    // *j='B';
    // The above statement will give CTE
    // Once Ptr(*j) value is
    // assigned, later it can't
    // be modified(Error)
 
    cout << *i << " and " << *j;

}
```
```ruby
output: 9 and A
```

3)constant methods:

syntax: const  class_name  object_name ;

there are 2 ways of constant function declaration:
```ruby
ordinary  const-function declaration:                           A const member function of the class:
const void foo(){                                               class {
// void foo()  const Not valid                                   void foo() const
}                                                                {//...........
int main(){                                                         }
foo(x); }                                                           }
```

constant function parameters and return type:

a) for parameters:

Example:
```
#include <iostream>
using namespace std;

// Function foo() with variable
// const int
void foo(const int y)
{
// y = 6; const value
// can't be change
cout << y;
}

// Function foo() with variable int
void foo1(int y)
{
// Non-const value can be change
y = 5;
cout << '\n'
<< y;
}

// Driver Code
int main()
{
int x = 9;
const int z = 10;

    foo(z);
    foo1(x);
}
```
```ruby
output:
10
5
```


b)for return type:

Example:
```
#include <iostream>
using namespace std;

const int foo(int y)
{
y--;
return y;
}

int main()
{
int x = 9;
const int z = 10;
cout << foo(x) << '\n'
<< foo(z);

    
}
```
```
output:
8
9
```

c)for const parameters and const return type:

Example:
```
#include <iostream>
using namespace std;

const int foo(const int y)
{
// y = 9; it'll give CTE error as
// y is const var its value can't
// be change
return y;
}

// Driver code
int main()
{
int x = 9;
const int z = 10;
cout << foo(x) << '\n'
<< foo(z);
}
```
```
output:
9
10
```

4)Defining class Data members as const:

These are data variables in class which are defined using const keyword. They are not initialized during declaration. 
Their initialization is done in the constructor.

Example:
```
class Test
{
const int i;
public:
Test(int x):i(x)
{
cout << "\ni value set: " << i;
}
};

int main()
{
Test t(10);
Test s(20);
}
```


5)Defining class object as const:
syntax: const class_name object;
```
 const Test r(30);                              //following the previous example
 ```


6)Defining class's member function as const:

A const member functions never modifies data members in an object.

syntax: return_type function_name() const;

Example:
```
class StarWars
{
public:
int i;
StarWars(int x)    // constructor
{
i = x;
}

    int falcon() const  // constant function
    { 
        /* 
            can do anything but will not
            modify any data members
        */
        cout << "Falcon has left the Base";
    }

    int gamma()
    { 
        i++; 
    }
};

int main()
{
StarWars objOne(10);        // non const object
const StarWars objTwo(20);      // const object

    objOne.falcon();     // No error
    objTwo.falcon();     // No error

    cout << objOne.i << objTwo.i;

    objOne.gamma();     // No error
    objTwo.gamma();     // Compile time error
}
```

List all possible usage of & operator:

The & symbol is used as an operator in c++ . It is used in 2 different places , one as a bitwise and operator and one as
a pointer address of operator.

Bitwise AND (&):

compares each bit of the first operand to that bit of the second operand. 
if both bits are 1, the bit is set to 1.otherwise,the bit is set to 0.
Both operands to the bitwise AND operator must be of integral types .

Example:
```
#include <iostream>
using namespace std;
int main(){
unsigned short a=0x5555;  //pattern 0101....
unsigned short b=0xAAAA;  //pattern 1010....
cout<<hex<<(a&b)<< endl;
} 
```
```
Output:   0
```
Address of operator:

The address of operator(&), and it is the complement of * .it is  a unary operator that returns the address of the 
variable(r_value)specified by its operand.

Example:
```
#include <iostream>
using namespace std;
int main()
           { int var;
            int*ptr;
            int val;
            var=3000;
            ptr=&var;      //take the address of var
            val=*ptr;      //take the value available at ptr
           cout<<"value of var:"<<var<<endl;
           cout<<"value of ptr:"<<ptr<<endl;
           cout<<"value of val:"<<val<<endl;
    }
 ```
 ```
Output:
value of var:3000
value of ptr:0xbff64494
value of val:3000
```
