CC=gcc
CXX=g++
INCLUDE=./include
CFLAGS+=-O2 -std=c99
CXXFLAGS+=-O2 -std=c++17

all: libpheval.a libphevalplo4.a libphevalplo5.a libphevalplo6.a

libpheval.a: src/evaluator5.c.o src/hashtable5.c.o src/evaluator5.cc.o \
             src/evaluator6.c.o src/hashtable6.c.o src/evaluator6.cc.o \
             src/evaluator7.c.o src/hashtable7.c.o src/evaluator7.cc.o \
             src/evaluator8.c.o src/hashtable8.c.o src/evaluator8.cc.o \
             src/evaluator9.c.o src/hashtable9.c.o src/evaluator9.cc.o \
             src/hash.c.o src/hashtable.c.o src/dptables.c.o \
             src/rank.c.o src/7462.c.o src/tables_bitwise.c.o
	ar rcs $@ $^

libphevalplo4.a: src/dptables.c.o src/tables_plo4.c.o \
                  src/evaluator_plo4.c.o src/evaluator_plo4.cc.o \
                  src/hash.c.o src/tables_bitwise.c.o \
                  src/hashtable.c.o src/rank.c.o \
                  src/7462.c.o
	ar rcs $@ $^

libphevalplo5.a: src/dptables.c.o src/tables_plo5.c.o \
                 src/evaluator_plo5.c.o src/evaluator_plo5.cc.o \
                 src/hash.c.o src/tables_bitwise.c.o \
                 src/hashtable.c.o src/rank.c.o \
                 src/7462.c.o
	ar rcs $@ $^

libphevalplo6.a: src/dptables.c.o src/tables_plo6.c.o \
                 src/evaluator_plo6.c.o src/evaluator_plo6.cc.o \
                 src/hash.c.o src/tables_bitwise.c.o \
                 src/hashtable.c.o src/rank.c.o \
                 src/7462.c.o
	ar rcs $@ $^

src/tables_plo5.c: src/tables_plo5.tar.gz
	tar xzf $< -C src/

src/tables_plo6.c: src/tables_plo6.tar.gz
	tar xzf $< -C src/

%.c.o: %.c
	${CC} -c ${CFLAGS} -I${INCLUDE} $< -o $@

%.cc.o: %.cc
	${CXX} -c ${CXXFLAGS} -I${INCLUDE} $< -o $@

clean:
	rm -f src/*.o libpheval.a libphevalplo4.a libphevalplo5.a libphevalplo6.a
