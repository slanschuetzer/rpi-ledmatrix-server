cmake_minimum_required(VERSION 3.13)
project(rpi_ledmatrix_server)

set(CMAKE_CXX_STANDARD 14)

include_directories(.)

set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)
find_package(JPEG REQUIRED)
find_package(PNG REQUIRED)

#add_library(dma dma.c dma.h)

add_executable(rpi_ledmatrix_server
        clk.h
        dma.c
        dma.h
        gpio.h
        mailbox.c
        mailbox.h
        main.c
        pcm.c
        pcm.h
        pwm.c
        pwm.h
        readpng.c
        readpng.h
        rpihw.c
        rpihw.h
        spi.cpp
        spi.h
        ws2811.c
        ws2811.h)

target_link_libraries(rpi_ledmatrix_server PRIVATE Threads::Threads JPEG::JPEG PNG::PNG)