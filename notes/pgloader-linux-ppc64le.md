# Data migration with the pgloader util on the linux ppc64le platform

pgloader can be installed in different ways, so this article describes only one way, how to compile and install on 
the linux ppc64le platform.

## Installation of the SBCL (Steel Bank Common Lisp)

There are binaries for the platform (1.5.8 is the latest current version), 
but the problem is that threads support is disabled by default, 
so we will have to rebuild `SBCL` along with this feature. 

Download the latest binaries: http://www.sbcl.org/platform-table.html

```bash
bzip2 -cd sbcl-1.5.8-ppc64le-linux-binary.tar.bz2 | tar xvf -
cd sbcl-1.5.8-ppc64le-linux
sudo sh install.sh
sbcl
```

Write: `*features*`

This is SBCL 1.5.8, an implementation of ANSI Common Lisp.
More information about SBCL is available at <http://www.sbcl.org/>.

SBCL is free software, provided as is, with absolutely no warranty.
It is mostly in the public domain; some portions are provided under
BSD-style licenses.  See the CREDITS and COPYING files in the
distribution for more information.
* *features*
(:PPC64 :64-BIT :ALIEN-CALLBACKS :ANSI-CL :COMMON-LISP :COMPARE-AND-SWAP-VOPS
 :ELF :GENCGC :IEEE-FLOATING-POINT :LINKAGE-TABLE :LINUX :LITTLE-ENDIAN
 :OS-PROVIDES-BLKSIZE-T :OS-PROVIDES-DLADDR :OS-PROVIDES-DLOPEN
 :OS-PROVIDES-GETPROTOBY-R :OS-PROVIDES-POLL :OS-PROVIDES-PUTWC
 :OS-PROVIDES-SUSECONDS-T :PACKAGE-LOCAL-NICKNAMES :RELOCATABLE-HEAP :SB-DOC
 :SB-DYNAMIC-CORE :SB-EVAL :SB-LDB :SB-PACKAGE-LOCKS :SB-SOURCE-LOCATIONS
 :SB-UNICODE :SBCL :STACK-ALLOCATABLE-CLOSURES :STACK-ALLOCATABLE-FIXED-OBJECTS
 :STACK-ALLOCATABLE-LISTS :STACK-ALLOCATABLE-VECTORS :UNIX)

There is no support of threads, so we need to compile it from sources.

### Compiling SBCL from Source

SBCL can be compiled from source code using another ANSI-compliant Common Lisp implementation.

- SBCL itself
- CMU Common Lisp
- Clozure CL
- CLISP
- ABCL
- ECL

```bash
git clone git://git.code.sf.net/p/sbcl/sbcl
cd sbcl
git checkout sbcl-1.5.9
sh make.sh --with-sb-core-compression --with-sb-thread
sudo sh install.sh
sbcl
```

Write: `*features*`

This is SBCL 1.5.9, an implementation of ANSI Common Lisp.
More information about SBCL is available at <http://www.sbcl.org/>.

SBCL is free software, provided as is, with absolutely no warranty.
It is mostly in the public domain; some portions are provided under
BSD-style licenses.  See the CREDITS and COPYING files in the
distribution for more information.
* *features*
(:PPC64 :64-BIT :ALIEN-CALLBACKS :ANSI-CL :COMMON-LISP :COMPARE-AND-SWAP-VOPS
 :ELF :GENCGC :IEEE-FLOATING-POINT :LINKAGE-TABLE :LINUX :LITTLE-ENDIAN
 :OS-PROVIDES-BLKSIZE-T :OS-PROVIDES-DLADDR :OS-PROVIDES-DLOPEN
 :OS-PROVIDES-GETPROTOBY-R :OS-PROVIDES-POLL :OS-PROVIDES-PUTWC
 :OS-PROVIDES-SUSECONDS-T :PACKAGE-LOCAL-NICKNAMES :RELOCATABLE-HEAP
 :SB-CORE-COMPRESSION :SB-DOC :SB-DYNAMIC-CORE :SB-EVAL :SB-LDB
 :SB-PACKAGE-LOCKS :SB-SOURCE-LOCATIONS :SB-THREAD :SB-UNICODE :SBCL
 :STACK-ALLOCATABLE-CLOSURES :STACK-ALLOCATABLE-FIXED-OBJECTS
 :STACK-ALLOCATABLE-LISTS :STACK-ALLOCATABLE-VECTORS :UNIX)

## Compilation and installation of the pgloader util

```bash
git clone https://github.com/dimitri/pgloader.git
git checkout v3.6.2
```

To do an adhoc build and install, you can use bootstrap scripts:

```bash
chmod +x bootstrap-centos7.sh
make
./build/bin/pgloader --help
```

## Migration with the pgloader util

```bash
./build/bin/pgloader/pgloader mysql://$myUser:$myPassword@$myHost:$myPort/$myDb postgresql://$pgUser:$pgPassword@$pgHost:$pgPort/$pgDb
```

Where variables are:

```
myUser="user"
myPassword="password"
myHost="localhost"
myPort="3306"
myDb="database"

pgUser="user"
pgPassword="password"
pgHost="localhost"
pgPort="5432"
pgDb="database"
```

Enjoy!