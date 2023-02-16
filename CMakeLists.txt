cmake_minimum_required(VERSION 3.0.0)
project(SmtpClient-for-Qt VERSION 0.1.0)



set (FIX_BY_MAXIMUS TRUE CACHE BOOL "Fix smtpmime_global.h ")

set (BUILD_WITH_QT6 FALSE CACHE BOOL "Enable (broken, experimental) Qt6 support")
if (BUILD_WITH_QT6)
	set(QT_MIN_VERSION 6.0.0)
	set(QT_VERSION_BASE "Qt6")
else()
	set(QT_MIN_VERSION 5.14.0)
	set(QT_VERSION_BASE "Qt5")
endif()

add_subdirectory(src)
### add_subdirectory(test)
add_subdirectory(demos)


