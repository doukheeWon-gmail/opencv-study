CPP = g++

CPPSRCS = mat_abs.cpp

BUILDDIR = buildDir

TARGET = MatAbs

CPPFLAGS = `pkg-config --cflags --libs opencv3`

CPPOBJS = $(addprefix ${BUILDDIR}/, $(CPPSRCS:.cpp=.o))

all: clean createdirs build

createdirs:
	$(shell mkdir ${BUILDDIR})

build:$(CPPOBJS)
	$(CPP) -o $(BUILDDIR)/$(TARGET) $^ $(CPPFLAGS)

$(CPPOBJS):$(BUILDDIR)/%.o : %.cpp
	$(CPP) -c $(CPPFLAGS) $< -o $@

clean:
	rm -rf ${BUILDDIR}