PROJECT(framebuffer-vncserver)
CMAKE_MINIMUM_REQUIRED(VERSION 3.4)

set(CMAKE_VERBOSE_MAKEFILE ON)

FILE(GLOB SOURCES src/*.c)
ADD_EXECUTABLE(framebuffer-vncserver ${SOURCES})

set(libvnc_dir "/home/computer/workspace/libvnc_installed")
set(libvnc_headers "${libvnc_dir}/include")
set(libvnc_libs "-L/home/computer/workspace/build-libvncserver-dvr_uclibc-Release/ -lvncserver -lpthread")

target_include_directories(framebuffer-vncserver PUBLIC ${libvnc_headers})

target_link_libraries(framebuffer-vncserver PUBLIC ${libvnc_libs})

MESSAGE( STATUS "LIBVNC:         " ${LIBVNC} )
