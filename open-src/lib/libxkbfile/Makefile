###############################################################################
#
# libxkbfile - library for parsing & handling of XKB data files
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
MODULE_NAME=libxkbfile

# Version number (used in path names)
MODULE_VERSION=1.0.9

# Checksums for upstream tarball
TARBALL_MD5   = 4a4cfeaf24dab1b991903455d6d7d404
TARBALL_SHA1  = d708d3415212febbc67d4d996d02d7e3218e13ad
TARBALL_SHA256= 51817e0530961975d9513b773960b4edd275f7d5c72293d5a151ed4f42aeb16a

# Patches to apply to source after unpacking, in order
SOURCE_PATCHES =

DELIBTOOLIZE_FLAGS = --shared libxkbfile.so.5

# Library name
LIBNAME=xkbfile

# Man pages to apply Sun footer to & attributes to list
#SUNTOUCHED_MANPAGES=man/*.man
MODULE_STABILITY=Volatile
LIB_MAN_SUFFIX=3xkbfile

# pkg-config files that need to have -R added
FIX_PC_FILES=xkbfile.pc.in

# Compatibility links from /usr/X11/lib to /usr/lib
MODULE_X11_LIBCOMPAT_LINKS = libxkbfile.so libxkbfile.so.5

include ../Makefile.inc
