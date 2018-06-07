
# Comments
/*
The start of a comment block.
Everything between "/* "and " * / "
is in the comment block.
The end of a comment block. * /
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
**g++** is compiler

**main.cpp** is name of file

**-o** Flag for naming output

**main.out** Name of output file

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

```
/*The goal of this quiz is to practice writing and reading files.
**Read the contents of input.txt and then write to it.
**
**We are using input.txt as our file. This is not an ideal
**situation, because when we write to it, we cannot
**see the changes. We can manually write in input.txt and
**we can also use the program to write to the file.
**Then we can read what we wrote using our program.
**
**Your assignment for this quiz**
**Change the contents of the file called input.txt
**Change the ifstream and ofstream to fstream

*/
#include <iostream>
#include <fstream>
#include <string>
using namespace std;

int main () {
    string line;
    //create an output stream to write to the file
    // ios::app appends the new lines to the end of the file
    ofstream myfileI ("input.txt", ios::app);
    if (myfileI.is_open()){

        myfileI << "\nI am adding a line.\n";
        myfileI << "I am adding another line.\n";
        myfileI.close();
    }
    else cout << "Unable to open file for writing";

    //create an input stream to write to the file
    ifstream myfileO ("input.txt");
    if (myfileO.is_open()){

        while ( getline (myfileO,line) ){

            cout << line << '\n';
        }
        myfileO.close();
    }

    else cout << "Unable to open file for reading";
    return 0;
}
```


# Header Files
Anything that is a reference to a library or external file can be moved into a header `.hpp` file and reference in the `main.cpp` file. Notice that **" quotes "** represents local library, while **< angle brackets >** references the standard library
```
# include "header.hpp"
```


# User Input
Input can be read using:
```
std::cin >> var
```
But it has a limitation where it reads only up until the first space character. So we use
```
std:getLine(std:cin, variableName)
```
Example
```
#include<iostream>
#include<string>

int main(){
    std::string userName;
    std::cout<<"Tell me your nickname?: ";
    std::getline(std::cin, userName);
    std::cout<<"Hello "<<userName<<"\n";
    return 0;
}
```
Using `getline` and `cin` to input strings
```
#include <iostream>
#include <string>

int main(){
    std::string name1;
    std::string add1;
    std::string num1;
    std::cout << "What's your MOFO name? \n";
    std::getline(std::cin, name1);
    std::cout << "What's your MOFO address? \n";
    std::getline(std::cin, add1);
    std::cout << "What's your MOFO number? \n";
    std::getline(std::cin, num1);

    std::string name2;
    std::string add2;
    std::string num2;
    std::cout << "What's your MOFO name? \n";
    std::getline(std::cin, name2);
    std::cout << "What's your MOFO address? \n";
    std::getline(std::cin, add2);
    std::cout << "What's your MOFO number? \n\n";
    std::getline(std::cin, num2);

    std::cout << name1 << std::endl << "" << add1 << std::endl << "" << num1 << "\n";
    std::cout << name2 << std::endl << "" << add2 << std::endl << "" << num2 << "\n";
}
```
Out:
```
What's your MOFO name?
What's your MOFO address?
What's your MOFO number?
What's your MOFO name?
What's your MOFO address?
What's your MOFO number?

Imogene Penelope Freely
         2343 South View Road
         (408)435-3221
Sandy Beaches
         1123 Pebble Creek Road
         (408)546-5432
```

### StringStream

Include the Stringstream library.
```
    #include <sstream>
```
Use getline to get the string from the user
```
    std::getline(std::cin, stringVariable);
```
Convert the string variable to a float variable.
```
    std::stringstream(stringVariable) >> numericVariable;
```

* Example
```
std::string stringLength;
   float inches = 0;

   std::cout << "Enter number of inches: ";
   std::getline (std::cin,stringLength);
   std::stringstream(stringLength) >> inches
```


## Debugging

```
<< "\n"
```


## Math

```
#include<cmath>
std::pow(base, exponent)

//pi is equal to M_PI
M_PI = 3.14159265358979323846
```

## Prefix and Postfix
|Prefix|Postfix|
| --- | --- |
| ++a | a++ |
| --a | a-- |
| Increment value > return reference| Copy var > increment > return copied val B4 increment |

## Switch Statements  

```
switch(expression)
{
     case constant-expression : statements;
        // no break, all subsequent will execute until break is met
     case constant-expression : statements;
                               break; (this is optional);

     default : //optional
        statements;
}
```

## FOR Loops

```
for ( declaration : range ) statement;

for (initialization; condition; increase) statement;
```

## WHILE Loops

```
while(condition){
     statements;
}
```

## DO/WHILE Loops

```
do{
     statements;
} while(condition );
```


## Infinite Loops

```
# Using FOR
for( ; ;){
     std::cout<<"This for loop will run forever\n";
}

# Using WHILE
while(1){
     std::cout<<"This while loop will run forever\n";
}
```

## Exiting Loops 

* The break statement: will end the loop and begin executing the first statement that comes AFTER the end of the loop.

* The continue statement: The continue statement will force the next iteration to be executed.


# [POINTERS](http://www.cplusplus.com/doc/tutorial/pointers/)

**Pointers are the addresses of variables**

```
int a = 54;
std::cout<< &a << "\n"; // Prints the LOCATION of 'a'
```






























































































z

//
