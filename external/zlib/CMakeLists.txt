
cmake_minimum_required(VERSION 3.0)
project(zlib)
SET(ZLIB_SOURCE ./adler32.c 
                ./crc32.h ./crc32.c 
                ./deflate.h ./deflate.c
                ./gzguts.h ./gzclose.c 
                ./gzlib.c  ./gzread.c 
                ./gzwrite.c ./infback.c 
                ./inffast.h ./inffast.c 
                ./inffixed.h 
                ./inflate.h ./inflate.c
                ./inftrees.h ./inftrees.c 
                ./trees.h ./trees.c 
                ./zconf.h ./uncompr.c 
                ./zlib.h 
                ./zutil.h ./zutil.c)
SET(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/../../lib)
if(CMAKE_CL_64)
    #64位的设置
    set(CMAKE_DEBUG_POSTFIX "_64d")    
    set(CMAKE_RELEASE_POSTFIX "_64r") 
    #设置DEBUG的输出目录
    SET(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG ${PROJECT_SOURCE_DIR}/../../bin/Debug64/)
    #设置RELEASE的输出目录
    SET(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE ${PROJECT_SOURCE_DIR}/../../bin/Release64/)
else()
    #32位的设置
    #设置DEBUG版本的后缀为_32d
    set(CMAKE_DEBUG_POSTFIX "_32d")
    #设置Release版本的后缀为_32r    
    set(CMAKE_RELEASE_POSTFIX "_32r") 
    SET(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG ${PROJECT_SOURCE_DIR}/../../bin/Debug32/)
    SET(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE ${PROJECT_SOURCE_DIR}/../../bin/Release32/)
endif()
#设置生成共享lib
SET(BUILD_SHARED_LIBS OFF)
#设置生成的动态库的名称为zlib
add_library(zlib ${ZLIB_SOURCE})