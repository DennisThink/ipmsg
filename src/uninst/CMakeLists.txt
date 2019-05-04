cmake_minimum_required(VERSION 3.10)
project(uninst)
ADD_DEFINITIONS(-D_AFXDLL)
 
# 在共享库中使用MFC
SET(CMAKE_MFC_FLAG 2)
SET(SOURCE_FILE ./resource.h ./uninst.h ./uninst.cpp)
SET(RESOURCE_FILE ./setup.ico ./uninst.rc)
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

add_executable(uninst WIN32 ${SOURCE_FILE} ${RESOURCE_FILE} ${TLIB_SOURCE} ../version.h ../version.cpp ../install/instcmn.h ../install/instcmn.cpp)
add_dependencies(uninst zlib)
