###############################################################################
#
# xdm Makefile
#
# Copyright 2009 Sun Microsystems, Inc.  All rights reserved.
# Use is subject to license terms.
#
# Permission is hereby granted, free of charge, to any person obtaining a
# copy of this software and associated documentation files (the
# "Software"), to deal in the Software without restriction, including
# without limitation the rights to use, copy, modify, merge, publish,
# distribute, and/or sell copies of the Software, and to permit persons
# to whom the Software is furnished to do so, provided that the above
# copyright notice(s) and this permission notice appear in all copies of
# the Software and that both the above copyright notice(s) and this
# permission notice appear in supporting documentation.
# 
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
# OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
# MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT
# OF THIRD PARTY RIGHTS. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR
# HOLDERS INCLUDED IN THIS NOTICE BE LIABLE FOR ANY CLAIM, OR ANY SPECIAL
# INDIRECT OR CONSEQUENTIAL DAMAGES, OR ANY DAMAGES WHATSOEVER RESULTING
# FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT,
# NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION
# WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
# 
# Except as contained in this notice, the name of a copyright holder
# shall not be used in advertising or otherwise to promote the sale, use
# or other dealings in this Software without prior written authorization
# of the copyright holder.
#
#

# Package name used in tarballs
MODULE_NAME=xdm

# Version number (used in path names)
MODULE_VERSION=1.1.9

# Patches to apply to source after unpacking, in order
SOURCE_PATCHES = \
	mkdir.patch,-p1 \
	bindir.patch \
	terminateServer.patch \
	Xsession.patch

# Man pages to apply Sun footer to & attributes to list
SUNTOUCHED_MANPAGES=xdm.man.cpp
SUN_PACKAGE=SUNWxdm
MODULE_STABILITY=Committed
MODULE_SUNTOUCH_MAN_FLAGS= -p $(MODULE_PREFIX)/sbin/

# Where to install xdm files
MODULE_PREFIX=/usr
MODULE_PREFIX_SET=yes

# Additional configure script options
# Only build shared greeter module, not static
# Set various paths to better match Solaris
MODULE_CONFIG_OPTS= \
	--enable-shared=yes --enable-static=no \
	--with-xdmconfigdir=/etc/X11/xdm \
	--with-piddir=/var/run/xdm \
	--with-authdir=/var/run/xdm \
	--bindir=/usr/sbin \
	DEF_USER_PATH=/usr/bin:/usr/X11/bin:/usr/sbin:/sbin \
	DEF_SYSTEM_PATH=/usr/bin:/usr/X11/bin:/usr/sbin:/sbin


# Special handling while xdm is moved to /usr but other apps are still in
# /usr/X11
MODULE_CONFIG_OPTS += \
	--with-xrdb='/usr/X11/bin/xrdb' \
	--with-default-session=command='/usr/X11/bin/xterm -ls' \

# Additional build & install targets
MODULE_ADD_BUILD_TARGETS=build_xdm_configs
MODULE_ADD_INSTALL_TARGETS=install_xdmshell install_xdm_configs

include ../Makefile.inc

# Move xdmshell from default location to the place we put in our packages
install_xdmshell: default_install
	-rm -f $(PROTODIR)/usr/lib/X11/xdm/xdmshell
	mv $(PROTODIR)/usr/sbin/xdmshell $(PROTODIR)/usr/lib/X11/xdm/xdmshell

# Copy xdm config files from /etc to /usr for use as prototypes
XDM_CONFIG_FILES=Xaccess Xresources Xservers xdm-config
XDM_ETC_CONFIGDIR=/etc/X11/xdm
XDM_USR_CONFIGDIR=/usr/lib/X11/xdm
XCF_USR_FILES=$(XDM_CONFIG_FILES:%=$(PROTODIR)/$(XDM_USR_CONFIGDIR)/%)
XCF_ETC_SRCDIR=$(SOURCE_DIR)/config
XCF_ETC_SRCFILES=$(XDM_CONFIG_FILES:%=$(XCF_ETC_SRCDIR)/%)
XCF_USR_SRCDIR=$(SOURCE_DIR)/config/annotated
XCF_USR_SRCFILES=$(XDM_CONFIG_FILES:%=$(XCF_USR_SRCDIR)/%)

build_xdm_configs: $(XCF_USR_SRCFILES)
install_xdm_configs: $(XCF_USR_FILES) $(PROTODIR)/$(XDM_USR_CONFIGDIR)/README
$(XCF_ETC_SRCFILES): default_build

XCF_HEADER = %1$$s----------------------------------------------------------------------------
XCF_HEADER += \n%1$$s NOTE: The file provided in $(XDM_USR_CONFIGDIR) is a sample %2$$s
XCF_HEADER += \n%1$$s configuration file provided for your reference.
XCF_HEADER += \n%1$$s
XCF_HEADER += \n%1$$s xdm reads the actual configuration from the copies located in $(XDM_ETC_CONFIGDIR)
XCF_HEADER += \n%1$$s (unless configured otherwise by $(XDM_ETC_CONFIGDIR)/xdm-config or
XCF_HEADER += \n%1$$s  a file specified via the -config command line option).
XCF_HEADER += \n%1$$s----------------------------------------------------------------------------\n

$(PROTODIR)/$(XDM_USR_CONFIGDIR) $(XCF_USR_SRCDIR):
	mkdir -p $@

$(XCF_USR_FILES): $(PROTODIR)/$(XDM_USR_CONFIGDIR) $(XCF_USR_SRCFILES)
	-rm -f $@
	mkdir -p $(PROTODIR)/$(XDM_USR_CONFIGDIR)
	@ set -x ; cp -p $(XCF_USR_SRCDIR)/$$(basename $@) $@

$(XCF_USR_SRCFILES): $(XCF_USR_SRCDIR) $(XCF_ETC_SRCFILES)
	-rm -f $@
	FILENAME=$$(basename $@) ; \
	COMMENT_CHAR=$$(head -n 1 $(XCF_ETC_SRCDIR)/$${FILENAME}) ; \
	printf '$(XCF_HEADER)' $${COMMENT_CHAR} $${FILENAME} > $@ ; \
	cat $(XCF_ETC_SRCDIR)/$${FILENAME} >> $@

$(PROTODIR)/$(XDM_USR_CONFIGDIR)/README:$(PROTODIR)/$(XDM_USR_CONFIGDIR)  config-README.txt
	cp -p config-README.txt $@