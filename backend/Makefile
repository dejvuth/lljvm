CXX := clang++
CFLAGS := $(shell llvm-config --cxxflags) -fno-exceptions -fno-rtti
LDFLAGS := $(shell llvm-config --ldflags --libs --system-libs)

OBJS := \
    main.o \
    backend.o \
    block.o \
    branch.o \
    const.o \
    function.o \
    instruction.o \
    loadstore.o \
    name.o \
    printinst.o \
    sections.o \
    types.o

.PHONY: all doc clean

all: lljvm-backend

lljvm-backend: ${OBJS}
	$(CXX) ${OBJS} ${LDFLAGS} -o lljvm-backend

doc:
	doxygen

clean:
	rm -f *.o lljvm-backend
	rm -rf doc

.cpp.o:
	$(CXX) ${CFLAGS} -c $<

${OBJS}: backend.h

