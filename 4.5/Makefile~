DEBUG=1

OPTS=-Ofast
CFLAGS=-Wall -Wfatal-errors -fPIC
ifeq ($(DEBUG), 1) 
OPTS := -O0 -g
endif
 
CFLAGS+=$(OPTS)

LIBS = libtest.a
#GPATH = src
#VPATH = src
LDFLAGS += -L ./. –ltest
SRC_OBJS = $(patsubst %.c,%.o, $(wildcard ./src/*.c))
$(LIBS) : $(SRC_OBJS)
	@$(AR) $(ARFLAGS) $@ $^

# 将一个目标声明为伪目标
.PHONY:clean

clean:
	rm $(LIBS) $(SRC_OBJS)


