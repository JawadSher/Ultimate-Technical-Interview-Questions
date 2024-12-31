<h1 align='center'> C++ - TECHNICAL INTERVIEW - QUESTIONS</h1>

<p align='center'>Welcome to the <strong>C++ Technical Interview Questions</strong> repository. This comprehensive document serves as a valuable resource for mastering C++ concepts and preparing for technical interviews. It provides a well-structured collection of interview questions and detailed answers, tailored to help you build confidence and excel in your C++ interviews.</p>

## 🟢 Easy Questions

### ★ Question 01: What is the difference between C and C++?
*C++ is an extension of C. While C is a procedural programming language, C++ supports both procedural and object-oriented programming (OOP). This means C++ allows the use of classes, objects, inheritance, and polymorphism.*

**Example**
```cpp
// C code
#include <stdio.h>

void hello() {
    printf("Hello from C!\n");
}

int main() {
    hello();
    return 0;
}
```
```cpp
// C++ code with classes and objects
#include <iostream>
using namespace std;

class Greeting {
public:
    void hello() {
        cout << "Hello from C++!" << endl;
    }
};

int main() {
    Greeting g;
    g.hello();
    return 0;
}

```

### ★ Question 02: What are classes and objects in C++?
*A class is a blueprint for creating objects (instances). An object is an instance of a class. A class defines attributes (variables) and behaviors (functions).*

**Example**
```cpp
#include <iostream>
using namespace std;

class Car {
public:
    string color; // Attribute
    void drive() { // Behavior
        cout << "The car is driving" << endl;
    }
};

int main() {
    Car car1;  // Creating an object of Car
    car1.color = "Red";
    cout << "Car color: " << car1.color << endl;
    car1.drive();  // Calling method
    return 0;
}

```

### ★ Question 03: What are access modifiers in C++?
*Access modifiers control the visibility of class members (variables and functions). The three main access modifiers are:*
- public: Members are accessible from outside the class.
- private: Members are only accessible within the class.
- protected: Members are accessible within the class and derived classes.

**Example**
```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
    int publicVar; // Accessible outside the class
private:
    int privateVar; // Not accessible outside the class
};

int main() {
    MyClass obj;
    obj.publicVar = 10; // Valid
    // obj.privateVar = 20; // Error: privateVar is private
    return 0;
}

```

### ★ Question 04: What is the difference between the '==' operator and the '=' operator in C++?
*`==` is a comparison operator used to check if two values are equal. `=` is an assignment operator used to assign a value to a variable.*

**Example:**
```cpp
int a = 5;    // Assigns 5 to a
int b = 5;

if (a == b) {  // Compares a and b
    cout << "a and b are equal." << endl;
}
```

### ★ Question 05: Explain the difference between a while loop and a do-while loop in C++?
- **`while` loop**: The condition is checked before each iteration. If the condition is false initially, the loop may never run.  
- **`do-while` loop**: The condition is checked after each iteration, ensuring the loop runs at least once.

**Example:**
```cpp
// while loop
int i = 0;
while (i < 5) {
    cout << i << " ";
    i++;
}
// Output: 0 1 2 3 4

// do-while loop
int j = 0;
do {
    cout << j << " ";
    j++;
} while (j < 5);
// Output: 0 1 2 3 4
```


### ★ Question 06: What is the size of the int data type in C++?
*The size of the `int` data type depends on the system and compiler. Typically, it is 4 bytes (32 bits) on most systems.*

**Example:**
```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Size of int: " << sizeof(int) << " bytes" << endl;
    return 0;
}
```


### ★ Question 07: Which operator cannot be overloaded in C++?
*The following operators cannot be overloaded in C++:*
- `::` (Scope resolution operator)
- `.` (Member access operator)
- `.*` (Member pointer operator)
- `?:` (Ternary conditional operator)
- `sizeof` (Sizeof operator)

### ★ Question 08: How do you input strings with spaces in C++?
*You can use `getline()` to input a string with spaces, as `cin` will stop reading at the first space.*

**Example:**
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string name;
    cout << "Enter your full name: ";
    getline(cin, name);  // Reads the entire line including spaces
    cout << "Hello, " << name << "!" << endl;
    return 0;
}
```


### ★ Question 09: What is the difference between 'new' and 'malloc' in C++?
- `new` is an operator that allocates memory for an object and calls the constructor.
- `malloc` is a function in C that allocates raw memory but does not initialize it.

**Example:**
```cpp
// Using new
int* ptr1 = new int(5); // Allocates memory and initializes with 5

// Using malloc
int* ptr2 = (int*)malloc(sizeof(int)); // Allocates raw memory
*ptr2 = 5;  // Must manually initialize the value
```


### ★ Question 10: What is a constructor in C++?
*A constructor is a special member function that is called automatically when an object is created. It is used to initialize objects.*

**Example:**
```cpp
#include <iostream>
using namespace std;

class Car {
public:
    string color;
    int year;

    // Constructor
    Car(string c, int y) {
        color = c;
        year = y;
    }

    void display() {
        cout << "Car color: " << color << ", Year: " << year << endl;
    }
};

int main() {
    Car car1("Red", 2022);  // Constructor is called
    car1.display();
    return 0;
}
```


Here are the answers for the new set of questions, following the same pattern:



### ★ Question 11: What is the difference between a class and a struct in C++?
*In C++, both classes and structs are used to create user-defined data types, but the key difference is:*
- **class**: By default, members of a class are private.
- **struct**: By default, members of a struct are public.

**Example:**
```cpp
#include <iostream>
using namespace std;

class MyClass {
    int x; // private by default
};

struct MyStruct {
    int x; // public by default
};

int main() {
    MyStruct obj;
    obj.x = 10;  // Valid, as x is public in struct

    // MyClass obj2;
    // obj2.x = 10; // Error, as x is private in class
    return 0;
}
```



### ★ Question 12: What is polymorphism in C++?
*Polymorphism in C++ allows a single function or operator to work in different ways. It can be achieved through function overloading, operator overloading, and inheritance (method overriding).*

**Example:**
```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    virtual void draw() { cout << "Drawing Shape" << endl; }
};

class Circle : public Shape {
public:
    void draw() override { cout << "Drawing Circle" << endl; }
};

int main() {
    Shape* shape;
    Circle circle;
    shape = &circle;
    shape->draw();  // Polymorphism in action: calls Circle's draw() method
    return 0;
}
```



### ★ Question 13: What is the purpose of the 'virtual' keyword in C++?
*The `virtual` keyword is used to allow derived classes to override base class methods, enabling dynamic (runtime) polymorphism. It ensures the correct method is called for an object, even if it’s referenced through a base class pointer or reference.*

**Example:**
```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void sound() { cout << "Animal sound" << endl; }
};

class Dog : public Animal {
public:
    void sound() override { cout << "Bark" << endl; }
};

int main() {
    Animal* animal = new Dog();
    animal->sound();  // Virtual function ensures Dog's sound() is called
    delete animal;
    return 0;
}
```



### ★ Question 14: What is the difference between 'public', 'private', and 'protected' access specifiers in C++?
*Access specifiers in C++ control the accessibility of class members:*
- **`public`**: Members are accessible from outside the class.
- **`private`**: Members are only accessible within the class.
- **`protected`**: Members are accessible within the class and derived classes.

**Example:**
```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
    int publicVar;
    
protected:
    int protectedVar;
    
private:
    int privateVar;
};

int main() {
    MyClass obj;
    obj.publicVar = 10;  // Valid
    // obj.protectedVar = 20; // Error: protectedVar is protected
    // obj.privateVar = 30;   // Error: privateVar is private
    return 0;
}
```



### ★ Question 15: What is operator overloading in C++?
*Operator overloading allows you to define custom behavior for operators (e.g., `+`, `-`, etc.) when applied to user-defined types (like classes and structs).*

**Example:**
```cpp
#include <iostream>
using namespace std;

class Complex {
public:
    int real, imag;
    
    Complex operator + (const Complex& other) {
        Complex temp;
        temp.real = real + other.real;
        temp.imag = imag + other.imag;
        return temp;
    }
};

int main() {
    Complex c1, c2, c3;
    c1.real = 3; c1.imag = 4;
    c2.real = 1; c2.imag = 2;
    c3 = c1 + c2; // Uses overloaded + operator
    cout << "Sum: " << c3.real << " + " << c3.imag << "i" << endl;
    return 0;
}
```



### ★ Question 16: What is the difference between 'new' and 'delete' operators in C++?
- **`new`**: Allocates memory for an object and returns a pointer to it.
- **`delete`**: Deallocates memory previously allocated with `new`.

**Example:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int* ptr = new int(5);  // Allocates memory for an int and assigns 5
    cout << *ptr << endl;    // Prints: 5
    delete ptr;              // Frees the allocated memory
    return 0;
}
```



### ★ Question 17: What is the difference between '++i' and 'i++'?
- **`++i` (pre-increment)**: Increments the value of `i` before it is used in the expression.
- **`i++` (post-increment)**: Increments the value of `i` after it is used in the expression.

**Example:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 5;
    cout << ++i << endl;  // Prints: 6, increments before printing
    cout << i++ << endl;  // Prints: 6, increments after printing
    cout << i << endl;    // Prints: 7, after post-increment
    return 0;
}
```



### ★ Question 18: How do you declare and initialize a pointer in C++?
*To declare a pointer, specify the data type followed by an asterisk (`*`). To initialize it, use the address-of operator (`&`).*

**Example:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int num = 10;
    int* ptr = &num;  // Pointer initialized with the address of num
    cout << "Value of num: " << *ptr << endl;  // Dereferencing the pointer
    return 0;
}
```



### ★ Question 19: What is the difference between an array and a pointer in C++?
- **Array**: A fixed-size collection of elements of the same type, with a predefined size.
- **Pointer**: A variable that holds the memory address of another variable or object. It can be changed to point to different memory locations.

**Example:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[3] = {1, 2, 3};  // Array
    int* ptr = arr;  // Pointer to the first element of the array

    cout << "Array[0]: " << arr[0] << endl;
    cout << "Pointer[0]: " << *ptr << endl;  // Dereferencing the pointer
    return 0;
}
```



### ★ Question 20: What are static members in C++?
*Static members of a class are shared by all instances of the class. They are not tied to any specific object and are accessed using the class name.*

**Example:**
```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
    static int count;  // Static member
    MyClass() { count++; }
};

int MyClass::count = 0;  // Initialize static member

int main() {
    MyClass obj1, obj2;
    cout << "Object count: " << MyClass::count << endl;  // Accessing static member
    return 0;
}
```

Here are the answers for the new set of questions, following the same pattern:



### ★ Question 21: What is the difference between an abstract class and an interface in C++?
*An abstract class in C++ can have both pure virtual functions (methods that must be overridden in derived classes) and regular member functions. An interface, on the other hand, is essentially a class that only contains pure virtual functions and cannot have any implementation.*

- **Abstract Class**: Can have both abstract methods (pure virtual) and implemented methods.
- **Interface**: Contains only pure virtual methods, without any implementation.

**Example:**
```cpp
#include <iostream>
using namespace std;

class AbstractClass {
public:
    virtual void show() = 0;  // Pure virtual function (abstract)
    void display() { cout << "Display from Abstract Class" << endl; }  // Regular method
};

class Interface {
public:
    virtual void show() = 0;  // Pure virtual function (interface)
};

class DerivedClass : public AbstractClass, public Interface {
public:
    void show() override { cout << "Implemented show method" << endl; }
};

int main() {
    DerivedClass obj;
    obj.show();  // Calls the overridden show method
    obj.display();  // Calls the regular method from AbstractClass
    return 0;
}
```



### ★ Question 22: What are the uses of 'const' in C++?
*The `const` keyword is used to declare constants, making a variable's value unmodifiable. It can be applied to variables, pointers, and functions.*

- **Constant variables**: Prevent modification of a variable's value.
- **Constant pointers**: Prevent modification of the pointer itself.
- **Constant member functions**: Prevent modification of class members inside the function.

**Example:**
```cpp
#include <iostream>
using namespace std;

void printValue(const int val) {
    // val = 20;  // Error: Cannot modify a const variable
    cout << val << endl;
}

int main() {
    const int num = 10;
    printValue(num);
    
    int x = 5;
    const int* ptr = &x;  // Pointer to a constant integer
    // *ptr = 10;  // Error: Cannot modify the value pointed to by a const pointer
    return 0;
}
```



### ★ Question 23: What is a destructor in C++?
*A destructor is a special member function that is called when an object is destroyed. It is used to release resources allocated by the object (e.g., memory, file handles).*

- The destructor has the same name as the class but is preceded by a tilde (~).
- It cannot have any return type and cannot take parameters.

**Example:**
```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
    MyClass() { cout << "Constructor called" << endl; }
    ~MyClass() { cout << "Destructor called" << endl; }  // Destructor

};

int main() {
    MyClass obj;  // Constructor is called
    // Destructor is called automatically when obj goes out of scope
    return 0;
}
```



### ★ Question 24: What is the use of the 'friend' function in C++?
*A `friend` function is a function that can access the private and protected members of a class. It is not a member of the class, but it is allowed to access the class's private data.*

- The `friend` function is declared inside the class but defined outside the class.
- It can be a global function or a member of another class.

**Example:**
```cpp
#include <iostream>
using namespace std;

class MyClass {
private:
    int secret = 42;
    
public:
    // Declare the friend function
    friend void revealSecret(MyClass obj);
};

void revealSecret(MyClass obj) {
    cout << "The secret is: " << obj.secret << endl;  // Can access private members
}

int main() {
    MyClass obj;
    revealSecret(obj);  // Friend function can access private members
    return 0;
}
```



### ★ Question 25: How can you prevent a class from being inherited in C++?
*You can prevent a class from being inherited by making its constructor and/or destructor `private` or by using the `final` keyword.*

- **Using `private` constructor**: The class cannot be inherited because the constructor is not accessible.
- **Using `final` keyword**: This prevents further inheritance of the class.

**Example:**
```cpp
#include <iostream>
using namespace std;

class Base {
private:
    Base() {}  // Private constructor
    friend class Derived;  // Friend class to access the private constructor
    
public:
    static void createInstance() { cout << "Base class instance created" << endl; }
};

class Derived : public Base {  // Error: Cannot inherit from Base
};

int main() {
    // Base base;  // Error: Constructor is private
    Base::createInstance();
    return 0;
}
```

Or using `final`:
```cpp
#include <iostream>
using namespace std;

class Base final {  // Using 'final' to prevent inheritance
public:
    void show() { cout << "Base class" << endl; }
};

class Derived : public Base {  // Error: Cannot inherit from Base because it is final
};

int main() {
    Base obj;
    obj.show();
    return 0;
}
```

## 🟠 Medium Questions
1. **Explain the concept of exception handling in C++.**  
   *Exception handling allows you to manage runtime errors using `try`, `catch`, and `throw`.*


## 🔴 Hard Questions
1. **What is the difference between stack and heap memory?**  
   *Stack memory is used for static memory allocation, while heap memory is used for dynamic memory allocation.*


## ⭐ Best Practices
- Use examples for code-related questions.
- Include diagrams or tables where necessary to explain complex concepts.
- Keep the content concise and precise for quick revision.
