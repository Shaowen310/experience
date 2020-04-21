# cmake

## Example

CMakeLists.txt

```text
cmake_minimum_required (VERSION 3.6)

project (proj_name VERSION 0.1 LANGUAGES C)

set(OPENSSL_USE_STATIC_LIBS FALSE)
find_package(OpenSSL REQUIRED)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

# Sub directories
set(LIBRARY_DIR ${CMAKE_SOURCE_DIR}/lib)
add_subdirectory(${LIBRARY_DIR}/log.c)
add_subdirectory(${LIBRARY_DIR}/aes-gcm-wrapper)

set(PROJECT_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include)
set(PROJECT_SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src)

add_library(static_lib_name STATIC ${PROJECT_SOURCE_DIR}/static_lib_name.c ${PROJECT_SOURCE_DIR}/static_lib_name.c)
target_include_directories(static_lib_name
    PUBLIC 
        $<BUILD_INTERFACE:${PROJECT_INCLUDE_DIR}>)
target_link_libraries(static_lib_name PRIVATE aes-gcm-wrapper clogger)

add_executable(${PROJECT_NAME} proj_name.c)
target_link_libraries(${PROJECT_NAME} PRIVATE 
    clogger 
    static_lib_name)
```

## Points to note

### variables are scoped and will be passed from parent to children

eg.

```text
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin/lib)
add_subdirectory(${CMAKE_SOURCE_DIR}/lib/log.c)
```

Then the library's binary file will be stored in ${CMAKE\_BINARY\_DIR}/bin/lib

### PRIVATE INTERFACE PUBLIC when including a header

PRIVATE means it is used by its implementation file but not used by any external project

INTERFACE means it will be used by external projects but not by its implementation file, eg. a file with only MACROs

PUBLIC == PRIVATE + INTERFACE

### When linking libraries, just use built library names no need include headers again

