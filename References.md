
 This is called pass by value and this will just create a copy of the variable and not change the actual varialbe and not change the actual variable passed to it as the function will just create a copy of the given varialbe.

```cpp
int increment(int x);
```

```cpp
#include <iostream>

#define LOG(x) std::cout << x << "\n"

void Increment(int* value) // this is called pass by reference and this will change the acutal variable

{
    // value++; // will not work as this will just increment the address and the value at the address

    // *value++; // this will not work as "++" is of higer precedence than *(dereference) operator

    // so this will increment first and then dereference, which is not what we want

    (*value)++; // we use brackets to dereference first and then increment

}
```

Now we can achieve the same thing but with just using references

```cpp
void Increment(int& value) // this is called pass by reference

{

    value++; // here we dont' need to dereference

}

  

int main(void)

{

    // Pointers and references are pretty much the same thing

    // Semantically there are diffreneces between how we write and use them

    // Refrences are just syntatic sugar for pointers

    // Refrences don't occupy memory they don't really have storage

    // They are not tipical variable, they just reference some existing variable

  

    int a = 10;

    int& ref = a; // here the "&" is the part of declaration, the "&" is a variable type

    // there is also a "&" operator that is used to get the refrence of a variable

    // int* ptr = &a // here the & is used to get the address of a or the reference of a

  

    // what we have done is just created an alias

    // now this ref variable is not really a variable, it just exists in our source code

    // if you compile this code you will not get two variables a nad ref you are just going to have

    // a single variable a

    // but you can use ref as if it was a

  

    // if we change ref we change a

    ref = 2;

    LOG(a);

    // for all intenets and purposes ref is a, we've just created and alias for a

  

    Increment(&a); // for pointer

    LOG(a);

    Increment(a); // for dereference

    LOG(a);

  

    // we can not change what a reference references after we assign it a reference

    int b = 8;

    ref = b; // if we do this, it will not change the reference ref to reference b it'll just

    // set the value of a to equal to the value of b

    // i.e. a = 8 and b = 8

    // You can not declare a reference and not assign a value

    // you have to define a ref and give it a value at initialization

  

    return 0;

}
```