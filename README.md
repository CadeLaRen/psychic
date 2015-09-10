# psychic

Python-Powered C Unit Testing Library.
* Recursively finds all test_*.c files
* Supports setup and teardown
* Returns 0 if all tests pass and n != 0 if some of them fail (with n equals to the number of failed tests)
* Assumes any function name that starts with "test_" to be a test
* Automagically adds the needed headers, you can just go ahead and write assertions
* All you need to do is to type `psychic`!

## Getting Started

* Install psychic: `pip install psychic`
* Write a test by creating a file called "test_something.c"
```c
void test_something() {
        assert_equals_str("this", "that");
}
```
* Run with `psychic`. It will fail
* Fix it and run it again to see it passing
* You can add `setup` and `teardown`
```c
void setup() {
// do something before each test in this file
}

void teardown() {
// do something _after_ each test in this file
}
```

## Assertions
```c
void assert(int b);
void assert_true(int b);
void assert_false(int b);
void assert_null(void *p);

void assert_equals_int(int a, int b);
void assert_equals_str(char *a, char *b);
void assert_equals_char(char a, char b);
void assert_equals_float(float a, float b);
void assert_equals_double(double a, double b);

void assert_not_null(void *p);
void assert_not_equals_int(int a, int b);
void assert_not_equals_str(char *a, char *b);
void assert_not_equals_float(char *a, char *b);
void assert_not_equals_double(char *a, char *b);
```

## Options
* --cargs= : adds arguments to the C compiler (a common one will be -I for passing user library paths)
* -d : run on debug mode (requires gdb to be installed)

## License
```
Copyright 2015 Duda Dornelles

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
