ACLOCAL_AMFLAGS=-I m4
AUTOMAKE_OPTIONS = foreign subdir-objects

nobase_include_HEADERS=\
../src/hello/hello.h \
../src/test/hello.h       
  
lib_LTLIBRARIES=hello_test/libhello_test.la  
hello_test_libhello_test_la_SOURCES= \
../src/main.cpp \
../src/hello/hello.cpp \
../src/test/hello.cpp        
