TOP=../..

include $(TOP)/Makefile.inc

CFLAGS += -I$(TOP)/include

OBJS = compile.o

all: mali_compile

clean:
	rm -f *.P
	rm -f *.o
	rm -f mali_compile

mali_compile: $(OBJS)
	$(CC) $(CFLAGS) -o $@ $^ -lMali

install: mali_compile
	$(INSTALL) $^ $(prefix)/bin

run:
ifeq ($(OS),android)
	$(ADB) shell mali_compile -v /sdcard/shader.txt
endif

include $(TOP)/Makefile.post
