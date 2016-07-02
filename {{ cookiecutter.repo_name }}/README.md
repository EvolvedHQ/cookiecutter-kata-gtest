# {{}} Code Kata

##

```
$ cmake -DCMAKE_CXX_COMPILER=`which clang++-3.5` -DCMAKE_BUILD_TYPE=Debug \
  -DCMAKE_CXX_FLAGS="-std=c++14" \
  -DCMAKE_CXX_FLAGS_DEBUG="-fstandalone-debug -ggdb -O0" ..
```

##

## Test List

Kent Beck suggests using a test list. You can sketch one out here, if
that works for you.
