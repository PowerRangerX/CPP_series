```cpp

#include <iostream>

  

int main(void)

{

    int x = 1;

    bool comparisionResult = x == 5; // bool data type stores values ture or false

    // the "==" here is overlaoded operator that is used to comapare two primitive data

    // type, it is an overloaded function in C++ by deafult

    // The "==" equality operator is known as the equality operator

    // The return type of "==" is a bool i.e. true of false

  

    // if(comparisionResult == true); // same as if(comparisionResult)

    if(comparisionResult)

    {

        std::cout << "Hello World \n";

    };

    return 0;

}
```