LD_EXTRAS := -L. -l$(LIB_PREFIX)One -l$(LIB_PREFIX)Two
C_SOURCES := main.c
CFLAGS_EXTRAS := -g -O2 -glldb

include Makefile.rules

.PHONY:
a.out: lib_One lib_Two

lib_One: lib_Two

lib_%:
	$(MAKE) VPATH=$(SRCDIR)/$* -I $(SRCDIR) -f $(SRCDIR)/$*.mk DSYMUTIL=$(DSYMUTIL)

clean::
	$(MAKE) -f $(SRCDIR)/One.mk clean
	$(MAKE) -f $(SRCDIR)/Two.mk clean
