cmake_minimum_required(VERSION 3.0)
project(ipmsg)
# 需要增加这一条，具体原因不清楚
ADD_DEFINITIONS(-D_AFXDLL)
 
# 在共享库中使用MFC
SET(CMAKE_MFC_FLAG 2)
SET(SQLITE_SOURCE ./external/sqlite3/sqlite3.h ./external/sqlite3/sqlite3.c
                   ./external/sqlite3/sqlite3ext.h ./external/sqlite3/stdafx.h 
                   ./external/sqlite3/targetver.h)
SET(TLIB_SOURCE ./src/TLib/ipdict.h ./src/TLib/ipdict.cpp
                ./src/TLib/scopeexit.h 
                ./src/TLib/tads.cpp 
                ./src/TLib/tapi32ex.h ./src/TLib/tapi32ex.cpp
                ./src/TLib/tapi32u8.h ./src/TLib/tapi32u8.cpp
                ./src/TLib/tapp.cpp
                ./src/TLib/tcmndlg.h ./src/TLib/tcmndlg.cpp
                ./src/TLib/tdlg.cpp  
                ./src/TLib/texcept.h ./src/TLib/texcept.cpp 
                ./src/TLib/tgdiplus.h ./src/TLib/tgdiplus.cpp
                ./src/TLib/tinet.h    ./src/TLib/tinet.cpp
                ./src/TLib/tini.cpp   ./src/TLib/tlib.h
                ./src/TLib/tmisc.h    ./src/TLib/tmisc.cpp
                ./src/TLib/tregist.cpp 
                ./src/TLib/tstr.h     ./src/TLib/tstr.cpp
                ./src/TLib/twin.cpp)
SET(SOURCE_FILE ./src/aes.h ./src/aes.cpp 
                ./src/blowfish.h ./src/blowfish.cpp
                ./src/cfg.h ./src/cfg.cpp
                ./src/environ.h 
                ./src/histdlg.h ./src/histdlg.cpp 
                ./src/image.h   ./src/image.cpp
                ./src/ipipc.h   ./src/ipipc.cpp
                ./src/ipmsg.cpp
                ./src/ipmsg.h 
                ./src/ipmsg.h ./src/ipmsgbase.h
                ./src/ipmsgcmn.h 
                ./src/ipmsgdef.h
                ./src/logchilddef.h 
                ./src/logchildview.h ./src/logchildview.cpp
                ./src/logchildviewev.cpp
                ./src/logchildviewpt.cpp 
                ./src/logdb.h ./src/logdb.cpp
                ./src/logdbconv.h ./src/logdbconv.cpp 
                ./src/logeditdlg.h ./src/logeditdlg.cpp 
                ./src/logimportdlg.h ./src/logimportdlg.cpp
                ./src/logmng.h ./src/logmng.cpp 
                ./src/logview.h ./src/logview.cpp 
                ./src/logviewitem.h ./src/logviewitem.cpp
                ./src/mainwin.h     ./src/mainwin.cpp
                ./src/mainwincmd.cpp ./src/mainwindir.cpp
                ./src/mainwinev.cpp ./src/mainwinfile.cpp 
                ./src/mainwinmsg.cpp ./src/mainwinupd.cpp
                ./src/miscdlg.h ./src/miscdlg.cpp 
                ./src/miscfunc.h ./src/miscfunc.cpp
                ./src/msgmng.h   ./src/msgmng.cpp
                ./src/plugin.h   ./src/plugin.cpp
                ./src/pubkey.h   ./src/pubkey.cpp
                ./src/recvdlg.h  ./src/recvdlg.cpp
                ./src/remotedlg.h ./src/remotedlg.cpp
                ./src/resource.h
                ./src/sendmsg.h  ./src/sendmsg.cpp
                ./src/richedit.h ./src/richedit.cpp
                ./src/senddlg.h ./src/senddlg.cpp
                ./src/sendmng.h  ./src/sendmng.cpp
                ./src/setupdlg.h  ./src/setupdlg.cpp 
                ./src/share.h ./src/share.cpp
                ./src/taskbarui.h ./src/taskbarui.cpp
                ./src/tipwnd.h ./src/tipwnd.cpp
                ./src/tlib_env.h 
                ./src/toolbar.h  ./src/toolbar.cpp
                ./src/version.h  ./src/version.cpp)

add_executable(ipmsg WIN32 ${SOURCE_FILE} ${TLIB_SOURCE} ${SQLITE_SOURCE})

