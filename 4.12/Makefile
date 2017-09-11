# 静态模式规则的语法
# TARGETS ...: TARGET-PATTERN: PREREQ-PATTERNS ...
# COMMANDS

objects = foo.o bar.o

all: $(objects)

$(objects): %.o: %.c
	$(CC) -c $(CFLAGS) $< -o $@


# filter
files = foo.elc bar.o lose.o
# $(filter %.o,$(files))的结果为“bar.o lose.o”。
$(filter %.o,$(files)): %.o: %.c
	$(CC) -c $(CFLAGS) $< -o $@

$(filter %.elc,$(files)): %.elc: %.el
	emacs -f batch-byte-compile $<
