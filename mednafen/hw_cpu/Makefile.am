AUTOMAKE_OPTIONS = subdir-objects
DEFS = -DLOCALEDIR=\"$(datadir)/locale\" @DEFS@  
DEFAULT_INCLUDES = -I$(top_builddir)/include -I$(top_srcdir)/intl -I$(top_builddir)/include/blip -I$(top_srcdir)

noinst_LIBRARIES        =       libmdfnhwcpu.a

#SUBDIRS			=	c68k
#libmdfnhwcpu_a_DEPENDENCIES	=	c68k/

#SUBDIRS                        =       c68k
#libmdfnhwcpu_a_DEPENDENCIES    =       c68k/

noinst_PROGRAMS = gen68k
gen68k_SOURCES = c68k/c68kexec.c c68k/c68k.c c68k/gen68k.c
gen68k_CFLAGS = -DC68K_GEN
gen68k_LDFLAGS = -DC68K_GEN
nodist_pkgdata_DATA = c68k/c68k_op0.inc
c68k/c68k_op0.inc: c68k/*.h c68k/*.c c68k/c68k_ini.inc c68k/c68kmac.inc c68k/gen68k.inc
	make gen68k && cd c68k && ../gen68k$(EXEEXT)

libmdfnhwcpu_a_SOURCES 	=       c68k/c68kexec.c c68k/c68k.c

libmdfnhwcpu_a_SOURCES	+=      z80-fuse/z80.cpp z80-fuse/z80_ops.cpp

libmdfnhwcpu_a_SOURCES	+=	v810/v810_cpu.cpp v810/v810_cpuD.cpp v810/fpu-new/softfloat.c

libmdfnhwcpu_a_SOURCES  +=      huc6280/huc6280.cpp

if WANT_DEBUGGER
libmdfnhwcpu_a_SOURCES	+=	huc6280/dis6280.cpp
endif

