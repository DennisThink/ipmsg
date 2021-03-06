cmake_minimum_required(VERSION 3.0)
project(ipmsg)
# 需要增加这一条，具体原因不清楚
ADD_DEFINITIONS(-D_AFXDLL)
 
# 在共享库中使用MFC
SET(CMAKE_MFC_FLAG 2)
SET(TOAST_FILE ./src/toast/resource.h 
               ./src/toast/toast.cpp
               ./src/toast/toast.h 
               ./src/toast.rc)
SET(RES_FILE ./src/res/asc.bmp 
             ./src/res/basehead.bmp 
             ./src/res/blue.cur 
             ./src/res/bottom.bmp
             ./src/res/bottomhot.bmp 
             ./src/res/btnf.bmp
             ./src/res/btnmf.bmp 
             ./src/res/btnmn.bmp
             ./src/res/btnms.bmp 
             ./src/res/btnn.bmp
             ./src/res/btns.bmp
             ./src/res/camera.ico
             ./src/res/cameraxp.ico
             ./src/res/clip.bmp
             ./src/res/cliptb.bmp
             ./src/res/comment.bmp
             ./src/res/cropuser.bmp
             ./src/res/cross.cur
             ./src/res/desc.bmp
             ./src/res/dummypic.bmp
             ./src/res/dupwin.bmp
             ./src/res/fabtb.bmp
             ./src/res/fav.bmp
             ./src/res/favemp.bmp
             ./src/res/favmid.bmp
             ./src/res/favrev.bmp
             ./src/res/file.bmp
             ./src/res/filetb.bmp
             ./src/res/foldf.bmp
             ./src/res/foldt.bmp
             ./src/res/frommsg.bmp
             ./src/res/fulldisp.bmp
             ./src/res/genblue.cur
             ./src/res/gengreen.cur
             ./src/res/genred.cur
             ./src/res/genyellow.cur
             ./src/res/green.cur
             ./src/res/imenu.bmp
             ./src/res/imenumid.bmp
             ./src/res/imenumid.bmp
             ./src/res/imenurev.bmp
             ./src/res/ipexc.png
             ./src/res/ipmsg_mst.ico 
             ./src/res/ipmsg.ico
             ./src/res/ipmsg.png 
             ./src/res/ipmsg1.ico
             ./src/res/ipmsg2.ico
             ./src/res/ipmsg3.ico
             ./src/res/ipmsg4.ico
             ./src/res/ipmsg5.ico
             ./src/res/ipmsg6.ico
             ./src/res/ipmsg7.ico
             ./src/res/ipmsgrev.ico
             ./src/res/logview.ico
             ./src/res/logviewmono.ico 
             ./src/res/logviewtb.bmp
             ./src/res/LOUPE.cur
             ./src/res/lvbase.bmp
             ./src/res/mark.bmp
             ./src/res/markerblue.bmp
             ./src/res/markergreen.bmp
             ./src/res/markerred.bmp
             ./src/res/MARKERTB.bmp 
             ./src/res/markeryellow.bmp 
             ./src/res/marktb.bmp 
             ./src/res/memotb.bmp 
             ./src/res/menu.ico
             ./src/res/misc.bmp 
             ./src/res/msgto.bmp 
             ./src/res/multi.ico 
             ./src/res/multirev.ico 
             ./src/res/narrow.bmp 
             ./src/res/narrowd.bmp 
             ./src/res/noclip.bmp 
             ./src/res/pause.ico 
             ./src/res/play.ico 
             ./src/res/red.cur
             ./src/res/refresh.ico 
             ./src/res/reply.bmp 
             ./src/res/replyhide.bmp 
             ./src/res/replymsg.bmp 
             ./src/res/sendtb.bmp 
             ./src/res/sep.cur
             ./src/res/title.bmp 
             ./src/res/titledips.bmp
             ./src/res/titledisp.bmp 
             ./src/res/tomsg.bmp
             ./src/res/tomsg2.bmp 
             ./src/res/top.bmp 
             ./src/res/tophot.bmp 
             ./src/res/tray.gif
             ./src/res/tray.stg
             ./src/res/unopen.bmp
             ./src/res/unopenbig.bmp
             ./src/res/unopenr.bmp 
             ./src/res/unopentb.bmp
             ./src/res/userchk.bmp 
             ./src/res/yellow.cur
             ./src/ipmsg.rc)

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

add_subdirectory(./src/uninst/)
add_subdirectory(./external/zlib/)
add_subdirectory(./src/install/)

add_executable(ipmsg WIN32 ${SOURCE_FILE} ${TLIB_SOURCE} ${SQLITE_SOURCE} ${RES_FILE})
add_dependencies(ipmsg zlib)

