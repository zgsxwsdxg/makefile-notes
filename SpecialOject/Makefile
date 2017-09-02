# 特殊目标
.PHONY:clean

clean:
	@- echo 'Hello,world'

.SUFFIXES:duxiaogang

duxiaogang:
	@- mkdir -p dxg

.DEFAULT:sky

sky:
	mkdir -p sky

.PRECIOUS:

.SECONDAY:

.INTERMEDIATE:

.DELETE_ON_ERROR:

.IGNORE:

.LOW_RESOLUTION_TIME:dst

dst:src
	@- cp -p src dst

.SILENT:

# 出现在目标“.SILENT”的依赖列表中的文件,make 在创建这些文件时,不打印出重建此文件所执行的命令

.EXPORT_ALL_VARIABLES:

.NOTPARALLEL:
# 如果出现目标“.NOPARALLEL”,则所有命令按照串行方式执行

#所有定义的隐含规则后缀作为目标出现时,都被视为一个特殊目标,两个后缀串联
#起来也是如此,例如“.c.o”

.cc.o:

# 这样的目标被称为后缀规则的目标,这种定义方式是已经过时的定义隐含规则的方法

bigoutput littleoutput : text.g
	generate text.g -$(subst output,,$@) > $@



