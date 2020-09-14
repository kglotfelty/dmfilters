AC_INIT([dmfilters], [1.0.0], [glotfeltyk@si.edu])
AM_INIT_AUTOMAKE([foreign -Wall])
AC_PROG_CC
AC_PROG_RANLIB
AM_PROG_CC_C_O
AM_PROG_AR

# -- Hack to provide missing pkg-config files

#~ ## Missing .pc files: ascdm, region, and readline(?)
#~ for p in pkgconfig/*pc.in
#~ do
  #~ o=`echo $p | sed 's,\.in$,,'`  
  #~ sed s,@prefix@,$prefix,g < $p > $o
#~ done

#~ ## caldb in ciao4.11 is bad; fixed in 4.12
#~ cat $prefix/lib/pkgconfig/caldb4.pc | \
  #~ sed 's,^Libs:.*,Libs: -L${libdir} -lcaldb4,' | \
  #~ sed 's,^Cflags:.*,Cflags: -I${includedir},' > pkgconfig/caldb4.pc 

#~ ## Some OTS have hard coded /proj stuff
#~ if test -e $prefix/ots/lib/pkgconfig
#~ then
    #~ for p in cfitsio fftw3 fftw3f gsl xpa
    #~ do
        #~ sed "s,^prefix=.*,prefix=$prefix/ots," < $prefix/ots/lib/pkgconfig/${p}.pc > pkgconfig/${p}.pc
    #~ done
#~ fi


export PKG_CONFIG_PATH=$prefix/lib/pkgconfig:$prefix/ots/lib/pkgconfig:$PKG_CONFIG_PATH
PKG_CONFIG_PATH=./pkgconfig:${PKG_CONFIG_PATH}

PKG_CHECK_MODULES( [CIAO], [
  ds
])

#AC_CONFIG_HEADERS([config.h])
AC_CONFIG_FILES([
  Makefile
  src/Makefile
  src/dmfilters.pc
])


AC_OUTPUT
  
