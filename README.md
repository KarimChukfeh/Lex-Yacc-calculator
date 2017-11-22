# CSI 3130 - Assignment 3
#### Judah Olotu 8448799
#### Karim Chukfeh 6694525
#### Kritika Wadhera 8234314
#### Stephanie Giang 8311427

## Question 3: A working calculator which handles multiple variables.


## 1) The BNF
See assignment report

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
Gives the preceding variable the value of the succeeding integer.


### Semicolon ;
Return the evaluation of the preceding statement according to the BNF grammar.

## 3) Regular Expressions and examples

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
