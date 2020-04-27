EXTRA_DIST =
lib_LTLIBRARIES = libmodbus.la

AM_CPPFLAGS = \
    -include $(top_builddir)/config.h \
    -DSYSCONFDIR=\""$(sysconfdir)"\" \
    -DLIBEXECDIR=\""$(libexecdir)"\" \
    -I${top_srcdir}/include

AM_CFLAGS = ${my_CFLAGS}

libmodbus_la_SOURCES = \
        modbus.c \
        modbus-data.c \
        modbus-rtu.c \
        modbus-tcp.c 

libmodbus_la_LDFLAGS = -no-undefined \
        -version-info $(LIBMODBUS_LT_VERSION_INFO)

if OS_WIN32
libmodbus_la_LIBADD = -lwsock32
endif

if OS_QNX
libmodbus_la_LIBADD = -lsocket
endif

# Header files to install
libmodbusincludedir = $(includedir)/modbus
libmodbusinclude_HEADERS = \
	$(top_srcdir)/include/modbus.h\
	modbus-version.h\
	$(top_srcdir)/include/modbus-rtu.h\
	$(top_srcdir)/include/modbus-tcp.h

DISTCLEANFILES = modbus-version.h
EXTRA_DIST += modbus-version.h.in
CLEANFILES = *~
