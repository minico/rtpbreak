# src Makefile.

include VERSION

CC       = gcc -gdwarf-2 -gstrict-dwarf
CFLAGS   = -Wall #-O3  # debug: put -ggdb instead of -O3
LIBS     = -L. -lpcap
DEFS     = 

#####################################################################


all: header
	$(CC) -c -DVERSION=\"$(VERSION)\" $(CFLAGS) $(DEFS) main.c
	$(CC) -c $(CFLAGS) $(DEFS) common.c
	$(CC) -c $(CFLAGS) $(DEFS) net.c
	$(CC) main.o common.o net.o -o rtpbreak $(LIBS)
	@echo "%"

header:
	@echo "%"
	@echo "%  Compiling rtpbreak v$(VERSION)"
	@echo "%"
	@echo "%  CC...................: $(CC)"
	@echo "%  CFLAGS...............: $(CFLAGS)"
	@echo "%  LIBS.................: $(LIBS)"
	@echo "%  DEFS.................: $(DEFS)"
	@echo "%"

indent:
	astyle --convert-tabs --style=gnu *.[hc]

srcheaders:
	update_src_header.sh *h *c

clean:
	@rm -f rtpbreak *.[hc].orig rtp.*.txt rtp.*.*.* *.o *.wav *~~

#eof
