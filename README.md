# FindingSmoothTwins

## Environment

We conducted experiments on the below environments.

- Ubuntu 22.04
- dash  0.5.11+git20210903+057cd650a4ed-3build1
- SageMath 10.7
- Python 3.10.12
- Cython 3.2.1
- fpylll 0.6.4

## The Way To Unzip

The zip-file is zipped with **7-zip**, so please unzip with 7-zip.
```sh
$ sudo apt install p7zip-full p7zip-rar

# ----------------------------------------
# Example of result
# ----------------------------------------
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
p7zip-full is already the newest version (16.02+dfsg-8).
The following NEW packages will be installed:
  p7zip-rar
0 upgraded, 1 newly installed, 0 to remove and 1 not upgraded.
Need to get 44.8 kB of archives.
After this operation, 118 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu jammy/multiverse amd64 p7zip-rar amd64 16.02-3build1 [44.8 kB]
Fetched 44.8 kB in 0s (100 kB/s)
Selecting previously unselected package p7zip-rar.
(Reading database ... 118419 files and directories currently installed.)
Preparing to unpack .../p7zip-rar_16.02-3build1_amd64.deb ...
Unpacking p7zip-rar (16.02-3build1) ...
Setting up p7zip-rar (16.02-3build1) ...
```
The zip-file is locked with password, and the password is only written in my letter. If the letter is accepted and published, then I will publish the source codes.
```sh
$ 7z x FindingSmoothTwins.zip

# ----------------------------------------
# Example of result
# ----------------------------------------

7-Zip [64] 16.02 : Copyright (c) 1999-2016 Igor Pavlov : 2016-05-21
p7zip Version 16.02 (locale=en_US.UTF-8,Utf16=on,HugeFiles=on,64 bits,2 CPUs Intel(R) Xeon(R) CPU @ 2.20GHz (406F0),ASM,AES-NI)

Scanning the drive for archives:
1 file, 8628 bytes (9 KiB)

Extracting archive: FindingSmoothTwins.zip
--
Path = FindingSmoothTwins.zip
Type = zip
Physical Size = 8628


Enter password (will not be echoed):
Everything is Ok

Folders: 3
Files: 5
Size:       32316
Compressed: 8628
```

## Setups

To compile and run the sources, you needs Python, Cython, SageMath.
Please install previously.

## Installation

Please run ``Build.sh`` to build the cython sources.

```sh
FindingSmoothTwins$ sh Build.sh

Compiling FLSVPSmoothTwins.pyx because it changed.
Compiling MySmoothTwins.pyx because it changed.
[1/2] Cythonizing FLSVPSmoothTwins.pyx
[2/2] Cythonizing MySmoothTwins.pyx
running build_ext
building 'FLSVPSmoothTwins' extension
creating build/temp.linux-x86_64-cpython-313
x86_64-linux-gnu-gcc -fno-strict-overflow -Wsign-compare -DNDEBUG -g -O2 -Wall -g -fstack-protector-strong -Wformat -Werror=format-security -g -fwrapv -O2 -fPIC -I/usr/include/python3.13 -c FLSVPSmoothTwins.c -o build/temp.linux-x86_64-cpython-313/FLSVPSmoothTwins.o -O3 -march=native -mtune=native -mfpmath=both -ffast-math -funroll-loops -flto=auto -fopenmp
creating build/lib.linux-x86_64-cpython-313
x86_64-linux-gnu-gcc -shared -Wl,-O1 -Wl,-Bsymbolic-functions -Wl,-Bsymbolic-functions -g -fwrapv -O2 build/temp.linux-x86_64-cpython-313/FLSVPSmoothTwins.o -L/usr/lib/x86_64-linux-gnu -o build/lib.linux-x86_64-cpython-313/FLSVPSmoothTwins.cpython-313-x86_64-linux-gnu.so
lto-wrapper: warning: using serial compilation of 3 LTRANS jobs
building 'MySmoothTwins' extension
x86_64-linux-gnu-gcc -fno-strict-overflow -Wsign-compare -DNDEBUG -g -O2 -Wall -g -fstack-protector-strong -Wformat -Werror=format-security -g -fwrapv -O2 -fPIC -I/usr/include/python3.13 -c MySmoothTwins.c -o build/temp.linux-x86_64-cpython-313/MySmoothTwins.o -O3 -march=native -mtune=native -mfpmath=both -ffast-math -funroll-loops -flto=auto -fopenmp
x86_64-linux-gnu-gcc -shared -Wl,-O1 -Wl,-Bsymbolic-functions -Wl,-Bsymbolic-functions -g -fwrapv -O2 build/temp.linux-x86_64-cpython-313/MySmoothTwins.o -L/usr/lib/x86_64-linux-gnu -o build/lib.linux-x86_64-cpython-313/MySmoothTwins.cpython-313-x86_64-linux-gnu.so
lto-wrapper: warning: using serial compilation of 3 LTRANS jobs
copying build/lib.linux-x86_64-cpython-313/FLSVPSmoothTwins.cpython-313-x86_64-linux-gnu.so -> 
copying build/lib.linux-x86_64-cpython-313/MySmoothTwins.cpython-313-x86_64-linux-gnu.so -> 
```
