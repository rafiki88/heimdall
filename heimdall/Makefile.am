AUTOMAKE_OPTIONS = subdir-objects
ACLOCAL_AMFLAGS = ${ACLOCAL_FLAGS}
AM_CPPFLAGS = $(DEPS_CFLAGS) -std=c++0x -I../libpit/Source
STATIC_LIBS = ../libpit/libpit-1.4.a
bin_PROGRAMS = heimdall
heimdall_SOURCES = source/Arguments.cpp \
	source/Devices.cpp \
	source/BridgeManager.cpp \
	source/ClosePcScreenAction.cpp \
	source/DetectAction.cpp \
	source/DownloadPitAction.cpp \
	source/FlashAction.cpp \
	source/HelpAction.cpp \
	source/InfoAction.cpp \
	source/Interface.cpp \
	source/main.cpp \
	source/PrintPitAction.cpp \
	source/Utility.cpp \
	source/VersionAction.cpp \
	source/Devices.cpp

heimdall_LDADD = $(DEPS_LIBS) $(STATIC_LIBS)

if LINUXTARGET

udevrulesdir = @libdir@/udev/rules.d
udevrules_DATA = 60-heimdall.rules

install-data-hook:
	@echo ""
	@echo "IMPORTANT - You must reboot your machine or execute the following as root:"

if UDEVADM
	@echo "udevadm control --reload-rules"
else
	@echo "service udev restart"
endif
	@echo ""

endif

dist_noinst_SCRIPTS = autogen.sh
