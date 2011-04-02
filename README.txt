About jcurses-maven:

The configure script provided with Java Curses 0.9.5. did not work for me,
so rather than debug it, I implemented a simple build system using Maven and
CMake.

To compile the Java source, simply run "mvn" from the toplevel directory.

To build the native library, use CMake:
  $ cd target && cmake .. && make

The build has been tested only on Mac OS X but Linux probably works too.
Windows almost certainly does not work, but the official jcurses 0.9.5
release comes prebundled with the DLL anyway.

--
About Java Curses:

1. Preamble

The Java Curses Library is a library, that makes is possible to create text
based terminal applications with Java programming language, like curses under
Unix.  For this purpose a windowing toolkit is implemented, that, like AWT,
consists of many classes for text based windows and GUI elements, that are
layouted within these windows. An application,that  bases on the library,
creates one or more of this windows and reacts on events coming by user
interactions with GUI elements. 

2. Environment

The Java Curses Library consists of two parts: the plattform independent part,
that contains Java classes, used writing applicatons and plattform dependent
part, that consists of a native shared library making primitive input and
output operations available to the first part.
The first part comes as a jar file (jcurses.jar) the second part as a shared
library ( libjcurses.so under Linux, libjcurses.dll under Win32 ).
The Library is developed und tested with Linux und Windows 2000 und Windows 95,
other UNIX plattforms must be easy to port, because the autoconf is used to
create the makefile.

 To use the library following is required: 
 a) You must use JDK ab 1.2
 b) A curses implementation must be installed, if it is a UNIX OS
 c) The jcurses.jar must be in the CLASSPATH
 d) the shared library must be in the same directory as jcurses.jar

3. Installation

3.1 Binary Distribution

The binary distribution comes already compiled for the specified plattform,
it contains the library ( jcurses.jar and libjcurses.XXX ) in the lib
directory und the Java documentation in the javadoc.

3.2 Source Distribution

The Source distribution is to use under UNIX plattforms other as Linux.
To compile the library following conditions are required:

1. A JDK ab version 1.2 must be installed und be in the PATH
2. GCC must be installed und  be in the PATH

Steps to compile the library:

1. Change to the distribution directory
2. Call configure
3. Call make

To use the compiled library see 2.


  

