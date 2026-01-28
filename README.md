# ft_printf - 👤 Author: hdroliveira

![42 Porto](https://img.shields.io/badge/42-Porto-blue)
![Language](https://img.shields.io/badge/Language-C-orange)
![Score](https://img.shields.io/badge/Score-100%2F100-success)

**ft_printf** is a project at 42 that mimics the behavior of the standard C library function `printf`. The main goal is to learn about **Variadic Functions** (`stdarg.h`) and how to handle variable numbers of arguments in C.

## 📂 Supported Conversions

The function handles the following format specifiers:

| Specifier | Description | Example |
| :---: | :--- | :--- |
| **%c** | Prints a single character. | `ft_printf("%c", 'a');` |
| **%s** | Prints a string (as defined by the common C convention). | `ft_printf("%s", "Hello");` |
| **%p** | The `void *` pointer argument has to be printed in hexadecimal format. | `ft_printf("%p", ptr);` |
| **%d** | Prints a decimal number (base 10). | `ft_printf("%d", 42);` |
| **%i** | Prints an integer in base 10. | `ft_printf("%i", -42);` |
| **%u** | Prints an unsigned decimal number (base 10). | `ft_printf("%u", 4294967295);` |
| **%x** | Prints a number in hexadecimal (base 16) lowercase format. | `ft_printf("%x", 255);` -> `ff` |
| **%X** | Prints a number in hexadecimal (base 16) uppercase format. | `ft_printf("%X", 255);` -> `FF` |
| **%%** | Prints a percent sign. | `ft_printf("%%");` |

## 💡 Key Concepts

### Variadic Functions
This project introduces `stdarg.h`, allowing functions to accept an indefinite number of arguments.
- `va_start`: Initializes the argument list.
- `va_arg`: Retrieves the next argument.
- `va_end`: Cleans up the memory.

## 🛠️ Usage

### Prototype
```c
int ft_printf(const char *format, ...);

Return Value: The number of characters printed (excluding the null byte used to end output to strings).

Compilation
The project includes a Makefile that compiles the source files into a static library libftprintf.a.

Compile the library:
make

Compile your program with the library:
cc main.c libftprintf.a -o program

Example main.c

#include "ft_printf.h"
#include <stdio.h> // For comparison with original printf

int main(void)
{
    int len_ft;
    int len_std;

    // String and Char
    ft_printf("My char: %c\n", 'A');
    
    // Numbers
    len_ft = ft_printf("My number: %d\n", 42);
    len_std = printf("Std number: %d\n", 42);

    // Return value check
    printf("Lengths -> ft: %d | std: %d\n", len_ft, len_std);

    // Hexadecimal
    ft_printf("Hex: %x\n", 255);

    return (0);
}

⚠️ Notes
The buffer management is handled internally to ensure output is printed correctly.

This implementation focuses on the mandatory part (no flags like -0. unless you implemented the bonus).