```cpp
#include <iostream>

int main(void)
{
	// Try to mark your functions and variables static unless you need actually need them to be linked across translcation units.

	// There are two meanings to the keyword static
	// one when it is used inside a class or struct
	// and one when it is used outside a class or struct
	
	// static when used outside a class or struct means that
	// the linkage of that symbol that you delcared to be static is going to be internal
	// meaning it's only going to be visible to that translation unit that you have defined it in.

	// Whereas if static is used inside a class or struct means that
	// the variable is going to share memory with all of the instances of the class
	// meaning that basically all the instances that you create of that class or struct, there's
	// only going to be one instance of that static variable
	// Similar thing applies to static methods of a class there is no instance of that class
	// being passed into that method.
	
	// By convention static variables are prefixed with a s_ to indicate that they are static

	static int s_Variable = 0;

	// This variable s_Variable is only going to be linked inside of this translation unit, i.e. the linker 
	// is only going to look for this symbol in this C++ file.
	// A static variable or function means that when it actually comes time to link those actual functions or variables
	// to actully define symbols, the linked is not going to look outside the scope of this translation unit for that
	// symbol definition

	// The Visual Studio compiler will complie and link all the cpp file and link them together when you build the project
	// but you have to perform the linking operation manually in other development enviroments

	// If you create another file that has the same static variable and them try to compile and link them together
	// it will compile and link ok as the static variables only look for the variable in the same translation unit

	// We can also make a new file and define a variable with the same name but not static this time, it'll
	// still compile and link ok as the first static variable is scoped only to the same translation unit
	// it was defined in and the other non-static variable will not interfered by it, i.e. the non-static variable
	// will be the only global variable left

	/* 
		// Static.cpp //compiled and linked with Main.cpp
		static int s_Varialbe = 20;

		// Main.cpp // compiled and linked with static.cpp
		#include <iostream>

		int s_Variable = 10;
		
		int main()
		{
			std::cout << s_variable << "\n";
			return 0;
		}
		
		// Here the code will compile and link ok
		// Output will be 10;
	*/

	// But if we change the static.cpp to not have a static variable but a normal global variable
	/* 
		// Main.cpp // compiled and linked with static.cpp
		#include <iostream>

		int s_Variable = 10;
		
		int main()
		{
			std::cout << s_variable << "\n";
			return 0;
		}

		// Static.cpp // compiled and linked with Main.cpp
		int s_Variable = 10;

		// If we try to compile and link this, we will get a linker error
		// because this variable s_Variable is already been defined before
		// you are defining it again in another translaction unit(file)
		// both of the variables are trying to global variables, as none of them are staic(i.e scoped to the same translation unit)
		// and both of them cannot become global varialbe as you cannot define two variables of the same name in the same scope

		// So you cannot have two global variables with the same name

		// You can get ride of the linker error by getting ride of the assignment and making the variable s_Variable
		// to refer to the variable in another file by marking it external

		// Static.cpp // compiled and linked with Main.cpp
		int s_Variable = 10;
		
		// Main.cpp // compiled and linked with Static.cpp
		#include <iostream>

		external int s_Variable = 10;
		
		int main()
		{
			std::cout << s_variable << "\n";
			return 0;
		}
		// Now the code will compile and link ok, the s_Variable is just refering to the external s_Varible in
		// the Static.cpp file
		// this is called external linkage or external linking
		// Ouput will be 10;

		// But now if we change the s_Variable in Static.cpp to be static, and we try to compile and link the code
		// we'll get an error as the linker will not link a static variable outside it's own translation unit
		
		// Static.cpp // compiled and linked with Main.cpp
		static int s_Variable = 10;
		
		// Main.cpp // compiled and linked with Static.cpp
		#include <iostream>

		external int s_Variable = 10;
		
		int main()
		{
			std::cout << s_variable << "\n";
			return 0;
		}

		// We'll get a linker error, unresolved external symbol error as it canot find a s_Variable anywhere
		// because we've effectively marked our s_Variable as private

		// Similar thing happes with static function
		
		// So we can say that declaring a static variable is like declaring a priave variable in a class
		// as the static variable is not visible outside of it's own translation unit
	*/

	/*
		If you declare a static variable in a header file and include that header file in different cpp file
		what you doing is basically just declaring two static variables that are scoped to that translation unit
		Because all a header file does is copy and paste the entire code into another file 
	*/

	// Static 
	return 0;
}
```