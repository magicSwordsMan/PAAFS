## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by godlovevampire@gmail.com, please send email to godlovevampire@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5F__accum_read_invalid-read-memory-access

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack Fuzzout/crashes/H5F__accum_read_invalid-read-memory-access test
==114564== Memcheck, a memory error detector
==114564== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==114564== Using Valgrind-3.14.0-353a3587bb-20181007X and LibVEX; rerun with -h for copyright info
==114564== Command: ./h5repack Fuzzout/crashes/id:000013,sig:11,src:000000,op:havoc,rep:32 test
==114564== 
--114564-- Valgrind options:
--114564--    -v
--114564--    --tool=memcheck
--114564--    --leak-check=full
--114564-- Contents of /proc/version:
--114564--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--114564-- 
--114564-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--114564-- Page sizes: currently 4096, max supported 4096
--114564-- Valgrind library directory: /usr/lib/x86_64-linux-gnu/valgrind
--114564-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--114564-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.27.so
--114564--   Considering /usr/lib/debug/.build-id/fa/01a234506568b77ad2d1a6da398e45586c550b.debug ..
--114564--   .. build-id is valid
--114564-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/memcheck-amd64-linux
--114564--   Considering /usr/lib/debug/.build-id/93/5efea22a69d45c080fd7ebab50cfe06d56e7af.debug ..
--114564--   .. build-id is valid
--114564--    object doesn't have a dynamic symbol table
--114564-- Scheduler: using generic scheduler lock implementation.
--114564-- Reading suppressions file: /usr/lib/x86_64-linux-gnu/valgrind/default.supp
==114564== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-114564-by-root-on-???
==114564== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-114564-by-root-on-???
==114564== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-114564-by-root-on-???
==114564== 
==114564== TO CONTROL THIS PROCESS USING vgdb (which you probably
==114564== don't want to do, unless you know exactly what you're doing,
==114564== or are doing some strange experiment):
==114564==   /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=114564 ...command...
==114564== 
==114564== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==114564==   /path/to/gdb ./h5repack
==114564== and then give GDB the following command
==114564==   target remote | /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=114564
==114564== --pid is optional if only one valgrind process is running
==114564== 
--114564-- REDIR: 0x401e290 (ld-linux-x86-64.so.2:strlen) redirected to 0x580c97f2 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--114564-- REDIR: 0x401e070 (ld-linux-x86-64.so.2:index) redirected to 0x580c980c (vgPlain_amd64_linux_REDIR_FOR_index)
--114564-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_core-amd64-linux.so
--114564--   Considering /usr/lib/debug/.build-id/3d/5115a2ef08a4077609b25d33f892f9260b8b5b.debug ..
--114564--   .. build-id is valid
--114564-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_memcheck-amd64-linux.so
--114564--   Considering /usr/lib/debug/.build-id/19/fb020e170903e05352b43e84af203f8f9ed2d8.debug ..
--114564--   .. build-id is valid
==114564== WARNING: new redirection conflicts with existing -- ignoring it
--114564--     old: 0x0401e290 (strlen              ) R-> (0000.0) 0x580c97f2 vgPlain_amd64_linux_REDIR_FOR_strlen
--114564--     new: 0x0401e290 (strlen              ) R-> (2007.0) 0x04838d80 strlen
--114564-- REDIR: 0x401aab0 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839e40 (strcmp)
--114564-- REDIR: 0x401e7d0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d860 (mempcpy)
--114564-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--114564-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--114564--    object doesn't have a symbol table
--114564-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.27.so
--114564--   Considering /usr/lib/debug/.build-id/2b/51cce982e540854dd1995136601f770f127b05.debug ..
--114564--   .. build-id is valid
--114564-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.27.so
--114564--   Considering /usr/lib/debug/.build-id/b6/7df54e445705b0d3fc5fb78cee3c26357ecba3.debug ..
--114564--   .. build-id is valid
--114564-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.27.so
--114564--   Considering /usr/lib/debug/.build-id/e9/38fe6706abe362f6c3c7474373ccc626cf4805.debug ..
--114564--   .. build-id is valid
--114564-- REDIR: 0x57b6050 (libc.so.6:memmove) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b5280 (libc.so.6:strncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b6330 (libc.so.6:strcasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b4cd0 (libc.so.6:strcat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b52b0 (libc.so.6:rindex) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b7900 (libc.so.6:rawmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57d0e60 (libc.so.6:wmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b61c0 (libc.so.6:mempcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b5ff0 (libc.so.6:bcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b5240 (libc.so.6:strncmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b4d40 (libc.so.6:strcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b6120 (libc.so.6:memset) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57cfb60 (libc.so.6:wcschr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b51e0 (libc.so.6:strnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b4db0 (libc.so.6:strcspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b6380 (libc.so.6:strncasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b4d80 (libc.so.6:strcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b64c0 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57d20c0 (libc.so.6:wcsnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b52e0 (libc.so.6:strpbrk) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b4d00 (libc.so.6:index) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b51b0 (libc.so.6:strlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57bc1b0 (libc.so.6:memrchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b63d0 (libc.so.6:strcasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b5fc0 (libc.so.6:memchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57d0920 (libc.so.6:wcslen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b5590 (libc.so.6:strspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b6300 (libc.so.6:stpncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b62d0 (libc.so.6:stpcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b7930 (libc.so.6:strchrnul) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57b6420 (libc.so.6:strncasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x5888700 (libc.so.6:__strrchr_avx2) redirected to 0x4838790 (rindex)
--114564-- REDIR: 0x58888d0 (libc.so.6:__strlen_avx2) redirected to 0x4838c60 (strlen)
--114564-- REDIR: 0x5889290 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c790 (memset)
--114564-- REDIR: 0x57b15c0 (libc.so.6:malloc) redirected to 0x4835710 (malloc)
--114564-- REDIR: 0x5888510 (libc.so.6:__strchrnul_avx2) redirected to 0x483d390 (strchrnul)
--114564-- REDIR: 0x5875c90 (libc.so.6:__strcpy_ssse3) redirected to 0x4838db0 (strcpy)
--114564-- REDIR: 0x57b1d60 (libc.so.6:realloc) redirected to 0x4837d00 (realloc)
--114564-- REDIR: 0x5888e10 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c8a0 (memmove)
--114564-- REDIR: 0x57b1c50 (libc.so.6:free) redirected to 0x4836940 (free)
--114564-- REDIR: 0x5877440 (libc.so.6:__strncpy_ssse3) redirected to 0x4838f50 (strncpy)
--114564-- REDIR: 0x58640a0 (libc.so.6:__strcmp_ssse3) redirected to 0x4839d00 (strcmp)
--114564-- REDIR: 0x5884ee0 (libc.so.6:__memcmp_avx2_movbe) redirected to 0x483c060 (bcmp)
--114564-- REDIR: 0x57b22a0 (libc.so.6:calloc) redirected to 0x4837ab0 (calloc)
--114564-- REDIR: 0x57b5210 (libc.so.6:strncat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--114564-- REDIR: 0x57c70f0 (libc.so.6:__strncat_ssse3) redirected to 0x4838b00 (strncat)
--114564-- REDIR: 0x58843b0 (libc.so.6:__strcspn_sse42) redirected to 0x483dc00 (strcspn)
==114564== Invalid read of size 8
==114564==    at 0x483C924: memmove (vg_replace_strmem.c:1270)
==114564==    by 0x4AA75C2: H5F__accum_read (H5Faccum.c:201)
==114564==    by 0x4E2FBEC: H5PB_read (H5PB.c:731)
==114564==    by 0x4AD181E: H5F_block_read (H5Fio.c:117)
==114564==    by 0x495A053: H5C_load_entry (H5C.c:6620)
==114564==    by 0x495A053: H5C_protect (H5C.c:2357)
==114564==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==114564==    by 0x4C45F1D: H5HL_protect (H5HL.c:348)
==114564==    by 0x4BCAEA1: H5G__stab_iterate (H5Gstab.c:540)
==114564==    by 0x4BBF384: H5G__obj_iterate (H5Gobj.c:697)
==114564==    by 0x4BA13CF: H5G_visit (H5Gint.c:1220)
==114564==    by 0x4C753A2: H5L__visit (H5L.c:3480)
==114564==    by 0x4C753A2: H5Lvisit_by_name (H5L.c:1312)
==114564==    by 0x478390: traverse (h5trav.c:291)
==114564==  Address 0x0 is not stack'd, malloc'd or (recently) free'd
==114564== 
==114564== 
==114564== Process terminating with default action of signal 11 (SIGSEGV)
==114564==  Access not within mapped region at address 0x0
==114564==    at 0x483C924: memmove (vg_replace_strmem.c:1270)
==114564==    by 0x4AA75C2: H5F__accum_read (H5Faccum.c:201)
==114564==    by 0x4E2FBEC: H5PB_read (H5PB.c:731)
==114564==    by 0x4AD181E: H5F_block_read (H5Fio.c:117)
==114564==    by 0x495A053: H5C_load_entry (H5C.c:6620)
==114564==    by 0x495A053: H5C_protect (H5C.c:2357)
==114564==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==114564==    by 0x4C45F1D: H5HL_protect (H5HL.c:348)
==114564==    by 0x4BCAEA1: H5G__stab_iterate (H5Gstab.c:540)
==114564==    by 0x4BBF384: H5G__obj_iterate (H5Gobj.c:697)
==114564==    by 0x4BA13CF: H5G_visit (H5Gint.c:1220)
==114564==    by 0x4C753A2: H5L__visit (H5L.c:3480)
==114564==    by 0x4C753A2: H5Lvisit_by_name (H5L.c:1312)
==114564==    by 0x478390: traverse (h5trav.c:291)
==114564==  If you believe this happened as a result of a stack
==114564==  overflow in your program's main thread (unlikely but
==114564==  possible), you can try to increase the size of the
==114564==  main thread stack using the --main-stacksize= flag.
==114564==  The main thread stack size used in this run was 8388608.
==114564== 
==114564== HEAP SUMMARY:
==114564==     in use at exit: 1,335,081 bytes in 3,070 blocks
==114564==   total heap usage: 3,114 allocs, 44 frees, 1,341,101 bytes allocated
==114564== 
==114564== Searching for pointers to 3,070 not-freed blocks
==114564== Checked 1,436,608 bytes
==114564== 
==114564== LEAK SUMMARY:
==114564==    definitely lost: 0 bytes in 0 blocks
==114564==    indirectly lost: 0 bytes in 0 blocks
==114564==      possibly lost: 0 bytes in 0 blocks
==114564==    still reachable: 1,335,081 bytes in 3,070 blocks
==114564==                       of which reachable via heuristic:
==114564==                         length64           : 3,000 bytes in 17 blocks
==114564==         suppressed: 0 bytes in 0 blocks
==114564== Reachable blocks (those to which a pointer was found) are not shown.
==114564== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==114564== 
==114564== ERROR SUMMARY: 1 errors from 1 contexts (suppressed: 0 from 0)
==114564== 
==114564== 1 errors in context 1 of 1:
==114564== Invalid read of size 8
==114564==    at 0x483C924: memmove (vg_replace_strmem.c:1270)
==114564==    by 0x4AA75C2: H5F__accum_read (H5Faccum.c:201)
==114564==    by 0x4E2FBEC: H5PB_read (H5PB.c:731)
==114564==    by 0x4AD181E: H5F_block_read (H5Fio.c:117)
==114564==    by 0x495A053: H5C_load_entry (H5C.c:6620)
==114564==    by 0x495A053: H5C_protect (H5C.c:2357)
==114564==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==114564==    by 0x4C45F1D: H5HL_protect (H5HL.c:348)
==114564==    by 0x4BCAEA1: H5G__stab_iterate (H5Gstab.c:540)
==114564==    by 0x4BBF384: H5G__obj_iterate (H5Gobj.c:697)
==114564==    by 0x4BA13CF: H5G_visit (H5Gint.c:1220)
==114564==    by 0x4C753A2: H5L__visit (H5L.c:3480)
==114564==    by 0x4C753A2: H5Lvisit_by_name (H5L.c:1312)
==114564==    by 0x478390: traverse (h5trav.c:291)
==114564==  Address 0x0 is not stack'd, malloc'd or (recently) free'd
==114564== 
==114564== ERROR SUMMARY: 1 errors from 1 contexts (suppressed: 0 from 0)
Segmentation fault




```
---
