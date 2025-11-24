ft_printf is a custom implementation of the standard C function printf.
The challenge of this project is to handle formatted output with full control over parsing, conversions, and buffer management.

Supported Conversions

- %c – character
- %s – string
- %p – pointer address
- %d, %i – integers
- %u – unsigned integers
- %x, %X – hexadecimal (lower/upper)
- %% – literal %

Key Concepts

- Variadic functions (stdarg.h)
- Custom formatting parser
- Buffer output management
- Type casting and numeric base conversions
