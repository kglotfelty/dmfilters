AC_INIT([dmfilters], [4.13.0], [glotfeltyk@si.edu])
AM_INIT_AUTOMAKE([foreign -Wall])
AM_MAINTAINER_MODE([disable])
AC_PROG_CC
AC_PROG_RANLIB
AM_PROG_CC_C_O
AM_PROG_AR


export PKG_CONFIG_PATH=$prefix/lib/pkgconfig:$prefix/ots/lib/pkgconfig:$PKG_CONFIG_PATH
PKG_CONFIG_PATH=./pkgconfig:${PKG_CONFIG_PATH}

PKG_CHECK_MODULES( [CIAO], [
  ds
])

AC_CONFIG_FILES([
  Makefile
  src/Makefile
  src/dmfilters.pc
])


AC_OUTPUT
  
