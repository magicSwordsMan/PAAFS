## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by godlovevampire@gmail.com, please send email to godlovevampire@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5O_sdspace_encode_heap-buffer-overflow

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack Fuzzout/crashes/H5O_sdspace_encode_heap-buffer-overflow test
==84326== Memcheck, a memory error detector
==84326== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==84326== Using Valgrind-3.14.0-353a3587bb-20181007X and LibVEX; rerun with -h for copyright info
==84326== Command: ./h5repack Fuzzout/crashes/id:000039,sig:06,src:000081,op:flip4,pos:825 test
==84326== 
--84326-- Valgrind options:
--84326--    -v
--84326--    --tool=memcheck
--84326--    --leak-check=full
--84326-- Contents of /proc/version:
--84326--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--84326-- 
--84326-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--84326-- Page sizes: currently 4096, max supported 4096
--84326-- Valgrind library directory: /usr/lib/x86_64-linux-gnu/valgrind
--84326-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--84326-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.27.so
--84326--   Considering /usr/lib/debug/.build-id/fa/01a234506568b77ad2d1a6da398e45586c550b.debug ..
--84326--   .. build-id is valid
--84326-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/memcheck-amd64-linux
--84326--   Considering /usr/lib/debug/.build-id/93/5efea22a69d45c080fd7ebab50cfe06d56e7af.debug ..
--84326--   .. build-id is valid
--84326--    object doesn't have a dynamic symbol table
--84326-- Scheduler: using generic scheduler lock implementation.
--84326-- Reading suppressions file: /usr/lib/x86_64-linux-gnu/valgrind/default.supp
==84326== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-84326-by-root-on-???
==84326== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-84326-by-root-on-???
==84326== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-84326-by-root-on-???
==84326== 
==84326== TO CONTROL THIS PROCESS USING vgdb (which you probably
==84326== don't want to do, unless you know exactly what you're doing,
==84326== or are doing some strange experiment):
==84326==   /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=84326 ...command...
==84326== 
==84326== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==84326==   /path/to/gdb ./h5repack
==84326== and then give GDB the following command
==84326==   target remote | /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=84326
==84326== --pid is optional if only one valgrind process is running
==84326== 
--84326-- REDIR: 0x401e290 (ld-linux-x86-64.so.2:strlen) redirected to 0x580c97f2 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--84326-- REDIR: 0x401e070 (ld-linux-x86-64.so.2:index) redirected to 0x580c980c (vgPlain_amd64_linux_REDIR_FOR_index)
--84326-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_core-amd64-linux.so
--84326--   Considering /usr/lib/debug/.build-id/3d/5115a2ef08a4077609b25d33f892f9260b8b5b.debug ..
--84326--   .. build-id is valid
--84326-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_memcheck-amd64-linux.so
--84326--   Considering /usr/lib/debug/.build-id/19/fb020e170903e05352b43e84af203f8f9ed2d8.debug ..
--84326--   .. build-id is valid
==84326== WARNING: new redirection conflicts with existing -- ignoring it
--84326--     old: 0x0401e290 (strlen              ) R-> (0000.0) 0x580c97f2 vgPlain_amd64_linux_REDIR_FOR_strlen
--84326--     new: 0x0401e290 (strlen              ) R-> (2007.0) 0x04838d80 strlen
--84326-- REDIR: 0x401aab0 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839e40 (strcmp)
--84326-- REDIR: 0x401e7d0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d860 (mempcpy)
--84326-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--84326-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--84326--    object doesn't have a symbol table
--84326-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.27.so
--84326--   Considering /usr/lib/debug/.build-id/2b/51cce982e540854dd1995136601f770f127b05.debug ..
--84326--   .. build-id is valid
--84326-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.27.so
--84326--   Considering /usr/lib/debug/.build-id/b6/7df54e445705b0d3fc5fb78cee3c26357ecba3.debug ..
--84326--   .. build-id is valid
--84326-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.27.so
--84326--   Considering /usr/lib/debug/.build-id/e9/38fe6706abe362f6c3c7474373ccc626cf4805.debug ..
--84326--   .. build-id is valid
--84326-- REDIR: 0x57b6050 (libc.so.6:memmove) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b5280 (libc.so.6:strncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b6330 (libc.so.6:strcasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b4cd0 (libc.so.6:strcat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b52b0 (libc.so.6:rindex) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b7900 (libc.so.6:rawmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57d0e60 (libc.so.6:wmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b61c0 (libc.so.6:mempcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b5ff0 (libc.so.6:bcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b5240 (libc.so.6:strncmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b4d40 (libc.so.6:strcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b6120 (libc.so.6:memset) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57cfb60 (libc.so.6:wcschr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b51e0 (libc.so.6:strnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b4db0 (libc.so.6:strcspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b6380 (libc.so.6:strncasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b4d80 (libc.so.6:strcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b64c0 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57d20c0 (libc.so.6:wcsnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b52e0 (libc.so.6:strpbrk) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b4d00 (libc.so.6:index) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b51b0 (libc.so.6:strlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57bc1b0 (libc.so.6:memrchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b63d0 (libc.so.6:strcasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b5fc0 (libc.so.6:memchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57d0920 (libc.so.6:wcslen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b5590 (libc.so.6:strspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b6300 (libc.so.6:stpncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b62d0 (libc.so.6:stpcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b7930 (libc.so.6:strchrnul) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57b6420 (libc.so.6:strncasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x5888700 (libc.so.6:__strrchr_avx2) redirected to 0x4838790 (rindex)
--84326-- REDIR: 0x58888d0 (libc.so.6:__strlen_avx2) redirected to 0x4838c60 (strlen)
--84326-- REDIR: 0x5889290 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c790 (memset)
--84326-- REDIR: 0x57b15c0 (libc.so.6:malloc) redirected to 0x4835710 (malloc)
--84326-- REDIR: 0x5888510 (libc.so.6:__strchrnul_avx2) redirected to 0x483d390 (strchrnul)
--84326-- REDIR: 0x5875c90 (libc.so.6:__strcpy_ssse3) redirected to 0x4838db0 (strcpy)
--84326-- REDIR: 0x57b1d60 (libc.so.6:realloc) redirected to 0x4837d00 (realloc)
--84326-- REDIR: 0x5888e10 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c8a0 (memmove)
--84326-- REDIR: 0x57b1c50 (libc.so.6:free) redirected to 0x4836940 (free)
--84326-- REDIR: 0x5877440 (libc.so.6:__strncpy_ssse3) redirected to 0x4838f50 (strncpy)
--84326-- REDIR: 0x58640a0 (libc.so.6:__strcmp_ssse3) redirected to 0x4839d00 (strcmp)
--84326-- REDIR: 0x5884ee0 (libc.so.6:__memcmp_avx2_movbe) redirected to 0x483c060 (bcmp)
--84326-- REDIR: 0x57b22a0 (libc.so.6:calloc) redirected to 0x4837ab0 (calloc)
--84326-- REDIR: 0x57b5210 (libc.so.6:strncat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--84326-- REDIR: 0x57c70f0 (libc.so.6:__strncat_ssse3) redirected to 0x4838b00 (strncat)
--84326-- REDIR: 0x58843b0 (libc.so.6:__strcspn_sse42) redirected to 0x483dc00 (strcspn)
--84326-- REDIR: 0x58882e0 (libc.so.6:__strchr_avx2) redirected to 0x4838910 (index)
--84326-- REDIR: 0x5888df0 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483d4a0 (mempcpy)
==84326== Invalid write of size 1
==84326==    at 0x4D5A571: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A571: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746c8 is 0 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== Invalid write of size 1
==84326==    at 0x4D5A57B: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A57B: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746c9 is 1 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== Invalid write of size 1
==84326==    at 0x4D5A585: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A585: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746ca is 2 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== Invalid write of size 1
==84326==    at 0x4D5A58C: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A58C: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746cb is 3 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== Invalid write of size 1
==84326==    at 0x4D5A550: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A550: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746cc is 4 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== Invalid write of size 1
==84326==    at 0x4D5A553: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A553: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746cd is 5 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== Invalid write of size 1
==84326==    at 0x4D5A55D: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A55D: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746ce is 6 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== Invalid write of size 1
==84326==    at 0x4D5A567: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A567: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746cf is 7 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== Invalid read of size 4
==84326==    at 0x4B4D6C0: H5FL__reg_gc_list (H5FL.c:532)
==84326==    by 0x4B4D6C0: H5FL__reg_gc (H5FL.c:589)
==84326==    by 0x4B4D6C0: H5FL_garbage_coll (H5FL.c:2461)
==84326==    by 0x4B4BB20: H5FL_term_package (H5FL.c:184)
==84326==    by 0x4894380: H5_term_library (H5.c:359)
==84326==    by 0x489789D: H5close (H5.c:875)
==84326==    by 0x43BABA: h5tools_close (h5tools.c:179)
==84326==    by 0x40CF8F: leave (h5repack_main.c:245)
==84326==    by 0x4096E1: main (h5repack_main.c:775)
==84326==  Address 0x8 is not stack'd, malloc'd or (recently) free'd
==84326== 
==84326== 
==84326== Process terminating with default action of signal 11 (SIGSEGV)
==84326==  Access not within mapped region at address 0x8
==84326==    at 0x4B4D6C0: H5FL__reg_gc_list (H5FL.c:532)
==84326==    by 0x4B4D6C0: H5FL__reg_gc (H5FL.c:589)
==84326==    by 0x4B4D6C0: H5FL_garbage_coll (H5FL.c:2461)
==84326==    by 0x4B4BB20: H5FL_term_package (H5FL.c:184)
==84326==    by 0x4894380: H5_term_library (H5.c:359)
==84326==    by 0x489789D: H5close (H5.c:875)
==84326==    by 0x43BABA: h5tools_close (h5tools.c:179)
==84326==    by 0x40CF8F: leave (h5repack_main.c:245)
==84326==    by 0x4096E1: main (h5repack_main.c:775)
==84326==  If you believe this happened as a result of a stack
==84326==  overflow in your program's main thread (unlikely but
==84326==  possible), you can try to increase the size of the
==84326==  main thread stack using the --main-stacksize= flag.
==84326==  The main thread stack size used in this run was 8388608.
==84326== 
==84326== HEAP SUMMARY:
==84326==     in use at exit: 182,784 bytes in 2,035 blocks
==84326==   total heap usage: 3,842 allocs, 1,807 frees, 1,476,681 bytes allocated
==84326== 
==84326== Searching for pointers to 2,035 not-freed blocks
==84326== Checked 304,872 bytes
==84326== 
==84326== 312 (80 direct, 232 indirect) bytes in 1 blocks are definitely lost in loss record 1,640 of 1,681
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4EA43: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4EA43: H5FL_reg_malloc (H5FL.c:441)
==84326==    by 0x4B4EE83: H5FL_reg_calloc (H5FL.c:498)
==84326==    by 0x4D5BBDF: H5O_sdspace_pre_copy_file (H5Osdspace.c:469)
==84326==    by 0x4CF214D: H5O__copy_header_real (H5Ocopy.c:541)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== 736 (16 direct, 720 indirect) bytes in 1 blocks are definitely lost in loss record 1,663 of 1,681
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4E7D1: H5FL_reg_init (H5FL.c:283)
==84326==    by 0x4B4E7D1: H5FL_reg_malloc (H5FL.c:422)
==84326==    by 0x4B4EE83: H5FL_reg_calloc (H5FL.c:498)
==84326==    by 0x4A28437: H5O__dset_get_copy_file_udata (H5Doh.c:113)
==84326==    by 0x4CF0E61: H5O__copy_header_real (H5Ocopy.c:394)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== LEAK SUMMARY:
==84326==    definitely lost: 96 bytes in 2 blocks
==84326==    indirectly lost: 952 bytes in 46 blocks
==84326==      possibly lost: 0 bytes in 0 blocks
==84326==    still reachable: 181,736 bytes in 1,987 blocks
==84326==         suppressed: 0 bytes in 0 blocks
==84326== Reachable blocks (those to which a pointer was found) are not shown.
==84326== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==84326== 
==84326== ERROR SUMMARY: 111 errors from 11 contexts (suppressed: 0 from 0)
==84326== 
==84326== 1 errors in context 1 of 11:
==84326== Invalid read of size 4
==84326==    at 0x4B4D6C0: H5FL__reg_gc_list (H5FL.c:532)
==84326==    by 0x4B4D6C0: H5FL__reg_gc (H5FL.c:589)
==84326==    by 0x4B4D6C0: H5FL_garbage_coll (H5FL.c:2461)
==84326==    by 0x4B4BB20: H5FL_term_package (H5FL.c:184)
==84326==    by 0x4894380: H5_term_library (H5.c:359)
==84326==    by 0x489789D: H5close (H5.c:875)
==84326==    by 0x43BABA: h5tools_close (h5tools.c:179)
==84326==    by 0x40CF8F: leave (h5repack_main.c:245)
==84326==    by 0x4096E1: main (h5repack_main.c:775)
==84326==  Address 0x8 is not stack'd, malloc'd or (recently) free'd
==84326== 
==84326== 
==84326== 13 errors in context 2 of 11:
==84326== Invalid write of size 1
==84326==    at 0x4D5A567: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A567: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746cf is 7 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== 
==84326== 13 errors in context 3 of 11:
==84326== Invalid write of size 1
==84326==    at 0x4D5A55D: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A55D: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746ce is 6 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== 
==84326== 13 errors in context 4 of 11:
==84326== Invalid write of size 1
==84326==    at 0x4D5A553: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A553: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746cd is 5 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== 
==84326== 13 errors in context 5 of 11:
==84326== Invalid write of size 1
==84326==    at 0x4D5A550: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A550: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746cc is 4 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== 
==84326== 14 errors in context 6 of 11:
==84326== Invalid write of size 1
==84326==    at 0x4D5A58C: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A58C: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746cb is 3 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== 
==84326== 14 errors in context 7 of 11:
==84326== Invalid write of size 1
==84326==    at 0x4D5A585: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A585: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746ca is 2 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== 
==84326== 14 errors in context 8 of 11:
==84326== Invalid write of size 1
==84326==    at 0x4D5A57B: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A57B: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746c9 is 1 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== 
==84326== 14 errors in context 9 of 11:
==84326== Invalid write of size 1
==84326==    at 0x4D5A571: H5O_sdspace_encode (H5Osdspace.c:272)
==84326==    by 0x4D5A571: H5O_sdspace_shared_encode (H5Oshared.h:137)
==84326==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==84326==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==84326==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==84326==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==84326==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==84326==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==84326==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==84326==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==84326==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==84326==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==84326==    by 0x4AC96B8: H5F_try_close (H5Fint.c:2275)
==84326==    by 0x4AC8BB3: H5F__close_cb (H5Fint.c:2104)
==84326==  Address 0x5a746c8 is 0 bytes after a block of size 136 alloc'd
==84326==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==84326==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==84326==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==84326==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==84326==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==84326==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==84326==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==84326==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==84326==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==84326==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==84326==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==84326==    by 0x410FFD: h5repack (h5repack.c:54)
==84326==    by 0x40931F: main (h5repack_main.c:769)
==84326== 
==84326== ERROR SUMMARY: 111 errors from 11 contexts (suppressed: 0 from 0)
Segmentation fault

```
---
