# zhu yi:
gqw@debian:~/workspace$ cd test_hello/build/
gqw@debian:~/workspace/test_hello/build$ libtoolize --automake
gqw@debian:~/workspace/test_hello/build$ aclocal
gqw@debian:~/workspace/test_hello/build$ autoheader
gqw@debian:~/workspace/test_hello/build$ autoconf
gqw@debian:~/workspace/test_hello/build$ automake -a
configure.ac:7: installing `./config.guess'
configure.ac:7: installing `./config.sub'
configure.ac:6: installing `./install-sh'
configure.ac:6: installing `./missing'
Makefile.am: installing `./depcomp'
gqw@debian:~/workspace/test_hello/build$ ls
aclocal.m4      config.h.in  configure.ac  ltmain.sh    Makefile.in
autom4te.cache  config.sub   depcomp       m4           missing
config.guess    configure    install-sh    Makefile.am

