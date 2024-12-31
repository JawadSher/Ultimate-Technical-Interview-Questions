<h1 align='center'> C++ - TECHNICAL INTERVIEW - QUESTIONS</h1>

<p align='center'>Welcome to the <strong>C++ Technical Interview Questions</strong> repository. This comprehensive document serves as a valuable resource for mastering C++ concepts and preparing for technical interviews. It provides a well-structured collection of interview questions and detailed answers, tailored to help you build confidence and excel in your C++ interviews.</p>

This repository contains **91 C++ interview questions**, categorized by difficulty (Easy, Medium, Hard), with detailed answers and examples to help you prepare for technical interviews. It covers fundamental to advanced topics, including object-oriented programming, memory management, multithreading, templates, and design patterns.

#### Key Highlights:
- **Comprehensive Coverage**: Questions range from basic syntax to advanced concepts like RAII, smart pointers, and thread synchronization.
- **Real-world Examples**: Each answer includes practical examples for better understanding.
- **Interview-Ready**: Prepares you for C++ interviews at major tech companies by focusing on critical problem-solving techniques and best practices.

Perfect for anyone preparing for a C++ technical interview in 2025 or beyond.


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
Here are the answers to the provided questions, formatted similarly to the previous ones:



### ★ Question 26: Explain the concept of exception handling in C++.
*Exception handling in C++ allows a program to deal with unexpected situations (errors) during runtime. It uses three key keywords: `try`, `throw`, and `catch`.*

- **try**: Contains code that may throw an exception.
- **throw**: Used to throw an exception when an error occurs.
- **catch**: Catches and handles the thrown exception.

**Example:**
```cpp
#include <iostream>
using namespace std;

int divide(int a, int b) {
    if (b == 0) throw "Division by zero error";  // Throw an exception
    return a / b;
}

int main() {
    try {
        int result = divide(10, 0);  // Division by zero
    } catch (const char* msg) {
        cout << "Caught an exception: " << msg << endl;
    }
    return 0;
}
```



### ★ Question 27: What is the purpose of 'this' pointer in C++?
*The `this` pointer in C++ is an implicit pointer available in non-static member functions. It points to the current object of the class, allowing access to the object's members.*

- The `this` pointer helps distinguish between class members and parameters when they have the same name.

**Example:**
```cpp
#include <iostream>
using namespace std;

class MyClass {
private:
    int x;
public:
    MyClass(int x) {
        this->x = x;  // Using 'this' pointer to differentiate between member and parameter
    }
    void display() { cout << "Value of x: " << this->x << endl; }
};

int main() {
    MyClass obj(10);
    obj.display();  // Displays: Value of x: 10
    return 0;
}
```



### ★ Question 28: What is multiple inheritance in C++ and how can you resolve ambiguity?
*Multiple inheritance occurs when a class inherits from more than one base class. Ambiguity arises if the same member exists in both base classes. This can be resolved using scope resolution.*

- Use `ClassName::member` to resolve ambiguity.

**Example:**
```cpp
#include <iostream>
using namespace std;

class A {
public:
    void show() { cout << "Class A" << endl; }
};

class B {
public:
    void show() { cout << "Class B" << endl; }
};

class C : public A, public B {
public:
    void show() { 
        A::show();  // Resolving ambiguity
        B::show();
    }
};

int main() {
    C obj;
    obj.show();
    return 0;
}
```



### ★ Question 29: What is dynamic memory allocation in C++?
*Dynamic memory allocation allows you to allocate memory at runtime using operators like `new` and `delete`. This helps manage memory more efficiently.*

- **new**: Allocates memory.
- **delete**: Deallocates memory.

**Example:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int* ptr = new int;  // Dynamically allocate memory for an integer
    *ptr = 10;  // Assign value
    cout << *ptr << endl;  // Output: 10
    delete ptr;  // Free allocated memory
    return 0;
}
```



### ★ Question 30: What are the differences between a shallow copy and a deep copy in C++?
- **Shallow copy**: Copies the pointer values but not the actual objects they point to. Changes to the original object affect the copied object.
- **Deep copy**: Creates a copy of the actual object along with its data, ensuring that changes to the original object do not affect the copied object.

**Example:**
```cpp
#include <iostream>
using namespace std;

class MyClass {
private:
    int* ptr;
public:
    MyClass(int value) {
        ptr = new int;
        *ptr = value;
    }
    MyClass(const MyClass& obj) {  // Deep copy constructor
        ptr = new int;
        *ptr = *(obj.ptr);
    }
    ~MyClass() { delete ptr; }  // Destructor
    void display() { cout << *ptr << endl; }
};

int main() {
    MyClass obj1(10);
    MyClass obj2 = obj1;  // Deep copy
    obj2.display();  // Output: 10
    return 0;
}
```



### ★ Question 31: Explain the concept of function overloading in C++.
*Function overloading in C++ allows you to define multiple functions with the same name but different parameters (either in number or type). The correct function is chosen based on the arguments passed.*

**Example:**
```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
    void display(int x) { cout << "Integer: " << x << endl; }
    void display(double x) { cout << "Double: " << x << endl; }
};

int main() {
    MyClass obj;
    obj.display(10);  // Calls display(int)
    obj.display(3.14);  // Calls display(double)
    return 0;
}
```



### ★ Question 32: What is the difference between function overloading and function overriding in C++?
- **Function overloading**: Same function name but different parameter lists within the same class.
- **Function overriding**: A derived class provides its own implementation of a base class function with the same signature.

**Example of Overloading:**
```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
    void show(int x) { cout << "Integer: " << x << endl; }
    void show(double x) { cout << "Double: " << x << endl; }
};
```

**Example of Overriding:**
```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void display() { cout << "Base class display" << endl; }
};

class Derived : public Base {
public:
    void display() override { cout << "Derived class display" << endl; }
};

int main() {
    Base* obj = new Derived();
    obj->display();  // Calls overridden method in Derived class
    return 0;
}
```



### ★ Question 33: What is the use of 'virtual destructors' in C++?
*A virtual destructor ensures that when a base class pointer is used to delete a derived class object, the destructor of the derived class is called first, followed by the base class destructor.*

- This prevents memory leaks and ensures proper cleanup.

**Example:**
```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual ~Base() { cout << "Base destructor" << endl; }  // Virtual destructor
};

class Derived : public Base {
public:
    ~Derived() { cout << "Derived destructor" << endl; }
};

int main() {
    Base* obj = new Derived();
    delete obj;  // Calls Derived destructor, then Base destructor
    return 0;
}
```



### ★ Question 34: Explain the use of namespaces in C++.
*Namespaces are used in C++ to organize code and avoid name conflicts. Code elements (variables, functions, etc.) can be grouped inside a namespace to differentiate them from other code elements with the same name in different namespaces.*

**Example:**
```cpp
#include <iostream>
using namespace std;

namespace FirstNamespace {
    int value = 10;
}

namespace SecondNamespace {
    int value = 20;
}

int main() {
    cout << "First namespace value: " << FirstNamespace::value << endl;
    cout << "Second namespace value: " << SecondNamespace::value << endl;
    return 0;
}
```



### ★ Question 35: How do you implement a copy constructor in C++?
*A copy constructor is used to create a new object as a copy of an existing object. It is defined as a constructor that takes a reference to the same class type.*

**Example:**
```cpp
#include <iostream>
using namespace std;

class MyClass {
private:
    int* ptr;
public:
    MyClass(int value) {
        ptr = new int;
        *ptr = value;
    }
    MyClass(const MyClass& obj) {  // Copy constructor
        ptr = new int;
        *ptr = *(obj.ptr);
    }
    ~MyClass() { delete ptr; }
    void display() { cout << *ptr << endl; }
};

int main() {
    MyClass obj1(10);
    MyClass obj2 = obj1;  // Copy constructor called
    obj2.display();  // Output: 10
    return 0;
}
```

Here are the answers to the provided questions, formatted similarly to the previous ones:



### ★ Question 36: What is a virtual function in C++?
*A virtual function in C++ is a member function in the base class that is overridden in a derived class. It allows for dynamic (run-time) polymorphism, enabling the correct function to be called for an object, regardless of the type of reference (base or derived).*

- Declared using the `virtual` keyword.
- Used to achieve late binding (dynamic dispatch).

**Example:**
```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void display() { cout << "Base class display" << endl; }
};

class Derived : public Base {
public:
    void display() override { cout << "Derived class display" << endl; }
};

int main() {
    Base* obj = new Derived();
    obj->display();  // Calls Derived class display (late binding)
    delete obj;
    return 0;
}
```



### ★ Question 37: What are templates in C++ and how do they work?
*Templates in C++ allow for writing generic functions and classes. A template defines a function or class with placeholder types that can be specified later, making the code reusable for different data types.*

- **Function template**: Can define a function for any data type.
- **Class template**: Can define a class for any data type.

**Example:**
```cpp
#include <iostream>
using namespace std;

template <typename T>
T add(T a, T b) {
    return a + b;
}

int main() {
    cout << add(3, 5) << endl;  // Output: 8 (int)
    cout << add(3.5, 5.2) << endl;  // Output: 8.7 (double)
    return 0;
}
```



### ★ Question 38: What is the difference between template specialization and function overloading in C++?
- **Template specialization**: Allows for defining a specific implementation of a template for a particular type.
- **Function overloading**: Allows multiple functions with the same name but different parameter types or numbers.

**Example of Template Specialization:**
```cpp
#include <iostream>
using namespace std;

template <typename T>
void print(T value) {
    cout << "Generic print: " << value << endl;
}

template <>
void print<int>(int value) {  // Template specialization for int
    cout << "Specialized print for int: " << value << endl;
}

int main() {
    print(5);  // Calls specialized function
    print(3.5);  // Calls generic function
    return 0;
}
```



### ★ Question 39: How do you use the 'sizeof' operator in C++?
*The `sizeof` operator in C++ is used to determine the size, in bytes, of a data type or object in memory.*

- Returns the size of the data type or object.
- It is evaluated at compile time.

**Example:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 5;
    double b = 3.14;
    cout << "Size of int: " << sizeof(a) << " bytes" << endl;
    cout << "Size of double: " << sizeof(b) << " bytes" << endl;
    return 0;
}
```



### ★ Question 40: What is an iterator in C++?
*An iterator in C++ is an object that allows traversal through the elements of a container (such as vectors, lists, maps). It provides a way to access elements without exposing the underlying structure.*

- Similar to pointers, iterators can be used to iterate over container elements.

**Example:**
```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> vec = {1, 2, 3, 4, 5};
    for (auto it = vec.begin(); it != vec.end(); ++it) {
        cout << *it << " ";  // Dereferencing the iterator
    }
    return 0;
}
```



### ★ Question 41: What are move semantics and rvalue references in C++?
*Move semantics and rvalue references allow resources to be transferred (moved) from one object to another, instead of copying them, improving performance especially with large objects.*

- **Rvalue reference (`&&`)**: Allows you to bind to temporary (rvalue) objects.
- **Move constructor and move assignment operator**: Used to implement move semantics.

**Example:**
```cpp
#include <iostream>
using namespace std;

class MyClass {
private:
    int* ptr;
public:
    MyClass(int value) { ptr = new int(value); }
    ~MyClass() { delete ptr; }
    MyClass(MyClass&& obj) {  // Move constructor
        ptr = obj.ptr;
        obj.ptr = nullptr;
    }
};

int main() {
    MyClass obj1(10);
    MyClass obj2 = std::move(obj1);  // Move obj1 to obj2
    return 0;
}
```



### ★ Question 42: What is a lambda function in C++?
*A lambda function in C++ is an anonymous function that can be defined inline, often used for short tasks or as function arguments.*

- Lambda functions can capture variables from the surrounding scope.

**Example:**
```cpp
#include <iostream>
using namespace std;

int main() {
    auto add = [](int a, int b) { return a + b; };
    cout << add(3, 4) << endl;  // Output: 7
    return 0;
}
```



### ★ Question 43: How does C++ handle memory management?
*C++ handles memory management manually through the use of operators like `new`, `delete`, and smart pointers. It allows developers to allocate and free memory as needed, though it is prone to errors like memory leaks if not done correctly.*

- **new**: Allocates memory.
- **delete**: Frees memory.
- **smart pointers**: Automatically manage memory, e.g., `std::unique_ptr` and `std::shared_ptr`.

**Example:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int* ptr = new int;  // Allocating memory
    *ptr = 10;
    cout << *ptr << endl;  // Output: 10
    delete ptr;  // Freeing memory
    return 0;
}
```



### ★ Question 44: What is the difference between 'vector' and 'array' in C++?
- **Vector**: A dynamic array that can change size during runtime, provides more functionality (e.g., push_back, pop_back).
- **Array**: A fixed-size data structure that cannot change size after initialization.

**Example:**
```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    int arr[5] = {1, 2, 3, 4, 5};  // Fixed-size array
    vector<int> vec = {1, 2, 3, 4, 5};  // Dynamic-size vector
    vec.push_back(6);  // Adds 6 to the vector
    cout << "Array size: " << sizeof(arr)/sizeof(arr[0]) << endl;
    cout << "Vector size: " << vec.size() << endl;
    return 0;
}
```



### ★ Question 45: What are the various types of casts in C++?
*C++ supports four types of casts:*
- **static_cast**: Used for conversions between types that are related.
- **dynamic_cast**: Used for safe downcasting in class hierarchies.
- **const_cast**: Used to add or remove constness from a variable.
- **reinterpret_cast**: Used for low-level type conversions, such as converting between different pointer types.

**Example:**
```cpp
#include <iostream>
using namespace std;

class Base { virtual void foo() {} };
class Derived : public Base {};

int main() {
    Base* b = new Derived();
    Derived* d = dynamic_cast<Derived*>(b);  // dynamic_cast for downcasting
    if (d) cout << "Downcasted successfully!" << endl;
    return 0;
}
```



### ★ Question 46: What is the difference between 'std::shared_ptr' and 'std::unique_ptr'?
- **std::shared_ptr**: A smart pointer that can be shared among multiple owners. It uses reference counting to manage memory.
- **std::unique_ptr**: A smart pointer that ensures exclusive ownership of an object, meaning only one `unique_ptr` can point to an object at any time.

**Example:**
```cpp
#include <iostream>
#include <memory>
using namespace std;

int main() {
    unique_ptr<int> uptr1 = make_unique<int>(10);
    shared_ptr<int> sptr1 = make_shared<int>(20);
    cout << *uptr1 << endl;  // Output: 10
    cout << *sptr1 << endl;  // Output: 20
    return 0;
}
```



### ★ Question 47: What is the purpose of 'const_cast' in C++?
*`const_cast` is used to add or remove the `const` qualifier from a variable. It is useful when you need to modify a `const` object, or when working with APIs that require non-const arguments.*

**Example:**
```cpp
#include <iostream>
using namespace std;

void modify(int* ptr) {
    *ptr = 20;
}

int main() {
    const int x = 10;
    int* ptr = const_cast<int*>(&x);  // Removing const qualifier
    modify(ptr);  // Now x can be modified
    cout << x << endl;  // Output: 20
    return 0;
}
```



### ★ Question 48: How does C++ support multithreading and concurrency?
*C++ supports mult

ithreading and concurrency through the `<thread>`, `<mutex>`, and `<future>` libraries. You can create multiple threads and manage shared data using synchronization mechanisms like mutexes.*

**Example:**
```cpp
#include <iostream>
#include <thread>
using namespace std;

void print_message() {
    cout << "Hello from thread!" << endl;
}

int main() {
    thread t(print_message);
    t.join();  // Wait for the thread to finish
    return 0;
}
```



### ★ Question 49: What are the advantages and disadvantages of using a linked list in C++?
- **Advantages**:
  - Dynamic size, flexible memory usage.
  - Efficient insertions and deletions.
- **Disadvantages**:
  - Random access is slower than arrays.
  - More memory overhead due to pointers.



### ★ Question 50: What is the significance of the 'volatile' keyword in C++?
*The `volatile` keyword tells the compiler not to optimize a variable because its value can change unexpectedly, e.g., in embedded systems where variables might be changed by hardware or other threads.*

**Example:**
```cpp
#include <iostream>
using namespace std;

volatile int flag = 0;

int main() {
    while (flag == 0);  // Compiler won't optimize this loop
    cout << "Flag changed!" << endl;
    return 0;
}
```


## 🔴 Hard Questions
Here are the answers to your new set of questions, formatted similarly:



### ★ Question 51: What is the difference between a stack and a heap in memory management?
- **Stack**: A region of memory used for static memory allocation. It is managed automatically, with memory allocated and deallocated in a Last-In-First-Out (LIFO) manner.
  - Faster allocation and deallocation.
  - Limited size (depends on the system).
  - Used for local variables and function calls.
  
- **Heap**: A region of memory used for dynamic memory allocation. It is managed manually by the programmer.
  - Slower allocation and deallocation.
  - Larger size, limited by system memory.
  - Used for objects created during runtime (using `new`/`delete`).

**Example:**
```cpp
#include <iostream>
using namespace std;

void stackExample() {
    int x = 10;  // Stack memory
}

void heapExample() {
    int* ptr = new int(10);  // Heap memory
    delete ptr;
}

int main() {
    stackExample();
    heapExample();
    return 0;
}
```



### ★ Question 52: Explain RAII (Resource Acquisition Is Initialization) in C++.
*RAII is a C++ programming idiom where resource management (like memory, file handles, network connections) is tied to the lifetime of objects. Resources are acquired during object initialization and released during object destruction.*

- Ensures resources are cleaned up automatically.
- Prevents resource leaks and simplifies error handling.

**Example:**
```cpp
#include <iostream>
#include <fstream>
using namespace std;

class FileHandler {
private:
    ifstream file;
public:
    FileHandler(const string& filename) { file.open(filename); }
    ~FileHandler() { if (file.is_open()) file.close(); }  // Resource is released here
};

int main() {
    FileHandler handler("file.txt");  // File is opened when handler is created
    // File is automatically closed when handler goes out of scope
    return 0;
}
```



### ★ Question 53: How do you implement a thread-safe queue in C++?
*A thread-safe queue can be implemented using a mutex (or other synchronization primitives) to protect access to the queue in multithreaded environments.*

- **std::mutex** can be used to ensure that only one thread accesses the queue at a time.

**Example:**
```cpp
#include <iostream>
#include <queue>
#include <mutex>
#include <thread>
#include <condition_variable>
using namespace std;

template <typename T>
class ThreadSafeQueue {
private:
    queue<T> q;
    mutable mutex m;
    condition_variable cv;
public:
    void push(const T& value) {
        lock_guard<mutex> lock(m);
        q.push(value);
        cv.notify_one();
    }

    T pop() {
        unique_lock<mutex> lock(m);
        cv.wait(lock, [this]{ return !q.empty(); });
        T value = q.front();
        q.pop();
        return value;
    }
};

void producer(ThreadSafeQueue<int>& q) {
    for (int i = 0; i < 5; ++i) {
        q.push(i);
    }
}

void consumer(ThreadSafeQueue<int>& q) {
    for (int i = 0; i < 5; ++i) {
        cout << "Consumed: " << q.pop() << endl;
    }
}

int main() {
    ThreadSafeQueue<int> q;
    thread t1(producer, std::ref(q));
    thread t2(consumer, std::ref(q));
    
    t1.join();
    t2.join();
    return 0;
}
```



### ★ Question 54: What is the difference between 'std::map' and 'std::unordered_map' in C++?
- **std::map**: A sorted associative container that stores key-value pairs, maintaining the order of the keys using a comparison function.
  - **Key access time**: O(log n)
  
- **std::unordered_map**: An unsorted associative container that stores key-value pairs in no particular order, implemented using a hash table.
  - **Key access time**: O(1) on average (amortized constant time).

**Example:**
```cpp
#include <iostream>
#include <map>
#include <unordered_map>
using namespace std;

int main() {
    map<int, string> m = {{1, "One"}, {2, "Two"}};
    unordered_map<int, string> um = {{1, "One"}, {2, "Two"}};
    
    cout << "map[1]: " << m[1] << endl;
    cout << "unordered_map[1]: " << um[1] << endl;
    return 0;
}
```



### ★ Question 55: How would you handle memory leaks in a large C++ application?
- Use **smart pointers** (`std::unique_ptr`, `std::shared_ptr`) to automatically manage memory.
- Regularly use **tools** like Valgrind or AddressSanitizer to detect memory leaks.
- Perform manual memory management by ensuring every `new` has a corresponding `delete`, or use RAII techniques to ensure proper resource management.

**Example:**
```cpp
#include <memory>
using namespace std;

int main() {
    unique_ptr<int> ptr = make_unique<int>(10);  // Memory is automatically managed
    return 0;
}
```



### ★ Question 56: How do you implement a singleton design pattern in C++?
*The Singleton pattern ensures that a class has only one instance and provides a global point of access to it. This can be done by making the constructor private and providing a static method to get the instance.*

**Example:**
```cpp
#include <iostream>
using namespace std;

class Singleton {
private:
    static Singleton* instance;
    Singleton() {}  // Private constructor
public:
    static Singleton* getInstance() {
        if (instance == nullptr) {
            instance = new Singleton();
        }
        return instance;
    }
};

// Initialize the static member
Singleton* Singleton::instance = nullptr;

int main() {
    Singleton* s1 = Singleton::getInstance();
    Singleton* s2 = Singleton::getInstance();
    cout << (s1 == s2 ? "Same instance" : "Different instances") << endl;
    return 0;
}
```



### ★ Question 57: What are the different types of polymorphism in C++?
- **Compile-time polymorphism** (also known as static polymorphism):
  - Achieved through function overloading and operator overloading.
  
- **Runtime polymorphism** (also known as dynamic polymorphism):
  - Achieved through inheritance and virtual functions.

**Example (runtime polymorphism):**
```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void show() { cout << "Base class show" << endl; }
};

class Derived : public Base {
public:
    void show() override { cout << "Derived class show" << endl; }
};

int main() {
    Base* b = new Derived();
    b->show();  // Calls Derived class show
    delete b;
    return 0;
}
```



### ★ Question 58: What is a function pointer in C++ and how is it used?
*A function pointer in C++ is a pointer that points to a function instead of a variable. It allows for dynamic function calls.*

**Example:**
```cpp
#include <iostream>
using namespace std;

void greet() { cout << "Hello, world!" << endl; }
void farewell() { cout << "Goodbye, world!" << endl; }

int main() {
    void (*funcPtr)() = greet;  // Function pointer pointing to greet()
    funcPtr();  // Calls greet()
    
    funcPtr = farewell;  // Function pointer pointing to farewell()
    funcPtr();  // Calls farewell()
    
    return 0;
}
```



### ★ Question 59: What is the purpose of the 'alignof' operator in C++?
*The `alignof` operator is used to obtain the alignment requirement (in bytes) of a type or object, which is the number of bytes between the starting address of the object and the memory address of its data.*

**Example:**
```cpp
#include <iostream>
#include <type_traits>
using namespace std;

struct MyStruct {
    char a;
    int b;
};

int main() {
    cout << "Alignment of MyStruct: " << alignof(MyStruct) << endl;
    return 0;
}
```



### ★ Question 60: How do you handle circular dependencies in C++?
*Circular dependencies (when two or more files depend on each other) can be handled using forward declarations or by restructuring the code to minimize dependencies.*

- Use **forward declarations** to break the circular dependency between header files.
- Organize code in a way that reduces interdependencies.

**Example of forward declaration:**
```cpp
// A.h
class B;  // Forward declaration
class A {
    B* b;  // Pointer to B
};

// B.h
class A;  // Forward declaration
class B {
    A* a;  // Pointer to A
};
```



### ★ Question 61: What is the "diamond problem" in C++ and how can it be solved?
*The diamond problem occurs in multiple inheritance when a class inherits from two classes that both inherit from the same base class, leading to ambiguity about which version of the base class members to use.*

- **Solution**: Use **virtual inheritance** to ensure that only one instance of the base class is inherited.

**Example:**
```cpp
#include <iostream>
using namespace std;

class A {
public:
    void show() { cout << "A class" << endl; }
};

class B : virtual public A {};
class C : virtual public A {};

class D : public B, public C {};

int main() {
    D obj;
    obj.show();  // Resolves ambiguity by using virtual inheritance
    return 0;
}
```





### ★ Question 62: Explain how C++ handles object slicing.
*Object slicing happens when an object of a derived class is assigned to an object of a base class. The derived class-specific members are "sliced off," and only the base class part is copied.*

**Example:**
```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void show() { cout << "Base class" << endl; }
};

class Derived : public Base {
public:
    void show() override { cout << "Derived class" << endl; }
};

int main() {
    Derived d;
    Base b = d;  // Object slicing occurs here
    b.show();    // Calls Base class show, not Derived class show
    return 0;
}
```



### ★ Question 63: How do you prevent object slicing in C++?
*To prevent object slicing, use pointers or references to the base class instead of objects.*

**Example:**
```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void show() { cout << "Base class" << endl; }
};

class Derived : public Base {
public:
    void show() override { cout << "Derived class" << endl; }
};

int main() {
    Derived d;
    Base* b = &d;  // No object slicing, pointer is used
    b->show();     // Calls Derived class show
    return 0;
}
```



### ★ Question 64: What is the significance of the 'decltype' keyword in C++?
*The `decltype` keyword in C++ is used to query the type of an expression. It can be used to deduce the type of variables, especially in template programming or when working with auto.*

**Example:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10;
    decltype(a) b = 20;  // b will have the same type as a (int)
    cout << b << endl;
    return 0;
}
```



### ★ Question 65: What are 'variadic templates' in C++?
*Variadic templates allow you to create functions or classes that accept any number of template arguments. They are particularly useful for creating generic functions that can accept an arbitrary number of parameters.*

**Example:**
```cpp
#include <iostream>
using namespace std;

template <typename... Args>
void print(Args... args) {
    (cout << ... << args) << endl;  // Fold expression (C++17)
}

int main() {
    print(1, 2, 3, "hello", 4.5);  // Can accept any number of arguments
    return 0;
}
```





### ★ Question 66: Explain the concept of 'move constructors' and 'move assignment operators' in C++.
*Move constructors and move assignment operators are used to transfer ownership of resources from one object to another without performing a deep copy, improving performance, especially in the context of temporary objects.*

- **Move Constructor**: Transfers resources from one object to another when an object is initialized.
  
- **Move Assignment Operator**: Transfers resources when an existing object is assigned a new value.

**Example (Move Constructor and Move Assignment):**
```cpp
#include <iostream>
#include <vector>
using namespace std;

class MyClass {
private:
    vector<int> data;
public:
    MyClass(vector<int> vec) : data(move(vec)) {}  // Move constructor

    MyClass& operator=(vector<int> vec) {  // Move assignment operator
        data = move(vec);
        return *this;
    }

    void print() {
        for (int n : data) cout << n << " ";
        cout << endl;
    }
};

int main() {
    vector<int> vec = {1, 2, 3};
    MyClass obj1(move(vec));  // Move constructor

    vector<int> vec2 = {4, 5, 6};
    MyClass obj2({});
    obj2 = move(vec2);  // Move assignment operator
    obj2.print();  // Output: 4 5 6
    return 0;
}
```



### ★ Question 67: How would you implement an LRU (Least Recently Used) Cache in C++?
*An LRU cache is a data structure that stores a limited number of items, removing the least recently used item when the cache exceeds its capacity. This can be implemented using a combination of a **doubly linked list** and a **hash map**.*

- **Hash Map**: For fast lookups.
- **Doubly Linked List**: For maintaining the order of access, with the least recently used item at the head.

**Example:**
```cpp
#include <iostream>
#include <unordered_map>
#include <list>
using namespace std;

class LRUCache {
private:
    int capacity;
    unordered_map<int, list<pair<int, int>>::iterator> cache;
    list<pair<int, int>> lruList;  // Holds key-value pairs in order of access

public:
    LRUCache(int cap) : capacity(cap) {}

    int get(int key) {
        if (cache.find(key) != cache.end()) {
            lruList.splice(lruList.begin(), lruList, cache[key]);  // Move to front
            return cache[key]->second;
        }
        return -1;  // Not found
    }

    void put(int key, int value) {
        if (cache.find(key) != cache.end()) {
            lruList.splice(lruList.begin(), lruList, cache[key]);  // Move to front
            cache[key]->second = value;
        } else {
            if (lruList.size() == capacity) {
                cache.erase(lruList.back().first);  // Remove least recently used
                lruList.pop_back();
            }
            lruList.push_front({key, value});
            cache[key] = lruList.begin();
        }
    }
};

int main() {
    LRUCache lru(2);
    lru.put(1, 1);
    lru.put(2, 2);
    cout << lru.get(1) << endl;  // Output: 1
    lru.put(3, 3);  // Evicts key 2
    cout << lru.get(2) << endl;  // Output: -1 (not found)
    return 0;
}
```



### ★ Question 68: How does C++ handle exception safety in resource management?
*C++ provides various levels of exception safety (no-throw guarantee, basic guarantee, and strong guarantee) to ensure that resources are managed properly even in the event of exceptions.*

- **Basic Guarantee**: The object remains in a valid state even if an exception occurs, but no rollback of operations is guaranteed.
- **Strong Guarantee**: Operations will either complete successfully or the object remains unchanged.
- **No-Throw Guarantee**: The operation will not throw any exception.

**Example (Exception Safety in Resource Management):**
```cpp
#include <iostream>
#include <vector>
using namespace std;

class MyClass {
    vector<int> data;
public:
    MyClass(vector<int> vec) : data(move(vec)) {}

    void addElement(int elem) {
        data.push_back(elem);  // This operation may throw
    }

    void print() {
        for (int n : data) cout << n << " ";
        cout << endl;
    }
};

int main() {
    try {
        MyClass obj({1, 2, 3});
        obj.addElement(4);  // May throw an exception
    } catch (...) {
        cout << "Exception caught!" << endl;
    }
    return 0;
}
```



### ★ Question 69: What is the use of 'std::atomic' in C++?
*`std::atomic` is used in C++ for performing atomic operations on variables, ensuring that operations are thread-safe without requiring a mutex. It allows multiple threads to safely modify shared data.*

- **Atomic Operations**: Operations like load, store, fetch-and-add, and compare-and-swap are performed atomically.

**Example:**
```cpp
#include <iostream>
#include <atomic>
#include <thread>
using namespace std;

atomic<int> count(0);

void increment() {
    for (int i = 0; i < 1000; ++i) {
        count.fetch_add(1, memory_order_relaxed);
    }
}

int main() {
    thread t1(increment);
    thread t2(increment);

    t1.join();
    t2.join();

    cout << "Count: " << count << endl;  // Output: 2000
    return 0;
}
```



### ★ Question 70: How do you implement custom allocators in C++?
*Custom allocators in C++ allow you to control memory allocation and deallocation. This is typically done by creating a class that defines `allocate` and `deallocate` methods.*

**Example:**
```cpp
#include <iostream>
#include <memory>
#include <vector>
using namespace std;

template <typename T>
struct MyAllocator {
    typedef T value_type;

    MyAllocator() = default;

    T* allocate(std::size_t n) {
        std::cout << "Allocating " << n << " elements." << std::endl;
        return static_cast<T*>(::operator new(n * sizeof(T)));
    }

    void deallocate(T* p, std::size_t n) {
        std::cout << "Deallocating " << n << " elements." << std::endl;
        ::operator delete(p);
    }
};

int main() {
    vector<int, MyAllocator<int>> vec;
    vec.push_back(1);
    vec.push_back(2);
    vec.push_back(3);
    return 0;
}
```



### ★ Question 71: What is a memory model in C++?
*C++ memory model defines how threads interact through memory and what operations on shared data are allowed. It specifies the rules for memory ordering, synchronization, and visibility of data across threads.*

- **Memory Order**: Ensures that operations are performed in the correct order across different threads.
- **Synchronization**: Uses atomic operations and mutexes to prevent race conditions.

**Example:**
```cpp
#include <iostream>
#include <atomic>
using namespace std;

atomic<int> a(0);

void threadFunction() {
    a.store(1, memory_order_relaxed);
}

int main() {
    thread t(threadFunction);
    t.join();
    cout << "a: " << a.load(memory_order_relaxed) << endl;  // Output: 1
    return 0;
}
```



### ★ Question 72: Explain the concept of 'copy-and-swap' idiom in C++.
*The copy-and-swap idiom is a technique used to implement the copy assignment operator efficiently and safely. It utilizes copy constructors and swap operations to minimize code duplication and avoid resource leaks.*

**Example:**
```cpp
#include <iostream>
#include <vector>
using namespace std;

class MyClass {
private:
    vector<int> data;
public:
    MyClass(const vector<int>& vec) : data(vec) {}

    // Copy assignment operator using copy-and-swap idiom
    MyClass& operator=(MyClass other) {
        swap(data, other.data);  // Swap with the temporary object
        return *this;
    }

    void print() {
        for (int n : data) cout << n << " ";
        cout << endl;
    }
};

int main() {
    MyClass obj1({1, 2, 3});
    MyClass obj2({4, 5, 6});
    obj2 = obj1;  // Copy assignment
    obj2.print();  // Output: 1 2 3
    return 0;
}
```



### ★ Question 73: What is the purpose of the 'noexcept' specifier in C++?
*The `noexcept` specifier is used to declare that a function does not throw any exceptions. It helps the compiler to optimize the code and provides better guarantees to users of the function.*

- **noexcept** can be applied to functions and lambda expressions.

**Example:**
```cpp
#include <iostream>
using namespace std;

void func() noexcept {
    cout << "This function doesn't throw exceptions!" << endl;
}

int main() {
    func();
    return 0;
}
```



### ★ Question 74: How do you implement a thread pool in C++?
*A thread pool is a collection of threads that can be used to execute tasks concurrently. Threads are reused instead of being created

 and destroyed for each task, improving efficiency.*

**Example:**
```cpp
#include <iostream>
#include <thread>
#include <vector>
#include <queue>
#include <functional>
#include <mutex>
#include <condition_variable>
using namespace std;

class ThreadPool {
private:
    vector<thread> workers;
    queue<function<void()>> tasks;
    mutex tasksMutex;
    condition_variable condVar;
    bool stop = false;

    void worker() {
        while (true) {
            function<void()> task;
            {
                unique_lock<mutex> lock(tasksMutex);
                condVar.wait(lock, [this] { return stop || !tasks.empty(); });
                if (stop && tasks.empty()) return;
                task = move(tasks.front());
                tasks.pop();
            }
            task();
        }
    }

public:
    ThreadPool(size_t numThreads) {
        for (size_t i = 0; i < numThreads; ++i)
            workers.emplace_back(&ThreadPool::worker, this);
    }

    void enqueue(function<void()> task) {
        {
            unique_lock<mutex> lock(tasksMutex);
            tasks.push(move(task));
        }
        condVar.notify_one();
    }

    void shutdown() {
        {
            unique_lock<mutex> lock(tasksMutex);
            stop = true;
        }
        condVar.notify_all();
        for (auto& worker : workers)
            worker.join();
    }
};

int main() {
    ThreadPool pool(2);
    pool.enqueue([] { cout << "Task 1\n"; });
    pool.enqueue([] { cout << "Task 2\n"; });
    pool.shutdown();
    return 0;
}
```



### ★ Question 75: What is a 'dependent type' in C++?
*In C++, dependent types are types that depend on template parameters. They are often used in template metaprogramming to create more general and flexible code.*

**Example:**
```cpp
#include <iostream>
using namespace std;

template <typename T, typename U>
void print(T t, U u) {
    cout << t << " " << u << endl;
}

int main() {
    print(1, 2.5);  // T is int, U is double
    return 0;
}
```

### ★ Question 76: How does C++ implement type erasure in the Standard Library?
*C++ implements type erasure using templates, which allow a class or function to operate on different types without knowing their exact types at compile time. The most notable example of type erasure in the Standard Library is `std::function`, which allows you to store any callable object in a type-safe manner.*

- **Type Erasure**: It hides the specific type of an object while still allowing operations to be performed on it. The implementation typically involves creating a base class with virtual functions and deriving specific implementations.

**Example (Type Erasure with `std::function`):**
```cpp
#include <iostream>
#include <functional>
using namespace std;

void printHello() {
    cout << "Hello, world!" << endl;
}

int main() {
    std::function<void()> f = printHello;  // Type erasure
    f();  // Calls printHello
    return 0;
}
```

Here, `std::function` erases the type of the function and allows it to be stored in a variable, making it callable without knowing its exact type.



### ★ Question 77: How do you optimize the performance of a C++ application?
*Optimizing the performance of a C++ application involves several techniques ranging from code-level optimizations to system-level adjustments.*

1. **Algorithm Optimization**: Use the most efficient algorithm with the right time and space complexity for your problem.
2. **Memory Management**: Minimize memory allocations, use memory pools, and avoid memory leaks.
3. **Cache Optimization**: Take advantage of CPU cache by improving data locality.
4. **Parallelism**: Use multithreading or GPU programming to perform operations concurrently.
5. **Compiler Optimization**: Enable compiler optimization flags (`-O2`, `-O3`, etc.) for better code generation.

**Example (Optimization via Algorithmic Choice):**
```cpp
// Efficient sorting using quicksort instead of bubble sort
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    vector<int> vec = {4, 2, 9, 1, 5};
    sort(vec.begin(), vec.end());  // Optimized sort (quicksort)
    for (int n : vec) cout << n << " ";
    return 0;
}
```



### ★ Question 78: How would you implement a C++ program that can run on both Windows and Linux without modification?
*To make a C++ program portable between Windows and Linux, we need to avoid platform-specific code or use preprocessor directives to handle platform-specific differences.*

1. **Use Cross-Platform Libraries**: Libraries like `Boost` or `Qt` provide cross-platform functionality for system and GUI programming.
2. **Conditional Compilation**: Use `#ifdef` to include platform-specific code for Windows and Linux.

**Example:**
```cpp
#include <iostream>
#ifdef _WIN32
#include <windows.h>  // Windows-specific headers
#elif __linux__
#include <unistd.h>  // Linux-specific headers
#endif

int main() {
    #ifdef _WIN32
    std::cout << "Running on Windows" << std::endl;
    #elif __linux__
    std::cout << "Running on Linux" << std::endl;
    #endif
    return 0;
}
```



### ★ Question 79: What is the significance of 'constexpr' in C++?
*The `constexpr` keyword in C++ is used to indicate that a function or variable is constant and can be evaluated at compile time. It allows the compiler to optimize code by evaluating expressions before the program runs.*

- **For Functions**: `constexpr` functions are evaluated at compile-time if their arguments are constant expressions.
- **For Variables**: `constexpr` variables are initialized with constant expressions and are evaluated at compile-time.

**Example (Using `constexpr`):**
```cpp
#include <iostream>
constexpr int square(int x) {
    return x * x;
}

int main() {
    constexpr int val = 5;
    std::cout << "Square of 5: " << square(val) << std::endl;  // Computed at compile-time
    return 0;
}
```



### ★ Question 80: What are smart pointers in C++ and how do they work?
*Smart pointers in C++ are wrapper objects for raw pointers that automatically manage the memory they point to, helping prevent memory leaks and dangling pointers.*

1. **`std::unique_ptr`**: Represents ownership of a resource. It ensures that only one smart pointer owns a resource at a time.
2. **`std::shared_ptr`**: Allows multiple smart pointers to share ownership of a resource. The resource is deleted when the last `shared_ptr` goes out of scope.
3. **`std::weak_ptr`**: Works with `shared_ptr` to prevent circular references by not affecting the reference count.

**Example (Using `std::unique_ptr`):**
```cpp
#include <iostream>
#include <memory>
using namespace std;

class MyClass {
public:
    void sayHello() { cout << "Hello!" << endl; }
};

int main() {
    unique_ptr<MyClass> ptr = make_unique<MyClass>();  // Memory managed automatically
    ptr->sayHello();
    // Memory is automatically freed when ptr goes out of scope
    return 0;
}
```



### ★ Question 81: How do you implement a binary search tree in C++?
*A binary search tree (BST) is a tree data structure where each node has at most two children, and the left child’s key is less than the parent node’s key, while the right child’s key is greater.*

**Example (Binary Search Tree Implementation):**
```cpp
#include <iostream>
using namespace std;

class BSTNode {
public:
    int data;
    BSTNode* left;
    BSTNode* right;

    BSTNode(int value) : data(value), left(nullptr), right(nullptr) {}
};

class BST {
private:
    BSTNode* root;

    void insert(BSTNode*& node, int value) {
        if (node == nullptr)
            node = new BSTNode(value);
        else if (value < node->data)
            insert(node->left, value);
        else
            insert(node->right, value);
    }

    void inorderTraversal(BSTNode* node) {
        if (node) {
            inorderTraversal(node->left);
            cout << node->data << " ";
            inorderTraversal(node->right);
        }
    }

public:
    BST() : root(nullptr) {}

    void insert(int value) {
        insert(root, value);
    }

    void inorderTraversal() {
        inorderTraversal(root);
        cout << endl;
    }
};

int main() {
    BST tree;
    tree.insert(50);
    tree.insert(30);
    tree.insert(70);
    tree.insert(20);
    tree.insert(40);
    tree.insert(60);
    tree.insert(80);

    tree.inorderTraversal();  // Output: 20 30 40 50 60 70 80
    return 0;
}
```



### ★ Question 82: How do you implement a graph in C++ using an adjacency list?
*An adjacency list is a space-efficient way to represent a graph. It stores a list of neighbors for each vertex in the graph.*

- **Graph Representation**: Use an unordered map (or a vector) where each vertex has a list (or vector) of adjacent vertices.

**Example (Graph using Adjacency List):**
```cpp
#include <iostream>
#include <unordered_map>
#include <list>
using namespace std;

class Graph {
private:
    unordered_map<int, list<int>> adjList;

public:
    void addEdge(int u, int v) {
        adjList[u].push_back(v);  // Add v to u's list of neighbors
        adjList[v].push_back(u);  // If undirected graph, also add u to v's list
    }

    void display() {
        for (auto& pair : adjList) {
            cout << pair.first << ": ";
            for (int neighbor : pair.second) {
                cout << neighbor << " ";
            }
            cout << endl;
        }
    }
};

int main() {
    Graph g;
    g.addEdge(1, 2);
    g.addEdge(1, 3);
    g.addEdge(2, 3);
    g.addEdge(3, 4);

    g.display();
    return 0;
}
```

Output:
```
1: 2 3
2: 1 3
3: 1 2 4
4: 3
```

### ★ Question 83: How would you implement an algorithm to detect a cycle in a directed graph?
*Detecting a cycle in a directed graph can be done using **Depth First Search (DFS)** along with recursion stack tracking. If we revisit a node that is already in the current recursion stack, a cycle is detected.*

**Algorithm (Using DFS and Recursion Stack):**
1. Perform DFS on all unvisited nodes.
2. Maintain a recursion stack during the DFS traversal. If a node is revisited that is already in the stack, a cycle exists.
3. After visiting a node, remove it from the recursion stack to avoid false positives.

**Example (Cycle Detection in Directed Graph):**
```cpp
#include <iostream>
#include <unordered_map>
#include <unordered_set>
#include <vector>
using namespace std;

class Graph {
    unordered_map<int, vector<int>> adjList;

public:
    void addEdge(int u, int v) {
        adjList[u].push_back(v);
    }

    bool dfs(int node, unordered_set<int>& visited, unordered_set<int>& recStack) {
        if (recStack.find(node) != recStack.end()) return true;  // Cycle detected
        if (visited.find(node) != visited.end()) return false;  // Already visited, no cycle

        visited.insert(node);
        recStack.insert(node);

        for (int neighbor : adjList[node]) {
            if (dfs(neighbor, visited, recStack)) return true;
        }

        recStack.erase(node);  // Remove from recursion stack
        return false;
    }

    bool detectCycle() {
        unordered_set<int> visited;
        unordered_set<int> recStack;

        for (const auto& node : adjList) {
            if (dfs(node.first, visited, recStack)) {
                return true;  // Cycle detected
            }
        }

        return false;  // No cycle
    }
};

int main() {
    Graph g;
    g.addEdge(0, 1);
    g.addEdge(1, 2);
    g.addEdge(2, 0);  // This creates a cycle

    if (g.detectCycle())
        cout << "Cycle Detected!" << endl;
    else
        cout << "No Cycle Detected!" << endl;

    return 0;
}
```



### ★ Question 84: What is the difference between stack-based and heap-based memory in C++?
*Stack and heap memory are both used for storing data, but they are managed differently:*

1. **Stack Memory**:
   - Used for local variables and function calls.
   - Memory is automatically managed: when a function exits, the memory is reclaimed.
   - Limited in size and grows downward.
   - Faster access compared to heap memory.

2. **Heap Memory**:
   - Used for dynamic memory allocation (e.g., using `new` or `malloc`).
   - Memory is managed manually (you must `delete` or `free` it).
   - Size is larger, but it can cause fragmentation.
   - Slower access due to the need to manage dynamic allocation.

**Example (Stack vs Heap):**
```cpp
#include <iostream>
using namespace std;

int main() {
    int stackVar = 10;  // Stack memory
    int* heapVar = new int(20);  // Heap memory

    cout << "Stack Variable: " << stackVar << endl;
    cout << "Heap Variable: " << *heapVar << endl;

    delete heapVar;  // Manually deallocate heap memory
    return 0;
}
```



### ★ Question 85: How do you implement a thread-safe linked list in C++?
*To implement a thread-safe linked list, you need to ensure that multiple threads can modify or access the list simultaneously without causing data corruption. This can be achieved by using mutexes or other synchronization mechanisms.*

**Example (Thread-Safe Linked List with `std::mutex`):**
```cpp
#include <iostream>
#include <mutex>
#include <thread>
using namespace std;

template <typename T>
class ThreadSafeList {
    struct Node {
        T data;
        Node* next;
        Node(T val) : data(val), next(nullptr) {}
    };

    Node* head;
    mutable std::mutex mtx;  // Mutex to protect the list

public:
    ThreadSafeList() : head(nullptr) {}

    void addNode(T data) {
        std::lock_guard<std::mutex> lock(mtx);  // Locking the list during modification
        Node* newNode = new Node(data);
        newNode->next = head;
        head = newNode;
    }

    void printList() const {
        std::lock_guard<std::mutex> lock(mtx);  // Locking the list during reading
        Node* current = head;
        while (current) {
            cout << current->data << " ";
            current = current->next;
        }
        cout << endl;
    }
};

int main() {
    ThreadSafeList<int> list;

    // Add nodes in parallel
    thread t1(&ThreadSafeList<int>::addNode, &list, 10);
    thread t2(&ThreadSafeList<int>::addNode, &list, 20);

    t1.join();
    t2.join();

    list.printList();  // Print the list

    return 0;
}
```



### ★ Question 86: What is the difference between 'std::vector' and 'std::deque' in C++?
*Both `std::vector` and `std::deque` are dynamic containers in C++, but they differ in their underlying implementations and use cases:*

1. **`std::vector`**:
   - Implements a dynamic array.
   - Fast access to elements by index (`O(1)`).
   - Slower insertion and deletion at the beginning (`O(n)`).
   - Memory is contiguous.
   
2. **`std::deque`**:
   - Implements a double-ended queue.
   - Allows fast insertion and deletion at both ends (`O(1)`).
   - Slower access by index compared to `std::vector` (`O(n)` in the worst case).
   - Memory is not contiguous (internal array of blocks).

**Example (Vector vs Deque):**
```cpp
#include <iostream>
#include <vector>
#include <deque>
using namespace std;

int main() {
    vector<int> vec = {1, 2, 3};
    deque<int> deq = {1, 2, 3};

    vec.push_back(4);  // Fast at the end
    deq.push_front(0);  // Fast at both ends

    cout << "Vector: ";
    for (int n : vec) cout << n << " ";
    cout << endl;

    cout << "Deque: ";
    for (int n : deq) cout << n << " ";
    cout << endl;

    return 0;
}
```



### ★ Question 87: How do you implement a custom iterator in C++?
*A custom iterator can be implemented by defining a class that behaves like a pointer (supports `++`, `*`, and `!=` operations) for a container.*

**Example (Custom Iterator Implementation):**
```cpp
#include <iostream>
using namespace std;

template <typename T>
class MyContainer {
    T* data;
    size_t size;

public:
    MyContainer(T* arr, size_t n) : data(arr), size(n) {}

    class Iterator {
        T* ptr;
    public:
        Iterator(T* p) : ptr(p) {}

        Iterator& operator++() { 
            ++ptr;
            return *this; 
        }

        bool operator!=(const Iterator& other) const { 
            return ptr != other.ptr;
        }

        T& operator*() { return *ptr; }
    };

    Iterator begin() { return Iterator(data); }
    Iterator end() { return Iterator(data + size); }
};

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    MyContainer<int> container(arr, 5);

    for (auto it = container.begin(); it != container.end(); ++it) {
        cout << *it << " ";
    }
    cout << endl;

    return 0;
}
```



### ★ Question 88: What are the common causes of segmentation faults in C++?
*Segmentation faults typically occur when a program tries to access memory that it is not allowed to. Common causes include:*

1. **Dereferencing a Null Pointer**: Accessing a pointer that is not initialized or has been set to `nullptr`.
2. **Array Out-of-Bounds Access**: Accessing elements outside the valid range of an array.
3. **Invalid Memory Access**: Trying to access freed memory (dangling pointers).
4. **Stack Overflow**: Too deep recursion causing the stack to exceed its allocated size.
5. **Uninitialized Pointers**: Using pointers before they are assigned a valid address.

**Example (Dereferencing Null Pointer):**
```cpp
#include <iostream>
using namespace std;

int main() {
    int* ptr = nullptr;
    cout << *ptr << endl;  // Segmentation fault: dereferencing null pointer
    return 0;
}
```



### ★ Question 89: How would you design an efficient C++ program to handle large datasets?
*To handle large datasets efficiently in C++, consider the following techniques:*

1. **Use Efficient Data Structures**: Choose the right data structure (e.g., `std::unordered_map` for fast lookups).
2. **Optimize Memory Usage**: Use memory pools or custom allocators to minimize overhead.
3. **Use Streaming**: Process data in chunks (streaming) instead of loading everything into memory.
4. **Parallel Processing**: Use multithreading (`std::thread`, `std::async`) or parallel algorithms (e.g

., `std::for_each`) to speed up computation.

**Example (Using Streaming):**
```cpp
#include <iostream>
#include <fstream>
#include <string>
using namespace std;

int main() {
    ifstream file("large_data.txt");
    string line;
    
    while (getline(file, line)) {
        // Process the data
        cout << line << endl;
    }

    file.close();
    return 0;
}
```



### ★ Question 90: What is a deadlock, and how can you avoid it in C++ multithreading?
*Deadlock occurs when two or more threads are blocked forever because each thread is waiting for the other to release resources. To avoid deadlocks:*

1. **Lock Ordering**: Always acquire locks in a predefined order to avoid circular dependencies.
2. **Use `std::unique_lock` and `std::lock`**: These allow safer locking mechanisms.
3. **Avoid Holding Multiple Locks**: Minimize the use of multiple locks at the same time.

**Example (Deadlock Prevention):**
```cpp
#include <iostream>
#include <mutex>
#include <thread>
using namespace std;

mutex mtx1, mtx2;

void func1() {
    lock(mtx1, mtx2);  // Lock both mutexes
    unique_lock<mutex> lk1(mtx1, adopt_lock);
    unique_lock<mutex> lk2(mtx2, adopt_lock);

    // Critical section
}

void func2() {
    lock(mtx1, mtx2);  // Lock both mutexes
    unique_lock<mutex> lk1(mtx1, adopt_lock);
    unique_lock<mutex> lk2(mtx2, adopt_lock);

    // Critical section
}

int main() {
    thread t1(func1);
    thread t2(func2);

    t1.join();
    t2.join();
    return 0;
}
```



### ★ Question 91: How would you use 'std::mutex' and 'std::lock_guard' in C++ for thread synchronization?
*`std::mutex` is used to protect shared resources, and `std::lock_guard` is used to automatically lock and unlock the mutex to avoid race conditions.*

**Example (Using `std::mutex` and `std::lock_guard`):**
```cpp
#include <iostream>
#include <mutex>
#include <thread>
using namespace std;

mutex mtx;

void printValue(int val) {
    lock_guard<mutex> lock(mtx);  // Lock is automatically released at the end of the scope
    cout << "Value: " << val << endl;
}

int main() {
    thread t1(printValue, 1);
    thread t2(printValue, 2);
    
    t1.join();
    t2.join();

    return 0;
}
```

---
🙂 Keep Learn Smile!
