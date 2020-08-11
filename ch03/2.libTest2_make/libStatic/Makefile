##
## Makefile : for Static/Shared/Dynamic Library Programming
##
##		Kim Soo Hyun(@")
##

PLATFORM = 

CC = $(PLATFORM)gcc
CFLAGS = -Wall -O2
ARFLAGS = -rcs
#ARFLAGS = -rcsU

LIB_SRCS = max.c min.c
LIB_OBJS = $(LIB_SRCS:.c=.o)

libtest.a : $(LOB_OBJS)
#libtest.a : libtest.a(min.o max.o)
	$(AR) $(ARFLAGS) $@ $^
	

clean :
	-rm -f $(LIB_OBJS)
	-rm -f libtest.a


