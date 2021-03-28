# luacpp
Lua CPP wrapper

## Build Status
[![<ORG_NAME>](https://circleci.com/gh/jordanvrtanoski/luacpp/tree/circleci-project-setup.svg?style=shield)](https://circleci.com/gh/jordanvrtanoski/luacpp)


## Installing

```
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Debug ../Source
make -j 4
```

## Building documents

```
sudo apt-get install texlive-latex-base texlive-latex-recommended texlive-latex-extra graphviz

mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Debug ../Source
make doc_doxygen

cd build/doc_doxygen/latex
make pdf
```

## Testing the memory management

```
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Debug ../Source
make -j 4

valgrind -v --run-cxx-freeres=yes --run-libc-freeres=yes ./hello
```

## Running the unit test

```
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Debug ../Source

make -j 4
make test 
```

## Running the coverage test

```
apt install gcovr
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Coverage ../Source

make -j 4
make coverage-cli
make coverage-html
```
