>COMP 251 NOTES


OS
-
OS doesnt run anything until woken up
to wake the kernal, interupt with: 

        ret = write (fd, buff, size);

user mode vs kernal mode
-
multiprogramming 
 a process is an os abstraction of a running program
 many os's support many programs running concurently

 to start a process:
 1. load instructions into ram, create and initialize new process, initialize cou state to run process

 kernal gets launched from bios, or booting

 kernal is core os fucntionalty for interfacing the hardware and I/O

tmux creates a new window with a consistent connection

you need another program or an interpertor to run code from python or java

c interpetor is 

        clang -o 

programming contraints
-
1. comments 
2. variables - initialization, delceration
3. I/O functions
4. statements (how they are indicated)
5. conditioanls - truth values
6. functions - call, define
7. loops
8. acess

/# include in c allows for pre compilation like import in PY

        #include <>

all variables and methods need to have a type

if method has no inputs then you put void in that spot

        int main(void)

haveing a return is like an error code for main

" is string literals and ' is used for chars


        #include <stdio.h>

        int main(void)
        {
                printf("Hello, World!\n");
                return 0;
        }

variable attributes
        name
        value
        size
        type
        location (in memory)
        scope
        lifetime

c does not have garbage collection (reallocation of unused memory automatically)

multiple declorations of variables on the same line

        long i, j, k;

other types are

1. int
2. long
3. char
4. float
5. double

chaining works in c (right to left)

        x=7
        i=j=k=x+2

all equal from right to left

asighnments return a value

0 is false and every other numver is true

ASCII encoding for letters to equal numbers

so char is technically sharing a value as an int so like 'A' is 1

format modifiers for printf
>(man 3 printf gives more info on the modifers)

/ is integer division "floor division"

unsighned before an int or double allows for no negative numbers but larger positive range

order of operations
-
1. x++ reads variable first then increments
2. ++x adds first then increments



        sizeof(x)

sizeof is an operator (not function) to find amount of bytes associates with type

        scanf("%d", &x);

the location in memory is gotten from the &

anything before the %d will be required as a must for input, almost like a password

curly braces are optional in an else to an if block ( if the else is one statement)

indents dont matter at all

when numbers are too large for their type, they roll over into the negatives for example 9999999999 would be less than 9, because it reads in that first number as some negative number

function prototype gives a signiture of a function doesnt define the function

there are no strings in c

man page sections
-
1. command line utilities (ls)
2. system calls (stat)
3. library calls (printf)


for project 1 (making ls) only have to worry about - or d (file or directory)

&& runs command directly after another

        gcc -o name name.c && name.c

        //this compiles and runs code in one line
 

types
-
- int
- float
- char
- double

arrays
-
name x, type int, values set equal to 0

- int x[5] = {0,0,0,0,0};
- int x[5]; x[0] = 0;

there is no bounds checking in C
- *"you better get your indexing correct"*

there is not index out of bounds error, rather going out of bounds goes to the next or prev or rather in relation memory in regaurds to how far you have gone. Basically all memory is kinda like a large array and going out of bounds just goes to a peice of memory.

- char [size] x;

sizeof(x) would return size if chars
but other size if other types, also only works in main

to tell size of an array you can counter variable

1. track size explicitly (direct)
>- loop through and send length with array into a function
2. sentinal value
>- add a single character at the end that tells when to stop a loop for counting '\0'.
>- name[0]= 'm'; name[1]='e'; name[2]='\0'; withe \0 being the sentinal value

segmentaion fault is when you start acessing memory that you are not supposed to, so if you call a length function on an array with no null terminator, it will go until it finds one, or maybe even never finds it.

STRINGS
-
strings can be made of an array of characters or Chars

- char [size] x;

sizeof(x) would return size if chars
but other size if other types, also only works in main

Look above for parsing and tracking string size
>string uses
- Strlen (find length)
        - returns length of array minus the sentinal value.

- Strcat (concatinate)
        - merges two strings

- Strcmp (compare)
        - returns an int so that of two strings = then val  is 0, if s1 is less than s2 return -num else positive 

- Strcpy (copy)
        -

        char s[10];
        strcpy(s,"hello");

- Strdmp (something with pointers)
        -

        char s[] = strcat("he","lo")

- strdup (duplicate)


- strtok (bad)

Truth in C 
-
0 = false, everything else is true

        if(operation that = 1){
                //code executes
        }
-

        if(operation that = 0){
                //code doesnt execute
        }
-

        if(s[1] == 'j'){
                //code executes if that char is j
        }

Structures
-

closest thing C has to classes

        struct studentT
        {
                char name[65];
                int age;
                float gpa;
                int grad_yr;
        }

readdir returts a struct

        void display_student(struct student_s s)

        morty.name

int is 4 bytes

        int x;

        06 0000 0000
        06 0000 0000
        06 0000 0000
        06 0000 0000

        //x=0

Pointers
-

        int * ptr_x
        //pointer to an int

stores a location to another peice of memory

just a type of variable

all pointers on 64 bit machines are 8 bytes

        char name[64] = "morty";

        //or

        char *name = "Morty Smith"
*

        char c = 'm'
        char *c_ptr = &c
        char c2 = *c_ptr
        *cptr = 'j'

modify something via address (derefrence)

        int n = 8;
        int * ptr;
        ptr = &n; //&= address
        int x = *ptr; // derefrencing
        *ptr = 10; // stores 10 for n

bits
-

        10011010
doesnt mean anything by itself, needs interpertaion
dont have enough info

things are just conventions set to interpret certain kinds of data

binary encoding

numaric bases overall
* decimal - 0 , 1, 2, 3, 4  ...
* hexidecimal - 0...9, a, b... 10
* binary - 0, 1, 10, 11, 100
* octal - 0 ... 7, 

unsigned integer (non negative integer values)

        1011

1 x 2^3
+
 0 x 2^2
 + 
 1 x  2^1
 + 
 1 x 2^0

 1 bit - 2 distinct values - 1
 2 bit - 4 distinct values - 3
 n bit - 2^n distinct values 

 186

        256 - 0 - 186

        128 -1 - 58

        64 - 0 - 58

        32 -1 -26

        16 - 1 - 10

        8 - 1 - 2

        4 - 0 -2

        2 - 1 - 0

        1 - 0 - 0

 010111010

        111 011 010
        rwx -wx -w-
        chmod 732 file

flip the bits +1 to change sign

overflow bits are ignored

memory
-

var attributes
1. name
2. type
3. value
4. size
5. location
6. lifetime
7. scope

parts of program memory
1. os
2. code
3. data
4. heap - 
5. stack - main at bottom (LIFO) last thing to pop

memory allocation
-

malloc

free

void * malloc(size_t, size);

typedef

void pointer is basically just a generic pointer that can point to any type

always cast malloc before using it 

int * intptr = malloc(1000)


static vs dynamic mem alloc
-
static memory - memory is allocated at compile time
1. number of array elements is peminatly fixed
2. allocated in stack or data

synamic memory - memory is allocated at runtime
1. numer of array elemnts is not fixed
2. allocated in heap

./

absolute path
-
        /home/kugele/comp251

fget for input

file descriptor
file streams 

standard in, standard out, standard error

standardIn_0_stdin

standardOut_1_stdout

standardError_2_stderr

print f from out
scan f from in
puts from error

fprtintf, takes in a file stream

fgets(char *s, int size, File *stream)

need to convert newline into null terminator

need to avoid double loop

process managment
-

        #include <stdio.h>
        #include <stdlib.h>
        #include <string.h>
        #include <unistd.h>
        #include <sys/wait.h>

        #define MAX_COMMAND_LENGTH 100
        #define MAX_ARGUMENTS 10

        int main() {
        char command[MAX_COMMAND_LENGTH];
        char *arguments[MAX_ARGUMENTS];
        int status;

        while (1) {
                printf("Shell> ");
                fgets(command, MAX_COMMAND_LENGTH, stdin);

                // Remove newline character from the command
                command[strcspn(command, "\n")] = '\0';

                // Tokenize the command into arguments
                char *token = strtok(command, " ");
                int argIndex = 0;
                while (token != NULL && argIndex < MAX_ARGUMENTS - 1) {
                arguments[argIndex] = token;
                token = strtok(NULL, " ");
                argIndex++;
                }
                arguments[argIndex] = NULL;

                // Fork a child process to execute the command
                pid_t pid = fork();

                if (pid < 0) {
                printf("Fork failed.\n");
                exit(1);
                } else if (pid == 0) {
                // Child process
                execvp(arguments[0], arguments);
                printf("Command not found.\n");
                exit(1);
                } else {
                // Parent process
                waitpid(pid, &status, 0);
                }
        }

        return 0;
        }

create a new process

ps - see processes

replace current running program

fork - pid_t(void) o is returned to the child and process id is returned to parent. basically relicates everything about the parent so child can continue onward

man exec - takes exsiting process and replaces it with new process

im waiting to reap my child!

wait(NULL)

need to wait to see if error from child process

with no wait child becomes zombie

if status z then zombie

array v structs
-

arrays 
* all elements same type
* acess elements with []
* contigues memory

structs 
* elements can have diff types
* acess elements with ->feild
* not contigues memory
