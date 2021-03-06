###############################################################################
#
# Copyright (c) 2010, 2016, Oracle and/or its affiliates. All rights reserved.
#
# Permission is hereby granted, free of charge, to any person obtaining a
# copy of this software and associated documentation files (the "Software"),
# to deal in the Software without restriction, including without limitation
# the rights to use, copy, modify, merge, publish, distribute, sublicense,
# and/or sell copies of the Software, and to permit persons to whom the
# Software is furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice (including the next
# paragraph) shall be included in all copies or substantial portions of the
# Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL
# THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
# FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
# DEALINGS IN THE SOFTWARE.
#
###############################################################################
#
# Files for integration with Solaris Service Management Framework (SMF) and
# Role Based Access Control (RBAC) shared by all the X server variants

MODULE_NAME = xserver-common

# Package metadata
MODULE_DESC = Xserver SMF & RBAC configuration files
ORACLE_TPNO = $(ORACLE_TPNO_xorg)

# ARC cases that covered this module
# PSARC/2004/752 X Consolidation conversion to SMF
MODULE_ARC_CASES = PSARC/2004/752
# PSARC/2010/161 Xorg configuration file for VESA driver selection
# (addition of SMF property options/config_file)
MODULE_ARC_CASES += PSARC/2010/161

# No upstream sources for these files, since they're Solaris-specific
MODULE_VERSION=$(XORGSERVER_VERS)
SOURCE_TARBALL_NAME=NONE
SOURCE_TARBALL_NAME_SET=yes
SOURCE_TARGETS=
SOURCE_TARGETS_SET=yes

CONFIGURE_TARGETS=
CONFIGURE_TARGETS_SET=yes

BUILD_TARGETS = check
BUILD_TARGETS_SET=yes

INSTALL_TARGETS = install_common
INSTALL_TARGETS_SET=yes

# Dates to show in Oracle copyright notice in pkg license file
# Earliest & latest of the copyrights in the Oracle files in this pkg
ORACLE_COPYRIGHT_YEARS = 2004, 2011

# Compatibility links from /usr/X11/bin to /usr/bin
MODULE_X11_BINCOMPAT_LINKS = X Xserver

### Include common rulesets
include ../Makefile.inc

DESTDIR=$(PROTODIR)

check: x11-server.xml
	/usr/sbin/svccfg validate x11-server.xml

install_common: $(BUILD_TARGETS)
	mkdir -p \
		$(DESTDIR)$(X11_SMF_MANIFEST_DIR) \
		$(DESTDIR)$(SMF_METHOD_DIR) \
		$(DESTDIR)$(MODULE_BIN_DIR) \
		$(DESTDIR)$(MODULE_MAN_DIR)/man1 \
		$(DESTDIR)/etc/security/auth_attr.d \
		$(DESTDIR)/etc/security/prof_attr.d
	$(INSTALL_SCRIPT) -c -m 0444 x11-server.xml \
		$(DESTDIR)$(X11_SMF_MANIFEST_DIR)/
	$(INSTALL_SCRIPT) -c -m 0755 x11-server $(DESTDIR)$(SMF_METHOD_DIR)/
	$(INSTALL_SCRIPT) -c -m 0755 Xserver $(DESTDIR)$(MODULE_BIN_DIR)/
	$(INSTALL_SCRIPT) -c -m 0444 auth_attr \
		$(DESTDIR)/etc/security/auth_attr.d/$(MODULE_NAME)
	$(INSTALL_SCRIPT) -c -m 0444 prof_attr \
		$(DESTDIR)/etc/security/prof_attr.d/$(MODULE_NAME)
	$(INSTALL_SCRIPT) -c -m 0444 Xnest.1 $(DESTDIR)$(MODULE_MAN_DIR)/man1/
