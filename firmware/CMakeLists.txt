cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(trackball)

pico_sdk_init()

add_compile_options(-Wall)

add_executable(trackball src/trackball.cc src/pmw3360.cc src/srom.cc src/crc.cc)

target_include_directories(trackball PRIVATE src)

target_link_libraries(trackball pico_stdlib hardware_spi hardware_flash hardware_adc tinyusb_device tinyusb_board)

pico_add_extra_outputs(trackball)
