SRCROOT=	../..
.include "$(SRCROOT)/pttbbs.mk"

PROGRAMS=	utmpserver utmpsync utmpserver2 utmpserver3 authserver
UTILDIR=	$(SRCROOT)/util
UTILOBJ=	$(UTILDIR)/util_var.o

LDLIBS+=$(SRCROOT)/common/bbs/libcmbbs.a \
	$(SRCROOT)/common/sys/libcmsys.a \
	$(SRCROOT)/common/osdep/libosdep.a

all:	${PROGRAMS}

.SUFFIXES: .c .cpp .o
.c.o:
	$(CC) $(CFLAGS) -c $*.c
.cpp.o:
	$(CXX) $(CXXFLAGS) -c $*.cpp

utmpserver: utmpserver.o
	${CC} ${CFLAGS} ${LDFLAGS} -o $* $*.o $(LDLIBS)
utmpserver2: utmpserver2.o friend.o
	${CXX} ${CFLAGS} ${LDFLAGS} -o $* $*.o friend.o $(LDLIBS)
utmpserver3: utmpserver3.o friend.o
	${CXX} ${CXXFLAGS} ${LDFLAGS} -o $* $*.o friend.o $(LDLIBS) -levent
utmpsync: utmpsync.o $(UTILOBJ)
	${CC} ${CFLAGS} ${LDFLAGS} -o $* $*.o $(UTILOBJ) $(LDLIBS)

authserver: authserver.o
	${CC} ${CFLAGS} ${LDFLAGS} -o $* $> $(LDLIBS) -lcrypt -levent

clean:
	rm -f *~ ${PROGRAMS} friend.o utmpserver.o utmpserver2.o utmpserver3.o utmpsync.o authserver.o
