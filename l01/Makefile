.PHONY: all
all: default

default: number.o program.o
	gcc -o libnumber.so -shared number.o
	gcc -o program program.o -lnumber -L.
	

number.o: number.c
	gcc -c -o number.o -fPIC number.c

program.o: program.c
	gcc -c -o program.o -fPIC program.c
	
clean:
	rm -f *.aux
	
distclean: clean
	rm -f *.o default

test: program
	-/program
