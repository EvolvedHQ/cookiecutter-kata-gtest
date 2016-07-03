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

TDD gives you a very fast feedback cycle, and helps you build a
solution incrementally, in baby steps.

TDD gives you feedback on your design and lets you make many, small,
incremental improvements to your code - you can do this with
confidence because the tests will catch any regressions.

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

## Resources

There's a great list of Code Kata exercises at
[codekata.com](http://codekata.com/). Emily Bache write and published
[an excellent book](https://leanpub.com/codingdojohandbook) on code
katas, and guidance for running coding dojos.

Read the documentation on [Google
Mock](https://github.com/google/googletest/tree/master/googlemock/docs/v1_7)
and [Google
Test](https://github.com/google/googletest/tree/master/googletest/docs)
online.
