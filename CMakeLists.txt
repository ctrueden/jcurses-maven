cmake_minimum_required(VERSION 2.8)

project(jcurses)

message(STATUS "")

message(STATUS "-- Java Native Interface:")
find_package(JNI REQUIRED)
message(STATUS "jawt lib      : ${JAVA_AWT_LIBRARY}")
message(STATUS "jvm lib       : ${JAVA_JVM_LIBRARY}")
message(STATUS "jni.h         : ${JAVA_INCLUDE_PATH}")
message(STATUS "jni_md.h      : ${JAVA_INCLUDE_PATH2}")
message(STATUS "jawt.h        : ${JAVA_AWT_INCLUDE_PATH}")
message(STATUS "")

message(STATUS "-- Curses:")
find_package(Curses REQUIRED)
message(STATUS "found         : ${CURSES_FOUND}")
message(STATUS "include dir   : ${CURSES_INCLUDE_DIR}")
message(STATUS "libraries     : ${CURSES_LIBRARIES}")
message(STATUS "curses.h      : ${CURSES_HAVE_CURSES_H}")
message(STATUS "ncurses.h     : ${CURSES_HAVE_NCURSES_H}")
message(STATUS "ncurses.h     : ${CURSES_HAVE_NCURSES_NCURSES_H}")
message(STATUS "curses.h      : ${CURSES_HAVE_NCURSES_CURSES_H}")
message(STATUS "")

set(BASE_DIR "src/main/c")

include_directories("${BASE_DIR}/include"
  "${JAVA_INCLUDE_PATH}" "${CURSES_INCLUDE_DIR}")

set(SRC "${BASE_DIR}/Toolkit.c")
#file(GLOB_RECURSE SRC "${BASE_DIR}/*.c")

add_library(jcurses SHARED "${SRC}")

target_link_libraries(jcurses "${JAVA_JVM_LIBRARY}" ${CURSES_LIBRARIES})
