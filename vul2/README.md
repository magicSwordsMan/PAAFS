## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by godlovevampire@gmail.com, please send email to godlovevampire@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5T_close_real_heap-buffer-overflow

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack Fuzzout/crashes/id:000022,sig:11,src:000076,op:flip1,pos:1458 test
==63095== Memcheck, a memory error detector
==63095== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==63095== Using Valgrind-3.14.0-353a3587bb-20181007X and LibVEX; rerun with -h for copyright info
==63095== Command: ./h5repack Fuzzout/crashes/id:000022,sig:11,src:000076,op:flip1,pos:1458 test
==63095== 
--63095-- Valgrind options:
--63095--    -v
--63095--    --tool=memcheck
--63095--    --leak-check=full
--63095-- Contents of /proc/version:
--63095--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--63095-- 
--63095-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--63095-- Page sizes: currently 4096, max supported 4096
--63095-- Valgrind library directory: /usr/lib/x86_64-linux-gnu/valgrind
--63095-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--63095-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.27.so
--63095--   Considering /usr/lib/debug/.build-id/fa/01a234506568b77ad2d1a6da398e45586c550b.debug ..
--63095--   .. build-id is valid
--63095-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/memcheck-amd64-linux
--63095--   Considering /usr/lib/debug/.build-id/93/5efea22a69d45c080fd7ebab50cfe06d56e7af.debug ..
--63095--   .. build-id is valid
--63095--    object doesn't have a dynamic symbol table
--63095-- Scheduler: using generic scheduler lock implementation.
--63095-- Reading suppressions file: /usr/lib/x86_64-linux-gnu/valgrind/default.supp
==63095== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-63095-by-root-on-???
==63095== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-63095-by-root-on-???
==63095== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-63095-by-root-on-???
==63095== 
==63095== TO CONTROL THIS PROCESS USING vgdb (which you probably
==63095== don't want to do, unless you know exactly what you're doing,
==63095== or are doing some strange experiment):
==63095==   /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=63095 ...command...
==63095== 
==63095== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==63095==   /path/to/gdb ./h5repack
==63095== and then give GDB the following command
==63095==   target remote | /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=63095
==63095== --pid is optional if only one valgrind process is running
==63095== 
--63095-- REDIR: 0x401e290 (ld-linux-x86-64.so.2:strlen) redirected to 0x580c97f2 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--63095-- REDIR: 0x401e070 (ld-linux-x86-64.so.2:index) redirected to 0x580c980c (vgPlain_amd64_linux_REDIR_FOR_index)
--63095-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_core-amd64-linux.so
--63095--   Considering /usr/lib/debug/.build-id/3d/5115a2ef08a4077609b25d33f892f9260b8b5b.debug ..
--63095--   .. build-id is valid
--63095-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_memcheck-amd64-linux.so
--63095--   Considering /usr/lib/debug/.build-id/19/fb020e170903e05352b43e84af203f8f9ed2d8.debug ..
--63095--   .. build-id is valid
==63095== WARNING: new redirection conflicts with existing -- ignoring it
--63095--     old: 0x0401e290 (strlen              ) R-> (0000.0) 0x580c97f2 vgPlain_amd64_linux_REDIR_FOR_strlen
--63095--     new: 0x0401e290 (strlen              ) R-> (2007.0) 0x04838d80 strlen
--63095-- REDIR: 0x401aab0 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839e40 (strcmp)
--63095-- REDIR: 0x401e7d0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d860 (mempcpy)
--63095-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--63095-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--63095--    object doesn't have a symbol table
--63095-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.27.so
--63095--   Considering /usr/lib/debug/.build-id/2b/51cce982e540854dd1995136601f770f127b05.debug ..
--63095--   .. build-id is valid
--63095-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.27.so
--63095--   Considering /usr/lib/debug/.build-id/b6/7df54e445705b0d3fc5fb78cee3c26357ecba3.debug ..
--63095--   .. build-id is valid
--63095-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.27.so
--63095--   Considering /usr/lib/debug/.build-id/e9/38fe6706abe362f6c3c7474373ccc626cf4805.debug ..
--63095--   .. build-id is valid
--63095-- REDIR: 0x57b6050 (libc.so.6:memmove) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b5280 (libc.so.6:strncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b6330 (libc.so.6:strcasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b4cd0 (libc.so.6:strcat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b52b0 (libc.so.6:rindex) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b7900 (libc.so.6:rawmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57d0e60 (libc.so.6:wmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b61c0 (libc.so.6:mempcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b5ff0 (libc.so.6:bcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b5240 (libc.so.6:strncmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b4d40 (libc.so.6:strcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b6120 (libc.so.6:memset) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57cfb60 (libc.so.6:wcschr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b51e0 (libc.so.6:strnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b4db0 (libc.so.6:strcspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b6380 (libc.so.6:strncasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b4d80 (libc.so.6:strcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b64c0 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57d20c0 (libc.so.6:wcsnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b52e0 (libc.so.6:strpbrk) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b4d00 (libc.so.6:index) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b51b0 (libc.so.6:strlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57bc1b0 (libc.so.6:memrchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b63d0 (libc.so.6:strcasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b5fc0 (libc.so.6:memchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57d0920 (libc.so.6:wcslen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b5590 (libc.so.6:strspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b6300 (libc.so.6:stpncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b62d0 (libc.so.6:stpcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b7930 (libc.so.6:strchrnul) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57b6420 (libc.so.6:strncasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x5888700 (libc.so.6:__strrchr_avx2) redirected to 0x4838790 (rindex)
--63095-- REDIR: 0x58888d0 (libc.so.6:__strlen_avx2) redirected to 0x4838c60 (strlen)
--63095-- REDIR: 0x5889290 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c790 (memset)
--63095-- REDIR: 0x57b15c0 (libc.so.6:malloc) redirected to 0x4835710 (malloc)
--63095-- REDIR: 0x5888510 (libc.so.6:__strchrnul_avx2) redirected to 0x483d390 (strchrnul)
--63095-- REDIR: 0x5875c90 (libc.so.6:__strcpy_ssse3) redirected to 0x4838db0 (strcpy)
--63095-- REDIR: 0x57b1d60 (libc.so.6:realloc) redirected to 0x4837d00 (realloc)
--63095-- REDIR: 0x5888e10 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c8a0 (memmove)
--63095-- REDIR: 0x57b1c50 (libc.so.6:free) redirected to 0x4836940 (free)
--63095-- REDIR: 0x5877440 (libc.so.6:__strncpy_ssse3) redirected to 0x4838f50 (strncpy)
--63095-- REDIR: 0x58640a0 (libc.so.6:__strcmp_ssse3) redirected to 0x4839d00 (strcmp)
--63095-- REDIR: 0x5884ee0 (libc.so.6:__memcmp_avx2_movbe) redirected to 0x483c060 (bcmp)
--63095-- REDIR: 0x57b22a0 (libc.so.6:calloc) redirected to 0x4837ab0 (calloc)
--63095-- REDIR: 0x57b5210 (libc.so.6:strncat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63095-- REDIR: 0x57c70f0 (libc.so.6:__strncat_ssse3) redirected to 0x4838b00 (strncat)
--63095-- REDIR: 0x58843b0 (libc.so.6:__strcspn_sse42) redirected to 0x483dc00 (strcspn)
==63095== 
==63095== Process terminating with default action of signal 11 (SIGSEGV)
==63095==  Bad permissions for mapped region at address 0x53AA880
==63095==    at 0x4CE65B7: H5O__chunk_deserialize (H5Ocache.c:1406)
==63095==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==63095==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==63095==    by 0x495AE26: H5C_protect (H5C.c:2357)
==63095==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==63095==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==63095==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==63095==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==63095==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==63095==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==63095==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==63095==    by 0x4D2DE3C: H5O__get_info_by_name (H5Oint.c:2375)
==63095==    by 0x4CAFD62: H5Oget_info_by_name2 (H5O.c:518)
==63095== 
==63095== HEAP SUMMARY:
==63095==     in use at exit: 1,342,436 bytes in 3,123 blocks
==63095==   total heap usage: 3,176 allocs, 53 frees, 1,349,884 bytes allocated
==63095== 
==63095== Searching for pointers to 3,123 not-freed blocks
==63095== Checked 1,444,720 bytes
==63095== 
==63095== LEAK SUMMARY:
==63095==    definitely lost: 0 bytes in 0 blocks
==63095==    indirectly lost: 0 bytes in 0 blocks
==63095==      possibly lost: 0 bytes in 0 blocks
==63095==    still reachable: 1,342,436 bytes in 3,123 blocks
==63095==                       of which reachable via heuristic:
==63095==                         length64           : 5,950 bytes in 30 blocks
==63095==         suppressed: 0 bytes in 0 blocks
==63095== Reachable blocks (those to which a pointer was found) are not shown.
==63095== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==63095== 
==63095== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 0 from 0)
==63095== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 0 from 0)
Segmentation fault


```
---
