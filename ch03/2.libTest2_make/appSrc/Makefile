##
## Makefile : for Static/Shared/Dynamic Library Programming
##
##		Kim Soo Hyun(@")
##

PLATFORM = 

INC_PATH = ../include
CC = $(PLATFORM)gcc
CFLAGS = -Wall -O2 -I$(INC_PATH)
LIB_PATH_STATIC = ../libStatic

app : app.o
	@echo "app create using static library...."
	make -C $(LIB_PATH_STATIC)
	$(CC) -o $@ $^ -L $(LIB_PATH_STATIC) -ltest

clean :
	-make -C $(LIB_PATH_STATIC) clean
	-rm -f app app.o


