cmake_minimum_required(VERSION 3.8) #REQUIRED, basically minumum version of CMake required for your own use

project(CMakeSingleFolder C CXX) #REQUIRED, sets the project name to first argument, and C & CXX specify what languages are 
#supported.

set(CMAKE_C_STANDARD 99)
set(CMAKE_CXX_STANDARD 11) #Makes sure the compiler knows what to link and include when compiling based on a certain c++ standard
set(CMAKE_POSITION_INDEPENDENT_CODE ON) #Makes sure the compiler doesn't fall back to an eariler version of c++ for linking 
#standards

set(EXECUTABLE_OUTPUT_PATH /Users/ericluu/Desktop/CMakeTutorial/bin) #Specifies the path for the executable to be put.
#Unfortunately putting bin or /bin will make a folder inside of the build subdirectory that CMake will create. In order to have 
#to output to the bin folder the absolute path is needed, so you'll need to change that if you want it in the bin folder, or just 
#leave this line out to have the executable be made in the build folder.

include_directories(include) #takes in a relative/absolute path to include files from.class Here we take them from the 
#subdirectory "include".

file(GLOB Sources "src/*.cpp") #Puts all cpp files from the "src" subdirectory into a subdirectory called "Sources."

add_executable(main ${Sources}) #Makes the executable, which is called main. We also put in our sources files from the variables 
#Sources.