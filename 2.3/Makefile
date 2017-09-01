#sample \
hello world

$(MAKEFILE_LIST)
objs = main.o kbd.o command.o display.o\ 
insert.o search.o files.o utils.o
edit : $(objs)
	cc -o edit $(objs)

define
endef

makefile_list = ./src/text-line/Makefile ./src/license-ocr/Makefile
-include $(makefile_list)

$(objs) : defs.h
kbd.o command.o : command.h
display.o search.o files.o : buffer.h

.PHONY : clean

clean:
	- rm edit $(objs)


	
