# CSI 3130 - Assignment 3
#### Judah Olotu 8448799
#### Karim Chukfeh 6694525
#### Kritika Wadhera 8234314
#### Stephanie Giang 8311427

## Question 3: A working calculator which handles multiple variables.


## 1) The BNF
```yacc
program:
    function	{ exit(0); }
    ;

function:
        function stmt   { interpret($2); freedom($2); }
        | /* NULL */
        ;

stmt:
    ';'				{ $$ = opera(';', 2, NULL, NULL); }
    | expr ';'			{ $$ = $1; }
    | PRT expr ';'		{ $$ = opera(PRT, 1, $2); }
    | VARIABLE '=' expr ';'	{ $$ = opera('=', 2, identifier($1), $3); }
    ;

expr:
    INTEGER                 { $$ = constant($1); }
    | VARIABLE              { $$ = identifier($1); }
    | expr '+' expr         { $$ = opera('+', 2, $1, $3); }
    | expr '-' expr         { $$ = opera('-', 2, $1, $3); }
    | expr '%' expr         { $$ = opera('%', 2, $1, $3); }
    | expr '*' expr         { $$ = opera('*', 2, $1, $3); }
    | expr '/' expr         { $$ = opera('/', 2, $1, $3); }
    | '(' expr ')'          { $$ = $2; }
    | '-' expr %prec UMINUS { $$ = opera(UMINUS, 1, $2); }
    ;

```
## 2) The Tokens
### Addition operator  +
Adds the succeeding value to the preceding value, from left to right.


### Subtraction operator  -
Subtracts the succeeding value from the preceding value, from left to right.


### Modulus operator  %
Gets the remainder of dividing the succeeding value to the preceding value, from left to right.


### Multiplication operator  *
Multiplies the succeeding value by the preceding value, from left to right.


### Division operator  /
Divides the succeeding value by the preceding value, from left to right.


### Open parenthesis symbol (
Evaluates the succeeding expression (until the close parenthesis symbol) first, from left to right.


### Close parenthesis symbol )
Evaluates the preceding expression (until the open parenthesis symbol) first, from left to right.


### Equal sign =
Expects a preceding variable and a succeeding variable or integer.
Gives the preceding variable the value of the succeeding variable/integer.


### Semicolon ;
Return the evaluation of the preceding statement according to the BNF grammar.


### Lower case alphabet characters [a-z] as variables
Treated as integer variables that have the value of the integer or variable succeeding an equal sign.
The math tokens above work with these variables as expected of a calculator.


## 3) Regular Expressions

### print
Outputs the return of the rest of the statement to console


## 4) Examples

Example 1:
`print 1+2;`
outputs
`Calculator output: 3`

Example 2:
`x = 2;`
`y = 3;`
`print x + y;`
outputs
`Calculator output: 5`


## 4) Compiling and using the calculator
### Step 1
In bash run the build_partial script by running inside the project main directory
  sh build_partial.sh

### Step 2
Run the calculator inside the build directory by running
   build/calculator_partial

### Step 3
Use the calculator as described above. i.e.
     print 1+2;

### Step 4
Exit the calculator with
     ctrl+c

### Step 5
Clean up the generated files by running the clean-up script inside the project main directory
     sh clean_partial.sh
