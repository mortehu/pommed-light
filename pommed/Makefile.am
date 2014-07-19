bin_PROGRAMS = pommed
dist_pkgdata_DATA = data/click.wav data/goutte.wav

AM_CFLAGS = -g -Wall $(PACKAGES_CFLAGS)
AM_CPPFLAGS = -DDATADIR=\"$(pkgdatadir)\"

pommed_SOURCES = \
  pommed.c cd_eject.c evdev.c conffile.c audio.c evloop.c power.c beep.c \
  video.c sysfs_backlight.c

pommed_LDADD = $(PACKAGES_LIBS) -lrt -lpthread

if ARCH_PPC
pommed_SOURCES += pmac/pmu.c pmac/kbd_backlight.c
else
pommed_SOURCES += mactel/x1600_backlight.c mactel/gma950_backlight.c \
		  mactel/nv8600mgt_backlight.c mactel/kbd_backlight.c \
                  mactel/acpi.c
endif
