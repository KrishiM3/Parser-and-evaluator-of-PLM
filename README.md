# Parser-and-evaluator-of-PLM
PLM (Programming Language of the Moment) is a language that allows users to write code that
computes non-negative integers. A PLM program consists of several lines of code, each of which
defines a single function. For instance the function that returns its argument incremented by 4
can be defined using the following syntax.
DEF ADDFOUR x { x+4 } ;
ADDFOUR will be called the function name, x will be called the parameter name and x+4 is
the function body.
A function definition must contain the seven elements specified below. They must occur in a
single line, exactly in the order listed below, and must be separated from each other by exactly
one space character.
• keyword DEF
• function name
• parameter name
• left brace
• function body
• right brace
• semicolon
Additionally, PLM code must satisfy all conditions described below.
1. The character D from DEF must be the first character on each line with a function definition.
2. The semicolon in the last function definition must be followed immediately by the end-ofline character and then the end-of-file character.
3. Function names are non-empty strings of upper-case letters with one exception. The word
DEF is a keyword and a reserved word in the language. Consequently, DEF cannot be used
as the name of a function.
4. Parameter names are non-empty strings of lower-case letters.
5. The only exception to the rules is the function name MAIN. No parameter name is allowed
after MAIN, i.e. MAIN must be followed by one space and then the left brace.
6. There can be no whitespace inside the function body, but remember that the body must
be separated from the enclosing braces by one space on each side.
7. The function body is an arithmetic expression built from non-negative integers, the associated parameter name as well as function calls. The only arithmetic operations allowed
are addition and multiplication. Parentheses are not allowed, except in function calls (see
next point). The function body must be non-empty.
8. Function calls have to refer to functions that have been defined as part of the same program.
Function definitions are listed in no particular order. It is possible for a function body to
make calls to functions defined later in the program. Functions can also call themselves.
9. Any function different from MAIN can be called. Function calls are made by mentioning
the relevant function name along with an argument enclosed in a pair of parentheses, e.g.
ADDFOUR(3+5*6). No Whitespace can occur between the parentheses. The argument must
satisfy the same constraints as function bodies. That is, it must be a non-empty arithmetic
expression built from addition, multiplication, non-negative integers, the parameter name
of the function that is making the call, as well as calls to other functions.
10. Every program must define the MAIN function.
11. No function can be defined twice.
12. No characters other than the specific ASCII characters referenced so far, are allowed.

To run:
javacc Parser.jj
javac *.java
For reading an input file called test.txt, the command
java Parser < test.txt
