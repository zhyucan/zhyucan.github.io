---
layout: post
title: Programming in C Exercises
categories: [blog ]
tags: [C ]
description: Programming in C Exercises
---

### 3 Compiling and Running Your First Program

**3-1**  
Type in and run the six programs presented in this chapter. Compare the output produced by each program with the output presented after each program in the text.

略.

**3-2**  
Write a program that prints the following text at the terminal.
* In C, lowercase letters are significant.* main is where program execution begins.* Opening and closing braces enclose program statements in a routine.
* All program statements must be terminated by a semicolon.

```c
#include <stdio.h>

int main(void)
{
    printf("In C, lowercase letters are significant.\nmain is where program execution begins.\nOpening and closing braces enclose program statements in a routine.\nAll program statements must be terminated by a semicolon.\n");

    return 0;
}
```

**3-3**  
What output would you expect from the following program?

```c
#include <stdio.h>
int main(void) 
{    printf("Testing..."); 
    printf("....1"); 
    printf("...2"); 
    printf("..3"); 
    printf("\n");
    return 0; 
}
```

```c
Testing.......1...2..3
```

**3-4**  
Write a program that subtracts the value 15 from 87 and displays the result, together with an appropriate message, at the terminal.

```c
#include <stdio.h>

int main(void)
{
    int value1, value2, diff;

    value1 = 15;
    value2 = 87;
    diff = value2 - value1;
    printf("subtracts the value 15 from 87: %i.\n", diff);

    return 0;
}
```

**3-5**  
Identify the syntactic errors in the following program.Then type in and run the corrected program to ensure you have correctly identified all the mistakes.

```c
#include <stdio.h>

int main(Void)
(
    INT sum;
    /* COMPUTE RESULT
    sum = 25 + 37 - 19
    /* DISPLAY RESULTS //
    printf("The answer is %i\n" sum);
    return 0;
}
```

```c
#include <stdio.h>

int main(void)
{
    int sum;
    // COMPUTE RESULT
    sum = 25 + 37 - 19;
    // DISPLAY RESULTS
    printf("The answer is %i\n", sum);

    return 0;
}
```

**3-6**  
What output might you expect from the following program?

```c
#include <stdio.h>
int main(void) 
{	int answer, result;
	answer = 100;	result = answer - 10;	printf("The result is %i\n", result + 5);
		return 0;
}
```

```c
The result is 95
```
