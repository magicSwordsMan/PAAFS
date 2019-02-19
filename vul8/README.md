## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by godlovevampire@gmail.com, please send email to godlovevampire@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5MM_xstrdup_invalid-read-memory-access

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack Fuzzout/crashes/H5MM_xstrdup_invalid-read-memory-access test
==2397== Memcheck, a memory error detector
==2397== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==2397== Using Valgrind-3.14.0-353a3587bb-20181007X and LibVEX; rerun with -h for copyright info
==2397== Command: ./h5repack Fuzzout/crashes/H5MM_xstrdup_invalid-read-memory-access test
==2397== 
--2397-- Valgrind options:
--2397--    -v
--2397--    --tool=memcheck
--2397--    --leak-check=full
--2397-- Contents of /proc/version:
--2397--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--2397-- 
--2397-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--2397-- Page sizes: currently 4096, max supported 4096
--2397-- Valgrind library directory: /usr/lib/x86_64-linux-gnu/valgrind
--2397-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--2397-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.28.so
--2397--   Considering /usr/lib/debug/.build-id/dd/8026f43793facd0aa3924fb2dd6b0033b7b431.debug ..
--2397--   .. build-id is valid
--2397-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/memcheck-amd64-linux
--2397--   Considering /usr/lib/debug/.build-id/93/5efea22a69d45c080fd7ebab50cfe06d56e7af.debug ..
--2397--   .. build-id is valid
--2397--    object doesn't have a dynamic symbol table
--2397-- Scheduler: using generic scheduler lock implementation.
--2397-- Reading suppressions file: /usr/lib/x86_64-linux-gnu/valgrind/default.supp
==2397== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-2397-by-root-on-???
==2397== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-2397-by-root-on-???
==2397== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-2397-by-root-on-???
==2397== 
==2397== TO CONTROL THIS PROCESS USING vgdb (which you probably
==2397== don't want to do, unless you know exactly what you're doing,
==2397== or are doing some strange experiment):
==2397==   /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=2397 ...command...
==2397== 
==2397== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==2397==   /path/to/gdb ./h5repack
==2397== and then give GDB the following command
==2397==   target remote | /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=2397
==2397== --pid is optional if only one valgrind process is running
==2397== 
--2397-- REDIR: 0x401e350 (ld-linux-x86-64.so.2:strlen) redirected to 0x580c97f2 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--2397-- REDIR: 0x401e130 (ld-linux-x86-64.so.2:index) redirected to 0x580c980c (vgPlain_amd64_linux_REDIR_FOR_index)
--2397-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_core-amd64-linux.so
--2397--   Considering /usr/lib/debug/.build-id/3d/5115a2ef08a4077609b25d33f892f9260b8b5b.debug ..
--2397--   .. build-id is valid
--2397-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_memcheck-amd64-linux.so
--2397--   Considering /usr/lib/debug/.build-id/19/fb020e170903e05352b43e84af203f8f9ed2d8.debug ..
--2397--   .. build-id is valid
==2397== WARNING: new redirection conflicts with existing -- ignoring it
--2397--     old: 0x0401e350 (strlen              ) R-> (0000.0) 0x580c97f2 vgPlain_amd64_linux_REDIR_FOR_strlen
--2397--     new: 0x0401e350 (strlen              ) R-> (2007.0) 0x04838d80 strlen
--2397-- REDIR: 0x401ab70 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839e40 (strcmp)
--2397-- REDIR: 0x401e890 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d860 (mempcpy)
--2397-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--2397-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--2397--    object doesn't have a symbol table
--2397-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.28.so
--2397--   Considering /usr/lib/debug/.build-id/60/1c7068f7cbc26814db9cbca61b1a2c00f5d66d.debug ..
--2397--   .. build-id is valid
--2397-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.28.so
--2397--   Considering /usr/lib/debug/.build-id/86/be4b7815704459f8a32170db4266066980289f.debug ..
--2397--   .. build-id is valid
--2397-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.28.so
--2397--   Considering /usr/lib/debug/.build-id/cd/ae5bb84a51c364471bdd287dbe9df7d1d235f3.debug ..
--2397--   .. build-id is valid
--2397-- REDIR: 0x57a6210 (libc.so.6:memmove) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a5400 (libc.so.6:strncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a64f0 (libc.so.6:strcasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a4e30 (libc.so.6:strcat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a5430 (libc.so.6:rindex) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a7b20 (libc.so.6:rawmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57c04e0 (libc.so.6:wmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57bff80 (libc.so.6:wcscmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a6380 (libc.so.6:mempcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a61b0 (libc.so.6:bcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a53a0 (libc.so.6:strncmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a4ea0 (libc.so.6:strcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a62e0 (libc.so.6:memset) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57bff50 (libc.so.6:wcschr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a5340 (libc.so.6:strnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a4f30 (libc.so.6:strcspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a6540 (libc.so.6:strncasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a4f00 (libc.so.6:strcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a6680 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57c1780 (libc.so.6:wcsnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a5460 (libc.so.6:strpbrk) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a4e60 (libc.so.6:index) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a5310 (libc.so.6:strlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57ac530 (libc.so.6:memrchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a6590 (libc.so.6:strcasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a6180 (libc.so.6:memchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57c0060 (libc.so.6:wcslen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a5700 (libc.so.6:strspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a64c0 (libc.so.6:stpncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a6490 (libc.so.6:stpcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a7b50 (libc.so.6:strchrnul) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57a65e0 (libc.so.6:strncasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x5879440 (libc.so.6:__strrchr_avx2) redirected to 0x4838790 (rindex)
--2397-- REDIR: 0x5879610 (libc.so.6:__strlen_avx2) redirected to 0x4838c60 (strlen)
--2397-- REDIR: 0x5879fd0 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c790 (memset)
--2397-- REDIR: 0x57a1610 (libc.so.6:malloc) redirected to 0x4835710 (malloc)
--2397-- REDIR: 0x5879250 (libc.so.6:__strchrnul_avx2) redirected to 0x483d390 (strchrnul)
--2397-- REDIR: 0x57ba3b0 (libc.so.6:__strcpy_sse2_unaligned) redirected to 0x4838db0 (strcpy)
--2397-- REDIR: 0x57a1eb0 (libc.so.6:realloc) redirected to 0x4837d00 (realloc)
--2397-- REDIR: 0x5879b50 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c8a0 (memmove)
--2397-- REDIR: 0x57a1c60 (libc.so.6:free) redirected to 0x4836940 (free)
--2397-- REDIR: 0x57ba9e0 (libc.so.6:__strncpy_sse2_unaligned) redirected to 0x48392e0 (__strncpy_sse2_unaligned)
--2397-- REDIR: 0x5874b50 (libc.so.6:__strcmp_avx2) redirected to 0x4839d00 (strcmp)
--2397-- REDIR: 0x5875c20 (libc.so.6:__memcmp_avx2_movbe) redirected to 0x483c060 (bcmp)
--2397-- REDIR: 0x57a23e0 (libc.so.6:calloc) redirected to 0x4837ab0 (calloc)
--2397-- REDIR: 0x57a5370 (libc.so.6:strncat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2397-- REDIR: 0x57bdc90 (libc.so.6:__strncat_sse2_unaligned) redirected to 0x4838b00 (strncat)
--2397-- REDIR: 0x5874760 (libc.so.6:__strcspn_sse42) redirected to 0x483dc00 (strcspn)
==2397== Invalid read of size 1
==2397==    at 0x4838C62: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4CA8067: H5MM_xstrdup (H5MM.c:465)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==  Address 0x5a5e898 is 0 bytes after a block of size 280 alloc'd
==2397==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2397==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==2397==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==2397==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==2397==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==2397==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==2397==    by 0x495AE26: H5C_protect (H5C.c:2357)
==2397==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==2397==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==2397==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==2397==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==2397==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==2397==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==2397==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==2397== 
==2397== Invalid read of size 1
==2397==    at 0x57BA3B0: __strcpy_sse2_unaligned (strcpy-sse2-unaligned.S:47)
==2397==    by 0x4CA8105: H5MM_xstrdup (H5MM.c:467)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==  Address 0x5a5e898 is 0 bytes after a block of size 280 alloc'd
==2397==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2397==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==2397==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==2397==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==2397==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==2397==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==2397==    by 0x495AE26: H5C_protect (H5C.c:2357)
==2397==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==2397==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==2397==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==2397==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==2397==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==2397==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==2397==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==2397== 
==2397== Invalid read of size 1
==2397==    at 0x4838C62: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4D05912: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397==  Address 0x5a5e898 is 0 bytes after a block of size 280 alloc'd
==2397==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2397==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==2397==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==2397==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==2397==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==2397==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==2397==    by 0x495AE26: H5C_protect (H5C.c:2357)
==2397==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==2397==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==2397==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==2397==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==2397==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==2397==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==2397==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==2397== 
==2397== Invalid read of size 1
==2397==    at 0x4838C74: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4CA8067: H5MM_xstrdup (H5MM.c:465)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==  Address 0x5a5e8b9 is 25 bytes after a block of size 288 in arena "client"
==2397== 
==2397== Invalid read of size 1
==2397==    at 0x4838DCB: strcpy (vg_replace_strmem.c:512)
==2397==    by 0x4CA8105: H5MM_xstrdup (H5MM.c:467)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==  Address 0x5a5e8b9 is 25 bytes after a block of size 288 in arena "client"
==2397== 
==2397== Invalid read of size 1
==2397==    at 0x4838C74: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4D05912: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397==  Address 0x5a5e8b9 is 25 bytes after a block of size 288 in arena "client"
==2397== 
==2397== Conditional jump or move depends on uninitialised value(s)
==2397==    at 0x4838C65: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4CA8067: H5MM_xstrdup (H5MM.c:465)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397== 
==2397== Conditional jump or move depends on uninitialised value(s)
==2397==    at 0x4838DBB: strcpy (vg_replace_strmem.c:512)
==2397==    by 0x4CA8105: H5MM_xstrdup (H5MM.c:467)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397== 
==2397== Conditional jump or move depends on uninitialised value(s)
==2397==    at 0x4838C65: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4D05912: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397== 
==2397== Conditional jump or move depends on uninitialised value(s)
==2397==    at 0x4838C78: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4CA8067: H5MM_xstrdup (H5MM.c:465)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397== 
==2397== Conditional jump or move depends on uninitialised value(s)
==2397==    at 0x4838DD0: strcpy (vg_replace_strmem.c:512)
==2397==    by 0x4CA8105: H5MM_xstrdup (H5MM.c:467)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397== 
==2397== Conditional jump or move depends on uninitialised value(s)
==2397==    at 0x4838C78: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4D05912: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397== 
==2397== Invalid read of size 8
==2397==    at 0x483CABC: memmove (vg_replace_strmem.c:1270)
==2397==    by 0x4D059BE: H5O_dtype_decode_helper (H5Odtype.c:486)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397==  Address 0x5ce0038 is 8 bytes before a block of size 16,777,216 alloc'd
==2397==    at 0x4837B65: calloc (vg_replace_malloc.c:752)
==2397==    by 0x4D02CF7: H5O_dtype_decode_helper (H5Odtype.c:469)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397== 
==2397== Invalid read of size 8
==2397==    at 0x483CAC8: memmove (vg_replace_strmem.c:1270)
==2397==    by 0x4D059BE: H5O_dtype_decode_helper (H5Odtype.c:486)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397==  Address 0x5ce0030 is 16 bytes before a block of size 16,777,216 alloc'd
==2397==    at 0x4837B65: calloc (vg_replace_malloc.c:752)
==2397==    by 0x4D02CF7: H5O_dtype_decode_helper (H5Odtype.c:469)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397== 
==2397== Invalid read of size 8
==2397==    at 0x483CAD0: memmove (vg_replace_strmem.c:1270)
==2397==    by 0x4D059BE: H5O_dtype_decode_helper (H5Odtype.c:486)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397==  Address 0x5ce0028 is 24 bytes before a block of size 16,777,216 alloc'd
==2397==    at 0x4837B65: calloc (vg_replace_malloc.c:752)
==2397==    by 0x4D02CF7: H5O_dtype_decode_helper (H5Odtype.c:469)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397== 
==2397== Invalid read of size 8
==2397==    at 0x483CADB: memmove (vg_replace_strmem.c:1270)
==2397==    by 0x4D059BE: H5O_dtype_decode_helper (H5Odtype.c:486)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397==  Address 0x5ce0020 is 32 bytes before a block of size 16,781,216 in arena "client"
==2397== 
--2397-- REDIR: 0x5879b30 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483d4a0 (mempcpy)
==2397== 
==2397== HEAP SUMMARY:
==2397==     in use at exit: 16,879,417 bytes in 8,209 blocks
==2397==   total heap usage: 11,654 allocs, 3,445 frees, 18,240,331 bytes allocated
==2397== 
==2397== Searching for pointers to 8,209 not-freed blocks
==2397== Checked 16,844,176 bytes
==2397== 
==2397== 7,460 bytes in 1,574 blocks are possibly lost in loss record 15 of 19
==2397==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2397==    by 0x4CA80B3: H5MM_malloc (H5MM.c:322)
==2397==    by 0x4CA80B3: H5MM_xstrdup (H5MM.c:465)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397== 
==2397== 94,421 (96 direct, 94,325 indirect) bytes in 1 blocks are definitely lost in loss record 18 of 19
==2397==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2397==    by 0x4B4EA43: H5FL_malloc (H5FL.c:243)
==2397==    by 0x4B4EA43: H5FL_reg_malloc (H5FL.c:441)
==2397==    by 0x4F3DB5F: H5T_copy (H5T.c:3227)
==2397==    by 0x4F6158A: H5T__array_create (H5Tarray.c:169)
==2397==    by 0x4F2520E: H5T__init_package (H5T.c:1016)
==2397==    by 0x4F219C8: H5T_init (H5T.c:578)
==2397==    by 0x4890CF8: H5_init_library (H5.c:218)
==2397==    by 0x4A6A2B3: H5Eget_auto2 (H5E.c:1601)
==2397==    by 0x406F60: main (h5repack_main.c:714)
==2397== 
==2397== 16,777,216 bytes in 1 blocks are possibly lost in loss record 19 of 19
==2397==    at 0x4837B65: calloc (vg_replace_malloc.c:752)
==2397==    by 0x4D02CF7: H5O_dtype_decode_helper (H5Odtype.c:469)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397== 
==2397== LEAK SUMMARY:
==2397==    definitely lost: 96 bytes in 1 blocks
==2397==    indirectly lost: 94,325 bytes in 6,630 blocks
==2397==      possibly lost: 16,784,676 bytes in 1,575 blocks
==2397==    still reachable: 320 bytes in 3 blocks
==2397==         suppressed: 0 bytes in 0 blocks
==2397== Reachable blocks (those to which a pointer was found) are not shown.
==2397== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==2397== 
==2397== Use --track-origins=yes to see where uninitialised values come from
==2397== ERROR SUMMARY: 315444 errors from 19 contexts (suppressed: 0 from 0)
==2397== 
==2397== 5 errors in context 1 of 19:
==2397== Conditional jump or move depends on uninitialised value(s)
==2397==    at 0x4838C78: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4D05912: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397== 
==2397== 
==2397== 5 errors in context 2 of 19:
==2397== Conditional jump or move depends on uninitialised value(s)
==2397==    at 0x4838DD0: strcpy (vg_replace_strmem.c:512)
==2397==    by 0x4CA8105: H5MM_xstrdup (H5MM.c:467)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397== 
==2397== 
==2397== 5 errors in context 3 of 19:
==2397== Conditional jump or move depends on uninitialised value(s)
==2397==    at 0x4838C78: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4CA8067: H5MM_xstrdup (H5MM.c:465)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397== 
==2397== 
==2397== 13 errors in context 4 of 19:
==2397== Conditional jump or move depends on uninitialised value(s)
==2397==    at 0x4838C65: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4D05912: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397== 
==2397== 
==2397== 13 errors in context 5 of 19:
==2397== Conditional jump or move depends on uninitialised value(s)
==2397==    at 0x4838DBB: strcpy (vg_replace_strmem.c:512)
==2397==    by 0x4CA8105: H5MM_xstrdup (H5MM.c:467)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397== 
==2397== 
==2397== 13 errors in context 6 of 19:
==2397== Conditional jump or move depends on uninitialised value(s)
==2397==    at 0x4838C65: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4CA8067: H5MM_xstrdup (H5MM.c:465)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397== 
==2397== 
==2397== 622 errors in context 7 of 19:
==2397== Invalid read of size 1
==2397==    at 0x4838C74: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4D05912: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397==  Address 0x5a5e8b9 is 25 bytes after a block of size 288 in arena "client"
==2397== 
==2397== 
==2397== 622 errors in context 8 of 19:
==2397== Invalid read of size 1
==2397==    at 0x4838DCB: strcpy (vg_replace_strmem.c:512)
==2397==    by 0x4CA8105: H5MM_xstrdup (H5MM.c:467)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==  Address 0x5a5e8b9 is 25 bytes after a block of size 288 in arena "client"
==2397== 
==2397== 
==2397== 622 errors in context 9 of 19:
==2397== Invalid read of size 1
==2397==    at 0x4838C74: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4CA8067: H5MM_xstrdup (H5MM.c:465)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==  Address 0x5a5e8b9 is 25 bytes after a block of size 288 in arena "client"
==2397== 
==2397== 
==2397== 1029 errors in context 10 of 19:
==2397== Invalid read of size 1
==2397==    at 0x4838C62: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4D05912: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397==  Address 0x5a5e898 is 0 bytes after a block of size 280 alloc'd
==2397==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2397==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==2397==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==2397==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==2397==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==2397==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==2397==    by 0x495AE26: H5C_protect (H5C.c:2357)
==2397==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==2397==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==2397==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==2397==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==2397==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==2397==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==2397==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==2397== 
==2397== 
==2397== 1029 errors in context 11 of 19:
==2397== Invalid read of size 1
==2397==    at 0x57BA3B0: __strcpy_sse2_unaligned (strcpy-sse2-unaligned.S:47)
==2397==    by 0x4CA8105: H5MM_xstrdup (H5MM.c:467)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==  Address 0x5a5e898 is 0 bytes after a block of size 280 alloc'd
==2397==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2397==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==2397==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==2397==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==2397==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==2397==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==2397==    by 0x495AE26: H5C_protect (H5C.c:2357)
==2397==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==2397==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==2397==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==2397==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==2397==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==2397==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==2397==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==2397== 
==2397== 
==2397== 1029 errors in context 12 of 19:
==2397== Invalid read of size 1
==2397==    at 0x4838C62: strlen (vg_replace_strmem.c:460)
==2397==    by 0x4CA8067: H5MM_xstrdup (H5MM.c:465)
==2397==    by 0x4D058FB: H5O_dtype_decode_helper (H5Odtype.c:474)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==  Address 0x5a5e898 is 0 bytes after a block of size 280 alloc'd
==2397==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2397==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==2397==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==2397==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==2397==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==2397==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==2397==    by 0x495AE26: H5C_protect (H5C.c:2357)
==2397==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==2397==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==2397==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==2397==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==2397==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==2397==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==2397==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==2397== 
==2397== 
==2397== 75565 errors in context 13 of 19:
==2397== Invalid read of size 8
==2397==    at 0x483CAC8: memmove (vg_replace_strmem.c:1270)
==2397==    by 0x4D059BE: H5O_dtype_decode_helper (H5Odtype.c:486)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397==  Address 0x5ce0030 is 16 bytes before a block of size 16,777,216 alloc'd
==2397==    at 0x4837B65: calloc (vg_replace_malloc.c:752)
==2397==    by 0x4D02CF7: H5O_dtype_decode_helper (H5Odtype.c:469)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397== 
==2397== 
==2397== 75565 errors in context 14 of 19:
==2397== Invalid read of size 8
==2397==    at 0x483CADB: memmove (vg_replace_strmem.c:1270)
==2397==    by 0x4D059BE: H5O_dtype_decode_helper (H5Odtype.c:486)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397==  Address 0x5ce0020 is 32 bytes before a block of size 16,781,216 in arena "client"
==2397== 
==2397== 
==2397== 79652 errors in context 15 of 19:
==2397== Invalid read of size 8
==2397==    at 0x483CABC: memmove (vg_replace_strmem.c:1270)
==2397==    by 0x4D059BE: H5O_dtype_decode_helper (H5Odtype.c:486)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397==  Address 0x5ce0038 is 8 bytes before a block of size 16,777,216 alloc'd
==2397==    at 0x4837B65: calloc (vg_replace_malloc.c:752)
==2397==    by 0x4D02CF7: H5O_dtype_decode_helper (H5Odtype.c:469)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397== 
==2397== 
==2397== 79652 errors in context 16 of 19:
==2397== Invalid read of size 8
==2397==    at 0x483CAD0: memmove (vg_replace_strmem.c:1270)
==2397==    by 0x4D059BE: H5O_dtype_decode_helper (H5Odtype.c:486)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397==  Address 0x5ce0028 is 24 bytes before a block of size 16,777,216 alloc'd
==2397==    at 0x4837B65: calloc (vg_replace_malloc.c:752)
==2397==    by 0x4D02CF7: H5O_dtype_decode_helper (H5Odtype.c:469)
==2397==    by 0x4D02B19: H5O_dtype_decode_helper (H5Odtype.c:460)
==2397==    by 0x4CFF09D: H5O_dtype_decode (H5Odtype.c:1110)
==2397==    by 0x4CFF09D: H5O_dtype_shared_decode (H5Oshared.h:82)
==2397==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2397==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2397==    by 0x4F70FC6: H5T__open_oid (H5Tcommit.c:989)
==2397==    by 0x4F70FC6: H5T_open (H5Tcommit.c:874)
==2397==    by 0x4F6E66D: H5T__open_name (H5Tcommit.c:827)
==2397==    by 0x4F6DF10: H5Topen2 (H5Tcommit.c:573)
==2397==    by 0x419E04: do_copy_objects (h5repack_copy.c:1165)
==2397==    by 0x419E04: copy_objects (h5repack_copy.c:353)
==2397==    by 0x410FFD: h5repack (h5repack.c:54)
==2397==    by 0x40931F: main (h5repack_main.c:769)
==2397== 
==2397== ERROR SUMMARY: 315444 errors from 19 contexts (suppressed: 0 from 0)







```
---
