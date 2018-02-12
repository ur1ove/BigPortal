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
