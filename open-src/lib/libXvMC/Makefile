###############################################################################
#
# libXvMC - Xlib-based client library for X-Video Motion Compensation extension
#
# Copyright (c) 2006, 2016, Oracle and/or its affiliates. All rights reserved.
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
#

# Package name used in tarballs
MODULE_NAME=libXvMC

# Version number (used in path names)
MODULE_VERSION=1.0.9

# Checksums for upstream tarball
TARBALL_MD5   = eba6b738ed5fdcd8f4203d7c8a470c79
TARBALL_SHA1  = 6fc54831734e781b2848b6f7e3bcc4f752665f21
TARBALL_SHA256= 0703d7dff6ffc184f1735ca5d4eb9dbb402b522e08e008f2f96aee16c40a5756

# Patches to apply to source after unpacking, in order
SOURCE_PATCHES += CVE-2016-7953.patch,-p1

# Library name
LIBNAME=XvMC

# Man pages to apply Sun footer to & attributes to list
#SUNTOUCHED_MANPAGES=man/*.man
MODULE_STABILITY=Volatile
LIB_MAN_SUFFIX=3xvMC

# pkg-config files that need to have -R added
FIX_PC_FILES=xvmc.pc.in

# Compatibility links from /usr/X11/lib to /usr/lib
MODULE_X11_LIBCOMPAT_LINKS = libXvMC.so libXvMC.so.1 libXvMCW.so libXvMCW.so.1

# configure passes "xv" to PKG_CHECK_MODULES since libXv headers are needed,
# but we don't need to link with it, so ignore it at link time.
MODULE_LDFLAGS = $(ZDISCARD_UNUSED_DEP)

include ../Makefile.inc
