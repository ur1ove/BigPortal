### 리눅스에서 윈도우 원격 데스크톱(RDP) 접속하기  
  
![rdesktop](https://avatars2.githubusercontent.com/u/13203812?s=200&v=4)  
Unix client for Microsoft Remote Desktop Services  
http://www.rdesktop.org  
  
https://github.com/rdesktop/rdesktop  
  
1. rdesktop 소스를 clone합니다.
~~~
Server:~/Desktop # git clone https://github.com/rdesktop/rdesktop
'rdesktop'에 복제합니다...
remote: Counting objects: 8098, done.
remote: Compressing objects: 100% (37/37), done.
remote: Total 8098 (delta 37), reused 53 (delta 33), pack-reused 8028
오브젝트를 받는 중: 100% (8098/8098), 2.12 MiB | 22.00 KiB/s, 완료.
델타를 알아내는 중: 100% (5764/5764), 완료.
~~~
2. autoconf합니다.(configure.ac 파일이 있어야 합니다.)  
~~~
Server:~/Desktop/rdesktop # aclocal
Server:~/Desktop/rdesktop # autoheader
autoheader: error: AC_CONFIG_HEADERS not found in configure.ac
Server:~/Desktop/rdesktop # autoconf
~~~
3. 설치하기 위해 설정파일을 만듭니다.  
~~~
Server:~/Desktop/rdesktop # ./configure 
checking build system type... x86_64-unknown-linux-gnu
checking host system type... x86_64-unknown-linux-gnu
checking for gcc... gcc
checking for C compiler default output file name... a.out
checking whether the C compiler works... yes
checking whether we are cross compiling... no
checking for suffix of executables... 
checking for suffix of object files... o
checking whether we are using the GNU C compiler... yes
checking whether gcc accepts -g... yes
checking for gcc option to accept ISO C89... none needed
checking for a BSD-compatible install... /usr/bin/install -c
checking how to run the C preprocessor... gcc -E
checking for grep that handles long lines and -e... /usr/bin/grep
checking for egrep... /usr/bin/grep -E
checking for ANSI C header files... yes
checking for sys/types.h... yes
checking for sys/stat.h... yes
checking for stdlib.h... yes
checking for string.h... yes
checking for memory.h... yes
checking for strings.h... yes
checking for inttypes.h... yes
checking for stdint.h... yes
checking for unistd.h... yes
checking whether byte ordering is bigendian... no
checking for X... no

ERROR: Could not find X Window System headers/libraries.
To specify paths manually, use the options --x-includes and --x-libraries
~~~
3.1. xorg-x11-devel이 설치되지 않아 발생하는 오류이다.  
  버전에 맞게 리파지터리를 추가하고 설치한다.
~~~
http://romolo.cmb.usc.edu/installs/SLES-11-SP3-SDK/CD1/
http://romolo.cmb.usc.edu/installs/SLES-11-SP3-SDK/CD2/
~~~
3.2. libopenssl-devel이 설치되지 않아 발생하는 오류이다.  
  버전에 맞게 리파지터리를 추가하고 설치한다.
~~~
......
checking for X... libraries , headers 
checking for gethostbyname... yes
checking for connect... yes
checking for remove... yes
checking for shmat... yes
checking for IceConnectionNumber in -lICE... yes
checking for pkg-config... /usr/bin/pkg-config
checking for library containing socket... none required
checking for library containing inet_aton... none required
checking sys/select.h usability... yes
checking sys/select.h presence... yes
checking for sys/select.h... yes
checking sys/modem.h usability... no
checking sys/modem.h presence... no
checking for sys/modem.h... no
checking sys/filio.h usability... no
checking sys/filio.h presence... no
checking for sys/filio.h... no
checking sys/strtio.h usability... no
checking sys/strtio.h presence... no
checking for sys/strtio.h... no
checking locale.h usability... yes
checking locale.h presence... yes
checking for locale.h... yes
checking langinfo.h usability... yes
checking langinfo.h presence... yes
checking for langinfo.h... yes
checking sysexits.h usability... yes
checking sysexits.h presence... yes
checking for sysexits.h... yes
checking for strip... strip
checking for OpenSSL directory... Not found

ERROR: Could not find OpenSSL headers/libraries.
To specify a path manually, use the --with-openssl option.
~~~
3.3. 귀찮다.
~~~
checking for OpenSSL directory... /usr
checking for pkg-config... (cached) /usr/bin/pkg-config
checking pkg-config is at least version 0.9.0... yes
checking for GSSAPI... no

CredSSP support requires GSSAPI, install the dependency
or disable the feature using --disable-credssp.
~~~
3.4. 필요없는거 비활성화하자!!!
~~~
Server:~/Desktop/rdesktop # ./configure --disable-credssp --disable-smartcard
configure: loading site script /usr/share/site/x86_64-unknown-linux-gnu
checking build system type... x86_64-unknown-linux-gnu
checking host system type... x86_64-unknown-linux-gnu
checking for gcc... gcc
checking for C compiler default output file name... a.out
checking whether the C compiler works... yes
checking whether we are cross compiling... no
checking for suffix of executables... 
checking for suffix of object files... o
checking whether we are using the GNU C compiler... yes
checking whether gcc accepts -g... yes
checking for gcc option to accept ISO C89... none needed
checking for a BSD-compatible install... /usr/bin/install -c
checking how to run the C preprocessor... gcc -E
checking for grep that handles long lines and -e... /usr/bin/grep
checking for egrep... /usr/bin/grep -E
checking for ANSI C header files... yes
checking for sys/types.h... yes
checking for sys/stat.h... yes
checking for stdlib.h... yes
checking for string.h... yes
checking for memory.h... yes
checking for strings.h... yes
checking for inttypes.h... yes
checking for stdint.h... yes
checking for unistd.h... yes
checking whether byte ordering is bigendian... no
checking for X... libraries , headers 
checking for gethostbyname... yes
checking for connect... yes
checking for remove... yes
checking for shmat... yes
checking for IceConnectionNumber in -lICE... yes
checking for pkg-config... /usr/bin/pkg-config
checking for library containing socket... none required
checking for library containing inet_aton... none required
checking sys/select.h usability... yes
checking sys/select.h presence... yes
checking for sys/select.h... yes
checking sys/modem.h usability... no
checking sys/modem.h presence... no
checking for sys/modem.h... no
checking sys/filio.h usability... no
checking sys/filio.h presence... no
checking for sys/filio.h... no
checking sys/strtio.h usability... no
checking sys/strtio.h presence... no
checking for sys/strtio.h... no
checking locale.h usability... yes
checking locale.h presence... yes
checking for locale.h... yes
checking langinfo.h usability... yes
checking langinfo.h presence... yes
checking for langinfo.h... yes
checking sysexits.h usability... yes
checking sysexits.h presence... yes
checking for sysexits.h... yes
checking for strip... strip
checking for OpenSSL directory... /usr
checking for pkg-config... (cached) /usr/bin/pkg-config
checking pkg-config is at least version 0.9.0... yes
checking for XRANDR... yes
checking for XCURSOR... yes
checking if architecture needs alignment... no
checking sys/soundcard.h usability... yes
checking sys/soundcard.h presence... yes
checking for sys/soundcard.h... yes
checking dmedia/audio.h usability... no
checking dmedia/audio.h presence... no
checking for dmedia/audio.h... no
checking sys/audioio.h usability... no
checking sys/audioio.h presence... no
checking for sys/audioio.h... no
checking for LIBAO... no
checking for PULSE... no
checking for ALSA... no
checking for LIBSAMPLERATE... no
checking for dirent.h that defines DIR... yes
checking for library containing opendir... none required
checking for dirfd... yes
checking whether dirfd is declared... yes
checking whether dirfd is a macro... no
checking iconv.h usability... yes
checking iconv.h presence... yes
checking for iconv.h... yes
checking for iconv... yes
checking for iconv declaration... 
         extern size_t iconv (iconv_t cd, char * *inbuf, size_t *inbytesleft, char * *outbuf, size_t *outbytesleft);
checking for socklen_t... yes
checking sys/vfs.h usability... yes
checking sys/vfs.h presence... yes
checking for sys/vfs.h... yes
checking sys/statvfs.h usability... yes
checking sys/statvfs.h presence... yes
checking for sys/statvfs.h... yes
checking sys/statfs.h usability... yes
checking sys/statfs.h presence... yes
checking for sys/statfs.h... yes
checking sys/param.h usability... yes
checking sys/param.h presence... yes
checking for sys/param.h... yes
checking for sys/mount.h... yes
configure: checking how to get filesystem space usage...
checking statvfs64 function (SVR4)... no
checking statvfs function (SVR4)... yes
checking for struct statfs.f_namemax... no
checking for struct statvfs.f_namemax... yes
checking for struct statfs.f_namelen... yes
checking for struct statvfs.f_namelen... no
checking for special C compiler options needed for large files... no
checking for _FILE_OFFSET_BITS value needed for large files... no
checking mntent.h usability... yes
checking mntent.h presence... yes
checking for mntent.h... yes
checking for setmntent... yes
configure: creating ./config.status
config.status: creating Makefile
~~~
