C++ Quick Syntax Reference - Source Code

*** Hello World ***
 
#include <iostream>
 
int main()
{
  std::cout << "Hello World";
}
 
 
#include <iostream>
using namespace std;
 
int main()
{
  cout << "Hello World";
}
 
*** Compile and Run ***
 
#include <iostream>
using namespace std;
 
int main()
{
  cout << "Hello World";
  cin.get();
}

// single-line comment
 
/* multi-line
   comment */

*** Variables ***
 
#include <iostream>
using namespace std;

int main()
{
  // Declaration and assignment
  int myInt = 50;
  int myAlt (50);
  int x = 1, y = 2, z;

  // Output
  cout << x << y; // "12"

  int myOct = 062;  // octal notation (0)
  int myHex = 0x32; // hexadecimal notation (0x)
  int myBin = 0b0011'0010; // binary notation (0b)
}


// Variable scope
int globalVar; // global variable
int main() { int localVar; } // local variable
 
 
// Default values
int globalVar; // initialized to 0
int main() { int localVar; } // uninitialized
 
 
// Integer types
#include <iostream>

int main()
{
  char  myChar  = 0; // -128   to +127
  short myShort = 0; // -32768 to +32767
  int   myInt   = 0; // -2^31  to +2^31-1
  long  myLong  = 0; // -2^31  to +2^31-1
  long long myL2 = 0; // -2^63 to +2^63-1

  std::cout << sizeof(myChar)  // 1 byte (per definition)
            << sizeof(myShort) // 2
            << sizeof(myInt)   // 4
            << sizeof(myLong)  // 4
            << sizeof(myL2);   // 8

  __int8   myInt8   = 0; // 8 bits
  __int16  myInt16  = 0; // 16 bits
  __int32  myInt32  = 0; // 32 bits
  __int64  myInt64  = 0; // 64 bits

  signed char  myChar  = 0; // -128   to +127
  signed short myShort = 0; // -32768 to +32767
  signed int   myInt   = 0; // -2^31  to +2^31-1
  signed long  myLong  = 0; // -2^31  to +2^31-1
  signed long long myL2= 0; // -2^63  to +2^63-1

  unsigned char  myChar  = 0; // 0 to 255
  unsigned short myShort = 0; // 0 to 32767
  unsigned int   myInt   = 0; // 0 to 2^32-1
  unsigned long  myLong  = 0; // 0 to 2^32-1
  unsigned long long myL2= 0; // 0 to 2^64-1

  unsigned uInt; // unsigned int
  signed sInt;   // signed int

  short myShort; // short int
  long myLong;   // long int

  // Floating-point types
  float  myFloat  = 3.14; // 3.4E +/- 38 (7 digits)
  double myDouble = 3.14; // 1.7E +/- 308 (15 digits)
  long double myLongDouble = 3.14; // same as double

  myFloat = 12345.678; // rounded to 12345.68
  myFloat = 3e2; // 3*10^2 = 300

  // Char type
  char c = 'x'; // assigns 120 (ASCII for 'x')
  std::cout << c; // prints 'x'

  int i = c;            // assigns 120
  std::cout << i;       // prints 120
  std::cout << (char)i; // prints 'x'

  char ascii = u8'x'; // use UTF-8 encoding
  
  // Bool type
  bool b = false; // true or false value
}
 
*** Operators ***
 
int main()
{
  // Arithmetic operators
  float f = 3 + 2; // 5 // addition
        f = 3 - 2; // 1 // subtraction
        f = 3 * 2; // 6 // multiplication
        f = 3 / 2; // 1.5 // division
        f = 3 % 2; // 1 // modulus (division remainder)

  // Combined assignment operators
  int i = 5;
      i += 5; // i = i+5;
      i -= 5; // i = i-5;
      i *= 5; // i = i*5; 
      i /= 5; // i = i/5;
      i %= 5; // i = i%5;

  // Increment and decrement operators
  i++; // i = i+1;
  i--; // i = i-1;

  i++; // post-increment
  i--; // post-decrement
  ++i; // pre-increment
  --i; // pre-decrement

  int j;
  i = 5; j = i++; // j=5, i=6   
  i = 5; j = ++i; // j=6, i=6

  // Comparison operators
  bool b = (2 == 3); // false // equal to
       b = (2 != 3); // true  // not equal to
       b = (2 > 3);  // false // greater than
       b = (2 < 3);  // true  // less than
       b = (2 >= 3); // false // greater than or equal to
       b = (2 <= 3); // true  // less than or equal to

  // Logical operators
  b = (true && false); // false // logical and
  b = (true || false); // true  // logical or
  b = !(true);         // false // logical not

  // Bitwise operators
  i = 5 & 4;  // 101 & 100 = 100 (4) // and
  i = 5 | 4;  // 101 | 100 = 101 (5) // or
  i = 5 ^ 4;  // 101 ^ 100 = 001 (1) // xor
  i = 4 << 1; // 100 << 1  =1000 (8) // left shift
  i = 4 >> 1; // 100 >> 1  =  10 (2) // right shift
  i = ~4;     // ~00000100 = 11111011 (-5) // invert

  i=5; i &= 4; // 101 & 100 = 100 (4) // and
  i=5; i |= 4; // 101 | 100 = 101 (5) // or
  i=5; i ^= 4; // 101 ^ 100 = 001 (1) // xor
  i=5; i <<= 1;// 101 << 1  =1010 (10)// left shift
  i=5; i >>= 1;// 101 >> 1  =  10 (2) // right shift
}

*** Pointers ***
 
#include <iostream>

int main()
{
  // Creating pointers
  int* p; // pointer to an integer
  int *q; // alternative syntax

  int i = 10;
  p = &i; // address of i assigned to p

  // Dereferencing pointers
  std::cout << "Address of i: " <<  p; // ex. 0017FF1C
  std::cout << "Value of i: "   << *p; // "10"

  p = &i;  // address of i assigned to p
  *p = 20; // value of i changed through p
  int* p2 = p; // copy of p (copies address stored in p)
  int** r = &p; // pointer to p (assigns address of p)

  std::cout << "Address of p: " << r;  // ex. 0017FF28
  std::cout << "Address of i: " << *r; // ex. 0017FF1C
  std::cout << "Value of i: "   << **r;// "20"

  // Dynamic allocation
  int* d = new int; // dynamic allocation
  delete d; // release allocated memory

  // Null pointer
  d = nullptr; // mark as null pointer
  delete d; // safe
  if (d != nullptr) { *d = 10; } // check for null pointer
  if (d) { *d = 10; } // alternative
}

*** References ***

#include <iostream>
using namespace std;

int main()
{
  int x = 5;
  int& r = x;    // r is an alias to x
  int &s = x;    // alternative syntax
  r = 10;        // assigns value to r/x
  int* ptr = &x; // ptr assigned address to x

  int&& ref = 1 + 2; // rvalue reference
  ref += 3;
  cout << ref; // "6"
}
 
*** Arrays ***
 
#include <iostream>

int main()
{
  // Array declaration and allocation
  int myArray[3]; // integer array with 3 elements

  // Array assignment
  myArray[0] = 1;
  myArray[1] = 2;
  myArray[2] = 3;

  int myArray2[3] = { 1, 2, 3 };
  int myArray3[] = { 1, 2, 3 };

  std::cout << myArray[0]; // "1"

  // Multi-dimensional arrays
  int myArray4[2][2] = { { 0, 1 }, { 2, 3 } };
  myArray4[0][0] = 0;
  myArray4[0][1] = 1;

  // Dynamic arrays
  int* p = new int[3]; // dynamically allocated array
  *(p+1) = 10; // p[1] = 10;
  delete[] p; // release allocated array
}


#include <iostream>

int main()
{
  // Array size
  int myArray[2] = { 1, 2 };
  myArray[2] = 3; // error: out of bounds
  int length = sizeof(myArray) / sizeof(int); // 2

  int size = 3;
  int* p = new int[size]; // dynamically allocated array
  delete[] p; // release allocated array
  p = nullptr; // mark pointer as unused
}

*** String ***
 
#include <string>
using namespace std;

int main()
{
  string h = "Hello";
  string w (" World");

  // String combining
  string a = h + w; // Hello World
  h += w; // Hello World

  string b = "Hello" + w; // ok

  char *c = "World"; // C-style string
  b = (string)c + c; // ok
  b = "Hello" + (string)" World"; // ok
  b = "Hel" "lo"; // ok

  // Escape characters
  string s = "Hello \
              World";
  s = "Hello \n World";

  s = "\0177" // octal character (0-0177)
  s = "\0x7F" // hexadecimal character (0-0x7F)

  string escaped = "c:\\Windows\\System32\\cmd.exe";
  string raw = R"(c:\Windows\System32\cmd.exe)";

  // String compare
  s = "Hello";
  bool x = (s == "Hello"); // true

  // String functions
  size_t i = s.length(); // 5, length of string
  i = s.size(); // 5, same as length()
  s.substr(0,2); // "He"
  char y = s[0]; // 'H'

  // String encodings
  wstring s1 = L"Hello";
  wchar_t *s2 = L"Hello";
  string s3 = "Compiler-defined encoding";
  string s4 = u8"UTF-8 string";
  u16string s5 = u"UTF-16 string";
  u32string s6 = U"UTF-32 string";
  string s7 = u8"An asterisk: \u002A";
}
 
*** Conditionals ***

#include <iostream>
using namespace std;

int main()
{
  int x = 1;

  // If statement
  if (x < 1) {
    cout << x << " < 1";
  }
  else if (x > 1) {
    cout << x << " > 1";
  }
  else {
    cout << x << " == 1";
  }

  if (x < 1)
    cout << x << " < 1";
  else if (x > 1)
    cout << x << " > 1";
  else
    cout << x << " == 1";

  // Switch statement
  switch (x)
  {
    case 0: cout << x << " is 0"; break;
    case 1: cout << x << " is 1"; break;
    default: cout << x << " is not 1 or 2"; break;
  }

  // Ternary operator
  x = (x < 0.5) ? 0 : 1; // ternary operator
  (x < 0.5) ? x = 0 : x = 1; // alternative syntax

  // Initializers
  int a = 2, b = 3;

  if (int sum = a+b; sum == 5) {
    cout << sum << " is 5";
  }

  switch (int sum = a+b; sum) {
    case 5: cout << sum << " is 5"; break;
  }
}
 
*** Loops ***
 
#include <iostream>
using namespace std;

int main()
{
  // While loop
  int i = 0;
  while (i < 10) { 
    cout << i++; // 0-9
  }

  // Do-while loop
  int j = 0;
  do { 
    cout << j++; // 0-9
  } while (j < 10); 

  // For loop
  for (int k = 0; k < 10; k++) { 
    cout << k; // 0-9
  }

  for (int k = 0, m = 0; k < 5; k++, m--) {
    cout << k+m; // "00000"
  }

  int a[3] = {1, 2, 3};
  for (int &i : a) {
    cout << i; // "123"
  }

  // Break and continue
  for (int i = 0; i < 10; i++)
  {
    if (i == 5) break; // end loop
    if (i == 3) continue; // start next iteration
    cout << i; // "0124"
  }

  // Goto statement
  goto myLabel; // jump to label
  myLabel:      // label declaration
}
 
*** Functions ***
 
#include <iostream>
#include <string>
using namespace std;

void myFunction()
{
  cout << "Hello World";
}

void myFunction(string a, string b)
{
  cout << a + " " + b;
}

int main()
{
  myFunction(); // "Hello World"
  myFunction("Hello", "World"); // "Hello World"
}
  
 
#include <iostream>
#include <string>
using namespace std;

// Default parameter values
void myFunction(string a, string b = "Earth")
{
  cout << a + " " + b;
}

int main()
{
  myFunction("Hello"); // "Hello Earth"
}
 
 
#include <iostream>
#include <string>
using namespace std;

// Function overloading
void myFunction(string a, string b) { cout << a+" "+b; }
void myFunction(string a)           { cout << a; }
void myFunction(int a)              { cout << a; }
 
 
#include <iostream>
using namespace std;

// Return statement
int getSum(int a, int b)
{
  return a + b;
}

void dummy() { return; }

int main()
{
  cout << getSum(5, 10); // "15"
  return 0;
}
 
 
// Forward declarations
void myFunction(int); // prototype
int main()
{
  myFunction(0);
}
void myFunction(int a) {}


// Pass by value
#include <iostream>
#include <string>
using namespace std;
 
void change(int i)    { i = 10; }
void change(string s) { s = "Hello World"; }
 
int main()
{
  int x = 0;     // value type
  change(x);     // value is passed
  cout << x;     // "0"
 
  string y = ""; // reference type
  change(y);     // object copy is passed
  cout << y;     // ""
}


// Pass by reference
#include <iostream>
using namespace std;
 
void change(int& i) { i = 10; }
 
int main()
{
  int x = 0; // value type
  change(x); // reference is passed
  cout << x; // "10"
}


// Pass by address
#include <iostream>
using namespace std;
 
void change(int* i) { *i = 10; }
 
int main()
{
  int x = 0;  // value type
  change(&x); // address is passed
  cout << x;  // "10"
}
 
 
// Return by value
#include <iostream>
using namespace std;
 
int byVal(int i) { return i + 1; }
 
int main()
{
  int a = 10;
  cout << byVal(a); // "11"
}
 
 
// Return by reference
#include <iostream>
using namespace std;

int& byRef(int& i) { return i; }
 
int main()
{
  int a = 10;
  cout << byRef(a); // "10"
}
 
 
// Return by address
#include <iostream>
using namespace std;

int* byAdr(int* i) { return i; }
 
int main()
{
  int a = 10;
  cout << *byAdr(&a); // "10"
}
 
 
// Inline functions
inline int myInc(int i) { return i++; }


// Auto and Decltype
#include <iostream>
#include <vector>
using namespace std;

int main()
{
  auto i = 5;     // int
  auto d = 3.14;  // double
  auto b = false; // bool

  int& iRef = i;
  auto myAuto = iRef; // int

  auto& myRef = iRef; // int&

  int i = 1;
  auto&& a = i; // int& (lvalue reference)
  auto&& b = 2; // int&& (rvalue reference)

  // Since C++11
  vector<int> myVector { 1, 2, 3 };
  for (auto& x : myVector) { cout << x; } // "123"

  // Prior to C++11
  for(vector<int>::size_type i = 0; i != myVector.size(); i++) {
    cout << myVector[i]; // "123"
  }

  decltype(3) b = 3; // int&&
  decltype(auto) = 3; // int&&
  decltype(5) getFive() { return 5; } // int

  // C++11
  auto getValue(int x) -> decltype(x) { return x; } // int

  // C++14
  auto getValue(int x) { return x; } // int
  decltype(auto) getRef(int& x) { return x; } // int&
}

// Returning multiple values
#include <tuple>
#include <iostream>
using namespace std;

auto getTuple() 
{
  return make_tuple(5, 1.2, 'b');
}

int main()
{
  auto mytuple = getTuple();
  cout << get<0>(mytuple); // "5"

  int i;
  double d;

  // Unpack tuple into variables
  tie(i, d, ignore) = getTuple();
  cout << i << " " << d; // "5 1.2"
}


#include <tuple>
#include <iostream>
using namespace std;

tuple<int, double, char> getTuple() 
{
  return { 5, 1.2, 'b' };
}

int main()
{
  auto [i, d, c] = getTuple();
  cout << i; // "5"
}


// Lambda functions
#include <iostream>
using namespace std;

int main()
{
  auto sum = [](int x, int y) -> int 
  { 
    return x + y; 
  };

  cout << sum(2, 3); // "5"
}


// Auto type deduction
auto sum = [](auto x, auto y) { return x + y; };


#include <iostream>
#include <functional>
using namespace std;

void call(int arg, function<void(int)> func) 
{
  func(arg);
}

int main() 
{
 auto printSquare = [](int x) { cout << x*x; };
 call(2, printSquare); // "4"
}


#include <iostream>
#include <functional>
using namespace std;

void call(function<void()> func) { func(); }

int main() {
 int i = 2;
 auto printSquare = [i]() { cout << i*i; };
 call(printSquare); // "4"
}


#include <iostream>
using namespace std;

int main() 
{
  int a = 1;
  [&a](int x) { a += x; }(2);
  cout << a; // "3"
}


#include <iostream>
using namespace std;

int main() 
{
  int a = 1, b = 1;
  [&, b]() mutable { b++; a += b; }();
  cout << a << b; // "31"
}


#include <iostream>
using namespace std;

int main() 
{
  int a = 1;
  [&, b = 2]() { a += b; }();
  cout << a; // "3"
}

*** Class ***
 
class MyRectangle
{
 public:
  int x, y;
  int getArea();
};
 
int MyRectangle::getArea() { return x * y; }

int main()
{
  MyRectangle r; // object creation
  r.x = 10;
  r.y = 5;
  int z = r.getArea(); // 50 (5*10)

  MyRectangle r2; // another instance of MyRectangle
  r2.x = 25;      // not same as r.x

  MyRectangle r3;
  MyRectangle *p = &r3; // object pointer
 
  p->getArea();
  (*p).getArea(); // alternative syntax
}
 
 
class MyClass; // class prototype
 
class OtherClass
{
  MyClass* m;
};
 
class MyClass
{
  OtherClass* o;
};
 
*** Constructor ***

class MyRectangle
{
 public:
  int x, y;
  MyRectangle();
  MyRectangle(int, int);
};
 
MyRectangle::MyRectangle() { x = 10; y = 5; }
MyRectangle::MyRectangle(int x, int y)
{
  this->x = x; this->y = y;
}

int main()
{
  // Calls parameterless constructor
  MyRectangle r;
 
  // Calls constructor accepting two integers
  MyRectangle t(2,3);
}


// Calling another constructor
MyRectangle::MyRectangle() : MyRectangle(10, 5);

// Field initialization
class MyRectangle
{
 public:
  int x = 10;
  int y = 5;
  MyRectangle(int, int);
};

MyRectangle::MyRectangle(int a, int b) : x(a), y(b) {}


// Destructor
class Semaphore
{
 public:
  bool *sem;
 
  Semaphore()  { sem = new bool; }
  ~Semaphore() { delete sem; }
};
 

// Special member functions
class A
{
 public:
  // Explicitly include default constructor
  A() = default;

  // Disable move constructor
  A(A&&) = delete;

  // Disable move assignment operator
  A& operator=(A&) = delete;

  // Disable copy constructor
  A(const A&) = delete;

  // Disable copy assignment operator
  A& operator=(const A&) = delete;
};


// Object initialization
class MyClass
{
 public:
  int i;
  MyClass() = default;
  MyClass(int x) : i(x) {}
};

int main()
{
  // Direct initialization
  MyClass a(5);
  MyClass b;

  // Value initialization
  const MyClass& a = MyClass();

  // Copy initialization
  MyClass a = MyClass();
  MyClass b(a);

  // New initialization
  MyClass* a = new MyClass();
  MyClass& b = *new MyClass();
  // …
  delete a, b;

  // Aggregate initialization
  MyClass a = { 2 }; // i is 2

  // Uniform initialization
  MyClass a { 3 }; // i is 3
}


// Uniform initialization
#include <string>
#include <vector>
using namespace std;

int main() 
{
  int i { 1 };
  string s { "Hello" };
  int a[] { 1, 2 };
  int *p = new int [2] { 1, 2 };
  vector<string> box { "one", "two" };
}
 

#include <iostream>
using namespace std;

class NewClass
{
 public:
  NewClass(initializer_list<int> args)
  {
    for (auto x : args)
      cout << x << " ";
  }
};

int main() 
{
  NewClass a { 1, 2, 3 }; // "1 2 3"
}

*** Inheritance ***
 
class Rectangle
{
 public:
  int x, y;
  int getArea() { return x * y; }
};
 
class Square : public Rectangle {};

int main()
{
  Square s;
  Rectangle& r = s;  // reference upcast
  Rectangle* p = &s; // pointer upcast

  Square& a = (Square&) r;  // reference downcast
  Square& b = (Square&) *p; // pointer downcast
}


// Constructor inheritance
#include <iostream>
using namespace std;

class B1 
{
 public:
  int x;
  B1() : x(5) {}
};

class D1 : public B1 {};

int main() 
{
  D1 d; // calls parameterless constructors of D1 and B1
  cout << d.x; // "5"
}


class B2
{
 public:
  int x;
  B2(int a) : x(a) {}
};

class D2 : public B2
{
 public:
  D2(int i) : B2(i) {} // call base constructor
};


class D2 : public B2
{
 public:
  using B2::B2; // inherit all constructors
  int y {0};
};

int main() 
{
  D2 d(3);
  cout << d.x; // "3"
}


// Multiple inheritance
class Person {}
class Employee {}

class Teacher: public Person, public Employee {}
 
*** Overriding ***
 
class Rectangle
{
 public:
  int x, y;
  int getArea() { return x * y; }
};
 
class Triangle : public Rectangle
{
 public:
  Triangle(int a, int b) { x = a; y = b; }
  int getArea() { return x * y / 2; }
};

int main()
{
  Triangle t = Triangle(2,3);
  t.getArea(); // 3 (2*3/2) calls Triangle's version

  Rectangle& r = t;
  r.getArea(); // 6 (2*3) calls Rectangle's version
}
 
 
class Rectangle
{
 public:
  int x, y;
  virtual int getArea() { return x * y; }
};

class Triangle : public Rectangle
{
 public:
  Triangle(int a, int b) { x = a; y = b; }
  int getArea() { return x * y / 2; }
};

int main()
{
  Triangle t = Triangle(2,3);
  Rectangle& r = t;
  r.getArea(); // 3 (2*3/2) calls Triangle's version
}
 
 
// Base class scoping
class Rectangle
{
 public:
  int x, y;
  virtual int getArea() { return x * y; }
};

class Triangle : public Rectangle
{
 public:
  Triangle(int a, int b) { x = a; y = b; }
  int getArea() { return Rectangle::getArea() / 2; }
};
 
// Calling base class constructor
class Rectangle
{
 public:
  int x, y;
  Rectangle(int a, int b) { x = a; y = b; }
};
 
class Triangle : public Rectangle
{
 public:
  Triangle(int a, int b) : Rectangle(a,b) {}
};

// Final specifier
class Base 
{
  virtual void foo() final {}
}

class Derived 
{
  void foo() {} // error: Base::foo marked as final
}
 

class B final {}
class D : B {} // error: B marked as final


*** Access Levels ***
 
class MyClass
{
  int myPrivate;
 
 public:
  int myPublic;
  void publicMethod();
};
 
 
class MyClass
{
  // Unrestricted access
  public: int myPublic;
 
  // Defining or derived class only
  protected: int myProtected;
 
  // Defining class only
  private: int myPrivate;
 
  void test()
  {
    myPublic    = 0; // allowed
    myProtected = 0; // allowed
    myPrivate   = 0; // allowed
  }
};

class MyChild : public MyClass
{
  void test()
  {
    myPublic    = 0; // allowed
    myProtected = 0; // allowed
    myPrivate   = 0; // inaccessible
  }
};

class OtherClass
{
  void test(MyClass& c)
  {
    c.myPublic    = 0; // allowed
    c.myProtected = 0; // inaccessible
    c.myPrivate   = 0; // inaccessible
  }
};
 
// Friend classes and functions
class MyClass
{
  int myPrivate;
 
  // Give OtherClass access
  friend class OtherClass;
};
 
class OtherClass
{
  void test(MyClass c) { c.myPrivate = 0; } // allowed
};
 
class MyClass
{
  int myPrivate;
 
  // Give myFriend access
  friend void myFriend(MyClass c);
};
 
void myFriend(MyClass c) { c.myPrivate = 0; } // allowed
 
*** Static ***
 
class MyCircle
{
 public:
  double r;         // instance field (one per object)
  static double pi; // static field (only one copy)

  double getArea() { return pi * r * r; }
  static double newArea(double a) { return pi * a * a; }
};
 
double MyCircle::pi = 3.14;

int main()
{
  double p = MyCircle::pi;
  double a = MyCircle::newArea(1);
}
  
// Static local variables
void myFunc()
{
  static int count = 0; // holds # of calls to function
  count++;
}

// Static global variables
static int myGlobal; // only visible within this source file

*** Enum ***
 
enum Color { Red, Green, Blue };

int main()
{
  Color c = Red;

  switch(c)
  {
    case Red:   break;
    case Green: break;
    case Blue:  break;
  }
}
 
 
enum Color
{
  Red,   // 0
  Green, // 1
  Blue   // 2
};
 
 
enum Color
{
  Red   = 5,        // 5
  Green = Red,      // 5
  Blue  = Green + 2 // 7
};


// Strongly typed enums
enum class Speed 
{
    Fast,
    Normal,
    Slow
};

int main()
{
  Speed s = Speed::Fast;

  if (s == Speed::Fast) {} // ok
  if (s == 0) {} // error
}

*** Struct and Union ***
 
struct Point
{
  int x, y;
} r, s; // object declarations
 
int main()
{
  Point p, q; // object declarations
}
 

struct Point 
{
  int x, y;
} r = { 2, 3 }; // set values of x and y
 
int main() 
{
  // Aggregate initialization
  Point p = { 2, 3 };

  // Uniform initialization
  Point q { 2, 3 };
}

 
union Mix
{
  char c;  // 1 byte
  short s; // 2 bytes
  int i;   // 4 bytes
} m;

int main()
{
  m.c = 0xFF; // set first 8 bits
  m.s = 0;    // reset first 16 bits
}
 

union Mix
{
  char c[4];                  // 4 bytes
  struct { short hi, lo; } s; // 4 bytes
  int i;                      // 4 bytes
} m;

int main()
{
  m.i=0xFF00F00F; // 11111111 00000000 11110000 00001111
  m.s.lo;         // 11111111 00000000
  m.s.hi;         //                   11110000 00001111
  m.c[3];         // 11111111
  m.c[2];         //          00000000
  m.c[1];         //                   11110000
  m.c[0];         //                            00001111
}
 
 
// Anonymous union
int main()
{
  union { short s; }; // defines an unnamed union object
  s = 15;
}
 
*** Operator Overloading ***
 
class MyNum
{
 public:
  int val;
  MyNum(int i) : val(i) {}
 
  MyNum add(MyNum &a)
  { return MyNum( val + a.val ); }

  MyNum operator +(MyNum &a)
  { return MyNum( val + a.val ); }

  MyNum& operator++() // ++ prefix
  { ++val; return *this; }

  MyNum operator++(int) // postfix ++
  {
    MyNum t = MyNum(val);
    ++val;
    return t;
  }
};

int main()
{
  MyNum a = MyNum(10), b = MyNum(5);
  MyNum c = a.add(b);
        c = a + b;
  MyNum d = a.operator+(b);
}
 
*** Custom Conversions ***
 
// Implicit conversion methods
class MyNum
{
 public:
  int value;
  MyNum(int i) { value = i; }
};

int main()
{
  MyNum a = 5;        // implicit conversion
  MyNum b = MyNum(5); // object construction
  MyNum c(5);         // object construction
  MyNum d = 'H';      // implicit conversion
}
 
 
// Explicit conversion methods
class MyNum
{
 public:
  int value;
  explicit MyNum(int i) { value = i; }
};

int main()
{
  MyNum a = 5;        // error
  MyNum b(5);         // allowed
  MyNum c = MyNum(5); // allowed
}


// Conversion operators
class MyNum
{
 public:
  int value;
  operator int() { return value; }
};

int main()
{
  MyNum A { 5 };
  int i = A; // 5
}


// Explicit conversion operators
class True
{
  explicit operator bool() const { 
    return true;
  }
};

int main()
{
  True a, b;
  if (a == b) {} // error
  if ((bool)a == (bool)b) {} // allowed
  if (a) {} // allowed
}

*** Namespaces ***
 
namespace furniture
{
  class Table {};
}
 
namespace html
{
  class Table {};
}

int main()
{
  furniture::Table fTable;
  html::Table hTable;
}
 
 
// Nesting namespaces

// Prior to C++17
namespace furniture
{
  namespace wood { class Table {}; }
}

// Since C++17
namespace furniture::wood { class Table {}; }

int main()
{
  furniture::wood::Table fTable;
}
 
 
// Importing namespaces
namespace html
{
  class Table {};
}

namespace furniture
{
  namespace wood { class Table {}; }
}

using namespace html; // global namespace import
 
int main()
{
  using namespace html; // local namespace import

  // Namespace member import
  using html::Table; // import a single namespace member

  // Namespace alias
  namespace myAlias = furniture::wood; // namespace alias
  myAlias::Table fTable;
}
 
 
// Type alias
typedef my::name::MyClass MyType;
MyType t;

typedef struct { int len; } Length;
Length a, b, c;

using MyType = my::name::MyClass;


// Include input/output prototypes
#include <iostream>

// Import standard library namespace to global scope 
using namespace std;

*** Constants ***
 
int main()
{
  const int var = 5;
  int const var2 = 10; // alternative order

  // Constant pointers
  int myPointee;
  int *const p = &myPointee; // pointer constant
  const int *q = &var; // pointee constant
  const int *const r = &var; // pointer & pointee constant

  // Constant references
  const int& y = var; // referee constant
}
 
 
// Constant objects
class MyClass
{
  public: int x;
  void setX(int a) { x = a; }

  // Constant return type and parameters
  const int& getX() const { return x; }
};

int main()
{
  const MyClass a, b;
  a = b;       // error: object is const
  a.x = 10;    // error: object field is const
  a.setX(2); // error: cannot call non-const method
}


// Constant fields
class MyClass
{
 public:
  int i;
  const int c;
  MyClass() : c(5), i(5) {}
};
 
 
class MyClass
{
 public:
  static int si;
  const static double csd;
  const static int csi = 5;
};
int MyClass::si = 1;
const double MyClass::csd = 1.23;
 

// Constant expressions
constexpr int myConst = 5;
myConst = 3; // error: variable is const
int myArray[myConst + 1]; // allowed

constexpr int getDefaultSize(int multiplier)
{ 
  return 3 * multiplier;
}

// Compile-time evaluation
int myArray[getDefaultSize(10)];

// Run-time evaluation
int mul = 10;
int size = getDefaultSize(mul);

auto answer = [](int i) { return 10+i; };
constexpr int reply = answer(32); // "42"

// Constexpr constructor
class Circle
{
 public:
  int r;
  constexpr Circle(int x) : r(x) {}
};

// Compile-time object
constexpr Circle c1(5);

// Run-time object
int x = 5;
Circle c2(x);

// Constexpr conditional statements
constexpr int debug = 0;
if constexpr(debug) {
  // Discarded if condition is false
}

*** Preprocessor ***
 
#include <iostream> // search default directory
#include "MyFile" // search current, then default
#include "C:\MyFile" // absolute path
#include "..\MyFile" // relative path

// Macros
#define MACRO 0 // macro definition
int x = MACRO; // x = 0

#undef MACRO // macro undefine
#undef MACRO // allowed

// Predefined macros
#include <iostream>
using namespace std;
int main()
{
  cout << "Error in " << __FILE__ << " at line " << __LINE__;
}

// Macro functions
#define SQUARE(x) ((x)*(x))
int main() 
{
  int x = SQUARE(2); // 4
}

#define SQUARE(x) x*x
int main() 
{
  int x = SQUARE(1+1); // 1+1*1+1 = 3
}

  
// Conditional compilation directives
#define DEBUG_LEVEL 3
 
#if DEBUG_LEVEL > 2
 // …
#elif DEBUG_LEVEL == 2
 // …
#else
 // …
#endif
 
 
// Compile if defined
#define DEBUG

#if defined DEBUG
 // …
#elif !defined DEBUG
 // …
#endif

#ifdef DEBUG
 // …
#endif
 
#ifndef DEBUG
 // …
#endif
 
// Error directive
#error Compilation aborted

// Line directive
#line 5 "My MyApp Error"

// Pragma directive
#pragma message( "Hello Compiler" )
#pragma warning(disable : 4507)
 

// Attributes
[[deprecated]] void foo() {} // mark as deprecated

// Mark as deprecated with comment
[[deprecated("foo() is unsafe, use bar() instead")]] void foo() {} 

[[noreturn]] void f() 
{ 
  exit(0); // terminate program
}

*** Exception Handling ***
 
#include <iostream>
using namespace std;

int divide(int x, int y)
{
  if (y == 0) throw 0;
  return x / y;
}

int main()
{
  try {
    divide(10,0);
  }
  catch(int& e) {
    cout << "Error code: " << e;
  }
  catch(char& e) {
    cout << "Error char: " << e;
  }
  catch(...) { cout << "Error"; }
}
 
 
// Re-throwing exceptions
int main()
{
  try {
    try { throw 0; }
    catch(...) { throw; } // re-throw exception
  }
  catch(...) { throw; } // run-time error
}
 
// Exception specification
void error1() {}            // may throw any exceptions
void error2() throw(...) {} // may throw any exceptions
void error3() throw(int) {} // may only throw int
void error4() throw() {}    // may not throw exceptions

void foo() noexcept {} // must not throw exceptions
void bar() {} // may throw exceptions 
 
int main()
{
  void(*)() noexcept f = foo;
  cout << noexcept(f); // "1" (true)
}


// Exception class
#include <iostream>
#include <exception>
using namespace std;

void make_error()
{
  throw exception("My Error Description");
}

int main()
{
  try { 
    make_error(); 
  }
  catch (exception e) {
    cout << e.what(); "My Error Description"
  }
}

*** Type Conversions ***
 
int main()
{
  // Promotion
  long   a = 5;  // int promoted to long
  double b = a2;  // long promoted to double
 
  // Demotion
  int  c = 10.5; // warning: possible loss of data
  bool d = c;    // warning: possible loss of data
}
 
 
int main()
{
  // Explicit conversions
  int  c = (int)10.5; // double demoted to int
  char d = (char)c;   // int demoted to char
}
 
 
int main()
{
  // Static cast
  char c = 10;       // 1 byte
  int *p = (int*)&c; // 4 bytes
  *p = 5; // run-time error: stack corruption
  int *q = static_cast<int*>(&c); // compile-time error

  // Reinterpret cast
  int *r = reinterpret_cast<int*>(&c); // forced conversion
}
 
 
// Const cast
#include <iostream>

void print(int *p) { std::cout << *p; }

int main()
{
  const int myConst = 5;
  int *nonConst = const_cast<int*>(&myConst); // removes const
  *nonConst = 10; // potential run-time error

  print(&myConst); // error: cannot convert 
                   // const int* to int*
  print(nonConst); // allowed
}
 
 
// Dynamic cast
#include <iostream>
#include <exception>
using namespace std;

class MyBase { public: virtual void test() {} };
class MyChild : public MyBase {};
 
int main()
{
  MyChild *child = new MyChild();
  MyBase  *base = dynamic_cast<MyBase*>(child); // ok

  MyBase  *base2 = new MyBase();
  MyChild *child2 = dynamic_cast<MyChild*>(base2);

  if (child2 == 0) cout << "Null pointer returned";

  try { MyChild &child = dynamic_cast<MyChild&>(*base2); }
  catch(bad_cast &e)
  {
    cout << e.what(); // bad dynamic_cast
  }
}
 
  
// Dynamic or static cast
class MyBase { public: virtual void test() {} };
class MyChild : public MyBase {};
 
int main()
{
  MyChild *child = new MyChild();
  MyBase *base = static_cast<MyBase*>(child); // ok

  // Succeeds for a MyChild object
  MyChild *child2 = dynamic_cast<MyChild*>(base);

  // Allowed, but invalid
  MyChild *child3 = static_cast<MyChild*>(base);
 
  // Incomplete MyChild object dereferenced
  (*child3);
}

*** Smart Pointers ***

#include <memory> // include smart pointers
#include <iostream>
using namespace std;

struct Foo 
{
  int val;
  Foo() { cout << "1"; }
 ~Foo() { cout << "3"; }
};

int main()
{
  unique_ptr<Foo> p(new Foo()); // "1"
  p->val = 2;
  cout << p->val; // "2"

  unique_ptr<Foo> u1(new Foo());
  unique_ptr<Foo> u2 = u1; // compile-time error
  unique_ptr<Foo> u3 = move(u1); // transfers ownership

} // "3"


// Shared pointer
#include <memory> // include smart pointers
using namespace std;

int main()
{
  shared_ptr<Foo> s1(new Foo());
  shared_ptr<Foo> s2 = s1; // extends ownership
  s1 = nullptr; // reset pointer
  s2 = nullptr; // reset last pointer and delete memory

  unique_ptr<Foo> u = make_unique<Foo>();
  shared_ptr<Foo> s = make_shared<Foo>();
}


// Weak shared pointer
#include <memory>
#include <iostream>
using namespace std;

void observe(weak_ptr<int> weak) 
{
  shared_ptr<int> s = weak.lock();
  if (s != nullptr) {
    cout << "Pointer is " << *s << endl;
  }
  else {
    cout << "Pointer has expired" << endl;
  }
}

int main()
{
  shared_ptr<int> s = make_shared<int>(5);
  weak_ptr<int> w = s; // copy pointer without ownership
  observe(w); // "Pointer is 5"
  s = nullptr; // delete managed object
  observe(w); // "Pointer has expired"
}

*** Templates ***
 
// Function templates
template<class T>
void swap(T& a, T& b)
{
  T tmp = a;
  a = b;
  b = tmp;
}

int main()
{
  int a = 1, b = 2;
  swap<int>(a,b); // calls int version of swap

  bool c = true, d = false;
  swap<bool>(c,d); // calls bool version of swap

  int e = 1, f = 2;
  swap(e,f); // calls int version of swap
}
 
 
template<class T, class U>
void swap(T& a, U& b)
{
  T tmp = a;
  a = b;
  b = tmp;
}

int main()
{
  int a = 1;
  long b = 2;
  swap<int, long>(a,b);
}
 
 
// Class templates
template<class T>
class myBox
{
 public:
  T a, b;
};

int main()
{
  myBox<int> box;
}

 
template<class T>
class myBox
{
 public:
  T a, b;
  void swap();
};
 
template<class T>
void myBox<T>::swap()
{
  T tmp = a;
  a = b;
  b = tmp;
}
 
 
// Non-type parameters
template<class T, int N>
class myBox
{
 public:
  T store[N];
};

int main()
{
  myBox<int, 5> box;
}
 
// Class template specialization
#include <iostream>
 
template<class T>
class myBox
{
 public:
  T a;
  void print() { std::cout << a; }
};

template<>
class myBox<bool>
{
 public:
  bool a;
  void print() { std::cout << (a ? "true" : "false"); }
};

int main()
{
  myBox<bool> box = { true };
  box.print(); // true
}
 
// Function template specialization
#include <iostream>
 
template<class T>
class myBox
{
 public:
  T a;
 
  template<class T> void print() {
    std::cout << a;
  }
 
  template<> void print<bool>() {
    std::cout << (a ? "true" : "false");
  }
};

int main()
{
  myBox<bool> box = { true };
  box.print<bool>(); // true
}


// Variable templates
template<class T> constexpr T pi = T(3.1415926535897932384626433L);
int i = pi<int>; // 3
float f = pi<float>; // 3.14…


// Variadic templates
#include <iostream>
#include <initializer_list>
using namespace std;


// Variadic function
int sum(initializer_list<int> numbers)
{
  int total = 0;
  for(auto& i : numbers) { total += i; }
  return total;
}

int main()
{
  cout << sum( { 1, 2, 3 } ); // "6"
}

// Variadic template
int sum() { return 0; } // end condition

template<class T0, class ... Ts>
decltype(auto) sum(T0 first, Ts ... rest)
{
  return first + sum(rest ...);
}

int main()
{
  cout << sum(1, 1.5, true); // "3.5"
}


// Fold expressions
template<class... T>
decltype(auto) sum(T... args)
{
  // Unpacks to: a1 + (a2 + (a3 + a4))…
  return (args + ...);
}


#include <iostream>
using namespace std;

template<class... T>
decltype(auto) difference(T... args)
{
  // Unpacks to: …(a1 - a2) - a3
  return (... - args);
}

int main()
{
  cout << difference(5, 2, 1); // "2" (5-2-1)
}
 
*** Headers ***
 
// MyFunc.c
void myFunc()
{
  // …
}
 
// MyApp.c
int main()
{
  myFunc(); // error: myFunc identifier not found
}
 
 
// MyApp.c
void myFunc(); // prototype
 
int main()
{
  myFunc(); // ok
}
 
 
// MyFunc.h
void myFunc(); // prototype
 
// MyApp.c
#include "MyFunc.h"
 
 
// MyApp.h - Interface
#define DEBUG 0
const double E = 2.72;
typedef unsigned long ulong;
void myFunc();

class MyClass
{
 public:
  void myMethod();
};
 
// MyApp.c
void MyClass::myMethod() {}
 

// MyApp.h
extern int myGlobal;

// MyApp.cpp
int myGlobal = 0;

 
// MyApp.h
inline void myFunc() {}
 
class MyClass
{
 public:
  void myMethod() {}
};

template<class T>
void templateFunction()
{
  // …
}
 

// Inline variables
struct MyStruct
{
  static const int a;
  inline static const int b = 10; // alternative
};
inline int const MyStruct::a = 10;


struct MyStruct {
  static constexpr int a = 10;
};


#include <cstdlib> // rand, srand
#include <ctime> // time

struct MyStruct {
  static const int die;
};
inline const int MyStruct::die = (srand((unsigned)time(0)), rand()%6+1); // 1-6


// Include guards
// MyApp.h
#ifndef MYAPP
#define MYAPP
// …
#endif

#if __has_include("myapp.h")
#include("myapp.h")
 