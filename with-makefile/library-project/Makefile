CC=gcc
CFLAGS=-Iinclude

all: libexample.a

install: libexample.a include/lib.h
	mkdir -p /usr/local/include/example
	cp include/lib.h /usr/local/include/example/lib.h
	cp dist/libexample.a /usr/local/lib/libexample.a

libexample.a: lib.o build_dir dist_dir
	ar rcs dist/libexample.a build/lib.o

lib.o: src/lib.c build_dir
	$(CC) $(CFLAGS) -c src/lib.c -o build/lib.o

build_dir:
	mkdir -p build

dist_dir:
	mkdir -p dist

clean:
	rm -rf build dist
