dnl Process this file with autoconf to produce a configure script.

# get rid of that stupid cache mechanism
rm -f config.cache

AC_INIT(configure.in)
AM_INIT_AUTOMAKE(entice, 0.9.3.004)
AM_CONFIG_HEADER(src/config.h)

AC_ISC_POSIX
AC_PROG_CC
AM_PROG_CC_STDC
AC_HEADER_STDC
AC_C_CONST
AM_ENABLE_SHARED
AM_PROG_LIBTOOL

AM_WITH_DMALLOC

dnl Add the languages which your application supports here.
ALL_LINGUAS=""

dnl Set PACKAGE_LOCALE_DIR in config.h.
if test "x${prefix}" = "xNONE"; then
  AC_DEFINE_UNQUOTED(PACKAGE_LOCALE_DIR, "${ac_default_prefix}/${DATADIRNAME}/locale", [Locale-specific data directory])
else
  AC_DEFINE_UNQUOTED(PACKAGE_LOCALE_DIR, "${prefix}/${DATADIRNAME}/locale", [Locale-specific data directory])
fi

dnl Set PACKAGE_DATA_DIR in config.h.
if test "x${datadir}" = 'x${prefix}/share'; then
  if test "x${prefix}" = "xNONE"; then
    AC_DEFINE_UNQUOTED(PACKAGE_DATA_DIR, "${ac_default_prefix}/share/${PACKAGE}", [Shared data directory])
  else
    AC_DEFINE_UNQUOTED(PACKAGE_DATA_DIR, "${prefix}/share/${PACKAGE}", [Shared data directory])
  fi
else
  AC_DEFINE_UNQUOTED(PACKAGE_DATA_DIR, "${datadir}/${PACKAGE}", [Shared data directory])
fi

dnl Set PACKAGE_BIN_DIR in config.h.
if test "x${datadir}" = 'x${prefix}/bin'; then
  if test "x${prefix}" = "xNONE"; then
    AC_DEFINE_UNQUOTED(PACKAGE_BIN_DIR, "${ac_default_prefix}/bin", [Installation directory for user executables])
  else
    AC_DEFINE_UNQUOTED(PACKAGE_BIN_DIR, "${prefix}/bin", [Installation directory for user executables])
  fi
else
  AC_DEFINE_UNQUOTED(PACKAGE_BIN_DIR, "${bindir}", [Installation directory for user executables])
fi

dnl Set PACKAGE_LIB_DIR in config.h.
if test "x${datadir}" = 'x${prefix}/lib'; then
  if test "x${prefix}" = "xNONE"; then
    AC_DEFINE_UNQUOTED(PACKAGE_LIB_DIR, "${ac_default_prefix}/lib", [Installation directory for libraries])
  else
    AC_DEFINE_UNQUOTED(PACKAGE_LIB_DIR, "${prefix}/lib", [Installation directory for libraries])
  fi
else
  AC_DEFINE_UNQUOTED(PACKAGE_LIB_DIR, "${libdir}", [Installation directory for libraries])
fi

dnl Set PACKAGE_SOURCE_DIR in config.h.
packagesrcdir=`cd $srcdir && pwd`
AC_DEFINE_UNQUOTED(PACKAGE_SOURCE_DIR, "${packagesrcdir}", [Source code directory])

AC_PATH_GENERIC(imlib2, 1.0.0,
  [ ],
  [ AC_MSG_ERROR(Cannot find imlib2) ]
)

AC_PATH_GENERIC(esmart, 0.9.0,
  [ ],
  [ AC_MSG_ERROR(Cannot find esmart) ]
)

AC_PATH_GENERIC(evas, 0.9.9,
  [ ],
  [ AC_MSG_ERROR(Cannot find evas) ]
)

AC_PATH_GENERIC(ecore, 0.9.9,
  [ ],
  [ AC_MSG_ERROR(Cannot find ecore) ]
)

AC_PATH_GENERIC(edje, 0.5.0,
  [ ],
  [ AC_MSG_ERROR(Cannot find edje) ]
)

AC_PATH_GENERIC(epsilon, 0.3.0,
  [ ],
  [ AC_MSG_ERROR(Cannot find epsilon) ]
)

AC_PATH_PROG(GIMP_REMOTE_BIN, "gimp-remote-2.2", "", $PATH)
if [ test -z $GIMP_REMOTE_BIN ]; then
  AC_PATH_PROG(GIMP_REMOTE_BIN, "gimp-remote-2.0", "", $PATH)
  if [ test -z $GIMP_REMOTE_BIN ]; then
    AC_PATH_PROG(GIMP_REMOTE_BIN, "gimp-remote", "", $PATH)
  fi
fi
if [ test -z $GIMP_REMOTE_BIN ]; then
  echo "The GIMP remote is not in your \$PATH. Please ensure it is.";
  echo "Read the manual page for you shell as to how to extend your path.";
  echo "You won't have the edit capabilities.";
else
  AC_DEFINE_UNQUOTED([GIMP_REMOTE_BIN], "$GIMP_REMOTE_BIN", [Path to gimp-remote])
fi  


AC_OUTPUT([
Makefile 
src/Makefile 
src/bin/Makefile
data/Makefile
data/fonts/Makefile
data/images/Makefile
data/themes/Makefile
data/themes/default/Makefile
data/themes/default/parts/Makefile
data/themes/default/programs/Makefile
data/themes/artifakt/Makefile
data/themes/artifakt/parts/Makefile
data/themes/artifakt/programs/Makefile
data/themes/artifakt/images/Makefile
data/themes/artifakt/fonts/Makefile
])
