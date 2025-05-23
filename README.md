# SWFcheck 0.1
An under development cli swf verification program based on github.com/flash-computer/libswftag

## Build Instructions:

1. Download the libswftag source code or clone the repository from [the repo](https://github.com/flash-computer/libswftag)

```sh
git clone https://github.com/flash-computer/libswftag
```

2. Make sure you have a version of make and a C compiler adhering to atleast c99 installed. The code is tested primarily with the GNU compiler collection (gcc) and GNU make, but other should work too

3. cd into the directory and run make and wait for the **ALL DONE!** message

```sh
cd libswftag
make
```

4. Copy the `include` and `lib`(You can ignore the `lib/optional` and `lib/intermediate` folders, they are not important. folders inside to the include and lib directories of your machine. For linux, it's usually `/usr/include/` and `/var/lib/`. Further, we'll alias these as $INCLUDE and $LIB.

5. Download or clone [the swfcheck repo](https://github.com/flash-computer/swfcheck)

```sh
git clone https://github.com/flash-computer/swfcheck
```

6. cd into the directory and compile with:

```sh
make
```

7. This will create an executable named `swfcheck` (followed by an extension like .exe if your OS mandates that for executables) in the current directory. You can copy this somewhere onto your path and use it.

```sh
swfcheck -h
```

## Debug Instructions

1. Follow all the steps upto 5, just replace the command in step 6 with:

```sh
cc swfcheck.c error.c /PATH/TO/LIBSWFTAG/src/*.c -Wall -std=c99 -pedantic -g -o swfcheck
```

Replacing `/PATH/TO/LIBSWFTAG/` with the actual path to the libswftag source directory.

2. Use a debugger like the GNU debugger to debug the executable.

```sh
gdb --args ./swfcheck /PATH/TO/SWF
```

Currently the program only accepts one file as argument, that being the last file argument provided.
