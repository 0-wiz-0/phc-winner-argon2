#
# Argon2 source code package
# 
# This work is licensed under a Creative Commons CC0 1.0 License/Waiver.
# 
# You should have received a copy of the CC0 Public Domain Dedication along with
# this software. If not, see <http://creativecommons.org/publicdomain/zero/1.0/>.
#
AUTOMAKE_OPTIONS=	subdir-objects

bin_PROGRAMS=		argon2
lib_LTLIBRARIES=	libargon2.la
noinst_PROGRAMS=	bench genkat

argon2_SOURCES=		run.c
argon2_LDADD=		libargon2.la
bench_SOURCES=		bench.c
bench_LDADD=		libargon2.la
genkat_SOURCES=		genkat.c
genkat_LDADD=		libargon2.la

EXTRA_DIST=		blake2/blake2-impl.h blake2/lake2.h blake2/blake2b.c blake2/blamka-round-opt.h blake2/blamka-round-ref.h
noinst_HEADERS=		argon2.h core.h encoding.h genkat.h opt.h ref.h thread.h

libargon2_la_SOURCES=	argon2.c core.c encoding.c blake2/blake2b.c thread.c
if COND_OPT
libargon2_la_SOURCES+=	opt.c
else
libargon2_la_SOURCES+=	ref.c
endif

AM_LDFLAGS=	$(PTHREAD_LIBS)
AM_CFLAGS=	-std=c89 $(PTHREAD_CFLAGS)
CC=		$(PTHREAD_CC)

format:
		clang-format -style="{BasedOnStyle: llvm, IndentWidth: 4}" -i *.c *.h blake2/*.c blake2/*.h
