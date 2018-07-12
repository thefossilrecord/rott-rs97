AUDIOLIB ?= audiolib.a

TOOLCHAIN = /opt/retrogame-toolchain/usr
SDL_CONFIG  = $(TOOLCHAIN)/mipsel-buildroot-linux-uclibc/sysroot/usr/bin/sdl-config

CC = $(TOOLCHAIN)/bin/mipsel-linux-gcc

AR = $(TOOLCHAIN)/bin/mipsel-linux-ar
CC = $(TOOLCHAIN)/bin/mipsel-linux-gcc
RANLIB ?= ranlib

ARFLAGS ?= rcT
CFLAGS ?= -g -O2
CFLAGS += -Wall
CFLAGS += `$(SDL_CONFIG) --cflags`

OBJS :=
OBJS += fx_man.o
OBJS += dsl.o
OBJS += ll_man.o
OBJS += multivoc.o
OBJS += mv_mix.o
OBJS += mvreverb.o
OBJS += nodpmi.o
OBJS += pitch.o
OBJS += user.o
OBJS += usrhooks.o

$(AUDIOLIB): $(OBJS)
	$(RM) $@
	$(AR) $(ARFLAGS) $@ $^
	$(RANLIB) $@

clean:
	$(RM) $(AUDIOLIB) $(OBJS)
