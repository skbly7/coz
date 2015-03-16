# Lets add coz in makefile
TARGETS := pbzip2
ROOT = ../..
CXXFLAGS_COZ_HEADER = -I$(ROOT)/include

CXXFLAGS = -pthread

CXXFLAGS += -D_POSIX_PTHREAD_SEMANTICS

CXXFLAGS += -O2

CXXFLAGS += -D_LARGEFILE64_SOURCE -D_FILE_OFFSET_BITS=64

# CXXFLAGS += -DPBZIP_DEBUG

CXXFLAGS += -DUSE_STACKSIZE_CUSTOMIZATION

CXXFLAGS += $(CXXFLAGS_COZ_HEADER)
CXXFLAGS += -Ibzip2-1.0.6

LIBS = bz2 dl pthread
LDFLAGS := -Lbzip2-1.0.6
include $(ROOT)/common.mk

# pbzip2 depends on the libbz2 library
pbzip2: bzip2-1.0.6/libbz2.a

bzip2-1.0.6/libbz2.a:
	@cd bzip2-1.0.6; $(MAKE) CFLAGS=-g > /dev/null