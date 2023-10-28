# EXT2FileFortress
## Introduction
Constructs a 1 MiB ext2 file system with 2 directories, 1 regular file and 1 symbolic link.
Implemented using ext2 data structures and wrapped system calls.
Passes the fsck.ext2 filesystem check with no errors.

## Usage
Compile and run C program to build the ext2 filesystem image:
```
$ make
$ ./ext2-create
```

Display characteristics of the filesystem:
```
$ dumpe2fs cs111-base.img
```
<img width="557" alt="Screenshot 2023-10-28 at 3 04 28 PM" src="https://github.com/alexsowinski/EXT2FileFortress/assets/125089619/9474377c-d02a-4d04-b38f-c7410b514270">

Run the filesystem integrity check:
```
$ fsck.ext2 cs111-base.img
```
<img width="557" alt="Screenshot 2023-10-28 at 3 07 06 PM" src="https://github.com/alexsowinski/EXT2FileFortress/assets/125089619/d089f7ae-4e4d-489b-8927-a01f394f5b49">

Mount the filesystem and access it:
```
$ mkdir mnt
$ sudo mount -o loop cs111-base.img mnt
$ cd mnt
$ ls -ain
$ cat hello-world
$ cat hello
```
<img width="604" alt="Screenshot 2023-10-28 at 3 15 21 PM" src="https://github.com/alexsowinski/EXT2FileFortress/assets/125089619/1baa5644-6cbe-428a-b224-7ce1646062e3">

Cleanup:
```
$ cd ..
$ sudo umount mnt
$ rmdir mnt
$ make clean
```

## Disclaimer
This is my final project 4 submission for UCLA Professor Eggert's CS 111 Operating Systems Principles course taught in Spring 2023,
of which I received a perfect score for. I do not condone any future use of my work in future CS 111 courses.
