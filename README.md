# c-polynomial

`libpolynomial` is a simple C library of a polynomial ADT that supports addition, subtraction, multiplication, differentation, integration, and other useful operations.

## Installation

To install the library to the default location (`/usr/local/`) run as root:

```bash
$ make install
```

## Usage

1. Include the `polynomial.h` header in your program.

    ```c
    #include <polynomial.h>
    ```
    
2. Use the library functions accordingly.

    ```c
    #include <polynomial.h>
    
    int main(int argc, char **argv)
    {
        Polynomial *p = polynomial_new(5);
        polynomial_set_coefficient(p, 0, 7);
        polynomial_set_coefficient(p, 1, 2);
        polynomial_set_coefficient(p, 2, 3.5);
        polynomial_set_coefficient(p, 3, 0.9);
        polynomial_set_coefficient(p, 4, 18);
        polynomial_set_coefficient(p, 5, 1);
    
        Polynomial *q = polynomial_new(3);
        polynomial_set_coefficient(q, 0, 1);
        polynomial_set_coefficient(q, 1, 3);
        polynomial_set_coefficient(q, 2, 0.2);
        polynomial_set_coefficient(q, 3, 4);
    
        Polynomial *add = polynomial_add(p, q);
        Polynomial *subtract = polynomial_subtract(p, q);
        Polynomial *multiply = polynomial_multiply(p, q);
        Polynomial *symmetric = polynomial_symmetric(p);
        Polynomial *derivative = polynomial_derivative(p);
        double integral = polynomial_definite_integral(p, 2, 3);
        double val = polynomial_evaluate(p, 3.5);
    
        polynomial_destroy(&p);
        polynomial_destroy(&q);
        polynomial_destroy(&add);
        polynomial_destroy(&subtract);
        polynomial_destroy(&multiply);
        polynomial_destroy(&symmetric);
        polynomial_destroy(&derivative);
    
        return 0;
    }
    ```

3. Link the program against the static library and compile it.

    ```bash
    $ gcc foo.c -lpolynomial -o foo
    ```

## Documentation

Coming soon.

## Development

##### Dependencies

- `gcc`.

##### Build

```bash
$ make
```
