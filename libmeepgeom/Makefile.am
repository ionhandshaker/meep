LIBCTLGEOM   = -lctlgeom
LIBMEEP      = $(top_builddir)/src/libmeep.la
MEEPLIBS     = $(LIBCTLGEOM) $(LIBMEEP)

lib_LTLIBRARIES = libmeepgeom.la
pkginclude_HEADERS = meepgeom.hpp material_data.hpp

#AM_CPPFLAGS = -I$(top_srcdir)/src -std=c++11
AM_CPPFLAGS = -I$(top_srcdir)/src

libmeepgeom_la_SOURCES = \
 meepgeom.cpp meepgeom.hpp material_data.hpp

libmeepgeom_la_LDFLAGS = -version-info @SHARED_VERSION_INFO@

check_PROGRAMS      = pw-source-ll ring-ll

pw_source_ll_SOURCES = pw-source-ll.cpp
pw_source_ll_LDADD   = libmeepgeom.la $(MEEPLIBS)

ring_ll_SOURCES = ring-ll.cpp
ring_ll_LDADD   = libmeepgeom.la $(MEEPLIBS)

TESTS               = pw-source-ll ring-ll

noinst_PROGRAMS = bend-flux-ll
bend_flux_ll_SOURCES = bend-flux-ll.cpp
bend_flux_ll_LDADD   = libmeepgeom.la $(MEEPLIBS)
