CC=gcc

all: example

example: main.o build_dir dist_dir
	$(CC) -o dist/example build/main.o -L/usr/local/lib -lexample

main.o: src/main.c build_dir
	$(CC) -c src/main.c -o build/main.o -I/usr/local/include

build_dir:
	mkdir -p build

dist_dir:
	mkdir -p dist

clean:
	rm -rf build dist
