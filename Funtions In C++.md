**Welcome everyone to `Laireipak Coding Camp`** 
---
*I hope you will enjoy  reading this **tutorial**.*

---

## Functions In C++
**Function:** `A function is a block of code that performs a specific task.`
***Example:***
1. a function to draw the circle
2. a function to color the circle

Two types of *function*:

1.  **Standard Library Functions:**  Predefined in C++
2.  **User-defined Function:**  Created by users

**C++ User-defined Function**
---
*A `user-defined function` groups code to perform a specific task and that group of code is given a name (identifier)*

The syntax to declare a function is:
```C++
returnType functionName (parameter1, parameter2,...) {
    // function body   
}
```
### Function Example:
---
```c++
// function declaration
void greet() {
    cout << "Hello World";
}
```

Here,

-   the name of the function is  `greet()`
-   the return type of the function is  `void`
-   the empty parentheses mean it doesn't have any parameters
-   the function body is written inside  `{}`
#### Calling A Function
Here's how we can call the above  `greet()`  function.

```C++
int main() {
     
    // calling a function   
    greet(); 

}
```

## Overloading Functions

>C++ **allows specification of more than one function of the same name in the same scope**


### Example Code :
***1: Overloading Using Different Types of Parameter***

```C++
// Program to compute absolute value
// Works for both int and float

#include <iostream>
using namespace std;

// function with float type parameter
float absolute(float var){
    if (var < 0.0)
        var = -var;
    return var;
}

// function with int type parameter
int absolute(int var) {
     if (var < 0)
         var = -var;
    return var;
}

int main() {
    
    // call function with int type parameter
    cout << "Absolute value of -5 = " << absolute(-5) << endl;

    // call function with float type parameter
    cout << "Absolute value of 5.5 = " << absolute(5.5f) << endl;
    return 0;
}
```

**Output**

`Absolute value of -5 = 5`
`Absolute value of 5.5 = 5.5`


***2: Overloading Using Different Number of Parameters***

```C++
#include <iostream>
using namespace std;

// function with 2 parameters
void display(int var1, double var2) {
    cout << "Integer number: " << var1;
    cout << " and double number: " << var2 << endl;
}

// function with double type single parameter
void display(double var) {
    cout << "Double number: " << var << endl;
}

// function with int type single parameter
void display(int var) {
    cout << "Integer number: " << var << endl;
}

int main() {

    int a = 5;
    double b = 5.5;

    // call function with int type parameter
    display(a);

    // call function with double type parameter
    display(b);

    // call function with 2 parameters
    display(a, b);

    return 0;
}
```

**Output**

`Integer number: 5`
`Float number: 5.5`
`nteger number: 5 and double number: 5.5`





**Code Used In My Youtube channel**
---
*It's all ``mixed up`` **: )** I will make it better next time. Also I can't find some of it too **:{***

***Passing Arrays In Functions***
```c++
#include<iostream>
using namespace std;
// passing arrays
double avg(double arr[],int size); // function prototype
int main(){
  cout<<"Passing Arrays"<<endl;
  double arry[]{45.5,78.4,963,78.4,75.1,45.78};
  int s;
  // inbuilt function
  s=sizeof(arry)/sizeof(arry[0]);
  cout<<"Size of the array :"<<s<<endl;
  cout<<"Average : "<<avg(arry,s)<<endl;
  
  return 0;
}

double avg(double arr[],int size){
  double total=0;
  for(int i=0;i<size;i++){
    total=total+arr[i];
  }
  return total/size;
}
```

***Scope Rules***
```C++
#include<iostream>
using namespace std;
// scope rules
// local scope and global scope
int num1=100;
int main(){
  int num1=90;
  cout<<num1<<endl;
  {
    // int num1=45;
    cout<<num1<<endl;
  }
  return 0;
}
```
***Recursive Function***
```c++
#include<iostream>
using namespace std;
// inline function --> function overhead
// inline void sum(){
//   // statements --2s
// }
// switch time> function execution time
  // sum(); --> 4s

// recursive function
// function calling itself
// 1. base case -- stop condition
// 
// 3!=1*2*3
// 4!=3!*4
// n!=(n-1)!*n;
int factorial(int n){
  // base case
  if(n==0 || n==1)return 1;
  return n*factorial(n-1);
}

int main(){
  int num=10;
  cout<<"Factorial of 10 : "<<factorial(num)<<endl;
  return 0;
}
```
---
###  &emsp; &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;The End !
---


***Pls Subscribe to My Youtube Channel:***
[Laireipak Coding Camp][2].

[2]:https://www.youtube.com/channel/UC_q7L6OcumcniSqvvYs21Lw 
