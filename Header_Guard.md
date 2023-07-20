# Header Guard
```cpp
#pragma once /* <-- this is know as a header guard

    It makes sure if a declartion in a header file is included once it wont' include it again. In ye old days header guard used to look like this
*/

#ifdef _SOMETHING_

#define _SOMETHING_

/*

    The name (_SOMETHING_) is just per convention you can name it what ever

    This #define will include the code that is to be used and then we use #ifdef to see if it's included before if it is included before it is not included again

    In other words if a block of code named "_SOMETHING_" is not defined before define it or if it is defined dont' define it.

*/

// Code goes here

#endif

/*

    The way this works is if you include this header file multiple times in some cpp files

    the ifdef will be false for only the first time and every subsequent time till will be true as _SOMETHING_

    will be defined

*/
```