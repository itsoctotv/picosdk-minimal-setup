# Minimum CMake version
cmake_minimum_required(VERSION 3.13)
include(pico_sdk_import.cmake)
project(program)
pico_sdk_init()


# Add executable
add_executable(program src/main.c)



# Link Pico SDK libraries
target_link_libraries(program pico_stdlib)

# Enable USB output, UART output, etc.
pico_enable_stdio_usb(program 1)
pico_enable_stdio_uart(program 1)

# Create map/bin/hex files
pico_add_extra_outputs(program)
