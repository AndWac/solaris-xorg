###############################################################################
#
# Copyright (c) 2006, 2014, Oracle and/or its affiliates. All rights reserved.
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
MODULE_NAME=encodings

# pkg(5) name we deliver the files in (override default)
MODULE_PKGNAME=x11/library/libfontenc
MODULE_PKGNAME_SET=yes

# Package metadata
MODULE_DESC = data files for libfontenc to map font encodings between character sets

# Version number (used in path names)
MODULE_VERSION = 1.0.4

# Checksums for upstream tarball
TARBALL_MD5  = 0f2d6546d514c5cc4ecf78a60657a5c1
TARBALL_SHA1 = 24ace2470403f85a0d393769204029bd8247992a

# Patches to apply to source after unpacking, in order
SOURCE_PATCHES=	

# Clone sources into build dir, since mkfontdir can't build encodings in
# other directories very well.
CLONE_SRC = yes

# Extra configure flags
MODULE_CONFIG_OPTS=--disable-gzip-small-encodings \
	--disable-gzip-large-encodings

### Include common rulesets
include ../Makefile.inc
