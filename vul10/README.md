## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by godlovevampire@gmail.com, please send email to godlovevampire@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5S_close_invalid-read-memory-access

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack Fuzzout/crashes/H5S_close_invalid-read-memory-access test
==3572== Memcheck, a memory error detector
==3572== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==3572== Using Valgrind-3.14.0-353a3587bb-20181007X and LibVEX; rerun with -h for copyright info
==3572== Command: ./h5repack Fuzzout/crashes/H5S_close_invalid-read-memory-access test
==3572== 
--3572-- Valgrind options:
--3572--    -v
--3572--    --tool=memcheck
--3572--    --leak-check=full
--3572-- Contents of /proc/version:
--3572--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--3572-- 
--3572-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--3572-- Page sizes: currently 4096, max supported 4096
--3572-- Valgrind library directory: /usr/lib/x86_64-linux-gnu/valgrind
--3572-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--3572-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.28.so
--3572--   Considering /usr/lib/debug/.build-id/dd/8026f43793facd0aa3924fb2dd6b0033b7b431.debug ..
--3572--   .. build-id is valid
--3572-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/memcheck-amd64-linux
--3572--   Considering /usr/lib/debug/.build-id/93/5efea22a69d45c080fd7ebab50cfe06d56e7af.debug ..
--3572--   .. build-id is valid
--3572--    object doesn't have a dynamic symbol table
--3572-- Scheduler: using generic scheduler lock implementation.
--3572-- Reading suppressions file: /usr/lib/x86_64-linux-gnu/valgrind/default.supp
==3572== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-3572-by-root-on-???
==3572== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-3572-by-root-on-???
==3572== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-3572-by-root-on-???
==3572== 
==3572== TO CONTROL THIS PROCESS USING vgdb (which you probably
==3572== don't want to do, unless you know exactly what you're doing,
==3572== or are doing some strange experiment):
==3572==   /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=3572 ...command...
==3572== 
==3572== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==3572==   /path/to/gdb ./h5repack
==3572== and then give GDB the following command
==3572==   target remote | /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=3572
==3572== --pid is optional if only one valgrind process is running
==3572== 
--3572-- REDIR: 0x401e350 (ld-linux-x86-64.so.2:strlen) redirected to 0x580c97f2 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--3572-- REDIR: 0x401e130 (ld-linux-x86-64.so.2:index) redirected to 0x580c980c (vgPlain_amd64_linux_REDIR_FOR_index)
--3572-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_core-amd64-linux.so
--3572--   Considering /usr/lib/debug/.build-id/3d/5115a2ef08a4077609b25d33f892f9260b8b5b.debug ..
--3572--   .. build-id is valid
--3572-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_memcheck-amd64-linux.so
--3572--   Considering /usr/lib/debug/.build-id/19/fb020e170903e05352b43e84af203f8f9ed2d8.debug ..
--3572--   .. build-id is valid
==3572== WARNING: new redirection conflicts with existing -- ignoring it
--3572--     old: 0x0401e350 (strlen              ) R-> (0000.0) 0x580c97f2 vgPlain_amd64_linux_REDIR_FOR_strlen
--3572--     new: 0x0401e350 (strlen              ) R-> (2007.0) 0x04838d80 strlen
--3572-- REDIR: 0x401ab70 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839e40 (strcmp)
--3572-- REDIR: 0x401e890 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d860 (mempcpy)
--3572-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--3572-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--3572--    object doesn't have a symbol table
--3572-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.28.so
--3572--   Considering /usr/lib/debug/.build-id/60/1c7068f7cbc26814db9cbca61b1a2c00f5d66d.debug ..
--3572--   .. build-id is valid
--3572-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.28.so
--3572--   Considering /usr/lib/debug/.build-id/86/be4b7815704459f8a32170db4266066980289f.debug ..
--3572--   .. build-id is valid
--3572-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.28.so
--3572--   Considering /usr/lib/debug/.build-id/cd/ae5bb84a51c364471bdd287dbe9df7d1d235f3.debug ..
--3572--   .. build-id is valid
--3572-- REDIR: 0x57a6210 (libc.so.6:memmove) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a5400 (libc.so.6:strncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a64f0 (libc.so.6:strcasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a4e30 (libc.so.6:strcat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a5430 (libc.so.6:rindex) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a7b20 (libc.so.6:rawmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57c04e0 (libc.so.6:wmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57bff80 (libc.so.6:wcscmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a6380 (libc.so.6:mempcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a61b0 (libc.so.6:bcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a53a0 (libc.so.6:strncmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a4ea0 (libc.so.6:strcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a62e0 (libc.so.6:memset) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57bff50 (libc.so.6:wcschr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a5340 (libc.so.6:strnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a4f30 (libc.so.6:strcspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a6540 (libc.so.6:strncasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a4f00 (libc.so.6:strcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a6680 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57c1780 (libc.so.6:wcsnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a5460 (libc.so.6:strpbrk) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a4e60 (libc.so.6:index) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a5310 (libc.so.6:strlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57ac530 (libc.so.6:memrchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a6590 (libc.so.6:strcasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a6180 (libc.so.6:memchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57c0060 (libc.so.6:wcslen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a5700 (libc.so.6:strspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a64c0 (libc.so.6:stpncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a6490 (libc.so.6:stpcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a7b50 (libc.so.6:strchrnul) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57a65e0 (libc.so.6:strncasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x5879440 (libc.so.6:__strrchr_avx2) redirected to 0x4838790 (rindex)
--3572-- REDIR: 0x5879610 (libc.so.6:__strlen_avx2) redirected to 0x4838c60 (strlen)
--3572-- REDIR: 0x5879fd0 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c790 (memset)
--3572-- REDIR: 0x57a1610 (libc.so.6:malloc) redirected to 0x4835710 (malloc)
--3572-- REDIR: 0x5879250 (libc.so.6:__strchrnul_avx2) redirected to 0x483d390 (strchrnul)
--3572-- REDIR: 0x57ba3b0 (libc.so.6:__strcpy_sse2_unaligned) redirected to 0x4838db0 (strcpy)
--3572-- REDIR: 0x57a1eb0 (libc.so.6:realloc) redirected to 0x4837d00 (realloc)
--3572-- REDIR: 0x5879b50 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c8a0 (memmove)
--3572-- REDIR: 0x57a1c60 (libc.so.6:free) redirected to 0x4836940 (free)
--3572-- REDIR: 0x57ba9e0 (libc.so.6:__strncpy_sse2_unaligned) redirected to 0x48392e0 (__strncpy_sse2_unaligned)
--3572-- REDIR: 0x5874b50 (libc.so.6:__strcmp_avx2) redirected to 0x4839d00 (strcmp)
--3572-- REDIR: 0x5875c20 (libc.so.6:__memcmp_avx2_movbe) redirected to 0x483c060 (bcmp)
--3572-- REDIR: 0x57a23e0 (libc.so.6:calloc) redirected to 0x4837ab0 (calloc)
--3572-- REDIR: 0x57a5370 (libc.so.6:strncat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3572-- REDIR: 0x57bdc90 (libc.so.6:__strncat_sse2_unaligned) redirected to 0x4838b00 (strncat)
--3572-- REDIR: 0x5874760 (libc.so.6:__strcspn_sse42) redirected to 0x483dc00 (strcspn)
--3572-- REDIR: 0x5879b30 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483d4a0 (mempcpy)
==3572== Invalid read of size 8
==3572==    at 0x4E4BA0F: H5S_close (H5S.c:448)
==3572==    by 0x48DB2B0: H5A__free (H5Aint.c:1166)
==3572==    by 0x4CCF6CF: H5O_attr_decode (H5Oattr.c:253)
==3572==    by 0x4CCF6CF: H5O_attr_shared_decode (H5Oshared.h:82)
==3572==    by 0x4D49613: H5O__msg_iterate_real (H5Omessage.c:1288)
==3572==    by 0x48DC6B1: H5A__compact_build_table (H5Aint.c:1544)
==3572==    by 0x4CD7C2F: H5O_attr_iterate_real (H5Oattribute.c:1283)
==3572==    by 0x4CD6DB0: H5O__attr_open_by_idx (H5Oattribute.c:611)
==3572==    by 0x48D6A92: H5A__open_by_idx (H5Aint.c:537)
==3572==    by 0x48B4F71: H5Aopen_by_idx (H5A.c:570)
==3572==    by 0x412A96: copy_attr (h5repack.c:364)
==3572==    by 0x41A57D: do_copy_objects (h5repack_copy.c:713)
==3572==    by 0x41A57D: copy_objects (h5repack_copy.c:353)
==3572==    by 0x410FFD: h5repack (h5repack.c:54)
==3572==  Address 0x18 is not stack'd, malloc'd or (recently) free'd
==3572== 
==3572== 
==3572== Process terminating with default action of signal 11 (SIGSEGV)
==3572==  Access not within mapped region at address 0x18
==3572==    at 0x4E4BA0F: H5S_close (H5S.c:448)
==3572==    by 0x48DB2B0: H5A__free (H5Aint.c:1166)
==3572==    by 0x4CCF6CF: H5O_attr_decode (H5Oattr.c:253)
==3572==    by 0x4CCF6CF: H5O_attr_shared_decode (H5Oshared.h:82)
==3572==    by 0x4D49613: H5O__msg_iterate_real (H5Omessage.c:1288)
==3572==    by 0x48DC6B1: H5A__compact_build_table (H5Aint.c:1544)
==3572==    by 0x4CD7C2F: H5O_attr_iterate_real (H5Oattribute.c:1283)
==3572==    by 0x4CD6DB0: H5O__attr_open_by_idx (H5Oattribute.c:611)
==3572==    by 0x48D6A92: H5A__open_by_idx (H5Aint.c:537)
==3572==    by 0x48B4F71: H5Aopen_by_idx (H5A.c:570)
==3572==    by 0x412A96: copy_attr (h5repack.c:364)
==3572==    by 0x41A57D: do_copy_objects (h5repack_copy.c:713)
==3572==    by 0x41A57D: copy_objects (h5repack_copy.c:353)
==3572==    by 0x410FFD: h5repack (h5repack.c:54)
==3572==  If you believe this happened as a result of a stack
==3572==  overflow in your program's main thread (unlikely but
==3572==  possible), you can try to increase the size of the
==3572==  main thread stack using the --main-stacksize= flag.
==3572==  The main thread stack size used in this run was 8388608.
==3572== 
==3572== HEAP SUMMARY:
==3572==     in use at exit: 1,343,582 bytes in 3,141 blocks
==3572==   total heap usage: 3,196 allocs, 55 frees, 1,350,110 bytes allocated
==3572== 
==3572== Searching for pointers to 3,141 not-freed blocks
==3572== Checked 1,448,880 bytes
==3572== 
==3572== LEAK SUMMARY:
==3572==    definitely lost: 0 bytes in 0 blocks
==3572==    indirectly lost: 0 bytes in 0 blocks
==3572==      possibly lost: 0 bytes in 0 blocks
==3572==    still reachable: 1,343,582 bytes in 3,141 blocks
==3572==                       of which reachable via heuristic:
==3572==                         length64           : 6,144 bytes in 15 blocks
==3572==         suppressed: 0 bytes in 0 blocks
==3572== Reachable blocks (those to which a pointer was found) are not shown.
==3572== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==3572== 
==3572== ERROR SUMMARY: 1 errors from 1 contexts (suppressed: 0 from 0)
==3572== 
==3572== 1 errors in context 1 of 1:
==3572== Invalid read of size 8
==3572==    at 0x4E4BA0F: H5S_close (H5S.c:448)
==3572==    by 0x48DB2B0: H5A__free (H5Aint.c:1166)
==3572==    by 0x4CCF6CF: H5O_attr_decode (H5Oattr.c:253)
==3572==    by 0x4CCF6CF: H5O_attr_shared_decode (H5Oshared.h:82)
==3572==    by 0x4D49613: H5O__msg_iterate_real (H5Omessage.c:1288)
==3572==    by 0x48DC6B1: H5A__compact_build_table (H5Aint.c:1544)
==3572==    by 0x4CD7C2F: H5O_attr_iterate_real (H5Oattribute.c:1283)
==3572==    by 0x4CD6DB0: H5O__attr_open_by_idx (H5Oattribute.c:611)
==3572==    by 0x48D6A92: H5A__open_by_idx (H5Aint.c:537)
==3572==    by 0x48B4F71: H5Aopen_by_idx (H5A.c:570)
==3572==    by 0x412A96: copy_attr (h5repack.c:364)
==3572==    by 0x41A57D: do_copy_objects (h5repack_copy.c:713)
==3572==    by 0x41A57D: copy_objects (h5repack_copy.c:353)
==3572==    by 0x410FFD: h5repack (h5repack.c:54)
==3572==  Address 0x18 is not stack'd, malloc'd or (recently) free'd
==3572== 
==3572== ERROR SUMMARY: 1 errors from 1 contexts (suppressed: 0 from 0)
Segmentation fault







```
---
