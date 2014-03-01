# libgpg-error for Visual Studio 2013

Just checkout/download this project and it should build immediately. Below are the instructions how I made this package.

## Generated from this source code version

http://git.gnupg.org/cgi-bin/gitweb.cgi?p=libgpg-error.git;a=commit;h=bb5318aa5536fa48ec240c2ff48b9e2e1d9916ef

## How I generated the files in this directory

* Downloaded + installed MinGW including MSYS
* Started `C:\MinGW\msys\1.0\msys.bat`
* Extracted http://git.gnupg.org/cgi-bin/gitweb.cgi?p=libgpg-error.git;a=snapshot;h=HEAD;sf=tgz
  into `C:\MinGW\msys\1.0\home\flakes\libgpg-error-HEAD`
* Added `--disable-languages --disable-rpath --disable-nls` to `configure_opts` in `autogen.rc`
* Ran `./autogen.sh` (ignore git errors if any)
* Ran `./autogen.sh --build-w32`
* Ran `make`

## Further steps I took

* Copied source files into `src`
* Copied generated files into `generated`
* Added git revision to `BUILD_REVISION` in `config.h`
* Crafted `libgpg-error-win32-defines.h`
* Removed `#line` from `versioninfo.rc`
* Added `return 0;` to `gpgrt_lock_init` in `w32-lock.c`
* For DLL builds, `#ifndef DLL_EXPORT` in `init.h` changed to:
  `#if !defined(DLL_EXPORT) || !defined(_GPG_ERR_HAVE_CONSTRUCTOR)`
