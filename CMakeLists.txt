# @TAG(DATA61_BSD)
cmake_minimum_required(VERSION 3.7.2)
# declare the hello-world CMake project and the languages it is written in (just C)
project(helloworld C)

add_executable(helloworld src/main.c)

# List of libraries to link with the application.
target_link_libraries(helloworld sel4 muslc utils sel4muslcsys sel4platsupport sel4utils sel4debug)

# Tell the build system that this application is the root task. 
DeclareRootserver(helloworld)

GenerateSimulateScript()

