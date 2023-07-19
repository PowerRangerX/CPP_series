# How C++ Compiler Works

![[how_CPP_works.png]]

C++ code is written into a text file, that's all a `cpp` file is a text file.

The compiler takes our C++ files and converts them into object files (`.obj` files or `.o` files) which is then passed on to the linker. The linker links them together into an executable binary.

#### Preprocessing

The preprocessor processes all the preprocessor statements that is all the lines that begin with a hash(`#`).

Once our code has been preprocessed it is then tokenized and parsed and the C++ code is transformed into a format that the compiler can understand this results in the creation of an abstract syntax, this tree  is just the representation of our code but as an abstract syntax tree. Once the abstract syntax tree has been created the compiler takes this tree and generates the machine code that a computer can understand and execute and it also makes the space to store all of our constant and variables.

Every single C++ file that we tell our compiler to compile will result in an object file all of these C++ file are called translation unit.

C++ does not care about files. Files do not exist in C++. For example, in Java, your class name has to be tied to your file name and your folder hierarchy has to be tied to your package, Java expects certain files to exist. In C++ however that is not the case there is no such thing as a file. A file is just a way to feed the compiler your C++ code. You are responsible for telling the compiler what kind of file type this is and how the compiler should treat that file. Now as per convention if you create a file with the extension `.cpp` the compiler is going to treat it as C++, a file and with a `.c` extension as a C file and a file with a `.h` extension as a header file but again these are just conventions you can override any of them. For example you can create a file with the extension `.thunder` and tell the compiler to treat it as a C++ file the compiler will treat it as a C++ file.

Files have no meaning.

Every C++ file that we feed into a compiler, it will compile it as a translation unit and a translation unit will result in an object file.

It is a common practice to include multiple C++ file into a single C++ file to create basically one big C++ file with lots of files in it and if we compile this one big file it will result in only one translation unit and thus one object file.

Every C++ file does not necessarily have two equal a translation unit however if you just make a project with individual C++ files and never include them in each other then every C++ file will will result in a translation unit and so every C++ file will generate an object file.

Every C++ file does not produce a translation unit and thus not an object file but every translation unit produces an object file.

If multiple C++ file are included in a single C++ file and that file is compiled it will only produce one translation unit and only one object file.