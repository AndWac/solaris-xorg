###############################################################################
#
# Xfixes 1.x Makefile
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
MODULE_NAME=libXfixes

# Version number (used in path names)
MODULE_VERSION=5.0.1

# Checksums for upstream tarball
TARBALL_MD5   = b985b85f8b9386c85ddcfe1073906b4d
TARBALL_SHA1  = e14fa072bd70b30eef47391cac637bdb4de9e8a3
TARBALL_SHA256= 63bec085084fa3caaee5180490dd871f1eb2020ba9e9b39a30f93693ffc34767

# Patches to apply to source after unpacking, in order
SOURCE_PATCHES = soversion.patch,-p1
SOURCE_PATCHES += CVE-2016-7944.patch,-p1

# Need to autoreconf since soversion.patch changes Makefile.am's
AUTORECONF=yes

# Library name
LIBNAME=Xfixes

# ARC cases that covered this module
# PSARC 2004/318 XFixes Xserver Extension
MODULE_ARC_CASES = PSARC/2004/318
# PSARC/2006/702 XFixes 4.0
MODULE_ARC_CASES += PSARC/2006/702

# Man pages to apply Sun footer to & attributes to list
SUNTOUCHED_MANPAGES=man/*.man
MODULE_STABILITY=Volatile
LIB_MAN_SUFFIX=3

# Link with version mapfile
MODULE_LD_OPTIONS = -M $(PWD)/mapfile-vers

# pkg-config files that need to have -R added
FIX_PC_FILES=xfixes.pc.in

# Compatibility links from /usr/X11/lib to /usr/lib
MODULE_X11_LIBCOMPAT_LINKS = libXfixes.so libXfixes.so.1

include ../Makefile.inc
