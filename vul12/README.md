## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by godlovevampire@gmail.com, please send email to godlovevampire@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5F__close_invalid-read-memory-access

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack Fuzzout/crashes/H5F__close_invalid-read-memory-access test
==5809== Memcheck, a memory error detector
==5809== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==5809== Using Valgrind-3.14.0-353a3587bb-20181007X and LibVEX; rerun with -h for copyright info
==5809== Command: ./h5repack Fuzzout/crashes/H5F__close_invalid-read-memory-access test
==5809== 
--5809-- Valgrind options:
--5809--    -v
--5809--    --tool=memcheck
--5809--    --leak-check=full
--5809-- Contents of /proc/version:
--5809--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--5809-- 
--5809-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--5809-- Page sizes: currently 4096, max supported 4096
--5809-- Valgrind library directory: /usr/lib/x86_64-linux-gnu/valgrind
--5809-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--5809-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.28.so
--5809--   Considering /usr/lib/debug/.build-id/dd/8026f43793facd0aa3924fb2dd6b0033b7b431.debug ..
--5809--   .. build-id is valid
--5809-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/memcheck-amd64-linux
--5809--   Considering /usr/lib/debug/.build-id/93/5efea22a69d45c080fd7ebab50cfe06d56e7af.debug ..
--5809--   .. build-id is valid
--5809--    object doesn't have a dynamic symbol table
--5809-- Scheduler: using generic scheduler lock implementation.
--5809-- Reading suppressions file: /usr/lib/x86_64-linux-gnu/valgrind/default.supp
==5809== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-5809-by-root-on-???
==5809== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-5809-by-root-on-???
==5809== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-5809-by-root-on-???
==5809== 
==5809== TO CONTROL THIS PROCESS USING vgdb (which you probably
==5809== don't want to do, unless you know exactly what you're doing,
==5809== or are doing some strange experiment):
==5809==   /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=5809 ...command...
==5809== 
==5809== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==5809==   /path/to/gdb ./h5repack
==5809== and then give GDB the following command
==5809==   target remote | /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=5809
==5809== --pid is optional if only one valgrind process is running
==5809== 
--5809-- REDIR: 0x401e350 (ld-linux-x86-64.so.2:strlen) redirected to 0x580c97f2 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--5809-- REDIR: 0x401e130 (ld-linux-x86-64.so.2:index) redirected to 0x580c980c (vgPlain_amd64_linux_REDIR_FOR_index)
--5809-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_core-amd64-linux.so
--5809--   Considering /usr/lib/debug/.build-id/3d/5115a2ef08a4077609b25d33f892f9260b8b5b.debug ..
--5809--   .. build-id is valid
--5809-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_memcheck-amd64-linux.so
--5809--   Considering /usr/lib/debug/.build-id/19/fb020e170903e05352b43e84af203f8f9ed2d8.debug ..
--5809--   .. build-id is valid
==5809== WARNING: new redirection conflicts with existing -- ignoring it
--5809--     old: 0x0401e350 (strlen              ) R-> (0000.0) 0x580c97f2 vgPlain_amd64_linux_REDIR_FOR_strlen
--5809--     new: 0x0401e350 (strlen              ) R-> (2007.0) 0x04838d80 strlen
--5809-- REDIR: 0x401ab70 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839e40 (strcmp)
--5809-- REDIR: 0x401e890 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d860 (mempcpy)
--5809-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--5809-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--5809--    object doesn't have a symbol table
--5809-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.28.so
--5809--   Considering /usr/lib/debug/.build-id/60/1c7068f7cbc26814db9cbca61b1a2c00f5d66d.debug ..
--5809--   .. build-id is valid
--5809-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.28.so
--5809--   Considering /usr/lib/debug/.build-id/86/be4b7815704459f8a32170db4266066980289f.debug ..
--5809--   .. build-id is valid
--5809-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.28.so
--5809--   Considering /usr/lib/debug/.build-id/cd/ae5bb84a51c364471bdd287dbe9df7d1d235f3.debug ..
--5809--   .. build-id is valid
--5809-- REDIR: 0x57a6210 (libc.so.6:memmove) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a5400 (libc.so.6:strncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a64f0 (libc.so.6:strcasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a4e30 (libc.so.6:strcat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a5430 (libc.so.6:rindex) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a7b20 (libc.so.6:rawmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57c04e0 (libc.so.6:wmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57bff80 (libc.so.6:wcscmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a6380 (libc.so.6:mempcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a61b0 (libc.so.6:bcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a53a0 (libc.so.6:strncmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a4ea0 (libc.so.6:strcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a62e0 (libc.so.6:memset) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57bff50 (libc.so.6:wcschr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a5340 (libc.so.6:strnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a4f30 (libc.so.6:strcspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a6540 (libc.so.6:strncasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a4f00 (libc.so.6:strcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a6680 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57c1780 (libc.so.6:wcsnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a5460 (libc.so.6:strpbrk) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a4e60 (libc.so.6:index) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a5310 (libc.so.6:strlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57ac530 (libc.so.6:memrchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a6590 (libc.so.6:strcasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a6180 (libc.so.6:memchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57c0060 (libc.so.6:wcslen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a5700 (libc.so.6:strspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a64c0 (libc.so.6:stpncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a6490 (libc.so.6:stpcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a7b50 (libc.so.6:strchrnul) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57a65e0 (libc.so.6:strncasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x5879440 (libc.so.6:__strrchr_avx2) redirected to 0x4838790 (rindex)
--5809-- REDIR: 0x5879610 (libc.so.6:__strlen_avx2) redirected to 0x4838c60 (strlen)
--5809-- REDIR: 0x5879fd0 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c790 (memset)
--5809-- REDIR: 0x57a1610 (libc.so.6:malloc) redirected to 0x4835710 (malloc)
--5809-- REDIR: 0x5879250 (libc.so.6:__strchrnul_avx2) redirected to 0x483d390 (strchrnul)
--5809-- REDIR: 0x57ba3b0 (libc.so.6:__strcpy_sse2_unaligned) redirected to 0x4838db0 (strcpy)
--5809-- REDIR: 0x57a1eb0 (libc.so.6:realloc) redirected to 0x4837d00 (realloc)
--5809-- REDIR: 0x5879b50 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c8a0 (memmove)
--5809-- REDIR: 0x57a1c60 (libc.so.6:free) redirected to 0x4836940 (free)
--5809-- REDIR: 0x57ba9e0 (libc.so.6:__strncpy_sse2_unaligned) redirected to 0x48392e0 (__strncpy_sse2_unaligned)
--5809-- REDIR: 0x5874b50 (libc.so.6:__strcmp_avx2) redirected to 0x4839d00 (strcmp)
--5809-- REDIR: 0x5875c20 (libc.so.6:__memcmp_avx2_movbe) redirected to 0x483c060 (bcmp)
--5809-- REDIR: 0x57a23e0 (libc.so.6:calloc) redirected to 0x4837ab0 (calloc)
--5809-- REDIR: 0x57a5370 (libc.so.6:strncat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--5809-- REDIR: 0x57bdc90 (libc.so.6:__strncat_sse2_unaligned) redirected to 0x4838b00 (strncat)
--5809-- REDIR: 0x5874760 (libc.so.6:__strcspn_sse42) redirected to 0x483dc00 (strcspn)
--5809-- REDIR: 0x5879b30 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483d4a0 (mempcpy)
==5809== Invalid read of size 4
==5809==    at 0x4AC84E3: H5F__close (H5Fint.c:2034)
==5809==    by 0x4A98D33: H5Fclose (H5F.c:667)
==5809==    by 0x416786: copy_objects (h5repack_copy.c:383)
==5809==    by 0x410FFD: h5repack (h5repack.c:54)
==5809==    by 0x40931F: main (h5repack_main.c:769)
==5809==  Address 0x1c is not stack'd, malloc'd or (recently) free'd
==5809== 
==5809== 
==5809== Process terminating with default action of signal 11 (SIGSEGV)
==5809==  Access not within mapped region at address 0x1C
==5809==    at 0x4AC84E3: H5F__close (H5Fint.c:2034)
==5809==    by 0x4A98D33: H5Fclose (H5F.c:667)
==5809==    by 0x416786: copy_objects (h5repack_copy.c:383)
==5809==    by 0x410FFD: h5repack (h5repack.c:54)
==5809==    by 0x40931F: main (h5repack_main.c:769)
==5809==  If you believe this happened as a result of a stack
==5809==  overflow in your program's main thread (unlikely but
==5809==  possible), you can try to increase the size of the
==5809==  main thread stack using the --main-stacksize= flag.
==5809==  The main thread stack size used in this run was 8388608.
==5809== 
==5809== HEAP SUMMARY:
==5809==     in use at exit: 3,351,517 bytes in 3,334 blocks
==5809==   total heap usage: 3,818 allocs, 484 frees, 3,941,285 bytes allocated
==5809== 
==5809== Searching for pointers to 3,334 not-freed blocks
==5809== Checked 954,264 bytes
==5809== 
==5809== 1,424,032 bytes in 1 blocks are definitely lost in loss record 2,756 of 2,756
==5809==    at 0x4837B65: calloc (vg_replace_malloc.c:752)
==5809==    by 0x4D0D130: H5O_efl_decode (H5Oefl.c:143)
==5809==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==5809==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==5809==    by 0x4A25993: H5D__layout_oh_read (H5Dlayout.c:643)
==5809==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==5809==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==5809==    by 0x4E45FE4: H5R__dereference (H5Rint.c:488)
==5809==    by 0x4E429F7: H5Rdereference2 (H5R.c:185)
==5809==    by 0x4318FB: do_copy_refobjs (h5repack_refs.c:174)
==5809==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==5809==    by 0x410FFD: h5repack (h5repack.c:54)
==5809==    by 0x40931F: main (h5repack_main.c:769)
==5809== 
==5809== LEAK SUMMARY:
==5809==    definitely lost: 1,424,032 bytes in 1 blocks
==5809==    indirectly lost: 0 bytes in 0 blocks
==5809==      possibly lost: 0 bytes in 0 blocks
==5809==    still reachable: 1,927,485 bytes in 3,333 blocks
==5809==                       of which reachable via heuristic:
==5809==                         length64           : 96 bytes in 1 blocks
==5809==         suppressed: 0 bytes in 0 blocks
==5809== Reachable blocks (those to which a pointer was found) are not shown.
==5809== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==5809== 
==5809== ERROR SUMMARY: 2 errors from 2 contexts (suppressed: 0 from 0)
==5809== 
==5809== 1 errors in context 1 of 2:
==5809== Invalid read of size 4
==5809==    at 0x4AC84E3: H5F__close (H5Fint.c:2034)
==5809==    by 0x4A98D33: H5Fclose (H5F.c:667)
==5809==    by 0x416786: copy_objects (h5repack_copy.c:383)
==5809==    by 0x410FFD: h5repack (h5repack.c:54)
==5809==    by 0x40931F: main (h5repack_main.c:769)
==5809==  Address 0x1c is not stack'd, malloc'd or (recently) free'd
==5809== 
==5809== ERROR SUMMARY: 2 errors from 2 contexts (suppressed: 0 from 0)
Segmentation fault




```
---
