# abacus

Abacus is a simple interactive calculator CLI with support for variables, comparison checks, and math functions

```
λ ./abacus -h         
abacus - a simple interactive calculator CLI with support for variables, 
comparison checks, and math functions

v1.0.0

Usage: abacus [--no-color] [--precision PRECISION] [--eval EVAL]

Options:
  --no-color, -n         disable color in output [default: false]
  --precision PRECISION, -p PRECISION
                         precision for calculations [default: 64]
  --eval EVAL, -e EVAL   evaluate expression and quit
  --help, -h             display this help and exit
  --version              display version and exit

```

## Install

`go get -u github.com/viktordanov/abacus`

## Features
- `History of expressions` and `Tab completion` of all math functions and defined variables
- All common operations
  ```
  > 1+1
  2
  > 1-20
  -19
  > 5^0 / 20
  0.05
  > 2**(2+5)
  128
  ```
- Variables
   ``` 
   > d = 12.5
   12.5
   > d * 5 + 5
   67.5
   > a * 5 + 5
   5
   ```
  **Note:** Undefined variables are equal to 0
- Comparisons `<, ==, >, <=, >=`
  ```
  > pi > phi
  true
  > 10 <=10
  true
  > 2 == 0
  false
  ```
- E, Pi, Phi
   ``` 
   > e
   2.7182818284590450907955982984276
   > pi
   3.1415926535897931159979634685442
   > phi
   1.6180339887498949025257388711907
   ```
- Single arity functions:
    - sqrt
    - ln
    - floor
    - ceil
    - exp
    - sin
    - cos
    - tan
    - round
- Two arity functions:
    - round (number, digits of precision)
   ```
   > round(1.123456789,4)
  1.123
   ```
    - log (number, base)
   ```
   > log(16,4)
  2
   ```
    - min, max
   ```
   > d = 10
   10 
   > min(d,4)
   4
   > max(d,4)
   10
   ```

## Reserved names
 
 * `quit` – If a query includes quit, the program will terminate and the query will not be saved to the history file
 * The constants `e`, `pi`, and `phi`

# TODO

- [x] Add full feature list
- [ ] Write tests
  - [x] Base tests
  - [x] Simple benchmark of a complicated expression
  - [ ] Improve tests
- [ ] Refactor to depend less on other packages
- [ ] Implement most single arity functions with `*big.Float` for improved precision
