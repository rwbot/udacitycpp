```

```
---
# Comments
/*The start of a comment block.
Everything between "/* "and " */ "
is in the comment block.
The end of a comment block.*/
---

# Style Guide
As with all programming languages, there are many different ways to style the code we write. For this course, we are not using a standard style. We are trying to remain consistent throughout the course, while making the codes as readable as possible.

There are a number of style guides available, the best one is the one used by the people who are paying you.

A straightforward style guide is:
               Modern C++ Coding Guidelines
https://github.com/Microsoft/AirSim/blob/master/docs/coding_guidelines.md
For a more detailed guideline:
               Google C++ Style Guideline
https://google.github.io/styleguide/cppguide.html
---

# Hello World
```
/*write a C++ program that outputs the following statement:
*** "Hello world, I am ready for C++"
*/
#include <iostream>

int main() {
    std::cout << "Hello world, I am ready for C++";
    return 0;
}
```
---

# Compiling
```
g++ main.cpp -o main.out
```
*g++* is compiler
*main.cpp* is name of file
*-o* Flag for naming output
*main.out* Name of output file

# Running
```
./main.out
```
---

# Namespace
```
int main(){
  std::cout << "Hello World"
}
```
can be shortened using the *namespace* command to specify that all commands used below are from the same library. This is convenient but because it is not explicity named, when added to another library, your code may may cause complications by referencing other libraries
```
using namespace std;
int main(){
  cout << "Hello World"
}
```


# Writing to the Console

```
std::cout << "Hello World"; //prints Hello World to the Console
std:cout << 23;             // prints the number 23 to Console
std:cout << variableName    // Prints Value of variableName to Console

int num
std::cout << "The value of num is " << num << "\n";
// \n adds a new line
```









































































































































































//
