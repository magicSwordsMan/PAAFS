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
valgrind -v --tool=memcheck --leak-check=full ./h5repack Fuzzout/crashes/id:000036,sig:11,src:000081,op:flip1,pos:1540 test
==63798== Memcheck, a memory error detector
==63798== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==63798== Using Valgrind-3.14.0-353a3587bb-20181007X and LibVEX; rerun with -h for copyright info
==63798== Command: ./h5repack Fuzzout/crashes/id:000036,sig:11,src:000081,op:flip1,pos:1540 test
==63798== 
--63798-- Valgrind options:
--63798--    -v
--63798--    --tool=memcheck
--63798--    --leak-check=full
--63798-- Contents of /proc/version:
--63798--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--63798-- 
--63798-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--63798-- Page sizes: currently 4096, max supported 4096
--63798-- Valgrind library directory: /usr/lib/x86_64-linux-gnu/valgrind
--63798-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--63798-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.27.so
--63798--   Considering /usr/lib/debug/.build-id/fa/01a234506568b77ad2d1a6da398e45586c550b.debug ..
--63798--   .. build-id is valid
--63798-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/memcheck-amd64-linux
--63798--   Considering /usr/lib/debug/.build-id/93/5efea22a69d45c080fd7ebab50cfe06d56e7af.debug ..
--63798--   .. build-id is valid
--63798--    object doesn't have a dynamic symbol table
--63798-- Scheduler: using generic scheduler lock implementation.
--63798-- Reading suppressions file: /usr/lib/x86_64-linux-gnu/valgrind/default.supp
==63798== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-63798-by-root-on-???
==63798== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-63798-by-root-on-???
==63798== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-63798-by-root-on-???
==63798== 
==63798== TO CONTROL THIS PROCESS USING vgdb (which you probably
==63798== don't want to do, unless you know exactly what you're doing,
==63798== or are doing some strange experiment):
==63798==   /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=63798 ...command...
==63798== 
==63798== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==63798==   /path/to/gdb ./h5repack
==63798== and then give GDB the following command
==63798==   target remote | /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=63798
==63798== --pid is optional if only one valgrind process is running
==63798== 
--63798-- REDIR: 0x401e290 (ld-linux-x86-64.so.2:strlen) redirected to 0x580c97f2 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--63798-- REDIR: 0x401e070 (ld-linux-x86-64.so.2:index) redirected to 0x580c980c (vgPlain_amd64_linux_REDIR_FOR_index)
--63798-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_core-amd64-linux.so
--63798--   Considering /usr/lib/debug/.build-id/3d/5115a2ef08a4077609b25d33f892f9260b8b5b.debug ..
--63798--   .. build-id is valid
--63798-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_memcheck-amd64-linux.so
--63798--   Considering /usr/lib/debug/.build-id/19/fb020e170903e05352b43e84af203f8f9ed2d8.debug ..
--63798--   .. build-id is valid
==63798== WARNING: new redirection conflicts with existing -- ignoring it
--63798--     old: 0x0401e290 (strlen              ) R-> (0000.0) 0x580c97f2 vgPlain_amd64_linux_REDIR_FOR_strlen
--63798--     new: 0x0401e290 (strlen              ) R-> (2007.0) 0x04838d80 strlen
--63798-- REDIR: 0x401aab0 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839e40 (strcmp)
--63798-- REDIR: 0x401e7d0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d860 (mempcpy)
--63798-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--63798-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--63798--    object doesn't have a symbol table
--63798-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.27.so
--63798--   Considering /usr/lib/debug/.build-id/2b/51cce982e540854dd1995136601f770f127b05.debug ..
--63798--   .. build-id is valid
--63798-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.27.so
--63798--   Considering /usr/lib/debug/.build-id/b6/7df54e445705b0d3fc5fb78cee3c26357ecba3.debug ..
--63798--   .. build-id is valid
--63798-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.27.so
--63798--   Considering /usr/lib/debug/.build-id/e9/38fe6706abe362f6c3c7474373ccc626cf4805.debug ..
--63798--   .. build-id is valid
--63798-- REDIR: 0x57b6050 (libc.so.6:memmove) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b5280 (libc.so.6:strncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b6330 (libc.so.6:strcasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b4cd0 (libc.so.6:strcat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b52b0 (libc.so.6:rindex) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b7900 (libc.so.6:rawmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57d0e60 (libc.so.6:wmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b61c0 (libc.so.6:mempcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b5ff0 (libc.so.6:bcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b5240 (libc.so.6:strncmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b4d40 (libc.so.6:strcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b6120 (libc.so.6:memset) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57cfb60 (libc.so.6:wcschr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b51e0 (libc.so.6:strnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b4db0 (libc.so.6:strcspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b6380 (libc.so.6:strncasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b4d80 (libc.so.6:strcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b64c0 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57d20c0 (libc.so.6:wcsnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b52e0 (libc.so.6:strpbrk) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b4d00 (libc.so.6:index) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b51b0 (libc.so.6:strlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57bc1b0 (libc.so.6:memrchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b63d0 (libc.so.6:strcasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b5fc0 (libc.so.6:memchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57d0920 (libc.so.6:wcslen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b5590 (libc.so.6:strspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b6300 (libc.so.6:stpncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b62d0 (libc.so.6:stpcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b7930 (libc.so.6:strchrnul) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57b6420 (libc.so.6:strncasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x5888700 (libc.so.6:__strrchr_avx2) redirected to 0x4838790 (rindex)
--63798-- REDIR: 0x58888d0 (libc.so.6:__strlen_avx2) redirected to 0x4838c60 (strlen)
--63798-- REDIR: 0x5889290 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c790 (memset)
--63798-- REDIR: 0x57b15c0 (libc.so.6:malloc) redirected to 0x4835710 (malloc)
--63798-- REDIR: 0x5888510 (libc.so.6:__strchrnul_avx2) redirected to 0x483d390 (strchrnul)
--63798-- REDIR: 0x5875c90 (libc.so.6:__strcpy_ssse3) redirected to 0x4838db0 (strcpy)
--63798-- REDIR: 0x57b1d60 (libc.so.6:realloc) redirected to 0x4837d00 (realloc)
--63798-- REDIR: 0x5888e10 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c8a0 (memmove)
--63798-- REDIR: 0x57b1c50 (libc.so.6:free) redirected to 0x4836940 (free)
--63798-- REDIR: 0x5877440 (libc.so.6:__strncpy_ssse3) redirected to 0x4838f50 (strncpy)
--63798-- REDIR: 0x58640a0 (libc.so.6:__strcmp_ssse3) redirected to 0x4839d00 (strcmp)
--63798-- REDIR: 0x5884ee0 (libc.so.6:__memcmp_avx2_movbe) redirected to 0x483c060 (bcmp)
--63798-- REDIR: 0x57b22a0 (libc.so.6:calloc) redirected to 0x4837ab0 (calloc)
--63798-- REDIR: 0x57b5210 (libc.so.6:strncat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--63798-- REDIR: 0x57c70f0 (libc.so.6:__strncat_ssse3) redirected to 0x4838b00 (strncat)
--63798-- REDIR: 0x58843b0 (libc.so.6:__strcspn_sse42) redirected to 0x483dc00 (strcspn)
--63798-- REDIR: 0x58882e0 (libc.so.6:__strchr_avx2) redirected to 0x4838910 (index)
--63798-- REDIR: 0x5888df0 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483d4a0 (mempcpy)
==63798== Invalid read of size 4
==63798==    at 0x4F41060: H5T_close_real (H5T.c:3684)
==63798==    by 0x4A286E8: H5O__dset_free_copy_file_udata (H5Doh.c:150)
==63798==    by 0x4CF6C5D: H5O__copy_header_real (H5Ocopy.c:931)
==63798==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==63798==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==63798==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==63798==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==63798==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==63798==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==63798==    by 0x410FFD: h5repack (h5repack.c:54)
==63798==    by 0x40931F: main (h5repack_main.c:769)
==63798==  Address 0x8 is not stack'd, malloc'd or (recently) free'd
==63798== 
==63798== 
==63798== Process terminating with default action of signal 11 (SIGSEGV)
==63798==  Access not within mapped region at address 0x8
==63798==    at 0x4F41060: H5T_close_real (H5T.c:3684)
==63798==    by 0x4A286E8: H5O__dset_free_copy_file_udata (H5Doh.c:150)
==63798==    by 0x4CF6C5D: H5O__copy_header_real (H5Ocopy.c:931)
==63798==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==63798==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==63798==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==63798==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==63798==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==63798==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==63798==    by 0x410FFD: h5repack (h5repack.c:54)
==63798==    by 0x40931F: main (h5repack_main.c:769)
==63798==  If you believe this happened as a result of a stack
==63798==  overflow in your program's main thread (unlikely but
==63798==  possible), you can try to increase the size of the
==63798==  main thread stack using the --main-stacksize= flag.
==63798==  The main thread stack size used in this run was 8388608.
==63798== 
==63798== HEAP SUMMARY:
==63798==     in use at exit: 1,369,185 bytes in 3,277 blocks
==63798==   total heap usage: 3,471 allocs, 194 frees, 2,457,227 bytes allocated
==63798== 
==63798== Searching for pointers to 3,277 not-freed blocks
==63798== Checked 1,469,544 bytes
==63798== 
==63798== 104 (80 direct, 24 indirect) bytes in 1 blocks are definitely lost in loss record 2,188 of 2,711
==63798==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==63798==    by 0x4B4EA43: H5FL_malloc (H5FL.c:243)
==63798==    by 0x4B4EA43: H5FL_reg_malloc (H5FL.c:441)
==63798==    by 0x4B4EE83: H5FL_reg_calloc (H5FL.c:498)
==63798==    by 0x4D5BBDF: H5O_sdspace_pre_copy_file (H5Osdspace.c:469)
==63798==    by 0x4CF214D: H5O__copy_header_real (H5Ocopy.c:541)
==63798==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==63798==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==63798==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==63798==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==63798==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==63798==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==63798==    by 0x410FFD: h5repack (h5repack.c:54)
==63798==    by 0x40931F: main (h5repack_main.c:769)
==63798== 
==63798== LEAK SUMMARY:
==63798==    definitely lost: 80 bytes in 1 blocks
==63798==    indirectly lost: 24 bytes in 1 blocks
==63798==      possibly lost: 0 bytes in 0 blocks
==63798==    still reachable: 1,369,081 bytes in 3,275 blocks
==63798==                       of which reachable via heuristic:
==63798==                         length64           : 6,270 bytes in 33 blocks
==63798==                         newarray           : 96 bytes in 5 blocks
==63798==         suppressed: 0 bytes in 0 blocks
==63798== Reachable blocks (those to which a pointer was found) are not shown.
==63798== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==63798== 
==63798== ERROR SUMMARY: 2 errors from 2 contexts (suppressed: 0 from 0)
==63798== 
==63798== 1 errors in context 1 of 2:
==63798== Invalid read of size 4
==63798==    at 0x4F41060: H5T_close_real (H5T.c:3684)
==63798==    by 0x4A286E8: H5O__dset_free_copy_file_udata (H5Doh.c:150)
==63798==    by 0x4CF6C5D: H5O__copy_header_real (H5Ocopy.c:931)
==63798==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==63798==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==63798==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==63798==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==63798==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==63798==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==63798==    by 0x410FFD: h5repack (h5repack.c:54)
==63798==    by 0x40931F: main (h5repack_main.c:769)
==63798==  Address 0x8 is not stack'd, malloc'd or (recently) free'd
==63798== 
==63798== ERROR SUMMARY: 2 errors from 2 contexts (suppressed: 0 from 0)
Segmentation fault


```
---
