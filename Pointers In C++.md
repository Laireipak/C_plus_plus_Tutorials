
 ## Pointers and References in C++

   &emsp; Ngacgi tutorial asida **Pointer** amasung **References** ki  matangd mayek sengna neinagani. Pointer amasung reference hairiba terms ani asi mayek sengna khangdragd yamna confuse chatpa yaba topic singgi manungda amani. Aduna, *let's get started*.

***
>Note: Tutorial asi paraga adom adom na henna vab tanabagi damk **practice** twbiyu.

___
+	***Pointer Hybac Karino ?***
		-	`Pointer:` `A variable whose value is an  address of another variable or a function`
		-	*Variable:* `karigumba khar pairg thmaba yaba memorygi saruk`

&nbsp; ***Pointer** haibasi atopa variable nttrag function gi memory address na maggi **Value** oiba variable amani*

---
**Pointers gi Magunsing (Properties)**
1.	 *Pointers* singi magi **type** leigani
2.	 Oiba yaba **types** singdi : `[int] [char] [string] [float] [double] [vector]` asina chingbani.
3.	 **' * '** - **asterick** *asibu karigumba matng amadna **Reference operator** oina siginaba yai karigumba matng amadna **De-reference operator** oina siginnaba yai*

---
**Example of variable and Pointer :**
```c++
// variable 'x' is declared & initialsed to '10'
int x=10;
// non-initialised pointer declaration
int *ptr; //this pointer holds a grabage value 
// initialised pointer declaration
int *b_ptr{0};// points to null


```
**`Use of Pointers:`**
`1.We can access variable or functions using pointers `
`2.Pointers can be used to operate on arrays`
`3.Dynamically allocate memory on the heap or free store`
`4.Can access specific address in memory`
`	--so it is useful in embedded and system a pplications`


---
### 2. Storing and Accessing Pointer Address
**Address Operator**:
`&`-address operator  haina khangnei 
`&`- unary operator amani habadi *operand ama* khaktad act twgni
```c++
// using address operator to access memory address
int age=39;
cout<<"Memory address :"<<&age; //0efcd82
// computer gi memory hexadecimal da represent twee
```
**Accessing Pointer Address**
*Recap:* `pointer c memory address store twba variable amani`
> Note: Pointer declaration twba matmd  *garbage value*
> nattba amad initialised twbiyu  *null pointer* d chtnabi oina initialised twnei. **Masina thokhaningdba errors singdgi kanba ngamgni**
```c++
// declaring a pointer
int *int_ptr{nullptr};
// 'int_ptr' kwba pointer variable ama declare twkhre amasung null pointerd initilsed twkhre
cout<<"Value of int_ptr:"<<int_ptr<<endl;// 0
// int_ptr pointer asina karigumba mapham amd thindb pointer amad lwsinkhibnina magi value '0' oigani
cout<<"Address of int_ptr:"<<&int_ptr<<endl;//0xfc34de
// pointer gi memory address
cout<<"Size of int_ptr"<<sizeof int_ptr;//4
```
**Storing Memory Address**
```c++
int x=19; // variable declaration
int *p; //pointer holding garbage value "0d4dfe"
p=&x; // storing address of 'x'
cout<<"Address of x:"<<&x<<endl;//02xfde8;
cout<<"Value of p:"<<p<<endl; //02xfde8;
cout<<"Address of p:"<<&p<<endl;//ef0xf34;
```
***Mathkki example asi neinac:***
`'x'- variable amani magi value '19'`
`'p'-garbage value hybd (memory gi jaga ama hek tagi addresski value) hold twba pointer amani`
`'&x'- 'x' ki memory address '02xfde8' ni`
`'p=&x'-'p' d 'x' ki memory address hapchinkhre`

---
### 3. De-referencing a Pointer
*Dereferencing operator*- * asi pointer n point twriba variable nttrag function adugi magi value access twbad siginngni.
**Code Example**
```C++
double temperature{109.6};
double temp_ptr{&temperature};
//  upto this so far so good, right :)
// akhoi na temp_ptr siginnrg temperature gi 
//value access twge hyrgd '*' singingni
cout<<"Value of temperature: "<<temperature<<endl;
cout<<"Value of temp_ptr:"<<temp_ptr<<endl;
cout<<"Access temperature value with temp_ptr<<*temp_ptr<<endl;
``` 
**Output**
`Value of temperature:109.6`
`Value of temp_ptr:0xcfde8`
`Access temperature value with temp_ptr:109.6`


Makha tana lemhouriba Topics sing asigi marmd henna khangnbagi dmk Youtube channel d yengbiro:
`dynamic memory allocation`&emsp;
`arrays and pointers`&emsp;
`pointer arithmetic`&emsp;
`const and pointers`&emsp;
`passing and returning pointers to functions`&emsp;
`pointer pitfalls`&emsp;
`Reference and l-value and r-value`&emsp;


---
**Codes Used In My Youtube Channel**
```C++
#include <iostream>
using namespace std;

//pointer
int *largest(int*,int*);
int main() {
  int x=193;
  int *ptr=0;
  cout<<"Address of x: "<<&x<<endl;
  cout<<"Value of Pointer ptr: "<<ptr<<endl;
  cout<<"Address of ptr: "<<&ptr<<endl;
  cout<<"After assigning :"<<endl;
  ptr=&x;
  cout<<"Value of pointer ptr: "<<ptr<<endl;
  // dereferencing pointers
  int high_temp{95};
  int *h_ptr=&high_temp;
  cout<<"Value of h_ptr:"<<h_ptr<<endl;
  cout<<"Dereferenced pointer value{h_ptr} :"<<*h_ptr<<endl;

  // dynamic memory allocation
  cout<<"------------------------------"<<endl;
int *p{nullptr};
  cout<<"Before"<<endl;
  cout<<" Value of p:"<<p<<endl;
  cout<<"After"<<endl;
  p=new int;
  cout<<"Value of p:"<<p<<endl;
delete p;
// array allocation 
  int *arr_ptr{nullptr};
  arr_ptr=new int[10];
  cout<<"Value of arr_ptr:"<<arr_ptr<<endl;
  cout<<arr_ptr+1<<endl;
  cout<<arr_ptr+2<<endl;
  cout<<arr_ptr+3<<endl;
  delete [] arr_ptr;
  cout<<"Deleted "<<endl;
// arrays and pointers
  int arr[5]{45,86,94,23,10};
  cout<<"Arrays and Pointers"<<endl;
  cout<<"First element : "<<arr[0]<<endl;// subscript notation
  cout<<arr<<endl;// address of the first element
  cout<<(arr+1)<<endl;// address of the second element
  cout<<(arr+2)<<endl;// address of the third element
  // offset notation
  int *a_ptr{arr};// assign memory address of the first element of the array
  cout<<"Pointers using array"<<endl;
  cout<<a_ptr+1<<endl;
  cout<<*a_ptr<<endl; 
  cout<<a_ptr[1]<<endl;//86

  // pointer arithmetic
  // ++
  // --
  // + -
  int ages[4]{42,25,23,56};
  int *x_ptr{ages};
while(*x_ptr!=56){
  cout<<"Age : "<<*x_ptr<<endl;
  x_ptr++;
}
  int t=90;
  int d=70;
  int *y_ptr{&t};
  int *z_ptr{&t};
  cout<<"Address of y:"<<y_ptr<<endl;
  cout<<"Address of z:"<<z_ptr<<endl;
  cout<<"Addition:"<<y_ptr+12<<endl;
  cout<<"Is equal :"<<(y_ptr==z_ptr)<<endl;

  // const and pointer
  int ty=189;
  int uy=788;
  
  // const int *c_ptr{&ty};
  // int *const c_ptr{&ty};
  const int *const c_ptr{&ty};
  cout<<"Before update:"<<ty<<endl;
  cout<<"Pointer:"<<*c_ptr<<endl;
  // *c_ptr=456;// error
  // c_ptr=&uy; // ok
  cout<<"After update:"<<ty<<endl;
  cout<<"Pointer"<<*c_ptr<<endl;
  
  // passing and return pointers in functions
 int num1=589;
  int num2=670;
  
int *res{nullptr};
  res=largest(&num1,&num2);
  cout<<"Address of num1 and num2:"<<&num1<<" : "<<&num2<<endl;
  cout<<"Larger value is :"<<res<<endl;
  
  return 0;
}   

int *largest(int *x,int *y){
  int *l{nullptr};
  if(*x>*y)l=x;
  l=y;
  return l;
}
```

 

***Pls Subscribe to My Youtube Channel:***
[Laireipak Coding Camp][2].

[2]:https://www.youtube.com/channel/UC_q7L6OcumcniSqvvYs21Lw 
