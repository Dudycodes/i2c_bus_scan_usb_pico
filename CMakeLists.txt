cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(bus_scan_usb_project C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
pico_sdk_init()

add_executable(bus_scan
    bus_scan.c
)

pico_enable_stdio_usb(bus_scan 1)
pico_enable_stdio_uart(bus_scan 0)

pico_add_extra_outputs(bus_scan)

target_link_libraries(bus_scan pico_stdlib hardware_i2c)
