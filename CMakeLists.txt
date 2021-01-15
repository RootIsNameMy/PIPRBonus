cmake_minimum_required(VERSION 3.17)
project(PIPRBonus)

set(CMAKE_CXX_STANDARD 14)

add_executable(bonus)
target_sources(bonus
        PUBLIC
        src/main.cpp
        )

find_package(OpenCL)
message(WARNING "OpenCL found")
message(WARNING "version: ${OpenCL_VERSION_STRING}")
message(WARNING ${OpenCL_INCLUDE_DIRS})
message(WARNING ${OpenCL_LIBRARIES})
target_include_directories(bonus PUBLIC include ${OpenCL_INCLUDE_DIRS})#/opt/AMDAPPSDK-3.0/include




target_link_libraries(bonus PUBLIC ${OpenCL_LIBRARIES})

