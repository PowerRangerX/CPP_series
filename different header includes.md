# different header includes

```cpp
#include <iostream> 
/* <-- "<some_header_file>" these angle brackets are used for predefined headerfiles

    These are header files that the compiler knows the default location to

    You can use quotes for these kinds of header files too

    But you cannot use angle brackets for non-compiler provided header files

*/

#include "header_guard.h" /* <-- '"location_to_some_header_file"' these quotes are used to differentiate

    between user defined and compiler provided header filest

    The default location for user defined header files is the same directory as the file it is begining included in

    i.e the current direcotry. The location of the header file is relative to the cpp file that it is beigning

    included in

*/

  

/*

    Double quotes for all header files but angle brackets only for compiler provided files

  

    Another distinction is that C standard header end with .h but not C++ standard header files

    (C++ standard header files don't have any extension but they just are regular header files

    This is just done to distinguish between the two.

*/
```