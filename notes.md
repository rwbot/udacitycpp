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
Using the specific namespace will combat most of the problems with implicit naming:
```
using std::cout;
using std::endl;
using std::setw;
```

# Writing to the Console

```
std::cout << "Hello World"; //prints Hello World to the Console
std:cout << 23;             // prints the number 23 to Console
std:cout << variableName    // Prints Value of variableName to Console

int num
std::cout << "The value of num is " << num << "\n";
// \n adds a new line

// endl also adds new Guideline
std::cout << "size of int =" << sizeof(int) << endl;

```



# Enumerated Constants (Enum)
```
enum type_name {
  value1,
  value2,
  value3,
  .
  .
} object_names;
```

Example:
```
//define MONTH as having 12 possible values
    enum MONTHS {Jan, Feb, Mar, Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec};

    //define bestMonth as a variable type MONTH
    MONTH bestMonth;

    //assign bestMonth one of the values of MONTH
    bestMonth = Jan;

    //now we can check the value of bestMonths just
    //like any other variable
    if(bestMonth == Jan)
    {
        cout<<"I'm not so sure January is the best month\n";
    }
```

# Formatting Output With Escape Sequences

```
#include <iomanip>

std::cout<<"\n\nThe text without any formating\n";
std::cout<<"Ints"<<"Floats"<<"Doubles"<< "\n";
std::cout<<"\nThe text with setw(15)\n";
std::cout<<"Ints"<<std::setw(15)<<"Floats"<<std::setw(15)<<"Doubles"<< "\n";
std::cout<<"\n\nThe text with tabs\n";
std::cout<<"Ints\t"<<"Floats\t"<<"Doubles"<< "\n";
```
Output:
```
The text without any formating
IntsFloatsDoubles

The text with setw(15)
Ints         Floats        Doubles

The text with tabs
Ints    Floats    Doubles
```


#include <iostream>
#include <iomanip>

int main()
{
    int a = 45;
    float b = 45.323;
    double c = 45.5468;
    int aa = a + 9;
    float bb = b + 9;
    double cc = c + 9;
    int aaa = aa + 9;
    float bbb = bb + 9;
    double ccc = cc + 9;

    std::cout << "Ints" << std::setw(12) << "Floats" << std::setw(12) << "Doubles" << std::endl;
    std::cout << a << std::setw(12) << b << std::setw(12) << c << std::endl;
    std::cout << aa << std::setw(12) << bb << std::setw(12) << cc << std::endl;
    std::cout << aaa << std::setw(12) << bbb << std::setw(12) << ccc << std::endl;

    return 0;
}


# File IO

- Include the ```<fstream>``` library
- Create a stream (input, output, both)
     - ```ofstream myfile;``` (for writing to a file)
     - ```ifstream myfile;``` (for reading a file)
     - ```fstream myfile;```(for reading and writing a file)
- Open the file  ```myfile.open(“filename”);```
- Write or read the file
- Close the file ```myfile.close();```
















































































































































//
