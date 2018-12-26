## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by godlovevampire@gmail.com, please send email to godlovevampire@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5D__chunk_set_info_real_Integer-divide-by-zero

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack Fuzzout/crashes/H5D__chunk_set_info_real_Integer-divide-by-zero test
==92835== Memcheck, a memory error detector
==92835== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==92835== Using Valgrind-3.14.0-353a3587bb-20181007X and LibVEX; rerun with -h for copyright info
==92835== Command: ./h5repack Fuzzout/crashes/id:000009,sig:08,src:000000,op:int16,pos:889,val:be:+512 test
==92835== 
--92835-- Valgrind options:
--92835--    -v
--92835--    --tool=memcheck
--92835--    --leak-check=full
--92835-- Contents of /proc/version:
--92835--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--92835-- 
--92835-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--92835-- Page sizes: currently 4096, max supported 4096
--92835-- Valgrind library directory: /usr/lib/x86_64-linux-gnu/valgrind
--92835-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--92835-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.27.so
--92835--   Considering /usr/lib/debug/.build-id/fa/01a234506568b77ad2d1a6da398e45586c550b.debug ..
--92835--   .. build-id is valid
--92835-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/memcheck-amd64-linux
--92835--   Considering /usr/lib/debug/.build-id/93/5efea22a69d45c080fd7ebab50cfe06d56e7af.debug ..
--92835--   .. build-id is valid
--92835--    object doesn't have a dynamic symbol table
--92835-- Scheduler: using generic scheduler lock implementation.
--92835-- Reading suppressions file: /usr/lib/x86_64-linux-gnu/valgrind/default.supp
==92835== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-92835-by-root-on-???
==92835== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-92835-by-root-on-???
==92835== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-92835-by-root-on-???
==92835== 
==92835== TO CONTROL THIS PROCESS USING vgdb (which you probably
==92835== don't want to do, unless you know exactly what you're doing,
==92835== or are doing some strange experiment):
==92835==   /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=92835 ...command...
==92835== 
==92835== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==92835==   /path/to/gdb ./h5repack
==92835== and then give GDB the following command
==92835==   target remote | /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=92835
==92835== --pid is optional if only one valgrind process is running
==92835== 
--92835-- REDIR: 0x401e290 (ld-linux-x86-64.so.2:strlen) redirected to 0x580c97f2 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--92835-- REDIR: 0x401e070 (ld-linux-x86-64.so.2:index) redirected to 0x580c980c (vgPlain_amd64_linux_REDIR_FOR_index)
--92835-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_core-amd64-linux.so
--92835--   Considering /usr/lib/debug/.build-id/3d/5115a2ef08a4077609b25d33f892f9260b8b5b.debug ..
--92835--   .. build-id is valid
--92835-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_memcheck-amd64-linux.so
--92835--   Considering /usr/lib/debug/.build-id/19/fb020e170903e05352b43e84af203f8f9ed2d8.debug ..
--92835--   .. build-id is valid
==92835== WARNING: new redirection conflicts with existing -- ignoring it
--92835--     old: 0x0401e290 (strlen              ) R-> (0000.0) 0x580c97f2 vgPlain_amd64_linux_REDIR_FOR_strlen
--92835--     new: 0x0401e290 (strlen              ) R-> (2007.0) 0x04838d80 strlen
--92835-- REDIR: 0x401aab0 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839e40 (strcmp)
--92835-- REDIR: 0x401e7d0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d860 (mempcpy)
--92835-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--92835-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--92835--    object doesn't have a symbol table
--92835-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.27.so
--92835--   Considering /usr/lib/debug/.build-id/2b/51cce982e540854dd1995136601f770f127b05.debug ..
--92835--   .. build-id is valid
--92835-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.27.so
--92835--   Considering /usr/lib/debug/.build-id/b6/7df54e445705b0d3fc5fb78cee3c26357ecba3.debug ..
--92835--   .. build-id is valid
--92835-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.27.so
--92835--   Considering /usr/lib/debug/.build-id/e9/38fe6706abe362f6c3c7474373ccc626cf4805.debug ..
--92835--   .. build-id is valid
--92835-- REDIR: 0x57b6050 (libc.so.6:memmove) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b5280 (libc.so.6:strncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b6330 (libc.so.6:strcasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b4cd0 (libc.so.6:strcat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b52b0 (libc.so.6:rindex) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b7900 (libc.so.6:rawmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57d0e60 (libc.so.6:wmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b61c0 (libc.so.6:mempcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b5ff0 (libc.so.6:bcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b5240 (libc.so.6:strncmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b4d40 (libc.so.6:strcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b6120 (libc.so.6:memset) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57cfb60 (libc.so.6:wcschr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b51e0 (libc.so.6:strnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b4db0 (libc.so.6:strcspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b6380 (libc.so.6:strncasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b4d80 (libc.so.6:strcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b64c0 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57d20c0 (libc.so.6:wcsnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b52e0 (libc.so.6:strpbrk) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b4d00 (libc.so.6:index) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b51b0 (libc.so.6:strlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57bc1b0 (libc.so.6:memrchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b63d0 (libc.so.6:strcasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b5fc0 (libc.so.6:memchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57d0920 (libc.so.6:wcslen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b5590 (libc.so.6:strspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b6300 (libc.so.6:stpncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b62d0 (libc.so.6:stpcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b7930 (libc.so.6:strchrnul) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57b6420 (libc.so.6:strncasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x5888700 (libc.so.6:__strrchr_avx2) redirected to 0x4838790 (rindex)
--92835-- REDIR: 0x58888d0 (libc.so.6:__strlen_avx2) redirected to 0x4838c60 (strlen)
--92835-- REDIR: 0x5889290 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c790 (memset)
--92835-- REDIR: 0x57b15c0 (libc.so.6:malloc) redirected to 0x4835710 (malloc)
--92835-- REDIR: 0x5888510 (libc.so.6:__strchrnul_avx2) redirected to 0x483d390 (strchrnul)
--92835-- REDIR: 0x5875c90 (libc.so.6:__strcpy_ssse3) redirected to 0x4838db0 (strcpy)
--92835-- REDIR: 0x57b1d60 (libc.so.6:realloc) redirected to 0x4837d00 (realloc)
--92835-- REDIR: 0x5888e10 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c8a0 (memmove)
--92835-- REDIR: 0x57b1c50 (libc.so.6:free) redirected to 0x4836940 (free)
--92835-- REDIR: 0x5877440 (libc.so.6:__strncpy_ssse3) redirected to 0x4838f50 (strncpy)
--92835-- REDIR: 0x58640a0 (libc.so.6:__strcmp_ssse3) redirected to 0x4839d00 (strcmp)
--92835-- REDIR: 0x5884ee0 (libc.so.6:__memcmp_avx2_movbe) redirected to 0x483c060 (bcmp)
--92835-- REDIR: 0x57b22a0 (libc.so.6:calloc) redirected to 0x4837ab0 (calloc)
--92835-- REDIR: 0x57b5210 (libc.so.6:strncat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--92835-- REDIR: 0x57c70f0 (libc.so.6:__strncat_ssse3) redirected to 0x4838b00 (strncat)
--92835-- REDIR: 0x58843b0 (libc.so.6:__strcspn_sse42) redirected to 0x483dc00 (strcspn)
==92835== 
==92835== Process terminating with default action of signal 8 (SIGFPE)
==92835==  Integer divide by zero at address 0x1004AFAC04
==92835==    at 0x49BCB94: H5D__chunk_set_info_real (H5Dchunk.c:699)
==92835==    by 0x49BC79F: H5D__chunk_set_info (H5Dchunk.c:744)
==92835==    by 0x49AFA53: H5D__chunk_init (H5Dchunk.c:976)
==92835==    by 0x4A25E2F: H5D__layout_oh_read (H5Dlayout.c:658)
==92835==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==92835==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==92835==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==92835==    by 0x4996485: H5Dopen2 (H5D.c:291)
==92835==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==92835==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==92835==    by 0x410FFD: h5repack (h5repack.c:54)
==92835==    by 0x40931F: main (h5repack_main.c:769)
==92835== 
==92835== HEAP SUMMARY:
==92835==     in use at exit: 1,361,893 bytes in 3,178 blocks
==92835==   total heap usage: 3,271 allocs, 93 frees, 1,372,965 bytes allocated
==92835== 
==92835== Searching for pointers to 3,178 not-freed blocks
==92835== Checked 1,462,400 bytes
==92835== 
==92835== LEAK SUMMARY:
==92835==    definitely lost: 0 bytes in 0 blocks
==92835==    indirectly lost: 0 bytes in 0 blocks
==92835==      possibly lost: 0 bytes in 0 blocks
==92835==    still reachable: 1,361,893 bytes in 3,178 blocks
==92835==                       of which reachable via heuristic:
==92835==                         length64           : 11,278 bytes in 32 blocks
==92835==                         newarray           : 32 bytes in 2 blocks
==92835==         suppressed: 0 bytes in 0 blocks
==92835== Reachable blocks (those to which a pointer was found) are not shown.
==92835== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==92835== 
==92835== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 0 from 0)
==92835== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 0 from 0)
Floating point exception





```
---
