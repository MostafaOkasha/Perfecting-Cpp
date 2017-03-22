# THIS IS ALL MY C++ CODE BANK

## C++ Libraries and their use:


| Library        | Used for:     | Source:      |
| -------------  |:-------------:| ------------:|
| #include \<iostream>     |Input/output streaming data - Whether to files, terminal or anything.| -         |
| #include \<fstream>      |Used to read and write into files. Needs iostream                    | -         |
| #include \<cstdio>       |         |          |
| #include \<stdio.h>      |         |          |
| #include \<stdlib.h>     |         |          |
| #include \<string.h>     |         |          |
| #include \<unistd.h>     |         |          |
| #include \<sys/types.h>  |         |          |
| #include \<stdint.h>     |         |          |
| #include \<fcntl.h>      |         |          |
| #include \<sys/stat.h>   |         |          |
| #include \<sys/ipc.h>    |         |          |
| #include \<sys/mman.h>   |         |          |
| #include \<stdbool.h>    |         |          |
| #include \<sys/sem.h>    |         |          |
| #include \<vector>    |         |          |
--------------

- #include \<fstream>
  - ofstream: Stream class to write on files
  - ifstream: Stream class to read from files
  - fstream: Stream class to both read and write from/to files.
--------

```cpp
//To output something to terminal and input into a file:
//#include <iostream>
#include <fstream> // NOTE: Here we do not need iostream since the header for iostream is included in the fstream header!!!
using namespace std; // Read note on why we used napespace std (see below)
 //  can also do int main(int argc, char** argv){
int main () {
  ofstream myfile; // because we're only writing.
  myfile.open ("example.txt");    // Opens the text file
  if (!myfile.is_open()) { /* ok, proceed with output */ }
  myfile << "Writing this to a file.\n";   // Writes into the exact position of the pointer in the text file.
  myfile.close();   // closes the text file
  return 0;   // end
  //return(0); // return 0 and return(0) are the same thing. but using return is better than exit because of destructors. exit isnt
  // always the safest way to do things. return gaurantees for us that the destructors have finished. see notes below
  //exit(0);
}
```
---------
NOTE: The std namespace is special; it is short for the word "standard." The built in C++ library routines are kept in the standard namespace. That includes stuff like cout, cin, string, vector, map, etc. SO! we are basically stating that we are using the standard namespace.
If you don't use the namespace std then when calling a function you will have to do: std::exit for example.

------------------

Note 2: Terminating the program without leaving the current block (e.g., by calling the function std::exit(int) (18.5)) does not destroy any objects with automatic storage duration (12.4). If std::exit is called to end a program during the destruction of an object with static or thread storage duration, the program has undefined behavior.

--------------------

Note 3: returning 0 is you just saying return the any value because your programs main is of type int so it has to return some value. In c++ context some compilers can allow you to not return anything at all in the main

----------

Note 4: The return value for main should indicate how the program exited. Normal exit is generally represented by a 0 return value from main. Abnormal termination is usually signalled by a non-zero return but there is no standard for how non-zero codes are interpreted. Also as noted by others, void main() is explicitly prohibited by the C++ standard and shouldn't be used.
----------



