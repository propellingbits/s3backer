
#
# s3backer - FUSE-based single file backing store via Amazon S3
# 
# Copyright 2008-2011 Archie L. Cobbs <archie@dellroad.org>
# 
# This program is free software; you can redistribute it and/or
# modify it under the terms of the GNU General Public License
# as published by the Free Software Foundation; either version 2
# of the License, or (at your option) any later version.
# 
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
# 
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA
# 02110-1301, USA.
#
# In addition, as a special exception, the copyright holders give
# permission to link the code of portions of this program with the
# OpenSSL library under certain conditions as described in each
# individual source file, and distribute linked combinations including
# the two.
#
# You must obey the GNU General Public License in all respects for all
# of the code used other than OpenSSL. If you modify file(s) with this
# exception, you may extend this exception to your version of the
# file(s), but you are not obligated to do so. If you do not wish to do
# so, delete this exception statement from your version. If you delete
# this exception statement from all source files in the program, then
# also delete it here.

bin_PROGRAMS=       s3backer

noinst_PROGRAMS=    tester

noinst_HEADERS=     s3backer.h \
			block_cache.h \
			block_part.h \
			dcache.h \
			ec_protect.h \
			erase.h \
			fuse_ops.h \
			hash.h \
			http_io.h \
			reset.h \
			test_io.h \
			s3b_config.h

man_MANS=           s3backer.1

docdir=             $(datadir)/doc/packages/$(PACKAGE)

doc_DATA=           CHANGES COPYING README INSTALL TODO

EXTRA_DIST=         CHANGES s3backer.1 s3backer.spec

s3backer_SOURCES=   main.c \
		    block_cache.c \
		    block_part.c \
		    dcache.c \
		    ec_protect.c \
		    erase.c \
		    fuse_ops.c \
		    hash.c \
		    http_io.c \
		    reset.c \
		    s3b_config.c \
		    test_io.c \
		    sslcompat.c \
		    gitrev.c

tester_SOURCES=     tester.c \
		    block_cache.c \
		    block_part.c \
		    dcache.c \
		    ec_protect.c \
		    erase.c \
		    hash.c \
		    http_io.c \
		    reset.c \
		    s3b_config.c \
		    test_io.c \
		    sslcompat.c \
		    gitrev.c

AM_CFLAGS=          $(FUSE_CFLAGS)

gitrev.c:
			printf 'const char *const s3backer_version = "%s";\n' "`git describe`" > gitrev.c

