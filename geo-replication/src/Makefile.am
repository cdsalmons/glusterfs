gsyncddir = $(libexecdir)/glusterfs

gsyncd_SCRIPTS = gverify.sh peer_gsec_create \
	set_geo_rep_pem_keys.sh peer_mountbroker

# peer_gsec_create and peer_add_secret_pub are not added to
# EXTRA_DIST as it's derived from a .in file
EXTRA_DIST = gverify.sh set_geo_rep_pem_keys.sh

gsyncd_PROGRAMS = gsyncd

gsyncd_SOURCES = gsyncd.c procdiggy.c

gsyncd_LDADD = $(GF_LDADD) $(top_builddir)/libglusterfs/src/libglusterfs.la

gsyncd_LDFLAGS = $(GF_LDFLAGS)

noinst_HEADERS = procdiggy.h

AM_CPPFLAGS = $(GF_CPPFLAGS) \
	-I$(top_srcdir)/libglusterfs/src\
	-DGSYNCD_PREFIX=\"$(libexecdir)/glusterfs\"\
	-DUSE_LIBGLUSTERFS\
	-DSBIN_DIR=\"$(sbindir)\" -DPYTHON=\"$(PYTHON)\"

AM_CFLAGS = -Wall $(GF_CFLAGS)


CLEANFILES =

$(top_builddir)/libglusterfs/src/libglusterfs.la:
	$(MAKE) -C $(top_builddir)/libglusterfs/src/ all
