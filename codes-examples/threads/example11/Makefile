CC=gcc
CXX=g++
RM=rm -f

TARGET=./example


INCLUDES=-I./include -I.
LDFLAGS=
LDLIBS=-lpthread

CXXFLAGS=-std=c++17 -Wall -O2 

DIR_OBJ=objs

SRCS=$(wildcard *.cc)

OBJS=$(patsubst %.cc,$(DIR_OBJ)/%.o,$(SRCS))


all: $(TARGET)
	@echo Made [ $? ] OK :\)

$(TARGET): $(OBJS)
	@echo Linking [$@]
	$(CXX) -o $@ $^ $(CXXFLAGS) $(LDLIBS) $(LDFLAGS) 

$(DIR_OBJ)/%.o: %.cc
	@echo Compiling [$@]
	@mkdir -p $(DIR_OBJ)
	$(CXX) -c -o $@ $< $(CXXFLAGS) $(INCLUDES)

clean:
	@$(RM) -r $(DIR_OBJ)
	@$(RM) *~ core

distclean: clean
	@$(RM) $(TARGET)

.PHONY: all clean distclean
	