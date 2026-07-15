# get_next_line - 42 School

##  About the Project
**get_next_line** is a project about file descriptors, memory allocation, and the power of static variables in C.   
The goal is to write a function that, when called in a loop, allows you to read a text file pointed to by a file descriptor, one line at a time, until the end of the file.

This project is highly practical, as you will use your `get_next_line` function in several future 42 project that requires parsing files (like cub3D, fdf, or minishell).  

These functions all obey `norminette` an automated tool (linter) that checks C code to ensure it strictly follows the school's precise rules on styling, formatting, and structure (such as limiting functions to 25 lines and forbidding more than 5 variables per function).

---

##  Key Concepts Learned
* **Static Variables:** Understanding how to persist data across multiple function calls.
* **File Descriptors (fds):** Managing input streams, standard input, and files.
* **Buffer Management:** Reading chunks of data of varying sizes (defined by `BUFFER_SIZE`) and stitching them together until a newline (`\n`) is reached.
* **Memory Management:** Avoiding memory leaks when dealing with continuous heap allocation and freeing unused buffers.

<div align="center">
    <br>
    <a href="https://github.com/tdanielsousa/42_School/blob/main/Subjects/gnl_subject.pdf" target="_blank">
        <img src="https://img.shields.io/badge/View%20Subject-PDF-red?style=for-the-badge&logo=adobe-acrobat-reader&logoColor=white" alt="Subject PDF" height="40">
    </a>
    <p><i>Click on the button above to see the subject's pdf.</i></p>
    <br>
</div>

---

##  Function Prototype

char *get_next_line(int fd);

### Return Values:
* **Read line:** Returns the line that was read, including the terminating `\n` character (except if the end of the file was reached without a newline).
* **NULL:** Returns `NULL` if there is nothing more to read, or if an error occurred.

---

##  Files Included
* `get_next_line.c` - Contains the main logic of the function.
* `get_next_line_utils.c` - Helper functions (like string manipulation) required for the main function.
* `get_next_line.h` - The header file containing prototypes and structures.

*Note: The repository also includes the `_bonus` files which handle reading from **multiple file descriptors** simultaneously without losing the reading thread of any of them.*

---

##  How to Compile and Run

To compile the project, you must define the `BUFFER_SIZE` macro at compilation time using the `-D` flag.  
You must also create a main.c to test since this is just a function.

### Basic Compilation:
```
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 get_next_line.c get_next_line_utils.c main.c -o gnl
```
### Testing with different buffer sizes:
You can change the buffer size to test your function's stability:
```
cc -Wall -Wextra -Werror -D BUFFER_SIZE=1 get_next_line.c get_next_line_utils.c main.c -o gnl
```

---

##  Testing
To verify that your code works flawlessly and has no memory leaks , you can use my custom made tester:

* **https://github.com/tdanielsousa/get_next_line_tester**

It's a compreensive tester that tests all buffer sizes and runs valgrind to check for memory leaks on every test!  

---
