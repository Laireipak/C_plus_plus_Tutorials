
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
*Dereferencing operator*- $*$ asi pointer n point twriba variable nttrag function adugi magi value access twbad siginngni.
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

***Subscribe to My Youtube Channel:***
![Youtube-channel](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAkGBw0QDQ0NDxAPDg0ODQ4ODxAPDQ8ODw4QFREXFhUSExUYHS0iGBolGxMTIjEhJSkrLi46Fx8/PzMsOCgtOisBCgoKDg0OGhAQGTUmICUtLy8tLS0yLS8vLS01Ly0vKy0uLS0tKy0tKy0vLS0tLS0vLS0tLSstLS0tLS0tKy0tLf/AABEIAOEA4QMBEQACEQEDEQH/xAAcAAEAAQUBAQAAAAAAAAAAAAAABwEDBAUGCAL/xABHEAACAgEBAggGDgcJAAAAAAAAAQIDBBEFBwYSITFBUWFxcoGRscHCExQiIzJCUlN0kqGi0dIlNVRigoOyJDNDY2Rzk6Pi/8QAGwEBAAIDAQEAAAAAAAAAAAAAAAEFAgQGAwf/xAA5EQEAAQMBAggNBAIDAAAAAAAAAQIDBBEGUQUSFCExQZGhFiIzNFJTYXGBscHR4SMyQnJighPw8f/aAAwDAQACEQMRAD8AnEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABTUCoAAAAAAAAAAAAAAFGBqdr8JMDEemRkV1y014mrnZp18SOr+w8q7tFHTLcxsDJyfJUTPt6u3oc7k70NmR+Asi3tjUor70keM5tuPatbezObV06R75+2rBt3s43xMW6XhTrh5tTCc6nqhs07KZHXXHexJ73JfFwl/Flf+DDl+6l707J1fyu935Wpb2rujDrXffJ+qRy+fRekbJU+tns/K3LexldGLSu+c2Ry+rcyjZO16yeyFt7183ox8b/ALH6Ry+rcy8E7PrJ7ny962f0U4v1bfzkcvq3J8FLHrJ7lFvWz/mcX6tv5xy6rcnwUsesnufa3r53TRjeL2VesOXVbmPgpY9ZPc+472MrpxqH/HYieX1bkTsna9ZPZC7He1f04lb7rpL1SeXz6LCdkqOq7PZ+VyG9ufThR8WS/wAhMZ++lhVsl6N3u/LKq3tUfHxLY+DbCfnSMuX07nhVspf6rkd7No3p7Ok9JV5Nfa665L7JGdObba9zZfMp/bMT8fvDebL4ZbMyZKFWTBTb0ULFKmTfUuOlq+49qb9uvolW5HBOZjxrXbnTfHP8m/1PZXKgAAAAAAAAAACjAj7eRwznjf2LFlxchxTusXK6YvmjHqm1y69C06+TSysjieLT0um4B4GjJ/XvR4kdEb/wiOcm25NuUpNuTbbbb5230sq5mZ6XeUURREREcyhD0AAAAAAAAAAAAAAAAYykDd3w1sqtrwsqbnj2NQqsm25UyfJGLb54N8nZydHNv42TMTxKuhyfDvAlFVE5FiNJjnmI643+9LyLNw6oAAAAAAAAABbusUYym+SMYuT7ElqxqmmmapiI63m3aWbLIvuyJ68a6yVj1eunGeqXiWi8RQXKuNVMvrmJYixZpt09UMYwbIAAAAAAAAAAAAAAAAAUYYzGr0NwO2g8nZ2JfJ8acqlGb65w9xJ+WLL2zXx6Il8o4Sx/+DKuW46Inu6W6PVpAAAAAAAAADTcMsh17MzprkaxbUu+UeKvtZ53p0omfY3eDrf/ACZdun/KHnkoX1gCQAAAAAAAAAAAAAAAAABEpn3Q5HG2ZKHzWTbHxNRn55Mt8KrW2+d7TW+Lm674iXcG254AAAAAAAAAcrvOt4ux8r950w8t0DXyp/SlccA08bPt/H5SgopX00CQAAAAAiUhVbu1k7OxMvFs4l9mPXOddjfsdkmuVxlzxflXcWHI4qoiqnpch4R12Mmu1ejWmJmImOmPu4baOzsjGsdWRVOmxfFkuddcXzSXatUaVduqidKodNjZdrIo49qrWGMYNkCQAAAAAAAIStuWs94zofJuqn9aDXqFpgz4sw4XaujS9bq3xPd/6kk3nKAAAAAAAAADjN7UtNkyXysihfe19Bq5nkl9s5TrnU+yJQmU76OBIAAAAAQ9B8CP1VgfRavMXtnydPufKOE/O7v9p+bO2rsnGyqnTkVRtg+bjLli+uMlyxfajKuimqNKoeGPk3cevj2qtJRfwm3Z31ca3Cbvr53TJpXRX7r5pryPvK+9hTHPQ7Hg7aaivSjJjSfS6vjucBZXKMnCUXGUXpKMouMovqafMaMxMc0uqouU108amdYfJDMCQAAAAAhJm5SXu9oR644z8jt/EscD+TjNrY8lP9volMsXGgAAAAAAAADh98D/AEZDty6l9yb9BqZvk/i6LZjz3/WfohgqH0MCQAAAAAPQfAj9VbP+i1eYvbPk6fc+T8J+d3f7T827PVomgGk4R8FcLOj7/DSxLSN1ekLY+PpXY9UeVyzRc/c38LhLIw6tbdXNu6kT8JuAebh8ayC9s4y1fslcXx4L9+HOu9aruKy7iV0c8c8O34O2gx8nSmvxavb0T7pcoaui/wBQJAAAAEJH3LP3/OX+VT/VIsMDpqcdtZ+218folgsnFgAAAAAAAADht8C/RlfZmVP7li9JqZvk/i6LZjz3/WfnCGSofQwJAAAAAA9B8CP1Vs/6LV5i9s+Tp9z5Pwn53d/tPzbw9WipqBg7X2xjYlbtyLY1Q6OM/dTfVGK5ZPsRhXXTRGtUtjHxbuRXxLVOsou4Tby77eNVhJ49XKvZZaO+S7OiH2vtRXXcyZ5qOZ2PB+zNFGleTPGnd1flwMpNtttttttt6tt9LZpa6uqppiI0hQhmAAAAISPuWXv+d/s0/wBUiwwOmpx21n7bXx+iWCycWAAAAAAAAAOL3tx12VJ/JyKX9rXpNXMj9JfbN1aZ0e2JQoU76OBIAAAAAQ9B8CH+isD6LV5i9s+Tp9z5Rwn53d/tPzbbJyK64SssnGuuC1lOclGMV1tvmPSZiI1lp0UVV1RTTGszuR3wm3nQjxqsCKslyp32J+xrwI88u96LvNG7mRHNQ6ng7Zmu5pXkzpG6On47kZ7Qz78ix3X2TtsfxpvXRdSXMl2LkK+u5VXOtUuyx8W1j08S1TpDGMGwBIAAAAAQkvcpH3zaD6oYy8rs/AscD+TjdrZ5rUe/6JULFxgAAAAAAAAA5TehXxtj5OnxZUS8l0fxNfKj9KVzwBVpn2/j8pQWUr6YBIAAAAAQlLE4fYuHszCorXtjKjjVpwT4tdb05py6+xa+Is+VU0W4jpnRwtXAN/Ky7ldXi08aeeemfdDgtvcIszNnxsixyinrGqPuaoeDH0vV9ppXL9dyeeXU4PBmPhxpbp5989LVHisYgCQAAAAAAAISruVr95zp/Ktph9WMn65Z4EeLMuG2rr1u26d0T/3uSUb7kwAAAAAAAABo+G9PH2XnxXK/a1kku2K4y/pPK/GtuYb/AAZc4mZaq/yj7PPhRPqwEgAAAAAAAAAAAAAAAAACEybnsfi7Osn87lWNd0YQj50y2wo0tvnm09fGzNN1MfV3ZuOdAAAAAAAAAFrKpU651v4M4Sg+5rR+ciY1jRlRVNFUVR1S81ZWPKqyymfw6pzrl4UW0/tRQV08WZiX13Huxdt01x1xErRi9wAAAAAAAAAAAAAAAAABEvQHATAdGy8Otpxk6vZZJ86lY3Np/WLyxTxbcQ+VcK34vZlyuOjX5czfnsrwAAAAAAAABRgRdvQ4I2Octo40HNSS9switZJpaK1LpWiWunVr1lfl48z49Pxdhs9wvTRHJr06ejP0+yMStdprqqGQAAAAAAAAAAAAAAADGXXcAOCU826N9sWsKqWsnJcl8l/hx61rzvxc5t42PNc8aehz3DnC9ONbm1bnx57vb9k3xRbvnj6AAAAAAAAAAAFGgOW21wC2blSlY63RZLlc6Jex6vrcdHFvt01NevGt188rfE4bzMaIppq1jdPP+e9zuTulrf8AdZc4rqspjP7U0a84FPVK2t7WXI/fbifdOn3YNu6bJXwMqmXhVzh5tTCcCd7ap2st9dqe1hz3WbTXNZiy/mWr1DGcGvqmHtTtVjT+6ie77rb3YbV/0z7rpemJHIbnsesbUYe6rs/K1LdrtZfEpfdfH0kciuMo2mwvb2Ph7udr/MwfdfX+JHI7rLwlwd89j4e7vbH7PF/z6fzDkd3cnwkwfSnskW7zbH7PH/np/MOR3dx4SYPpT2S+lu52v8zBd99X4jkd1HhJg+lPZK5Hdrtb5FS774+gnkVxE7TYW+excjux2q/2dd9z9ESeRXPYwnajD3Vdn5XI7rdpvnnir+bY/UJjBr3wwq2pxY6Kap7Puyqt0+W/h5NEfBjZPzpGUYFW94VbWWuq3PbDNo3SrX3zMbXVDH0flcjOMCOuprXNrKv4Wu2fxDebM3a7MpkpTVmTJcqV01xNfBikn3PU9qMS3SrcnaLMvRpExT7vu7CqqMYqMYqMYpKMYpKMV1JLmRtaaKOZmqdZXAgAAAAAAAAAAAACmgACoAAAApoBUAAAAAKAVApoA0AqAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAD//Z)
Youtube channel [Laireipak Coding Camp][2].

[2]:https://www.youtube.com/channel/UC_q7L6OcumcniSqvvYs21Lw 
