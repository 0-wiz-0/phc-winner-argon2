# autoconf/automake base variables
AC_PREREQ([2.62])
AC_INIT([argon2],[0.0.1])
AC_CONFIG_SRCDIR([src/argon2.c])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_AUX_DIR([support])
AC_CANONICAL_HOST

# user visible options -- this has to happen before testing the variables
AC_ARG_ENABLE(optimization,
    [AS_HELP_STRING([--enable-optimization], [enable optimized code])],,enable_optimization=no)
AM_CONDITIONAL(COND_OPT, test "$enable_optimization" = "yes")

AM_CFLAGS="-Wall"

AM_INIT_AUTOMAKE
#AM_SILENT_RULES([yes])
AC_PROG_LIBTOOL

#AX_CFLAGS_FORCE_C89
AX_PTHREAD

# create all Makefiles (e.g., for 'make dist')
AC_CONFIG_FILES([Makefile])
AC_CONFIG_FILES([src/Makefile])
AC_CONFIG_FILES([kats/Makefile])

AC_OUTPUT
