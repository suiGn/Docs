# Programming in C
<!-- SuiGn: C Programming and General Syntax -->

**Data Types** when **<u>declaring variables</u>**:

| Type     | Description                             | Values                          |
| -------- | --------------------------------------- | ------------------------------- |
| `int`    | Whole number                            | -2,147,483,648 to 2,147,483,647 |
| `float`  | Number with decimals                    | 6 decimal places                |
| `double` | Number with decimals                    | 15 decimal places               |
| `char`   | stores one character (letter or number) | a single character              |

The basic format is:
`printf("string to display", [list of optional parameters])`.

Optional parameters on the string let you add dynamic values to the string:

```C
int main() {
 int guest = 5;
printf("Hello World, you are guest: %d", guest); //Where %d will be replaced by the first variable listed (guest).
}
```

Indicate a **variable type** to replace on the string:

| symbol   | type            |
| -------- | --------------- |
| %d or %i | int             |
| %f       | double or float |
| %c       | char            |

Common **reserved symbols** for formatting:

| symbol | effect          |
| ------ | --------------- |
| \n     | newline         |
| \r     | carriage return |
| \t     | tab             |

When declaring a `char` **variable**, use single quotes:

```c
char example = 'a';
char foo = '2';
```

Declare a **constant** using the keyword `const` before the type.

it would be `const type variable_name`.

```C
const int SPEEDOFSOUND = 343;
```

*It is best practice to use all upper case letters when declaring a constant.*

To **change the value type of a variable** there are two types of conversions:

1. Implicit: When you set one variable to be the same as another,  but their types do not match, the compiler will try to convert them. The compiler will make a best guess.

2. Explicit:  Telling the compiler what type to set the variable to.

   ```C
   a = b; //Implicit
   a = (int)b; //Explicit
   ```

###### Float Vs Double

A `float` has 6 decimal places vs 15 of a `double. Therefore a `float` takes up less memory (4 vs 8 bytes). 

A `double` runs faster, you gain speed-paying memory usage.

Choose `double`  any time accuracy is important.

