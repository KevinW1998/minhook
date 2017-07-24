# Header
cmake_minimum_required (VERSION 3.7.2)
project(MinHook C)

set(CMAKE_DEBUG_POSTFIX d)

set(MINHOOK_FILES 
    include/MinHook.h
    src/hde/hde32.c
    src/hde/hde32.h
    src/hde/hde64.c
    src/hde/hde64.h
    src/hde/pstdint.h
    src/hde/table32.h
    src/hde/table64.h
    src/buffer.c
    src/buffer.h
    src/hook.c
    src/trampoline.c
    src/trampoline.h
)

add_library(MinHookStaticLib STATIC ${MINHOOK_FILES})

install(TARGETS MinHookStaticLib
        RUNTIME DESTINATION bin
        LIBRARY DESTINATION lib
        ARCHIVE DESTINATION lib/static)

install(DIRECTORY include/ DESTINATION include)



