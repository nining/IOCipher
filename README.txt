
Building Native Bits
--------------------

This app relies on OpenSSL libcrypto, sqlcipher, and libsqlfs, which
are all "native" C code that needs to be built before working with the
Java. First, make sure you have the prerequisites:

  apt-get install tcl libtool automake autoconf gawk

Now build everything:

  cd /path/to/guardianproject/iocipher
  git submodule init
  git submodule update
  make -C external
  ndk-build

The shared library .so files are in libs/armeabi and the libsqlfs.a
static library is in external/libsqlfs/.libs/libsqlfs.a.

License
-------

When taken as a whole, this project is under the the LGPLv3 license
since it is the only license that is compatible with the licenses of
all the components.  The source code for this comes from a few
different places, so there are a number of licenses for different
chunks.

* Apache 2.0 (Android Internals): Much of the code here is taken from
  the Android internals, so it has an Apache 2.0 license.

* OpenSSL License: It is linked to the OpenSSL that is provided with
  Android, so it should be covered under Android's handling of the
  advertisment clause.

* LGPL 2.1 (libsqlfs)

* BSD-style (sqlcipher)

