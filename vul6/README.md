## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by godlovevampire@gmail.com, please send email to godlovevampire@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5T_get_size_invalid-read-memory-access (CVE-2019-8398)

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack Fuzzout/crashes/H5T_get_size_invalid-read-memory-access test
==41230== Memcheck, a memory error detector
==41230== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==41230== Using Valgrind-3.14.0-353a3587bb-20181007X and LibVEX; rerun with -h for copyright info
==41230== Command: ./h5repack Fuzzout/crashes/H5T_get_size_invalid-read-memory-access test
==41230== 
--41230-- Valgrind options:
--41230--    -v
--41230--    --tool=memcheck
--41230--    --leak-check=full
--41230-- Contents of /proc/version:
--41230--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--41230-- 
--41230-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--41230-- Page sizes: currently 4096, max supported 4096
--41230-- Valgrind library directory: /usr/lib/x86_64-linux-gnu/valgrind
--41230-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--41230-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.27.so
--41230--   Considering /usr/lib/debug/.build-id/fa/01a234506568b77ad2d1a6da398e45586c550b.debug ..
--41230--   .. build-id is valid
--41230-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/memcheck-amd64-linux
--41230--   Considering /usr/lib/debug/.build-id/93/5efea22a69d45c080fd7ebab50cfe06d56e7af.debug ..
--41230--   .. build-id is valid
--41230--    object doesn't have a dynamic symbol table
--41230-- Scheduler: using generic scheduler lock implementation.
--41230-- Reading suppressions file: /usr/lib/x86_64-linux-gnu/valgrind/default.supp
==41230== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-41230-by-root-on-???
==41230== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-41230-by-root-on-???
==41230== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-41230-by-root-on-???
==41230== 
==41230== TO CONTROL THIS PROCESS USING vgdb (which you probably
==41230== don't want to do, unless you know exactly what you're doing,
==41230== or are doing some strange experiment):
==41230==   /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=41230 ...command...
==41230== 
==41230== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==41230==   /path/to/gdb ./h5repack
==41230== and then give GDB the following command
==41230==   target remote | /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=41230
==41230== --pid is optional if only one valgrind process is running
==41230== 
--41230-- REDIR: 0x401e290 (ld-linux-x86-64.so.2:strlen) redirected to 0x580c97f2 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--41230-- REDIR: 0x401e070 (ld-linux-x86-64.so.2:index) redirected to 0x580c980c (vgPlain_amd64_linux_REDIR_FOR_index)
--41230-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_core-amd64-linux.so
--41230--   Considering /usr/lib/debug/.build-id/3d/5115a2ef08a4077609b25d33f892f9260b8b5b.debug ..
--41230--   .. build-id is valid
--41230-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_memcheck-amd64-linux.so
--41230--   Considering /usr/lib/debug/.build-id/19/fb020e170903e05352b43e84af203f8f9ed2d8.debug ..
--41230--   .. build-id is valid
==41230== WARNING: new redirection conflicts with existing -- ignoring it
--41230--     old: 0x0401e290 (strlen              ) R-> (0000.0) 0x580c97f2 vgPlain_amd64_linux_REDIR_FOR_strlen
--41230--     new: 0x0401e290 (strlen              ) R-> (2007.0) 0x04838d80 strlen
--41230-- REDIR: 0x401aab0 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839e40 (strcmp)
--41230-- REDIR: 0x401e7d0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d860 (mempcpy)
--41230-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--41230-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--41230--    object doesn't have a symbol table
--41230-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.27.so
--41230--   Considering /usr/lib/debug/.build-id/2b/51cce982e540854dd1995136601f770f127b05.debug ..
--41230--   .. build-id is valid
--41230-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.27.so
--41230--   Considering /usr/lib/debug/.build-id/b6/7df54e445705b0d3fc5fb78cee3c26357ecba3.debug ..
--41230--   .. build-id is valid
--41230-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.27.so
--41230--   Considering /usr/lib/debug/.build-id/e9/38fe6706abe362f6c3c7474373ccc626cf4805.debug ..
--41230--   .. build-id is valid
--41230-- REDIR: 0x57b6050 (libc.so.6:memmove) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b5280 (libc.so.6:strncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b6330 (libc.so.6:strcasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b4cd0 (libc.so.6:strcat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b52b0 (libc.so.6:rindex) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b7900 (libc.so.6:rawmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57d0e60 (libc.so.6:wmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b61c0 (libc.so.6:mempcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b5ff0 (libc.so.6:bcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b5240 (libc.so.6:strncmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b4d40 (libc.so.6:strcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b6120 (libc.so.6:memset) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57cfb60 (libc.so.6:wcschr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b51e0 (libc.so.6:strnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b4db0 (libc.so.6:strcspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b6380 (libc.so.6:strncasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b4d80 (libc.so.6:strcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b64c0 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57d20c0 (libc.so.6:wcsnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b52e0 (libc.so.6:strpbrk) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b4d00 (libc.so.6:index) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b51b0 (libc.so.6:strlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57bc1b0 (libc.so.6:memrchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b63d0 (libc.so.6:strcasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b5fc0 (libc.so.6:memchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57d0920 (libc.so.6:wcslen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b5590 (libc.so.6:strspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b6300 (libc.so.6:stpncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b62d0 (libc.so.6:stpcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b7930 (libc.so.6:strchrnul) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57b6420 (libc.so.6:strncasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x5888700 (libc.so.6:__strrchr_avx2) redirected to 0x4838790 (rindex)
--41230-- REDIR: 0x58888d0 (libc.so.6:__strlen_avx2) redirected to 0x4838c60 (strlen)
--41230-- REDIR: 0x5889290 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c790 (memset)
--41230-- REDIR: 0x57b15c0 (libc.so.6:malloc) redirected to 0x4835710 (malloc)
--41230-- REDIR: 0x5888510 (libc.so.6:__strchrnul_avx2) redirected to 0x483d390 (strchrnul)
--41230-- REDIR: 0x5875c90 (libc.so.6:__strcpy_ssse3) redirected to 0x4838db0 (strcpy)
--41230-- REDIR: 0x57b1d60 (libc.so.6:realloc) redirected to 0x4837d00 (realloc)
--41230-- REDIR: 0x5888e10 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c8a0 (memmove)
--41230-- REDIR: 0x57b1c50 (libc.so.6:free) redirected to 0x4836940 (free)
--41230-- REDIR: 0x5877440 (libc.so.6:__strncpy_ssse3) redirected to 0x4838f50 (strncpy)
--41230-- REDIR: 0x58640a0 (libc.so.6:__strcmp_ssse3) redirected to 0x4839d00 (strcmp)
--41230-- REDIR: 0x5884ee0 (libc.so.6:__memcmp_avx2_movbe) redirected to 0x483c060 (bcmp)
--41230-- REDIR: 0x57b22a0 (libc.so.6:calloc) redirected to 0x4837ab0 (calloc)
--41230-- REDIR: 0x57b5210 (libc.so.6:strncat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41230-- REDIR: 0x57c70f0 (libc.so.6:__strncat_ssse3) redirected to 0x4838b00 (strncat)
--41230-- REDIR: 0x58843b0 (libc.so.6:__strcspn_sse42) redirected to 0x483dc00 (strcspn)
--41230-- REDIR: 0x58882e0 (libc.so.6:__strchr_avx2) redirected to 0x4838910 (index)
--41230-- REDIR: 0x5888df0 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483d4a0 (mempcpy)
==41230== Invalid read of size 8
==41230==    at 0x4F59568: H5T_get_size (H5T.c:4040)
==41230==    by 0x4D11828: H5O_fill_old_decode (H5Ofill.c:350)
==41230==    by 0x4D11828: H5O_fill_shared_decode (H5Oshared.h:82)
==41230==    by 0x4CF1E2E: H5O__copy_header_real (H5Ocopy.c:532)
==41230==    by 0x4CF08E1: H5O_copy_header_map (H5Ocopy.c:989)
==41230==    by 0x4C7B2C7: H5L__link_copy_file (H5L.c:3594)
==41230==    by 0x4D407D9: H5O__link_post_copy_file (H5Olink.c:784)
==41230==    by 0x4CF54A5: H5O__copy_header_real (H5Ocopy.c:870)
==41230==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==41230==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==41230==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==41230==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==41230==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==41230==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==41230==    by 0x410FFD: h5repack (h5repack.c:54)
==41230==    by 0x40931F: main (h5repack_main.c:769)
==41230==  Address 0x28 is not stack'd, malloc'd or (recently) free'd
==41230== 
==41230== 
==41230== Process terminating with default action of signal 11 (SIGSEGV)
==41230==  Access not within mapped region at address 0x28
==41230==    at 0x4F59568: H5T_get_size (H5T.c:4040)
==41230==    by 0x4D11828: H5O_fill_old_decode (H5Ofill.c:350)
==41230==    by 0x4D11828: H5O_fill_shared_decode (H5Oshared.h:82)
==41230==    by 0x4CF1E2E: H5O__copy_header_real (H5Ocopy.c:532)
==41230==    by 0x4CF08E1: H5O_copy_header_map (H5Ocopy.c:989)
==41230==    by 0x4C7B2C7: H5L__link_copy_file (H5L.c:3594)
==41230==    by 0x4D407D9: H5O__link_post_copy_file (H5Olink.c:784)
==41230==    by 0x4CF54A5: H5O__copy_header_real (H5Ocopy.c:870)
==41230==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==41230==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==41230==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==41230==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==41230==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==41230==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==41230==    by 0x410FFD: h5repack (h5repack.c:54)
==41230==    by 0x40931F: main (h5repack_main.c:769)
==41230==  If you believe this happened as a result of a stack
==41230==  overflow in your program's main thread (unlikely but
==41230==  possible), you can try to increase the size of the
==41230==  main thread stack using the --main-stacksize= flag.
==41230==  The main thread stack size used in this run was 8388608.
==41230== 
==41230== HEAP SUMMARY:
==41230==     in use at exit: 1,357,903 bytes in 3,207 blocks
==41230==   total heap usage: 3,319 allocs, 112 frees, 1,374,290 bytes allocated
==41230== 
==41230== Searching for pointers to 3,207 not-freed blocks
==41230== Checked 1,458,904 bytes
==41230== 
==41230== 88 bytes in 1 blocks are definitely lost in loss record 1,723 of 2,677
==41230==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41230==    by 0x4B4EA43: H5FL_malloc (H5FL.c:243)
==41230==    by 0x4B4EA43: H5FL_reg_malloc (H5FL.c:441)
==41230==    by 0x4B4EE83: H5FL_reg_calloc (H5FL.c:498)
==41230==    by 0x4D11403: H5O_fill_old_decode (H5Ofill.c:326)
==41230==    by 0x4D11403: H5O_fill_shared_decode (H5Oshared.h:82)
==41230==    by 0x4CF1E2E: H5O__copy_header_real (H5Ocopy.c:532)
==41230==    by 0x4CF08E1: H5O_copy_header_map (H5Ocopy.c:989)
==41230==    by 0x4C7B2C7: H5L__link_copy_file (H5L.c:3594)
==41230==    by 0x4D407D9: H5O__link_post_copy_file (H5Olink.c:784)
==41230==    by 0x4CF54A5: H5O__copy_header_real (H5Ocopy.c:870)
==41230==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==41230==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==41230==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==41230==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==41230==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==41230==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==41230==    by 0x410FFD: h5repack (h5repack.c:54)
==41230== 
==41230== LEAK SUMMARY:
==41230==    definitely lost: 88 bytes in 1 blocks
==41230==    indirectly lost: 0 bytes in 0 blocks
==41230==      possibly lost: 0 bytes in 0 blocks
==41230==    still reachable: 1,357,815 bytes in 3,206 blocks
==41230==                       of which reachable via heuristic:
==41230==                         length64           : 6,918 bytes in 33 blocks
==41230==                         newarray           : 72 bytes in 3 blocks
==41230==         suppressed: 0 bytes in 0 blocks
==41230== Reachable blocks (those to which a pointer was found) are not shown.
==41230== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==41230== 
==41230== ERROR SUMMARY: 2 errors from 2 contexts (suppressed: 0 from 0)
==41230== 
==41230== 1 errors in context 1 of 2:
==41230== Invalid read of size 8
==41230==    at 0x4F59568: H5T_get_size (H5T.c:4040)
==41230==    by 0x4D11828: H5O_fill_old_decode (H5Ofill.c:350)
==41230==    by 0x4D11828: H5O_fill_shared_decode (H5Oshared.h:82)
==41230==    by 0x4CF1E2E: H5O__copy_header_real (H5Ocopy.c:532)
==41230==    by 0x4CF08E1: H5O_copy_header_map (H5Ocopy.c:989)
==41230==    by 0x4C7B2C7: H5L__link_copy_file (H5L.c:3594)
==41230==    by 0x4D407D9: H5O__link_post_copy_file (H5Olink.c:784)
==41230==    by 0x4CF54A5: H5O__copy_header_real (H5Ocopy.c:870)
==41230==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==41230==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==41230==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==41230==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==41230==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==41230==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==41230==    by 0x410FFD: h5repack (h5repack.c:54)
==41230==    by 0x40931F: main (h5repack_main.c:769)
==41230==  Address 0x28 is not stack'd, malloc'd or (recently) free'd
==41230== 
==41230== ERROR SUMMARY: 2 errors from 2 contexts (suppressed: 0 from 0)
Segmentation fault





```
---
