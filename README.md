*This project has been created as part of the 42 curriculum by gogalsty.*

# ft_printf

## 📌 Description

The **ft_printf** project consists of recreating the standard C `printf()` function. The goal is to understand how formatted output works internally and to learn how to handle a variable number of arguments using variadic functions.

This implementation mimics the behavior of the original `printf` from the C standard library, supporting a set of required format specifiers.

Through this project, key concepts such as low-level output handling, recursion, number conversion, and variadic arguments are explored.

---

## ⚙️ Features

The following conversions are implemented:

* `%c` → Prints a single character
* `%s` → Prints a string
* `%p` → Prints a pointer address in hexadecimal format
* `%d` → Prints a decimal integer
* `%i` → Prints an integer in base 10
* `%u` → Prints an unsigned decimal number
* `%x` → Prints a hexadecimal number (lowercase)
* `%X` → Prints a hexadecimal number (uppercase)
* `%%` → Prints a percent sign

---

## 🛠 Instructions

### Compilation

To compile the library, run:

```bash
make
```

This will generate:

```
libftprintf.a
```

---

### Available Makefile rules

```bash
make        # Compile the library
make clean  # Remove object files
make fclean # Remove object files and library
make re     # Recompile everything
```

---

### Usage

Include the header in your project:

```c
#include "ft_printf.h"
```

Example:

```c
ft_printf("Hello %s! Number: %d\n", "world", 42);
```

---

## 🧠 Implementation Details

The project is structured in a modular way to ensure readability and extensibility.

### Core Components

* **ft_printf** → Main function that parses the format string
* **ft_handle_format** → Dispatches format specifiers
* **Printing functions** → Handle each conversion
* **Utility functions** → Handle character output and base conversions

---

### Algorithm & Data Structure

The implementation follows these steps:

1. Iterate through the format string character by character
2. When a `%` is found, identify the next character as a format specifier
3. Use a dispatcher function to call the correct printing function
4. Convert numbers using a recursive base conversion algorithm
5. Count and return the total number of printed characters

#### Number Conversion

Numbers are converted using a recursive approach:

* Divide the number by the base
* Recursively print higher digits
* Print the remainder using a base string

This allows reuse of the same logic for:

* Decimal
* Hexadecimal
* Pointer addresses

---

## 📚 Resources

* C Standard Library `printf` documentation
* Variadic functions (`stdarg.h`)
* 42 Intra materials

### AI Usage

AI tools were used for:

* Understanding project structure
* Clarifying edge cases (e.g., `INT_MIN`, NULL handling)
* Improving code organization and readability

All implementations were written, tested, and understood manually.

---

## 🚀 Notes

* No buffer management is implemented (as required)
* Only the mandatory conversions are supported
* The project follows the 42 Norm

---

## 🧪 Example Output

```c
ft_printf("Char: %c\n", 'A');
ft_printf("String: %s\n", "Hello");
ft_printf("Pointer: %p\n", ptr);
ft_printf("Decimal: %d\n", -42);
ft_printf("Hex: %x\n", 255);
```

---

## 📎 Final Thoughts

This project strengthens understanding of:

* Variadic functions
* Memory-safe printing
* Recursive algorithms
* Clean and modular C design

It also serves as a reusable library for future 42 projects.
