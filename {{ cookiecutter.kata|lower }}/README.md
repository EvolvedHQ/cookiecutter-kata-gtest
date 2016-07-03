# {{ cookiecutter.kata }} Code Kata

Welcome to your new Code Kata.  Test-driven C++ is a lot of fun, and a
great form of "deliberate practice".  You're almost there - there's
one more step needed to get up and running.

## Generating the build

You've used a cookiecutter to generate this project, but there's
another step to get started - this project is based on CMake, so you
need to use this CMake build to generate a build that will work on
your system.

This build structure can be done "out of tree" (ie not in this folder
structure), or use the .build/ folder that's automatically created -
this is also in the .gitignore by default, if you want

A typical CMake invocation (for Clang and C++14) would be:

```
$ cd .build
$ cmake -DCMAKE_CXX_COMPILER=clang++ -DCMAKE_BUILD_TYPE=Debug
  -DCMAKE_CXX_FLAGS="-std=c++14"
  -DCMAKE_CXX_FLAGS_DEBUG="-fstandalone-debug -ggdb -O0" ..
```

Then run the makefile as (for example):

```
$ make -j8 unit
```

## The TDD microcycle

TDD gives you a very fast feedback cycle, and helps you build a
solution incrementally, in baby steps.  TDD gives you feedback on your
design and lets you make many, small, incremental improvements to your
code - you can do this with confidence because the tests will catch
any regressions.

TDD uses a microcycle of three phases, always starting with "RED" : a
failing test, or failing compilation.

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
