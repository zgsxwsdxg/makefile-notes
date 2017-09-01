#sample Makefile
all : prog1 prog2 prog3
.PHONY : all
 
prog1 : prog1.o utils.o
	cc -o prog1 prog1.o utils.o

prog2 : prog2.o
	cc -o prog2 prog2.o

prog3 : prog3.o sort.o utils.o
	cc -o prog3 prog3.o sort.o utils.o

.PHONY : clean

clean:
	@- rm -f *.o
	$(RM) *.o

# 通常在清除文件的伪目标所定义的命令中“rm”使用选项“–f”(--force)来防止
# 在缺少删除文件时出错并退出,使“make clean”过程失败
# 也可以在“rm”之前加上“-”来防止“rm”错误退出,这种方式时 make 会提示错误信息但不会退出
# 为了不看到这些讨厌的信息,需要使用上述的第一种方式

# make 存在一个内嵌隐含变量“RM”,它被定义为:“RM = rm –f”
# 因此在书写“clean”规则的命令行时可以使用变量“$(RM)”来代替“rm”,这样可以免出现一些不必要的麻烦!这是我们推荐的用法。


