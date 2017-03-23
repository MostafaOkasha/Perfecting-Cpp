# C++ CODE BANK: IOSTREAM AND FSTREAM + BASIC KNOWLEDGE.

## C++ Libraries used here:


| Library        | Used for:     | Source:      |
| -------------  |:-------------:| ------------:|
| #include \<iostream>     |Input/output streaming data - Whether to files, terminal or anything.| -         |
| #include \<fstream>      |Used to read and write into files. Needs iostream                    | -         |
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
  if (!myfile.is_open()) { exit(0); //exits if the file did not open. }
  myfile << "Writing this to a file.\n";   // Writes into the exact position of the pointer in the text file.
  myfile.close();   // closes the text file
  return 0;   // end
  //return(0); // return 0 and return(0) are the same thing. but using return is better than exit because of destructors. exit isnt
  // always the safest way to do things. return gaurantees for us that the destructors have finished. see notes below
  //exit(0);
}
```
##  Now we look at reading and writing from the command line (user):
E.G:
```cpp
if (myfile.is_open()) {
else cout << "Unable to open file"; //else if the file didnt open
}
```
cout --> connected to the standard output device (display screen)
```cpp
int main( ) {
   char str[] = "Hello C++"; // we created a string object array (using namespace std obviously called before)
   cout << "Value of str is : " << str << endl; // The << places the string we are sending to the display screen at that specific point.
}                                     // NOTE: endl is used to add a new line at the end of the code
//  The << operator is overloaded to output data items of built-in types integer, float, double, strings and pointer values.

E.G 2: //The standard input stream (cin)

int main( ) {
   char name[50];
   cout << "Please enter your name: ";
   cin >> name;      //stores the input to the character name which is printed in the next line.
   cout << "Your name is: " << name << endl;
  //operator>> will skip whitespace by default.
}
 // USE cin >> name >> age; for more than one input.
 // USE cerr << "Error message : " << str << endl; for errors --> runs right away and better than cout since it is attached to the
  // standard error device.
  // can also use clog where it logs the error message into a buffer. (more pro use)

```
---------

NOTE 1: The std namespace is special; it is short for the word "standard." The built in C++ library routines are kept in the standard namespace. That includes stuff like cout, cin, string, vector, map, etc. SO! we are basically stating that we are using the standard namespace.
If you don't use the namespace std then when calling a function you will have to do: std::exit for example.

------------------

NOTE 2: The C++ compiler also determines the data type of the entered value and selects the appropriate stream extraction operator to extract the value and store it in the given variables. The stream extraction operator >> may be used more than once in a single statement. To request more than one datum you can use the following:

----------------------

Note 3: Terminating the program without leaving the current block (e.g., by calling the function std::exit(int) (18.5)) does not destroy any objects with automatic storage duration (12.4). If std::exit is called to end a program during the destruction of an object with static or thread storage duration, the program has undefined behavior.

--------------------

Note 4: returning 0 is you just saying return the any value because your programs main is of type int so it has to return some value. In c++ context some compilers can allow you to not return anything at all in the main

----------

Note 5: The return value for main should indicate how the program exited. Normal exit is generally represented by a 0 return value from main. Abnormal termination is usually signalled by a non-zero return but there is no standard for how non-zero codes are interpreted. Also as noted by others, void main() is explicitly prohibited by the C++ standard and shouldn't be used.

----------



