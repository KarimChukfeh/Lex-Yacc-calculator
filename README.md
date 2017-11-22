# CSI 3130 - Assignment 3
## Working calculator which handles multiple variables.


#### Judah Olotu
#### Karim Chukfeh 6694525
#### Kritika Wadhera
#### Stephanie Giang

## BNF
See assignment report

## Tokens
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
Gives the preceding variable the value of the succeeding integer.


### Semicolon ;
Return the evaluation of the preceding statement according to the BNF grammar.

## Regular Expressions

### print
Outputs the return of the succeeding expression to console

Example:
`print 1+2;`
outputs
`Calculator output: 3`


### Single alphabet characters [a-z, A-Z] as variables
Treated as variables that store the value succeeding an equal sign

Example:
`x = 2;
y = 3;
print x + y;`
outputs
`Calculator output: 5`

## Compiling and using the calculator
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
