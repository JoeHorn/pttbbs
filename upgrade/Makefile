# Usually you won't build everything for upgrading, so we let you decide what to run.

SRCROOT=	..
.include "$(SRCROOT)/pttbbs.mk"

CFLAGS+= -DPTTBBS_UTIL

BBSBASE=	$(SRCROOT)/include/var.h

UTIL_OBJS=	../util/util_var.o

LDLIBS:=  $(UTIL_OBJS) \
	  $(SRCROOT)/common/bbs/libcmbbs.a \
	  $(SRCROOT)/common/sys/libcmsys.a \
	  $(SRCROOT)/common/osdep/libosdep.a \
	  $(LDLIBS)

all:
	@echo "Usually you won't build everything for upgrading, "
	@echo "        so we let you decide what to run."
	@echo "Please type make rDDDD_XXXX to build your upgrade program."

#$(SRCROOT)/include/var.h: $(SRCROOT)/mbbsd/var.c
#	cd $(SRCROOT)/mbbsd; $(MAKE) $(SRCROOT)/include/var.h
