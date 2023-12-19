cmake_minimum_required(VERSION 3.6)

project(glTFviewer)

find_package(Vulkan REQUIRED)
find_package(glfw3 REQUIRED)

add_subdirectory(ThirdParty/glm)

add_executable(${PROJECT_NAME} src/main.cpp)
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)
target_compile_definitions(${PROJECT_NAME} PRIVATE RESOURCES_ROOT_DIR="${CMAKE_CURRENT_SOURCE_DIR}")
target_link_libraries(${PROJECT_NAME} Vulkan::Vulkan glm glfw)

