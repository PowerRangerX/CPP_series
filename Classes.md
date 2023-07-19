Class are basically types.

Variables made from class types are called objects and a new object variable is called an instance or a class instance.

There is no real difference between a struct and a class in C++, except for the visibility, in a struct all the members are public by default, while in a class all the members a private by default.

Structs mostly exist in C++ for backward combability with C.
```cpp
#include <iostream>

// Class are basiclly types
class Player
{
public:
	int x; // member variable
	int y;
	int speed;

	void Move(int xa,int ya) // member function
	{
		x = xa * speed;
		y = ya * speed;
	}
};

int main(void)
{
	Player p; // this is an object of type Player
	return 0;
}
```