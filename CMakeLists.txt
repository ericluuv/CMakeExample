cmake_minimum_required(VERSION 3.8) #REQUIRED, basically minumum version of CMake required for your own use

project(CMakeSingleFolder C CXX) #REQUIRED, sets the project name to whatever we type in at first, 
                                 #with C and CXX being the languages supported

set(CMAKE_C_STANDARD 99) 
set(CMAKE_CXX_STANDARD 11) #Makes sure the compiler knows what to link and include when compiling based on C++ 11
set(CMAKE_POSITION_INDEPENDENT_CODE ON) #Makes sure the compiler doesn't fall back to an eariler version of c++ for linking standards

set(EXECUTABLE_OUTPUT_PATH /Users/ericluu/Desktop/CMakeTutorial/bin) #Where we are putting our executables.
#DO NOT just put bin as the ouput path. The compiler will make a bin folder in the build folder and leave it there.

include_directories(include) #includes header files from where ever we want, in this case in the folder "include"

file(GLOB Sources "src/*.cpp") #Puts all cpp files from the src subdirectory into variable called Sources

add_executable(main ${Sources}) #makes the executable, which is called main

