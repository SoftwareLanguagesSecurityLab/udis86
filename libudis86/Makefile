
ifeq ($(MAKECMDGOALS),all64)
	CFLAGS=-fPIC -DHAVE_STRING_H -g
else
	CFLAGS=-m32 -fPIC -DHAVE_STRING_H -g
endif

all: decode.o syn-att.o syn-intel.o syn.o itab.o udis86.o
	$(AR) -rsc libudis86.a $^

all64: decode.o syn-att.o syn-intel.o syn.o itab.o udis86.o
	$(AR) -rsc libudis86-64.a $^

%.o: %.c
	$(CC) $(CFLAGS) -c $^

install: all
	mkdir -p /usr/local/include/libudis86
	cp extern.h /usr/local/include/libudis86/extern.h
	cp types.h /usr/local/include/libudis86/types.h
	cp itab.h /usr/local/include/libudis86/itab.h
	cp ../udis86.h /usr/local/include/udis86.h
	cp libudis86.a /usr/local/lib/libudis86.a

install64: all64
	mkdir -p /usr/local/include/libudis86
	cp extern.h /usr/local/include/libudis86/extern.h
	cp types.h /usr/local/include/libudis86/types.h
	cp itab.h /usr/local/include/libudis86/itab.h
	cp ../udis86.h /usr/local/include/udis86.h
	cp libudis86-64.a /usr/local/lib/libudis86-64.a

clean:
	rm -f *.o libudis86.a libudis86-64.a
