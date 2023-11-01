This repository contains the files needed to complete the LIFO FIFO project in ALX.

The files and their functions are recorded within this readme.

# Monty Scripting Language

Monty 0.98 is a scripting language that undergoes an initial compilation into Monty bytecode, similar to Python. It operates based on a distinct stack and includes specific instructions for stack manipulation. The primary objective of this project is to develop an interpreter for Monty ByteCodes files.

## Monty Byte Code Files

Monty bytecode files typically employ the .m extension, a widely adopted convention in the industry, although it is not mandated by the language specification. Each line contains only one instruction, and any number of spaces before or after the opcode and its associated argument are permissible. Here's an example:

```plaintext
push 0$
push 1$
push 2$
push 3$
pall$
push 4$
push 5$
push 6$
pall$
```

Monty bytecode files can also include blank lines or lines filled with spaces, and any additional text following the opcode or its required argument is ignored. For instance:

```plaintext
push 0 Push 0 onto the stack$
push 1 Push 1 onto the stack$

push 2$
push 3$
pall$
$
$
$
push 4$

push 5$
push 6$
pall This is the end of our program. Monty is awesome!$
```

# Usage

To compile all the files, use the following command:

```shell
gcc -Wall -Werror -Wextra -pedantic *.c -o monty
```

To execute the program, run:

```shell
./monty bytecode_file
```

Available operation codes are as follows:

| Opcode | Description |
| ------- | ----------- |
| push   | Pushes an element onto the stack. For example, `push 1` pushes 1 onto the stack. |
| pall   | Prints all the values on the stack, starting from the top of the stack. |
| pint   | Prints the value at the top of the stack. |
| pop    | Removes the top element from the stack. |
| swap   | Swaps the top two elements of the stack. |
| add    | Adds the top two elements of the stack. The result is stored in the second node, and the first node is removed. |
| nop    | This opcode has no effect. |
| sub    | Subtracts the top two elements of the stack from the second top element. The result is stored in the second node, and the first node is removed. |
| div    | Divides the top two elements of the stack from the second top element. The result is stored in the second node, and the first node is removed. |
| mul    | Multiplies the top two elements of the stack from the second top element. The result is stored in the second node, and the first node is removed. |
| mod    | Computes the remainder of the top two elements of the stack from the second top element. The result is stored in the second node, and the first node is removed. |
| #      | When a line begins with a # character, the entire line is treated as a comment. |
| pchar  | Prints the integer stored at the top of the stack as its ASCII value representation. |
| pstr   | Prints the integers stored in the stack as their ASCII value representations. It stops printing when the value is 0, when the stack is empty, or when the value of an element is a non-ASCII value. |
| rotl   | Rotates the top of the stack to the bottom of the stack. |
| rotr   | Rotates the bottom of the stack to the top of the stack. |
| stack  | This represents the default behavior, setting the format of the data into a stack (Last In, First Out - LIFO). |
| queue  | Sets the format of the data into a queue (First In, First Out - FIFO). |
