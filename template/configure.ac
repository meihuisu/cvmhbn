N#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_INIT([%%CVMHBN%],[1.0],[mei@usc.edu])
AC_CONFIG_AUX_DIR([./aux-config])
AC_CONFIG_SRCDIR([src])
AM_INIT_AUTOMAKE([foreign no-exeext])
AC_PROG_RANLIB

# Checks for programs.
AC_PROG_CC

# Checks for libraries.

# Checks for header files.
m4_warn([obsolete],
[The preprocessor macro `STDC_HEADERS' is obsolete.
  Except in unusual embedded environments, you can safely include all
  ISO C90 headers unconditionally.])dnl

AC_CHECK_HEADERS([stdlib.h string.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_CONST

if test x"$UCVM_INSTALL_PATH" = x; then
AM_CONDITIONAL(UCVM, false)
UCVM_CFLAGS=
UCVM_LDFLAGS=
else
AM_CONDITIONAL(UCVM, true)
UCVM_CFLAGS="-I$UCVM_INSTALL_PATH/include"
UCVM_LDFLAGS="-L$UCVM_INSTALL_PATH/lib -lucvm -dynamic  -L$UCVM_INSTALL_PATH/lib/euclid3/lib -letree -L$UCVM_INSTALL_PATH/lib/proj-5/lib -lproj -lpthread -L$UCVM_INSTALL_PATH/lib/fftw/lib -lfftw3 -lm -ldl"
fi

# Checks for library functions.

# Set final CFLAGS and LDFLAGS
CFLAGS="$CFLAGS"
LDFLAGS="$LDFLAGS"

AC_CONFIG_FILES([Makefile data/Makefile gctpc/source/Makefile src/Makefile test/Makefile test_validation/Makefile])

AC_OUTPUT
