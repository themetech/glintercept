INCLUDE = -I. -I../glslang -I../glslang/Include -I../glslang/OSDependent/Linux -I../glslang/MachineIndependent
WARNINGS = -Wall -Wwrite-strings -Wpointer-arith -Wcast-align -Wstrict-prototypes \
	-Wnested-externs
DEFINE = -Dlinux -D__i386__
  
CPP = g++
CPPOPTIONS = -O3 -Wno-deprecated -D_ALT_NS=1
CPPOPTIONS = -g -Wno-deprecated -D_ALT_NS=1 
CPPFLAGS = $(CPPOPTIONS) $(DEFINE) $(INCLUDE)

#
# Linking related
#
AR = ar
STATIC_OPTION = rcs

#
# Misc
#
export PERL = perl
export RM = rm -f
export MV = mv -f
export DEPEND = g++ -M

#
# Object file variables are defined here.
#
OSSRCS = InitializeDll.cpp
OSOBJS = InitializeDll.o

LIBNAME = libInitializeDll.a

all : $(LIBNAME)

$(LIBNAME) : $(OSOBJS)
	 $(AR) $(STATIC_OPTION) $(LIBNAME) $(OSOBJS) 

%.o : %.cpp
	$(CPP) $(CPPFLAGS) -c $<

#
# Dependency
#
depend : $(OSSRCS)
	$(DEPEND) $(CPPFLAGS) $(OSSRCS) > depend
include depend

#
# Cleanup
#
.PHONY : clean
clean :
	$(RM) *.o *.a
