# Template for TDD Code Katas in C++

Hey there. This is a cookiecutter template for a simple TDD code kata
using Google Test/Google Mock.  It's intended to give you a repeatable
way of very quickly getting started for a "deliberate practice"
session with C++.

## Features of this template

This generates a project for doing a test-driven code kata in C++.

- Includes Google Test and Google Mock libraries
- Generates a header, "production" source file and an empty test
- Generates a CMake build which will work on most platforms
- Has some convenience targets for generating etags and running unit
  tests

## Pre-requisites

You'll need to have [cookiecutter
installed](https://github.com/audreyr/cookiecutter). This is a Python
tool - on most platforms, install using:

```
$ pip install cookiecutter
```

After the kata project is created, you'll need to generate a build
using CMake, and then of course compile, link and execute the
kata. This is all going to take a fairly complete C++ development
toolchain, and you'll need to figure out how to get this configured
for your platform, if you don't already have one.

The minimum requirements are from Google Mock, which supports C++98 or
later (although we'd suggest that TDD in C++ is so much more fun with
C++14 or later using a modern toolchain...):

https://github.com/google/googletest

## Generating your project

Start by invoking cookiecutter. This can be done locally - handy if
you're working disconnected:

```
$ cookiecutter <path-to-this-template>
```

or directly from the GitHub URL where the template lives:

```
$ cookiecutter https://github.com/13coders/template-kata-gtest
```

Cookiecutter will prompt you for only a few parameters, and most of
them can be globally configured for reuse.

```
kata [CodeKata]: 
```

This is name of the Code Kata. Typical values will be "GameOfLife".
Whatever name you provide will be capitalised exactly as you enter it
for:

- The name of the test file, source file and header will be, for
  example "GameOfLife.cpp", "GameOfLifeTest.cpp" etc

- The name will be lowercased for the CMake file, the name of the
  repository, the value in the #include guard and the dummy namespace
  that's

So, long story short, if you're a CamelCase type, use "GameOfLife" as
the kata name, or if you're a snake_case type, then use "game_of_life".

```
etags [y]:
```

Whether or not to include the build file magic for generating an etags
file when recompiling-, which defaults to "y". If you choose no, there
will be no dependency on etags in the build.

If you want to, you can always add any extra tools you need (static
analyzers, sanitizers etc) into the CMake file yourself - it's a
minimal starting point.

## Next steps

Your newly generated project has its own README.md, which has the next
steps for compiling, linking and running the tests. There are also
some useful resources linked in there on TDD, software craftsmanship
and code katas to try out.

Happy coding !
