## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by godlovevampire@gmail.com, please send email to godlovevampire@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5O__pline_decode_invalid-read-memory-access

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack Fuzzout/crashes/H5O__pline_decode_invalid-read-memory-access test
==41153== Memcheck, a memory error detector
==41153== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==41153== Using Valgrind-3.14.0-353a3587bb-20181007X and LibVEX; rerun with -h for copyright info
==41153== Command: ./h5repack Fuzzout/crashes/H5O__pline_decode_invalid-read-memory-access test
==41153== 
--41153-- Valgrind options:
--41153--    -v
--41153--    --tool=memcheck
--41153--    --leak-check=full
--41153-- Contents of /proc/version:
--41153--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--41153-- 
--41153-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--41153-- Page sizes: currently 4096, max supported 4096
--41153-- Valgrind library directory: /usr/lib/x86_64-linux-gnu/valgrind
--41153-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--41153-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.27.so
--41153--   Considering /usr/lib/debug/.build-id/fa/01a234506568b77ad2d1a6da398e45586c550b.debug ..
--41153--   .. build-id is valid
--41153-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/memcheck-amd64-linux
--41153--   Considering /usr/lib/debug/.build-id/93/5efea22a69d45c080fd7ebab50cfe06d56e7af.debug ..
--41153--   .. build-id is valid
--41153--    object doesn't have a dynamic symbol table
--41153-- Scheduler: using generic scheduler lock implementation.
--41153-- Reading suppressions file: /usr/lib/x86_64-linux-gnu/valgrind/default.supp
==41153== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-41153-by-root-on-???
==41153== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-41153-by-root-on-???
==41153== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-41153-by-root-on-???
==41153== 
==41153== TO CONTROL THIS PROCESS USING vgdb (which you probably
==41153== don't want to do, unless you know exactly what you're doing,
==41153== or are doing some strange experiment):
==41153==   /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=41153 ...command...
==41153== 
==41153== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==41153==   /path/to/gdb ./h5repack
==41153== and then give GDB the following command
==41153==   target remote | /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=41153
==41153== --pid is optional if only one valgrind process is running
==41153== 
--41153-- REDIR: 0x401e290 (ld-linux-x86-64.so.2:strlen) redirected to 0x580c97f2 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--41153-- REDIR: 0x401e070 (ld-linux-x86-64.so.2:index) redirected to 0x580c980c (vgPlain_amd64_linux_REDIR_FOR_index)
--41153-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_core-amd64-linux.so
--41153--   Considering /usr/lib/debug/.build-id/3d/5115a2ef08a4077609b25d33f892f9260b8b5b.debug ..
--41153--   .. build-id is valid
--41153-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_memcheck-amd64-linux.so
--41153--   Considering /usr/lib/debug/.build-id/19/fb020e170903e05352b43e84af203f8f9ed2d8.debug ..
--41153--   .. build-id is valid
==41153== WARNING: new redirection conflicts with existing -- ignoring it
--41153--     old: 0x0401e290 (strlen              ) R-> (0000.0) 0x580c97f2 vgPlain_amd64_linux_REDIR_FOR_strlen
--41153--     new: 0x0401e290 (strlen              ) R-> (2007.0) 0x04838d80 strlen
--41153-- REDIR: 0x401aab0 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839e40 (strcmp)
--41153-- REDIR: 0x401e7d0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d860 (mempcpy)
--41153-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--41153-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--41153--    object doesn't have a symbol table
--41153-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.27.so
--41153--   Considering /usr/lib/debug/.build-id/2b/51cce982e540854dd1995136601f770f127b05.debug ..
--41153--   .. build-id is valid
--41153-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.27.so
--41153--   Considering /usr/lib/debug/.build-id/b6/7df54e445705b0d3fc5fb78cee3c26357ecba3.debug ..
--41153--   .. build-id is valid
--41153-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.27.so
--41153--   Considering /usr/lib/debug/.build-id/e9/38fe6706abe362f6c3c7474373ccc626cf4805.debug ..
--41153--   .. build-id is valid
--41153-- REDIR: 0x57b6050 (libc.so.6:memmove) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b5280 (libc.so.6:strncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b6330 (libc.so.6:strcasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b4cd0 (libc.so.6:strcat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b52b0 (libc.so.6:rindex) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b7900 (libc.so.6:rawmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57d0e60 (libc.so.6:wmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b61c0 (libc.so.6:mempcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b5ff0 (libc.so.6:bcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b5240 (libc.so.6:strncmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b4d40 (libc.so.6:strcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b6120 (libc.so.6:memset) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57cfb60 (libc.so.6:wcschr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b51e0 (libc.so.6:strnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b4db0 (libc.so.6:strcspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b6380 (libc.so.6:strncasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b4d80 (libc.so.6:strcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b64c0 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57d20c0 (libc.so.6:wcsnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b52e0 (libc.so.6:strpbrk) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b4d00 (libc.so.6:index) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b51b0 (libc.so.6:strlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57bc1b0 (libc.so.6:memrchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b63d0 (libc.so.6:strcasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b5fc0 (libc.so.6:memchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57d0920 (libc.so.6:wcslen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b5590 (libc.so.6:strspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b6300 (libc.so.6:stpncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b62d0 (libc.so.6:stpcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b7930 (libc.so.6:strchrnul) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57b6420 (libc.so.6:strncasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x5888700 (libc.so.6:__strrchr_avx2) redirected to 0x4838790 (rindex)
--41153-- REDIR: 0x58888d0 (libc.so.6:__strlen_avx2) redirected to 0x4838c60 (strlen)
--41153-- REDIR: 0x5889290 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c790 (memset)
--41153-- REDIR: 0x57b15c0 (libc.so.6:malloc) redirected to 0x4835710 (malloc)
--41153-- REDIR: 0x5888510 (libc.so.6:__strchrnul_avx2) redirected to 0x483d390 (strchrnul)
--41153-- REDIR: 0x5875c90 (libc.so.6:__strcpy_ssse3) redirected to 0x4838db0 (strcpy)
--41153-- REDIR: 0x57b1d60 (libc.so.6:realloc) redirected to 0x4837d00 (realloc)
--41153-- REDIR: 0x5888e10 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c8a0 (memmove)
--41153-- REDIR: 0x57b1c50 (libc.so.6:free) redirected to 0x4836940 (free)
--41153-- REDIR: 0x5877440 (libc.so.6:__strncpy_ssse3) redirected to 0x4838f50 (strncpy)
--41153-- REDIR: 0x58640a0 (libc.so.6:__strcmp_ssse3) redirected to 0x4839d00 (strcmp)
--41153-- REDIR: 0x5884ee0 (libc.so.6:__memcmp_avx2_movbe) redirected to 0x483c060 (bcmp)
--41153-- REDIR: 0x57b22a0 (libc.so.6:calloc) redirected to 0x4837ab0 (calloc)
--41153-- REDIR: 0x57b5210 (libc.so.6:strncat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--41153-- REDIR: 0x57c70f0 (libc.so.6:__strncat_ssse3) redirected to 0x4838b00 (strncat)
--41153-- REDIR: 0x58843b0 (libc.so.6:__strcspn_sse42) redirected to 0x483dc00 (strcspn)
==41153== Invalid read of size 1
==41153==    at 0x4D52ABC: H5O__pline_decode (H5Opline.c:166)
==41153==    by 0x4D52ABC: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8d8 is 0 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== Invalid read of size 1
==41153==    at 0x4D52AC3: H5O__pline_decode (H5Opline.c:166)
==41153==    by 0x4D52AC3: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8d9 is 1 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== Invalid read of size 1
==41153==    at 0x4D52B9C: H5O__pline_decode (H5Opline.c:172)
==41153==    by 0x4D52B9C: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8da is 2 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== Invalid read of size 1
==41153==    at 0x4D52BA0: H5O__pline_decode (H5Opline.c:172)
==41153==    by 0x4D52BA0: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8db is 3 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== Invalid read of size 1
==41153==    at 0x4D52C68: H5O__pline_decode (H5Opline.c:178)
==41153==    by 0x4D52C68: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8dc is 4 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== Invalid read of size 1
==41153==    at 0x4D52C70: H5O__pline_decode (H5Opline.c:178)
==41153==    by 0x4D52C70: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8dd is 5 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== Invalid read of size 1
==41153==    at 0x4D52C7E: H5O__pline_decode (H5Opline.c:181)
==41153==    by 0x4D52C7E: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8de is 6 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== Invalid read of size 1
==41153==    at 0x4D52C87: H5O__pline_decode (H5Opline.c:181)
==41153==    by 0x4D52C87: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8df is 7 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
--41153-- REDIR: 0x58882e0 (libc.so.6:__strchr_avx2) redirected to 0x4838910 (index)
==41153== Invalid read of size 2
==41153==    at 0x483C9E7: memmove (vg_replace_strmem.c:1270)
==41153==    by 0x4D325FD: H5O__layout_decode (H5Olayout.c:213)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A258AA: H5D__layout_oh_read (H5Dlayout.c:634)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6c7d8 is 0 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== Invalid read of size 2
==41153==    at 0x483C9D8: memmove (vg_replace_strmem.c:1270)
==41153==    by 0x4D325FD: H5O__layout_decode (H5Olayout.c:213)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A258AA: H5D__layout_oh_read (H5Dlayout.c:634)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6c7de is 6 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
--41153-- REDIR: 0x5888df0 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483d4a0 (mempcpy)
==41153== Invalid write of size 2
==41153==    at 0x483C9DB: memmove (vg_replace_strmem.c:1270)
==41153==    by 0x4D368F3: H5O__layout_encode (H5Olayout.c:580)
==41153==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==41153==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==41153==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==41153==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==41153==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==41153==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==41153==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==41153==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==41153==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==41153==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==41153==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==41153==  Address 0x5ac07b8 is 0 bytes after a block of size 136 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==41153==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==41153==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==41153==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==41153==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==41153==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==41153==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==41153==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153== 
==41153== Invalid read of size 8
==41153==    at 0x4B55048: H5FL__fac_gc_list (H5FL.c:2260)
==41153==    by 0x4B55048: H5FL_fac_term (H5FL.c:2352)
==41153==    by 0x4EBAFD7: H5SL_term_package (H5SL.c:658)
==41153==    by 0x489417C: H5_term_library (H5.c:356)
==41153==    by 0x489789D: H5close (H5.c:875)
==41153==    by 0x43BABA: h5tools_close (h5tools.c:179)
==41153==    by 0x40CF8F: leave (h5repack_main.c:245)
==41153==    by 0x4096E1: main (h5repack_main.c:775)
==41153==  Address 0x50 is not stack'd, malloc'd or (recently) free'd
==41153== 
==41153== 
==41153== Process terminating with default action of signal 11 (SIGSEGV)
==41153==  Access not within mapped region at address 0x50
==41153==    at 0x4B55048: H5FL__fac_gc_list (H5FL.c:2260)
==41153==    by 0x4B55048: H5FL_fac_term (H5FL.c:2352)
==41153==    by 0x4EBAFD7: H5SL_term_package (H5SL.c:658)
==41153==    by 0x489417C: H5_term_library (H5.c:356)
==41153==    by 0x489789D: H5close (H5.c:875)
==41153==    by 0x43BABA: h5tools_close (h5tools.c:179)
==41153==    by 0x40CF8F: leave (h5repack_main.c:245)
==41153==    by 0x4096E1: main (h5repack_main.c:775)
==41153==  If you believe this happened as a result of a stack
==41153==  overflow in your program's main thread (unlikely but
==41153==  possible), you can try to increase the size of the
==41153==  main thread stack using the --main-stacksize= flag.
==41153==  The main thread stack size used in this run was 8388608.
==41153== 
==41153== HEAP SUMMARY:
==41153==     in use at exit: 198,060 bytes in 2,161 blocks
==41153==   total heap usage: 3,751 allocs, 1,590 frees, 1,969,364 bytes allocated
==41153== 
==41153== Searching for pointers to 2,161 not-freed blocks
==41153== Checked 319,056 bytes
==41153== 
==41153== LEAK SUMMARY:
==41153==    definitely lost: 0 bytes in 0 blocks
==41153==    indirectly lost: 0 bytes in 0 blocks
==41153==      possibly lost: 0 bytes in 0 blocks
==41153==    still reachable: 198,060 bytes in 2,161 blocks
==41153==         suppressed: 0 bytes in 0 blocks
==41153== Reachable blocks (those to which a pointer was found) are not shown.
==41153== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==41153== 
==41153== ERROR SUMMARY: 86436 errors from 12 contexts (suppressed: 0 from 0)
==41153== 
==41153== 1 errors in context 1 of 12:
==41153== Invalid read of size 8
==41153==    at 0x4B55048: H5FL__fac_gc_list (H5FL.c:2260)
==41153==    by 0x4B55048: H5FL_fac_term (H5FL.c:2352)
==41153==    by 0x4EBAFD7: H5SL_term_package (H5SL.c:658)
==41153==    by 0x489417C: H5_term_library (H5.c:356)
==41153==    by 0x489789D: H5close (H5.c:875)
==41153==    by 0x43BABA: h5tools_close (h5tools.c:179)
==41153==    by 0x40CF8F: leave (h5repack_main.c:245)
==41153==    by 0x4096E1: main (h5repack_main.c:775)
==41153==  Address 0x50 is not stack'd, malloc'd or (recently) free'd
==41153== 
==41153== 
==41153== 2 errors in context 2 of 12:
==41153== Invalid read of size 1
==41153==    at 0x4D52C87: H5O__pline_decode (H5Opline.c:181)
==41153==    by 0x4D52C87: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8df is 7 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== 
==41153== 2 errors in context 3 of 12:
==41153== Invalid read of size 1
==41153==    at 0x4D52C7E: H5O__pline_decode (H5Opline.c:181)
==41153==    by 0x4D52C7E: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8de is 6 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== 
==41153== 2 errors in context 4 of 12:
==41153== Invalid read of size 1
==41153==    at 0x4D52C70: H5O__pline_decode (H5Opline.c:178)
==41153==    by 0x4D52C70: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8dd is 5 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== 
==41153== 2 errors in context 5 of 12:
==41153== Invalid read of size 1
==41153==    at 0x4D52C68: H5O__pline_decode (H5Opline.c:178)
==41153==    by 0x4D52C68: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8dc is 4 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== 
==41153== 2 errors in context 6 of 12:
==41153== Invalid read of size 1
==41153==    at 0x4D52BA0: H5O__pline_decode (H5Opline.c:172)
==41153==    by 0x4D52BA0: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8db is 3 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== 
==41153== 2 errors in context 7 of 12:
==41153== Invalid read of size 1
==41153==    at 0x4D52B9C: H5O__pline_decode (H5Opline.c:172)
==41153==    by 0x4D52B9C: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8da is 2 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== 
==41153== 2 errors in context 8 of 12:
==41153== Invalid read of size 1
==41153==    at 0x4D52AC3: H5O__pline_decode (H5Opline.c:166)
==41153==    by 0x4D52AC3: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8d9 is 1 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== 
==41153== 2 errors in context 9 of 12:
==41153== Invalid read of size 1
==41153==    at 0x4D52ABC: H5O__pline_decode (H5Opline.c:166)
==41153==    by 0x4D52ABC: H5O_pline_shared_decode (H5Oshared.h:82)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A257C1: H5D__layout_oh_read (H5Dlayout.c:620)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6b8d8 is 0 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== 
==41153== 5316 errors in context 10 of 12:
==41153== Invalid read of size 2
==41153==    at 0x483C9D8: memmove (vg_replace_strmem.c:1270)
==41153==    by 0x4D325FD: H5O__layout_decode (H5Olayout.c:213)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A258AA: H5D__layout_oh_read (H5Dlayout.c:634)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6c7de is 6 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== 
==41153== 15941 errors in context 11 of 12:
==41153== Invalid read of size 2
==41153==    at 0x483C9E7: memmove (vg_replace_strmem.c:1270)
==41153==    by 0x4D325FD: H5O__layout_decode (H5Olayout.c:213)
==41153==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==41153==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==41153==    by 0x4A258AA: H5D__layout_oh_read (H5Dlayout.c:634)
==41153==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==41153==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==41153==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==41153==    by 0x4996485: H5Dopen2 (H5D.c:291)
==41153==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==41153==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153==  Address 0x5a6c7d8 is 0 bytes after a block of size 280 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==41153==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==41153==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==41153==    by 0x495AE26: H5C_protect (H5C.c:2357)
==41153==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==41153==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==41153==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==41153==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==41153==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==41153==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==41153==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==41153== 
==41153== 
==41153== 65162 errors in context 12 of 12:
==41153== Invalid write of size 2
==41153==    at 0x483C9DB: memmove (vg_replace_strmem.c:1270)
==41153==    by 0x4D368F3: H5O__layout_encode (H5Olayout.c:580)
==41153==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==41153==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==41153==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==41153==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==41153==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==41153==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==41153==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==41153==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==41153==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==41153==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==41153==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==41153==  Address 0x5ac07b8 is 0 bytes after a block of size 136 alloc'd
==41153==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==41153==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==41153==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==41153==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==41153==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==41153==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==41153==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==41153==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==41153==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==41153==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==41153==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==41153==    by 0x410FFD: h5repack (h5repack.c:54)
==41153==    by 0x40931F: main (h5repack_main.c:769)
==41153== 
==41153== ERROR SUMMARY: 86436 errors from 12 contexts (suppressed: 0 from 0)
Segmentation fault



```
---
