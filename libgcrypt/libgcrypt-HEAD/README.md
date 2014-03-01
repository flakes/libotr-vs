# libgpgcrypt for Visual Studio 2013

## Generated from this source code version

http://git.gnupg.org/cgi-bin/gitweb.cgi?p=libgcrypt.git;a=tree;h=3fa79caec69b1ce4b959c7cacd654675bf108864;hb=8804b9ae40e8dd81ee46e18581da79cef7a4eaea

## How I generated the files in this directory

* Downloaded + installed MinGW including MSYS
* Started `C:\MinGW\msys\1.0\msys.bat`
* Ran `make install` in the previously used `libgpg-error` source directory
* Extracted http://git.gnupg.org/cgi-bin/gitweb.cgi?p=libgcrypt.git;a=snapshot;h=3fa79caec69b1ce4b959c7cacd654675bf108864;sf=tgz
	into `C:\MinGW\msys\1.0\home\flakes\libgcrypt-HEAD`
* Ran `./autogen.sh` (ignore git errors if any)
* Ran `./autogen.sh --build-w32`
* Ran `make`

## Further steps I took

* Copied source files into `src`, `compat`, `random`, `mpi`, `cipher`
* Copied generated files into `generated`
* Adjusted `config.h`
* Crafted `libgcrypt-win32-defines.h` and some dummy and compatibility header files
