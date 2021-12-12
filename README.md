# CONST keyword usage in C++:

## 1-with variables

to make constant variables whose values cannot be changed and they must be initialized in declaration 
Ex:
~~~cpp  
int main
{
    const int x = 1;
    x++;     //  Compile time error   
}

~~~

## 2-with pointers 

pointers can be declared using const keyword in two ways
 
### a)pointer to a const variable
Ex:
~~~cpp 
const int* ptr;
~~~
or
~~~cpp 
int const* ptr;
~~~
here ptr is a pointer that can point to a const int type variable 


### b)const pointer

by placing the const keyword to the right of the astrisk *
Ex:
~~~cpp 
int x=5;
int* const ptr=&x;
~~~
here ptr only and always points to the variable x of type int and it can change the value of x but the pointer itself cannot be changed(always points to the same address)

### c)const pointer of a const variable 
Ex:
~~~cpp 
const int* const ptr;
~~~
neither the value of the variable that ptr points to nor the pointer itself can be changed 


## 3-with class data member

it is initialized with each object using constructor and once initialized it cannot be changed


## 4-with class object

declaring an object as const means that its data members cannot be changed

EX:
~~~cpp 
class Test
{
    const int i;
    public:
    Test(int x):i(x)
    {
        cout << i;
    }
};

int main()
{        
        Test t2(10);  //i is initialized in constructor//point 3
  const Test t(20);  // i can never be changed after being initialized //point 4
   
} 

~~~

## 5-with class's member function

const member function cannot modify any data member in an object

EX:
~~~cpp 
class GPA
{
public:
   Degree(string name, int gpa);
   string getname() const;     //function can't modify an object
   void setGPA( int x );     // A write function; can't be const

private:
int gpa;
string name;
};

string GPA::getname() const
{
   return name;        // Doesn't modify anything
}
void GPA::setGPA( int x )
{
   gpa = x;          // Modifies data member
}
int main()
{
   GPA student1( "maha", 4 );
   const GPA student2( "hossam", 2.8 );
   student1.setGPA( 3.8 );    // Okay
   student2.getname();       // Okay
   student2.setGPA( 3.3 );  //  Error
}
~~~

## 6-with functions arguments and return types:-

Used to make the return type or arguments of a function as const.

Ex:
~~~cpp 
const int f1()
{
return 1;
}

~~~

# Ampersand (&) usage in C++:


## 1-declare a reference
 
using & in the left hand side of the declared variable means that you expect to have a reference to the declared type

Ex:
~~~cpp 
int x=5;
int& y=x;
~~~
this means that y is the reference of x (points to its address)

## 2-get address of a variable 

#### -using & in the right hand side in a variable declaration make this variable a pointer and & is known as address operator
Ex:
~~~cpp 
int x=1;
int* ptr=&x;
~~~
#### -using & in front of a variable will return the address of the variable
Ex:
~~~cpp 
int x=1;
std::cout<<&x;      //print address of x
~~~
## 3-a bitwise operator
it is an infix operator taking two numbers as inputs and doing an AND on each of the bit pairs of the inputs.

Ex:
~~~cpp 
int a = 15;     //001111 (In Binary)
int b = 10;    //001010 (In Binary)
cout << ( a & b );  // prints 10 which is 001010 (In Binary)
~~~
