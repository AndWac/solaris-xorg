###############################################################################
#
# libXrender - Xlib-based client library for Render extension protocol
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
MODULE_NAME=libXrender

# Version number (used in path names)
MODULE_VERSION=0.9.9

# Checksums for upstream tarball
TARBALL_MD5   = 5db92962b124ca3a8147daae4adbd622
TARBALL_SHA1  = 31bf63dfb4fcb82a6db73abe98df87cb50c17176
TARBALL_SHA256= fc2fe57980a14092426dffcd1f2d9de0987b9d40adea663bd70d6342c0e9be1a

# Patches to apply to source after unpacking, in order
SOURCE_PATCHES += CVE-2016-7949.patch,-p1
SOURCE_PATCHES += CVE-2016-7950.patch,-p1

# Library name
LIBNAME=Xrender

# Man pages to apply Sun footer to & attributes to list
#SUNTOUCHED_MANPAGES=man/*.man
MODULE_STABILITY=Volatile
LIB_MAN_SUFFIX=3xrender

# ARC cases that covered this module
# LSARC/2001/125 Xserver Render Extension
MODULE_ARC_CASES = LSARC/2001/125
# LSARC/2004/414 X Render Extension 0.8
MODULE_ARC_CASES += LSARC/2004/414
# LSARC/2007/193 X Render Extension: Protocol 0.10 / API 0.9 
MODULE_ARC_CASES += LSARC/2007/193

# Environment variable options to GNU autoconf configure script
MODULE_CFLAGS=-I../include

# Link with version mapfile
MODULE_LD_OPTIONS = -M $(PWD)/mapfile-vers



# pkg-config files that need to have -R added
FIX_PC_FILES=xrender.pc.in

# Compatibility links from /usr/X11/lib to /usr/lib
MODULE_X11_LIBCOMPAT_LINKS = libXrender.so libXrender.so.1

include ../Makefile.inc
