# makefile-notes
learn makefile notes as follow:
= 是最基本的赋值
:= 是覆盖之前的值
?= 是如果没有被赋值过就赋予等号后面的值
+= 是添加等号后面的值

自动化变量$?代表依赖文件列表中被改变过的所有文件。
自动化变量$^代表所有通过目录搜索得到的依赖文件的完整路径名(目录 + 一般文件名)列表。
自动化变量$@代表规则的目标。
自动化变量$<代表规则中通过目录搜索得到的依赖文件列表的第一个依赖文件。

$@ 	目标的全路径名
$% 	档案文件成员结构中的文件名
$< 	比给定的目标文件时间标记更新的依赖文件名
$^ 	所有必要条件的文件名，用空格隔开
$+ 	所有必要条件的文件名，用空格隔开，包括重复的文件名
$* 	工作目标的主文件名,若当前目标是pro.o，则$*表示pro。
$?    比目标的修改时间更晚的那些依赖模块表。

#makefile 隐含变量 
隐含规则中所使用的变量(隐含变量)分为两类:
1. 代表一个程序的名字(例如:“CC”代表了编译器这个可执行程序)。
2. 代表执行这个程序使用的参数(例如:变量“CFLAGS”,多个参数使用空格分开。当然也允许在程序的名字中包含参数。但是这种方式建议不要使用。）

##以下是一些作为程序名的隐含变量定义:
代表命令的变量
AR
函数库打包程序,可创建静态库.a文档。默认是“ar”。
AS
汇编程序。默认是“as”。

CC
C编译程序。默认是“cc”。

CXX
C++编译程序。默认是“g++”。

CO
从 RCS中提取文件的程序。默认是“co”。

CPP
C程序的预处理器(输出是标准输出设备)。默认是“$(CC) -E”。

FC
编译器和预处理Fortran 和 Ratfor 源文件的编译器。默认是“f77”。

GET
从SCCS中提取文件程序。默认是“get”

LEX
将 Lex 语言转变为 C 或 Ratfo 的程序。默认是“lex”。

PC
Pascal语言编译器。默认是“pc”。

YACC
Yacc文法分析器(针对于C程序)。默认命令是“yacc”。

YACCR
Yacc文法分析器(针对于Ratfor程序)。默认是“yacc -r”。

MAKEINFO
转换Texinfo源文件(.texi)到Info文件程序。默认是“makeinfo”。

TEX
从TeX源文件创建TeX DVI文件的程序。默认是“tex”。

TEXI2DVI
从Texinfo源文件创建TeX DVI 文件的程序。默认是“texi2dvi”。

WEAVE
转换Web到TeX的程序。默认是“weave”。

CWEAVE
转换C Web 到 TeX的程序。默认是“cweave”。

TANGLE
转换Web到Pascal语言的程序。默认是“tangle”。

CTANGLE
转换C Web 到 C。默认是“ctangle”。

RM
删除命令。默认是“rm -f”。

## 命令参数的变量
下边的是代表命令执行参数的变量。如果没有给出默认值则默认值为空。

ARFLAGS
执行“AR”命令的命令行参数。默认值是“rv”。

ASFLAGS
执行汇编语器“AS”的命令行参数(明确指定“.s”或“.S”文件时)。

CFLAGS
执行“CC”编译器的命令行参数(编译.c源文件的选项)。

COFLAGS
执行“co”的命令行参数(在RCS中提取文件的选项)。

CPPFLAGS
执行C预处理器“cc -E”的命令行参数(C 和 Fortran 编译器会用到)。

FFLAGS
Fortran语言编译器“f77”执行的命令行参数(编译Fortran源文件的选项)。

GFLAGS
SCCS “get”程序参数。

LDFLAGS
链接器(如:“ld”)参数。

LFLAGS
Lex文法分析器参数。

PFLAGS
Pascal语言编译器参数。

RFLAGS
Ratfor 程序的Fortran 编译器参数。

YFLAGS
Yacc文法分析器参数




