SRC = bench.cpp convergence_cyl_waveguide.cpp cylindrical.cpp flux.cpp	\
known_results.cpp one_dimensional.cpp physical.cpp symmetry.cpp		\
three_d.cpp two_dimensional.cpp

EXTRA_DIST = $(SRC)

OBJ = $(SRC:.cpp=.o)
DAC = $(SRC:.cpp=.dac)
DONE = $(SRC:.cpp=.done)

LIBMEEP = $(top_builddir)/src/libmeep.la
AM_CPPFLAGS = -I$(top_srcdir)/src

SUFFIXES = .dac .done

noinst_PROGRAMS = bench

bench_SOURCES = bench.cpp
bench_LDADD = $(LIBMEEP)

check-local: $(DONE)

# Note: this requires GNU make

.o.dac:
	$(CXXLINK) $< $(LIBMEEP) $(LIBS)

.dac.done:
	$(RUNCODE) ./$<
	touch $@

benchmark: bench
	$(RUNCODE) ./bench

clean-local::
	rm -f *.o *.dac debug_out_* *.done
