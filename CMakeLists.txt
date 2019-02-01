# @TAG(DATA61_BSD)
cmake_minimum_required(VERSION 3.7.2)
# declare the hello-world CMake project and the languages it is written in (just C)
project(helloworld C)

set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -u __vsyscall_ptr")

add_executable(helloworld src/main.c)

# List of libraries to link with the application.
target_link_libraries(helloworld muslc sel4 utils sel4muslcsys sel4platsupport sel4utils sel4debug)

# Tell the build system that this application is the root task. 
DeclareRootserver(helloworld)

GenerateSimulateScript()

