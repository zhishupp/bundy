SUBDIRS = . tests

# old data, should be removed in the near future once conversion is done
pythondir = $(pyexecdir)/bundy/datasrc
python_PYTHON = __init__.py sqlite3_ds.py


# new data

AM_CPPFLAGS = -I$(top_srcdir)/src/lib -I$(top_builddir)/src/lib
AM_CPPFLAGS += $(BOOST_INCLUDES)
AM_CPPFLAGS += $(SQLITE_CFLAGS)
AM_CXXFLAGS = $(BUNDY_CXXFLAGS)

python_LTLIBRARIES = datasrc.la
datasrc_la_SOURCES = datasrc.cc datasrc.h
datasrc_la_SOURCES += client_python.cc client_python.h
datasrc_la_SOURCES += iterator_python.cc iterator_python.h
datasrc_la_SOURCES += finder_python.cc finder_python.h
datasrc_la_SOURCES += updater_python.cc updater_python.h
datasrc_la_SOURCES += journal_reader_python.cc journal_reader_python.h
datasrc_la_SOURCES += configurableclientlist_python.cc
datasrc_la_SOURCES += configurableclientlist_python.h
datasrc_la_SOURCES += zone_loader_python.cc zone_loader_python.h
datasrc_la_SOURCES += zonetable_accessor_python.cc zonetable_accessor_python.h
datasrc_la_SOURCES += zonetable_iterator_python.cc zonetable_iterator_python.h
datasrc_la_SOURCES += zonewriter_python.cc zonewriter_python.h

datasrc_la_CPPFLAGS = $(AM_CPPFLAGS) $(PYTHON_INCLUDES)
datasrc_la_CXXFLAGS = $(AM_CXXFLAGS) $(PYTHON_CXXFLAGS)
datasrc_la_LDFLAGS = $(PYTHON_LDFLAGS)
datasrc_la_LDFLAGS += -module -avoid-version
datasrc_la_LIBADD = $(top_builddir)/src/lib/datasrc/libbundy-datasrc.la
datasrc_la_LIBADD += $(top_builddir)/src/lib/cc/libbundy-cc.la
datasrc_la_LIBADD += $(top_builddir)/src/lib/dns/python/libbundy-pydnspp.la
datasrc_la_LIBADD += $(PYTHON_LIB)

EXTRA_DIST = client_inc.cc
EXTRA_DIST += configurableclientlist_inc.cc
EXTRA_DIST += finder_inc.cc
EXTRA_DIST += iterator_inc.cc
EXTRA_DIST += updater_inc.cc
EXTRA_DIST += journal_reader_inc.cc
EXTRA_DIST += zone_loader_inc.cc
EXTRA_DIST += zonewriter_inc.cc

CLEANDIRS = __pycache__

clean-local:
	rm -rf $(CLEANDIRS)

