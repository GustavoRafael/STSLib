# vim: noet sts=8 sw=8
CFLAGS ?= -Wall
STSAPP_BIN ?= /usr/local/bin

.SUFFIXES: .cc

.cc.o:
	g++ $(CFLAGS) -c $<

project:	project_main.o project.o
	g++ $(CFLAGS) -o project project_main.o project.o -lsts -lbdd
	strip project

install: project
	test -d $(STSAPP_BIN) || mkdir -p $(STSAPP_BIN)
	cp project $(STSAPP_BIN)
###################

.PHONY : clean
clean:
	rm -f *.o project
