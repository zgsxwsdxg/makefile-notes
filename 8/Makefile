# make的内嵌函数
# 函数的调用语法,语法格式如下:$(FUNCTION ARGUMENTS)或者${FUNCTION ARGUMENTS}
# “ARGUMENTS”是函数的参数,参数和函数名之间使用若干个空格或者[tab]字符分割
# 如果存在多个参数时,参数之间使用逗号“,”分开。


# 文本处理函数
# $(subst FROM,TO,TEXT)
# 函数名称:字符串替换函数—subst。
# 函数功能:把字串“TEXT”中的“FROM”字符替换为“TO”。
# 返回值:替换后的新字符串。
$(subst ee,EE,feet on the street)

# $(patsubst PATTERN,REPLACEMENT,TEXT)
# 函数名称:模式替换函数—patsubst。
# 函数功能:搜索“TEXT”中以空格分开的单词,将否符合模式“TATTERN”替换为“REPLACEMENT”。
# 参数“PATTERN”中可以使用模式通配符“%”来代表一个单词中的若干字符
# 返回值:替换后的新字符串。
# 函数说明:参数“TEXT”单词之间的多个空格在处理时被合并为一个空格,并忽略前导和结尾空格。
$(patsubst %.c,%.o,x.c.c bar.c)

# 变量的替换引用
$(VAR:PATTERN=REPLACEMENT)
# 就相当于:
$(patsubst PATTERN,REPLACEMENT,$(VAR))
# 另外一种更为简单的替换字符后缀的实现:
$(VAR:SUFFIX=REPLACEMENT)
# 它等于:
$(patsubst %SUFFIX,%REPLACEMENT,$(VAR))
# eg:
objects = foo.o bar.o baz.o
srcs = $(objects:.o=.c)
srcs = $(patsubst %.o,%.c,$(objects))

# $(strip STRINT)
# 函数功能:去掉字串(若干单词,使用若干空字符分割)“STRINT”开头和结尾的空字符,并将其中多个连续空字符合并为一个空字符。
# 返回值:无前导和结尾空字符、使用单一空格分割的多单词字符串。
# 函数说明:空字符包括空格、[Tab]等不可显示字符。
# 示例:
STR =	a    b c
LOSTR = $(strip $(STR))
#LOSTR结果是“a b c”

# $(findstring FIND,IN)
# 函数名称:查找字符串函数—findstring。
# 函数功能:搜索字串“IN”,查找“FIND”字串。
# 返回值:如果在“IN”之中存在“FIND”,则返回“FIND”,否则返回空。
# 函数说明:字串“IN”之中可以包含空格、[Tab]。搜索需要是严格的文本匹配。
# 示例:
$(findstring a,a b c)
$(findstring a,b c)
# 第一个函数结果是字“a”;第二个值为空字符。

# $(filter PATTERN...,TEXT)
sources := foo.c bar.c baz.s ugh.h
foo: $(sources)
	cc $(filter %.c %.s,$(sources)) -o foo
# 使用“$(filter %.c %.s,$(sources))”的返回值给 cc 来编译生成目标“foo”,函数返回值为“foo.c bar.c baz.s”。

# $(filter-out PATTERN...,TEXT)
# 函数名称:反过滤函数—filter-out。
# 函数功能:和“filter”函数实现的功能相反。过滤掉字串“TEXT”中所有符合模式“PATTERN”的单词,保留所有不符合此模式的单词。可以有多个模式。
# 存在多个模式时,模式表达式之间使用空格分割。。
# 返回值:空格分割的“TEXT”字串中所有不符合模式“PATTERN”的字串。
# 函数说明:“filter-out”函数也可以用来去除一个变量中的某些字符串,(实现和“filter”函数相反)。
# 示例:
objects=main1.o foo.o main2.o bar.o
mains=main1.o main2.o
$(filter-out $(mains),$(objects))
# 实现了去除变量“objects”中“mains”定义的字串(文件名)功能。它的返回值为“foo.o bar.o”。

# $(sort LIST)
# 函数名称:排序函数—sort。
# 函数功能:给字串“LIST”中的单词以首字母为准进行排序(升序),并取掉重复的单词。
# 返回值:空格分割的没有重复单词的字串。
# 函数说明:两个功能,排序和去字串中的重复单词。可以单独使用其中一个功能。
# 示例:
$(sort foo bar lose foo)
# 返回值为:“bar foo lose”

# $(word N,TEXT)
# 函数名称:取单词函数。
# 函数功能:取字串“TEXT”中第“N”个单词(“N”的值从 1 开始)。
# 返回值:返回字串“TEXT”中第“N”个单词。
# 函数说明:如果“N”值大于字串“TEXT”中单词的数目,返回空字符串。如果“N”为 0,出错!
# 示例:
$(word 2, foo bar baz)
# 返回值为“bar”。

# $(wordlist S,E,TEXT)
# 函数名称:取子串函数。
# 函数功能:从字串“TEXT”中取出从“S”开始到“E”的子单词串。“S”和“E”表示单词在字串中位置的数字。
# 返回值:字串“TEXT”中从第“S”到“E”(包括“E”)的单词字串。
# 函数说明:“S”和“E”都是从 1 开始的数字。
# 当“S”比“TEXT”中的字数大时,返回空。如果“E”大于“TEXT”字数,返回从“S”开始,到“TEXT”结束的单词串。如果“S”大于“E”,返回空。
# 示例:
$(wordlist 2, 3, foo bar baz)
# 返回值为:“bar baz”。

# $(words TEXT)
# 函数名称:统计单词数目函数—words。
# 函数功能:字算字串“TEXT”中单词的数目。
# 返回值:“TEXT”字串中的单词数。
# 示例:
$(words, foo bar)
# 返 回 值 是 “ 2 ”.

# $(firstword NAMES...)
# 函数名称:取首单词函数—firstword。
# 函数功能:取字串“NAMES...”中的第一个单词。
# 返回值:字串“NAMES...”的第一个单词。
# 函数说明:“NAMES”被认为是使用空格分割的多个单词(名字)的序列。函数忽略“NAMES...”中除第一个单词以外的所有的单词。
# 示例:
$(firstword foo bar)
# 返回值为“foo”。函数“firstword”实现的功能等效于“$(word 1, NAMES...)”。

# 对于源代码所包含的头文件的搜索路径需要使用gcc的“-I”参数指定目录来实现,“VPATH”罗列的目录是用冒号“:”分割的。
# 示例:
VPATH = src:../includes
override CFLAGS += $(patsubst %,-I%,$(subst :, ,$(VPATH)))
# $(subst :, ,$(VPATH)) 替换: 为空格
# $(patsubst %,-I%,$(VAR)) 将每个变量起始位置加统一前缀'-I'




#############
# 文件名处理函数
#############

# $(dir NAMES...)
# 函数名称:取目录函数—dir。
# 函数功能:从文件名序列“NAMES...”中取出各个文件名的目录部分。文件名的目录部分就是包含在文件名中的最后一个斜线(“/”)(包括斜线)之前的部分。
# 返回值:空格分割的文件名序列“NAMES...”中每一个文件的目录部分。
# 函数说明:如果文件名中没有斜线,认为此文件为当前目录(“./”)下的文件。
# 示例:
$(dir src/foo.c hacks)
# 返回值为“src/ ./”。

# $(notdir NAMES...)
# 函数名称:取文件名函数——notdir。
# 函数功能:从文件名序列“NAMES...”中取出非目录部分。目录部分是指最后一个斜线(“/”)(包括斜线)之前的部分。删除所有文件名中的目录部分,只保留非目录部分。
# 返回值:文件名序列“NAMES...”中每一个文件的非目录部分。
# 函数说明:如果“NAMES...”中存在不包含斜线的文件名,则不改变这个文件名。以反斜线结尾的文件名,是用空串代替,因此当“NAMES...”中存在多
# 个这样的文件名时,返回结果中分割各个文件名的空格数目将不确定! 这是此函数的一个缺陷。
# 示例:
$(notdir src/foo.c hacks)
# 返回值为:“foo.c hacks”。

# $(suffix NAMES...)
# 函数名称:取后缀函数—suffix。
# 函数功能:从文件名序列“NAMES...”中取出各个文件名的后缀。后缀是文件名中最后一个以点“.”开始的(包含点号)部分,如果文件名中不包含一个点号,则为空。
# 返回值:以空格分割的文件名序列“NAMES...”中每一个文件的后缀序列。
# 函数说明:“NAMES...”是多个文件名时,返回值是多个以空格分割的单词序列。如果文件名没有后缀部分,则返回空。
# 示例:
$(suffix src/foo.c src-1.0/bar.c hacks)
# 返回值为“.c .c”。

# $(basename NAMES...)
# 函数名称:取前缀函数—basename。
# 函数功能:从文件名序列“NAMES...”中取出各个文件名的前缀部分(点号之后的部分)。前缀部分指的是文件名中最后一个点号之前的部分。
# 返回值:空格分割的文件名序列“NAMES...”中各个文件的前缀序列。如果文件没有前缀,则返回空字串。
# 函数说明:如果“NAMES...”中包含没有后缀的文件名,此文件名不改变。如果一个文件名中存在多个点号,则返回值为此文件名的最后一个点号之前的文件名部分。
# 示例:
$(basename src/foo.c src-1.0/bar.c /home/jack/.font.cache-1 hacks)
# 返回值为:“src/foo src-1.0/bar /home/jack/.font hacks”

# $(addsuffix SUFFIX,NAMES...)
# 函数名称:加后缀函数—addsuffix。
# 函数功能:为“NAMES...”中的每一个文件名添加后缀“SUFFIX”。参数“NAMES...”为空格分割的文件名序列,将“SUFFIX”追加到此序列的每一个文件名的末尾。
# 返回值:以单空格分割的添加了后缀“SUFFIX”的文件名序列。
# 函数说明:
# 示例:
$(addsuffix .c,foo bar)
# 返回值为“foo.c bar.c”

# $(addprefix PREFIX,NAMES...)
# 函数名称:加前缀函数—addprefix。
# 函数功能:为“NAMES...”中的每一个文件名添加前缀“PREFIX”。参数“NAMES...”是空格分割的文件名序列,将“SUFFIX”添加到此序列的每一个文件名之前。
# 返回值:以单空格分割的添加了前缀“PREFIX”的文件名序列。
# 函数说明:
# 示例:
$(addprefix src/,foo bar)
# 返回值为“src/foo src/bar”。

# $(join LIST1,LIST2)
# 函数名称:单词连接函数——join。
# 函数功能:将字串“LIST1”和字串“LIST2”各单词进行对应连接。就是将“LIST2”中的第一个单词追加“LIST1”第一个单词字后合并为一个单词;将“LIST2”中的第二个单词追加到“LIST1”的第一个单词之后并合并为一个单词,......依次列推。
# 返回值:单空格分割的合并后的字(文件名)序列。
# 函数说明:如果“LIST1”和“LIST2”中的字数目不一致时,两者中多余部分将被作为返回序列的一部分。
# 示例 1:
$(join a b , .c .o)
# 返回值为:“a.c b.o”。
# 示例 2:
$(join a b c , .c .o)
# 返回值为:“a.c b.o c”。

# $(wildcard PATTERN)
# 函数名称:获取匹配模式文件名函数—wildcard
# 函数功能:列出当前目录下所有符合模式“PATTERN”格式的文件名。
# 返回值:空格分割的、存在当前目录下的所有符合模式“PATTERN”的文件名。
# 函数说明:“PATTERN”使用shell可识别的通配符,包括“?”(单字符)、“*”(多字符)等
# 示例:
$(wildcard *.c)
# 返回值为当前目录下所有.c 源文件列表。

# foreach 函数
# foreach”函数的语法：$(foreach VAR,LIST,TEXT)
# 函数功能:这个函数的工作过程是这样的:如果需要(存在变量或者函数的引用),首先展开变量“VAR”和“LIST”的引用;而表达式“TEXT”中的变量引用不展开。执行时把“LIST”中使用空格分割的单词依次取出赋值给变量“VAR”,然后执行“TEXT”表达式。重复直到“LIST”的最后一个单词(为空时结束)。“TEXT”中的变量或者函数引用在执行时才被展开,因此如果在“TEXT”中存在对“VAR”的引用,那么“VAR”的值在每一次展开式将会到的不同的值。
# 返回值:空格分割的多次表达式“TEXT”的计算的结果。
# 我们来看一个例子,定义变量“files”,它的值为四个目录(变量“dirs”代表的 a、b、c、d 四个目录)下的文件列表:
dirs := a b c d
files := $(foreach dir,$(dirs),$(wildcard $(dir)/*))
# 所以此函数所实现的功能就和一下语句等价:
files := $(wildcard a/* b/* c/* d/*)

#当函数的“TEXT”表达式过于复杂时,我们可以通过定义一个中间变量,此变量代表表达式的一部分。并在函数的“TEXT”中引用这个变量 上边的例子也可以这样来实现:
dirs := a b c d
find_files = $(wildcard $(dir)/*)
dirs := a b c d
files := $(foreach dir,$(dirs),$(find_files))

# if 函数
# 函数“if”提供了一个在函数上下文中实现条件判断的功能。就像make所支持的条件语句—ifeq
# 函数语法: $(if CONDITION,THEN-PART[,ELSE-PART])
# 函数示例:
SUBDIR += $(if $(SRC_DIR) $(SRC_DIR),/home/src)
# 函数的结果是:如果“SRC_DIR”变量值不为空,则将变量“SRC_DIR”指定的目录作为一个子目录;否则将目录“/home/src”作为一个子目录。







