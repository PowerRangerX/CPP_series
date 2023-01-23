# How C++ Works

Bacially in C++ we write our code in some source file and them pass them on to a compiler that turns them into a binary.

![[how_CPP_works.png]]

Following is a very simple C++ program. We'll use this program to learn how C++ works.

```cpp
#include <iostream>

int main(void)
{
	std::cout << "Hello World\n";
	return 0;
}
```

#### Preprocessor Statments [[How_CPP_Compiler_Works#Preprocessing]]

The first line of this program `#include <iostream>` is called a preprocessor statment. Anything that beigns with a `#` symbol will be a preprocessor statment. The first things a compiler does when it see a source file is it preporcess all of your preprocessor statment. That is why they are called preprocessor statments because they happen just before the actual compilation(process of compliing).

##### `#include`
In this case it is something called `include`, what `include` will do is find a file, so in this case we're looking for a file called `iostream`, `include` will then take all of the content of the file and just paste it into this current file, these file theat you include are called header files.

The reason we are including iostream is becuase we need a declaration a function called `cout`, which will lets us print stuff to our console.

#### The Entry Point

The main function is called the entry point. It is the entry point for our application, that means that when we run our application, our computer starts executing code that begins in this function.

As our program is running our computer will execute the lines of code in order(line by line) this flow of execution can be interrupted by control flow statements or functional calls.

The `main()` function is a special function that does not need to return any kind of value. If you don't return anything form the `main()` it will assume that you have returned 0 this only applies to the `main()` function.

Operators are just functions.

Header files are not compiled only C++ files are complied.
Header files get included by the preprocessor statement into a C++ every C++ file will get compiled individually into an object file with the general extension `*.obj`.

All the `*.obj` files are linked by the linker into executable binary, when you compile files individually no linking happens but when you build a project (in Visual Studio) ithere is no need for the linker to be invoked, it gets invoked automatically.

We separate our code into multiple files to make our code more clean, readable, understandable and maintainable.

Every symbol (cout, etc) in C++ needs a declaration. `cout` and other functions are included in a file called `iostream`.

We need to declare a function if we wish to invoke it in a file. Declaration just means that we declare that some function exists.

Example :-
```cpp
void log(const char* m); // <-- Declaration of a function called log
```

`Note: Declaration of a fucntion does not require the arguments be named, i.e. declaration of fucntion only requires the type of arguments.`


And now the compiler will accept that a function `log` exists.

The compiler does not care about resolving where that `log` function is that's the linker's job.

Declaration :- This function or symbol exist.

Definition :- This is the actual functions, it defines what a function does when invoked.

```cpp
// Declaration along with the body of the function is the Definition of the function.

void log(const char* m) // <-- Declaration
{                            // \
	std::cout << m << "\n";  //  |- body of the function
}                            // /
```

The compiler does not know if it declared symbol exists or not i.e. if it's defined or not, it just trusts that a declared function exist

the linker is the one that finds the ....l that's when we get a linker error the linker is the one that finds the definition of a declared function or symbol if it can't find a definition for a declared symbol that's when we get a linker error

Linker errors all generally abbreviated with `LNKXXXX` where the `XXXX` purse used to specify what type of error it is  purse used to specify what type of error it is.

For example `LNK2019` means a linker error with code 2019 meaning `"unresolved external symbol"`.

Linker's job is to via the functions and symbol linker's job is to via the functions and symbol.

The Linker takes the star `*.obj` files and stitches them together into an executable binary.

For example lets say that we have a `log` function inside a file `log.cpp` and a `main.cpp` file where we use that `log` function.

Example :-

`main.cpp`
```cpp
#include <iostream>

void long(const char* m)

int main(void)
{
	log("Hello");
	std::cin.get();
}
```

`log.cpp`
```cpp
#include <iostream>

void log(const char* m)
{
	std::cout << m << "\n";
}
```

The compiler will compile the two files into their own object files i.e. `main.obj` & `log.obj`.

Then the linker will take the definition of the `log` function and put it into a common binary that contins definition of both `main` and `log`.