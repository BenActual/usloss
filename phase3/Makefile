TARGET=libphase3.a
ASSIGNMENT=452phase3
CC=gcc
AR=ar
COBJS= phase3.o semtables.o linkedlist.o
CSRCS=${COBJS:.o=.c}
HDRS= sems.h main.h semtables.h linkedlist.h

INCLUDE = ./usloss/include
CFLAGS = -Wall -g -I${INCLUDE} -I. -Wno-int-to-pointer-cast -Wno-pointer-to-int-cast


LDFLAGS = -L. -L./usloss/lib
TESTDIR=testcases
TESTS= test00 test01 test02 test03 test04 test05 test06 test07 test08 \
       test09 test10 test11 test12 test13 test14 test15 test16 test17 \
       test18 test19 test20 test21 test22 test23 test24 test25


LIBS = -l452phase2 -l452phase1 -lusloss -l452phase1\
		-l452phase2 -lphase3

$(TARGET):	$(COBJS)
		$(AR) -r $@ $(COBJS)

$(TESTS):	$(TARGET)  p1.o libuser.o
	$(CC) $(CFLAGS) -c $(TESTDIR)/$@.c
	$(CC) $(CFLAGS) -c libuser.c
	$(CC) $(LDFLAGS) -o $@ $@.o $(LIBS) p1.o libuser.o

clean:
	rm -f $(COBJS) $(TARGET) test*.o term* $(TESTS) libuser.o p1.o core testOutput.txt

cleanAll:
	rm -f test??.c
	#make clean

phase3.o:	sems.h main.h semtables.h 
	$(CC) $(CFLAGS) -c phase3.c


