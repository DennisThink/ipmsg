cmake_minimum_required(VERSION 3.10)
project(inst)
ADD_DEFINITIONS(-D_AFXDLL)
 
# 在共享库中使用MFC
SET(CMAKE_MFC_FLAG 2)

SET(SOURCE_FILE ./install.h ./install.cpp 
                ./instcmn.h  ./instcmn.cpp 
                ./instcore.h  ./instcore.cpp
                ./resource.h)

SET(RESOURCE_FILE ./setup.ico ./install.rc )

SET(TLIB_SOURCE ../TLib/ipdict.h ../TLib/ipdict.cpp
                ../TLib/scopeexit.h 
                ../TLib/tads.cpp 
                ../TLib/tapi32ex.h ../TLib/tapi32ex.cpp
                ../TLib/tapi32u8.h ../TLib/tapi32u8.cpp
                ../TLib/tapp.cpp
                ../TLib/tcmndlg.h ../TLib/tcmndlg.cpp
                ../TLib/tdlg.cpp  
                ../TLib/texcept.h ../TLib/texcept.cpp 
                ../TLib/tgdiplus.h ../TLib/tgdiplus.cpp
                ../TLib/tinet.h    ../TLib/tinet.cpp
                ../TLib/tini.cpp   ../TLib/tlib.h
                ../TLib/tmisc.h    ../TLib/tmisc.cpp
                ../TLib/tregist.cpp 
                ../TLib/tstr.h     ../TLib/tstr.cpp
                ../TLib/twin.cpp)
link_directories(../../lib/Debug/)
link_libraries(zlib_32d.lib)
add_executable(inst WIN32 ${SOURCE_FILE} ${RESOURCE_FILE} ${TLIB_SOURCE} ../version.h ../version.cpp )
add_dependencies(inst zlib)