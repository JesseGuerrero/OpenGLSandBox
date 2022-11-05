cmake_minimum_required(VERSION 3.23)
project(NewProject)

set(CMAKE_CXX_STANDARD 23)

include("D:/Other/New folder/vcpkg/scripts/buildsystems/vcpkg.cmake")
include_directories("include")

find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)
find_library( ASSIMP_LIBRARY assimp-vc142-mtd)
find_package(assimp REQUIRED)
find_package(GLEW REQUIRED)


find_package(glfw3 REQUIRED)
find_library( GLFW3_LIBRARY glfw3dll )
find_package(glad CONFIG REQUIRED)
find_package(glm CONFIG REQUIRED)

add_executable(main main.cpp)

target_link_libraries(main PRIVATE ${OPENGL_gl_LIBRARY})
target_link_libraries(main PRIVATE ${GLFW3_LIBRARY})
target_link_libraries(main PRIVATE ${ASSIMP_LIBRARY})
#target_link_libraries(main PRIVATE irrKlang)
#        target_link_libraries(${_name} PRIVATE assimp::assimp)
#target_link_libraries(main PRIVATE GLEW::GLEW)
target_link_libraries(main PRIVATE glad::glad)
#        target_link_libraries(${_name} PRIVATE glfw)
target_link_libraries(main PRIVATE glm::glm)