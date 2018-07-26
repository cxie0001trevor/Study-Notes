# 基础

标签： C++

---

### 1. Intro to Stream Object: Hello world case
```C++
#include <iostream>
using namespace std; //statement comes with semicolon

int main() {
  cout << "Hello world" << endl;
  return 0;
}
```
C++ uses a convenient abstraction called <font color='blue'>**streams**</font> to perform input and output operations. <font color='red'>**A stream is an entity where a program can either insert or extract characters to/from**</font>. The standard library defines a handful of stream objects that can be used to access what are considered the standard sources and destinations of characters:
| Name    |         Description         |
| ------- | :-------------------------: |
| `cin`   |      std input stream       |
| `cout`  |      std output stream      |
| `cerr`  |  std error (output) stream  |
| `clong` | std logging (output) stream |

In C++, the stream object defined to access is `cout`.
```C++
cout << "Output sentence"; // prints 'Output sentence' on screen
cout << 120;               // prints number 120 on screen
cout << x;                 // prints the value of x on screen  
```
Chaining insertions is useful to mix literals and variables in a single statement:
```C++
cout << "Name: " << name << "\nAge: " << age;
```
The `endl` manipulator can also be used to <font color='red'>**break lines**</font> (endl ='end-line')
```C++
cout << "Name: " << name << endl;
cout << "Age: " << age << endl;
```
Also, we can avoid breaking a line by `flush`:
```C++
cout << "Program initialising ... " << flush;
```

Finally, the return `0` means that 'everything is Okay' by convention, while `1` means errors.

---
Now, if we want to get user input, we need to use `cin`:
```C++
cout << 'Enter your name:' << flush;
string name;
cin >> name;
```

---
