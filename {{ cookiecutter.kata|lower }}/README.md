# {{ cookiecutter.kata }} Code Kata

Welcome to your new Code Kata.  Test-driven C++ is a lot of fun, and a
highly immersive learning experience.

## Generating the build

The author of this Cookiecutter uses Clang and C++14, so his CMake
invocation is:

```
$ cmake -DCMAKE_CXX_COMPILER=clang++ -DCMAKE_BUILD_TYPE=Debug -DCMAKE_CXX_FLAGS="-std=c++14"
  -DCMAKE_CXX_FLAGS_DEBUG="-fstandalone-debug -ggdb -O0" ..
```

## The TDD microcycle

TDD explanation todo

```                                 
  +--------------------------------+
  | RED: write the smallest amount |
  | of code to make the test fail, |------------+
  | and treat compilation failures |            |
  | as a test failure.             |            |
  +--------------------------------+            |
         ^                                      |
         |                                      v
         |                +-------------------------------------+
         |                | GREEN: write the smallest amount of |
         |                | production code to pass the one     |
         |                | failing test.                       |
         |                +---------------------+---------------+
         |                                      |
         |                                      |
     +---+-----------------------------+        |
     | REFACTOR: clean up the code,    |        |
     | remove duplication, improve     |<-------+
     | names to better express intent. |
     +---------------------------------+
```
