# tiny-process-library
A small platform independent library making it simple to create and stop new processes in C++, as well as writing to stdin and reading from stdout and stderr of a new process.

This library was created for, and is used by the C++ IDE project [juCi++](https://gitlab.com/cppit/jucipp).

### Features
* No external dependencies
* Simple to use
* Platform independent
  * Creating processes using executables is supported on all platforms
  * Creating processes using functions is only possible on Unix-like systems
* Read separately from stdout and stderr using anonymous functions
* Write to stdin
* Kill a running process (SIGTERM is supported on Unix-like systems)
* Correctly closes file descriptors/handles

### Usage
See [examples.cpp](examples.cpp).

### Get, compile and run

#### Unix-like systems
```sh
git clone http://gitlab.com/eidheim/tiny-process-library
cd tiny-process-library
mkdir build
cd build
cmake ..
make
./examples
```

#### Windows with MSYS2 (https://msys2.github.io/)
```sh
git clone http://gitlab.com/eidheim/tiny-process-library
cd tiny-process-library
mkdir build
cd build
cmake -G"MSYS Makefiles" ..
make
./examples
```

#### Windows with MSVC installed
```sh
git clone http://gitlab.com/eidheim/tiny-process-library
cd tiny-process-library
mkdir build
cd build
cmake ..

To build a shared library run instead the command below
cmake -DBUILD_SHARED_LIBS=ON ..

To build with Debug config run the command below:
cmake --build .

But to build for release run the command below:
cmake --build . --config Release

cd to Debug or Release folder and run examples.exe.

Ensure that tiny-process-library/install directory exists,
and it contains two folders - 'shared' for shared library and 'static' for static library.
Then run the commands below to get the usable library:
for shared library -
cmake --install . --prefix ../install/shared
for static library -
cmake --install . --prefix ../install/static
```
