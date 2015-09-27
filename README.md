# Chip-8 Emulator

## Building

This code has only been tested on Linux, although it may work on other platforms provided the required dependencies are available.

### Requirements
- A C++11 compiler
- [GLFW3](http://www.glfw.org/)
- GLEW (OpenGL Extension Wrangler)

### Compilation
Then compile using CMake:
```
mkdir build
cd build
cmake ../
make
```

or just run:
```
g++ main.cpp chip8.cpp -std=c++11  -lglfw -lGLEW -lGL -lGLU -pthread -O3 -Wall -pedantic
```

## Usage

    ./chip8 program-file [instructions_per_step]

You can adjust the speed of the emulator by changing `instructions_per_step` (defaults to 10). This parameter represents the number of Chip-8 instructions executed for each tick of the timers (which run at 60Hz).

10 (or a little higher) works well for most games tested, but Connect4 needs `instructions_per_step=1` to be playable.

### Keyboard map
    Chip-8:    QWERTY keyboard:

    1 2 3 C        1 2 3 4
    4 5 6 D        Q W E R
    7 8 9 E        A S D F
    A 0 B F        Z X C V

## TODO
- Add sound
- Add more configuration options, e.g. screen size, colours