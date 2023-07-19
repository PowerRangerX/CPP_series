# Variables in C++

Variables allow us to name data. Variables are nothing but numbers. The only main or real difference between variables is their size. We use int for integers and char for characters just per convetions.

Example: You can output an int as a char and viceversa

```c++
char --> 1 byte, short --> 2 bytes, int --> 4 bytes, long --> 4 bytes(usually)
```

These are compiler(machine) dependent
You can have certain combinations of these

Showing how characters are just numbers, that are interpreted differently.
```c++
int a = 97;
int something = 39;
char m = 65;
char c = 99;
```

Except for double and float (kind of)

double and float allows us to store decimal point numbers

```c++
float --> 4 bytes, double --> 8 bytes
```

When you define a float and assign it a value it is stored as a double

To define a float you have to append an 'a' to the end of the value

```c++
float fd = 23.32; // the value is a double
float f = 23.32f; // this is a float
double d = 23.32;
```

bool is another primitive in C++ that can any of two values true or false

```c++
bool --> 1 byte
```

A bool is just a number

0 for false and true for anything else

A bool takes 8 bytes and not 1 bit because memory is byte addressable

```c++
bool b = true;
bool b2 = false;
bool r = 23;
bool s = 0;
```

The sizeof operator can be used to determine the sizeof any data type

```cpp
std::cout << "a = " << a << " char a = " << (char)a << "\n"
	<< "something = " << something << " (char)something = " << (char)something << "\n"
	<< "c = " << c << " (int)c = " << (int)c << "\n"
	<< "m = " << m << " (int)m = " << (int)m << "\n"
	<< "f = " << f << " fd = " << fd << " d = " << d << "\n"
	<< "b = " << b << " b2 = " << b2 << " s = " << s << " r = " << r << "\n";
return 0;
```