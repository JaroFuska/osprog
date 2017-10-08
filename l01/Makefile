.PHONY: all
all: program

program: number.o program.o libnumber.so
	gcc -o program program.o -lnumber -L.
	
libnumber.so: number.o
	gcc -o libnumber.so -shared number.o


number.o: number.c
	gcc -c -o number.o -fPIC number.c

program.o: program.c
	gcc -c -o program.o -fPIC program.c
	
clean:
	rm -f *.aux
	
distclean: clean
	rm -f *.o program

test: program
	-/program
