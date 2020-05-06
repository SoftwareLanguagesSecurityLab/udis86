
all: udcli.o
	$(CC) -m32 -g $^ ../libudis86/libudis86.a -o udcli

%.o: %.c
	$(CC) -m32 -fPIC -g -I../libudis86/ -I../ -c $^

clean:
	rm -f *.o udcli
