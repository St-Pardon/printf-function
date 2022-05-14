# Understanding The `printf()` Function

The `printf()` function is a c function used to output results to the standard input and output `(stdio)`. The function is variadic by nature which means it can take a varied number of arguments.

**Printf** uses *format identifies* (which describes the expected data) to output various data types and format to the stdio. Some of these *format identifies* are:

- `%d %i`  - This is used to output decimal(meaning base 10) signed integers.

- `%o` -  This is used to output octal(meaning base 8) integers.

- `%x %X` - This is used to output hex(meaning base 16) integers.

- `%u` - This is used to output unsigned integers.

- `%c` - This is used to output characters.

- `%s` - This is used to output strings (an array of characters).

- `%f` - This is used to output float (a number with a decimal point).

- `%p` - This is used to output pointers.

- `%n` - This is used to output the number of characters written by this printf.



It is important to note that there are more format indicators than the ones mentioned above, but some of these above are the one we have come across during the course of our journey with ALX.

Looking at the flags/indicators above we can notice they have one thing in common which is the **%** symbol.

So basically what this means is that we are going to build a function that will output to the stdio the various data types and structure from our c program and this will require understanding how the `printf()` sends its output to the stdio.

The simplest way to explain and understand this is by using the `putchar()` function or in our case `“_putchar()”` for **ALX**. The `_putchar()` function as we know is used to output a single character to the standard output. It does this with the help of a “`write()` function” from the `“unistd library”`. On the other hand, the `_putchar()` is also used to output more than one character by looping through the list of characters and outputting them to the standard output one by one without any *space or newline (\n)* making it look like it outputs a string. For example

```c

int main(void)

{

	char str[] = “Hello World”;
	
	_putchar(“Hello World\n”);
	
}

```

The above code will throw an error during compilation. While the code below

```c

int main(void)

{

int i;

char str[] = “Hello World”;

     for (i = 0; i != ‘\0’; i++)
     
     {
     
	_putchar(str[i]);
	
}

_putchar(‘\n);

}

```

Will loop through and output the character one by one until it reaches the null value `(\0)` and then prints a newline `(\n)`.



> NB: string is not a data type in c, it’s better referred to as an array of characters to which the computer uses the null value `(\0)` to know the end of the string. So when we have a string like `“hello world”` it would look like this in the computer memory `{“h”, “e”, “l”, “l”, “o”, “ “, “w”, “o”, “r”, “l”, “d”, “\0”}` with the null marking the end.



Understanding this will help in figuring out the `printf()` which is a lot more complex because it uses a more helper function like `_putchar()` to write to the `stdio`.

The `printf()` function being variadic in nature pairs a helper function to its flag and also helps in grouping the arguments it receives.



