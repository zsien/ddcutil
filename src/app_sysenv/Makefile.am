if ENABLE_ENVCMDS_COND

AM_CPPFLAGS =        \
  $(GLIB_CFLAGS)     \
  -I$(top_srcdir)/src \
  -I$(top_srcdir)/src/public

if USE_LIBDRM_COND
AM_CPPFLAGS += \
  $(LIBDRM_CFLAGS)
endif


AM_CFLAGS = -Wall
if WARNINGS_ARE_ERRORS_COND
AM_CFLAGS += -Werror
endif
# AM_CFLAGS += -Wpedantic

if ENABLE_CALLGRAPH_COND
AM_CFLAGS += -fdump-rtl-expand
endif

CLEANFILES = \
*expand

# Intermediate Library
noinst_LTLIBRARIES = libappsysenv.la

libappsysenv_la_SOURCES =     \
query_sysenv.c \
query_sysenv_access.c \
query_sysenv_base.c \
query_sysenv_dmidecode.c \
query_sysenv_i2c.c \
query_sysenv_logs.c \
query_sysenv_modules.c \
query_sysenv_procfs.c \
query_sysenv_sysfs_common.c \
query_sysenv_original_sys_scans.c \
query_sysenv_detailed_bus_pci_devices.c \
query_sysenv_simplified_sys_bus_pci_devices.c \
query_sysenv_sysfs.c \
query_sysenv_xref.c 

if ENABLE_USB_COND
libappsysenv_la_SOURCES += \
   query_sysenv_usb.c
endif

if USE_LIBDRM_COND
libappsysenv_la_SOURCES += \
   query_sysenv_drm.c
endif

endif
