A pointer is a just number(an integer) that stores a memory address. Types have nothing to do with that, types are some kind of fiction that we've created to make our lives easier, types are completely meaningless.

Pointer for all types is just that number that stores it's memory address.

```cpp
// void* ptr = NULL; // This is another way to define pointer to NULL

void* ptr = nullptr;
```
This defines a type-less pointer that points to NULL(NULL just means 0). 0 (NULL) is not a valid memory address. We cannot read or write to an invalid memory address.

The `&` operator is used to get the address of a variable.
```cpp
int a = 10;

void aptr = &a;
```

The following will also work as types are used for size and don't really mean anything.
```cpp
int a = 10;

double* aptr = (double*)&a
```

Sample program
```cpp
#include <iostream>

int main(void)
{
    // void* ptr = NULL;
    void* ptr = nullptr; // typeless pointer, pointing to null
  
    int a = 10;
    // double* aptr = (double*)&a // this will also work, as types are used for size and have no meaning

    void* aptr = &a; // the & operator is used to get the address of a variable
    std::cout << aptr << "\n";
    
    // wait for user input
    std::cin.get();
}
```