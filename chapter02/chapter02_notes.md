# Chapter 2 Notes
---
## How to get a file to run?
1. Create a file called `helloworld.c` – `.c` extension is required by compilers.

``` c
#include <stdio.h>
int main(void)
{
printf("To C, or not to C: that is the question.\n");
return 0;
}
```
Next: Need to convert the program to a for that the mahcine can executute. This involves three steps:
- **Preprocessing**: The program is first given to a *preprocessor*, which obeys commands that begin with # (known as as *directives*). A preprocessor is a bit like an editor; it can add things to the program and make modifications.
- **Compiling**: The modified program now goes to a *compiler*, which translates it into mahcine instructions (*object code*). The program isn't quite ready to run yet, however.
- **Linking**: In the final step, a *linker* combines the object code produced by the compiler with any additional code needed to yield a complete executable  program.  This additional code includes library functions (like `printf`) that are used in the program. 

In UNIX, the C compiler is usually named `cc`. To compile and link the `helloword.c` program, enter the following command in terminal.

``` c
cc pun.c
```

After compiling and linking the program, `cc` leaves the executable program in a file named a `.out` by default. The `-o` option allows us to choose the name of the file contain the executable program.

For examples, to have the executable version of `helloworld.c` to be named `helloworld`, we would run:
```
cc -o helloworld helloworld.c
```

One of the most popular C compilers is the GCC compiler. To run:
```
gcc -o helloworld helloworld.c
```

## General Form of a Simple Program
```
directives

int main (void)
{
    statements
}
```
**Directives**: Before a C progrm is compiled, it is first edited by a preprocessor. Commands intended for the preprocessor are called *directives*. Directives always began with a # character. 

```
#include <studio.h>
```
This states that the information in `<stdio.h>` is to be included into the program before it is compiled. We use `<stdio.h>` because in C, unlike most programming languages, has no built-in "read" and "write" commands. The ability to perform input an doutput is provided instead by functions in the standard library. 

**Functions*: A series of statements that have been grouped together an dgiven a name. The `main` function is **MANDATORY**. 

If you take a look at 

``` c
#include <stdio.h>
int main(void)
{
printf("To C, or not to C: that is the question.\n");
return 0;
}
```
The `int` before mains indicates that the `main` function returns an integer value. The `void` indicates that `main` has no arguments.

If there's no return statement at the end of the `main` function, the program will still terminate. However, many compilers will produce a warning message (because the function was supposed to return an integer but failed to).

**Statements**: A statements is to be executed when a program runs. Asking a function to perform its assigned task is known as *calling* the function. 

**Comments**:
```c
/* This is a comment*/

/*  This is an
*    example of a
*    multi-line comment
*/

// This is also a comment
```

## Variable Types:

`int`: whole numbers, but caps at 2,147,483,647
`float`: decimals, but can store much larger numbers and slower than arithmetic on `int`

These must be delcared. For example:

```
int height, length, width, volume;
float profit, loss;
```

When main contains declarations, they must precede statements:
```
int main(void)
{
    declarations
    statements
}
```
But they do not have to in C99.

## Printing Values:
```c
printf("Height: %d\n", height);     //Where d% is for int
printf("Profit: $%.2f\n", profit);  //f% is for floats

```