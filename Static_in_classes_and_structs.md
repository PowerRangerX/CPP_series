```cpp
#include <iostream>

// We use strtuct instead of class here because we want all of our members to be public
struct Entity
{
	// If you'd used non-static variable(instance variables)
	// Each instance of the class will have different memory for x and y
	static int x, y;
	void print()
	{
		std::cout << "x = " << x << " y = " << y << "\n";
	}
};

// Just type "typename Class::Variable"
// Doing this is sufficient for definition of the static member variables
// We don't need to initialize the varialbes
// By default they are initizlized to zero(0)

int Entity::x;
int Entity::y;

// If we don't define them
// The initilization of the variables will fail as x and y are no longer class members

// Running this code without defining the static variables
// will produce linker error unresolved external symbol public: static int Entity::x
// This is because we have to define those static variables
// We can do that anywhere

int main(void)
{
	// static inside a class or struct means a certain thing
	// If you use static with a variable it means that there is only going to be one instance of that varialbe
	// across all instances of the class

	Entity e;
	
	/*
	// Accessing static varialbes this way is wrong i.e. like an instance variable
	// e.x = 2;
	// e.y = 3;
	*/

	// If we access the static variable like the Instance variable (through an object)
	// but the compiler will show the warning message and it won’t halt the program. 
	// The compiler will replace the object name with the class name automatically.

	// If we access the static variable without the class name, the Compiler will automatically append the class name.
	// Although you should not do this.

	// e.x = 2; // don't do it this way but'll work
	// e.y = 3;

	// Instance variable of a class can also be initizlized using an iinitizlizer
	// Entity e = {2, 3};

	Entity::x = 2; // correct way of writting static members of a class
	Entity::y = 3;

	Entity e1;
	Entity::x = 23;
	Entity::y = 24;

	e.print();
	e1.print();

	// Now if we run this we get 23 24 printed twice
	// That is because the x and y variables are static, that means there is only one instance of those two variables
	// across all instance of our Entity class instances
	// Which means that when we're changing the second x and y they are exactly the same as the first one
	// They are pointing to the same memory
	// Picture two instances of the Entity class, however the x and y that they are pointing to are shared,
	// they are pointing to the same x and y
	// And thus they are reffered by the class's scope
	// Because that's what they are
	// It's like creating two variables called x and y in namespace called Entity
	// They don't really belong to the class(kind of)
	// They do because, they can be private and public and they are still part of the class but not just a namespace
	// But they are just like beinging in a namespace beacuase they have anything to do with allocation when you create an
	// new instance of the class

	// This is very useful if you want to have variables across classes
	// You could just create global variables or instead of a global variable it could be a static global variable
	// But doing that would not have the same effect as this, as it would make less sense in a conventional way
	// Meaning if you have a piece of information a data that you want to be shared across all the members of class
	// It makes sense to store it in the entity class, for orginizational purposes you're much better making a static variable
	// inside the class rather than having a static or global variable

	return 0;
}
```