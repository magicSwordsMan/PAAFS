## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by godlovevampire@gmail.com, please send email to godlovevampire@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5O_mtime_encode_invalid-write-memory-access

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack Fuzzout/crashes/H5O_mtime_encode_invalid-write-memory-access test
==3719== Memcheck, a memory error detector
==3719== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==3719== Using Valgrind-3.14.0-353a3587bb-20181007X and LibVEX; rerun with -h for copyright info
==3719== Command: ./h5repack Fuzzout/crashes/H5O_mtime_encode_invalid-write-memory-access test
==3719== 
--3719-- Valgrind options:
--3719--    -v
--3719--    --tool=memcheck
--3719--    --leak-check=full
--3719-- Contents of /proc/version:
--3719--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--3719-- 
--3719-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--3719-- Page sizes: currently 4096, max supported 4096
--3719-- Valgrind library directory: /usr/lib/x86_64-linux-gnu/valgrind
--3719-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--3719-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.28.so
--3719--   Considering /usr/lib/debug/.build-id/dd/8026f43793facd0aa3924fb2dd6b0033b7b431.debug ..
--3719--   .. build-id is valid
--3719-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/memcheck-amd64-linux
--3719--   Considering /usr/lib/debug/.build-id/93/5efea22a69d45c080fd7ebab50cfe06d56e7af.debug ..
--3719--   .. build-id is valid
--3719--    object doesn't have a dynamic symbol table
--3719-- Scheduler: using generic scheduler lock implementation.
--3719-- Reading suppressions file: /usr/lib/x86_64-linux-gnu/valgrind/default.supp
==3719== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-3719-by-root-on-???
==3719== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-3719-by-root-on-???
==3719== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-3719-by-root-on-???
==3719== 
==3719== TO CONTROL THIS PROCESS USING vgdb (which you probably
==3719== don't want to do, unless you know exactly what you're doing,
==3719== or are doing some strange experiment):
==3719==   /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=3719 ...command...
==3719== 
==3719== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==3719==   /path/to/gdb ./h5repack
==3719== and then give GDB the following command
==3719==   target remote | /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=3719
==3719== --pid is optional if only one valgrind process is running
==3719== 
--3719-- REDIR: 0x401e350 (ld-linux-x86-64.so.2:strlen) redirected to 0x580c97f2 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--3719-- REDIR: 0x401e130 (ld-linux-x86-64.so.2:index) redirected to 0x580c980c (vgPlain_amd64_linux_REDIR_FOR_index)
--3719-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_core-amd64-linux.so
--3719--   Considering /usr/lib/debug/.build-id/3d/5115a2ef08a4077609b25d33f892f9260b8b5b.debug ..
--3719--   .. build-id is valid
--3719-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_memcheck-amd64-linux.so
--3719--   Considering /usr/lib/debug/.build-id/19/fb020e170903e05352b43e84af203f8f9ed2d8.debug ..
--3719--   .. build-id is valid
==3719== WARNING: new redirection conflicts with existing -- ignoring it
--3719--     old: 0x0401e350 (strlen              ) R-> (0000.0) 0x580c97f2 vgPlain_amd64_linux_REDIR_FOR_strlen
--3719--     new: 0x0401e350 (strlen              ) R-> (2007.0) 0x04838d80 strlen
--3719-- REDIR: 0x401ab70 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839e40 (strcmp)
--3719-- REDIR: 0x401e890 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d860 (mempcpy)
--3719-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--3719-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--3719--    object doesn't have a symbol table
--3719-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.28.so
--3719--   Considering /usr/lib/debug/.build-id/60/1c7068f7cbc26814db9cbca61b1a2c00f5d66d.debug ..
--3719--   .. build-id is valid
--3719-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.28.so
--3719--   Considering /usr/lib/debug/.build-id/86/be4b7815704459f8a32170db4266066980289f.debug ..
--3719--   .. build-id is valid
--3719-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.28.so
--3719--   Considering /usr/lib/debug/.build-id/cd/ae5bb84a51c364471bdd287dbe9df7d1d235f3.debug ..
--3719--   .. build-id is valid
--3719-- REDIR: 0x57a6210 (libc.so.6:memmove) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a5400 (libc.so.6:strncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a64f0 (libc.so.6:strcasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a4e30 (libc.so.6:strcat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a5430 (libc.so.6:rindex) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a7b20 (libc.so.6:rawmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57c04e0 (libc.so.6:wmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57bff80 (libc.so.6:wcscmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a6380 (libc.so.6:mempcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a61b0 (libc.so.6:bcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a53a0 (libc.so.6:strncmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a4ea0 (libc.so.6:strcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a62e0 (libc.so.6:memset) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57bff50 (libc.so.6:wcschr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a5340 (libc.so.6:strnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a4f30 (libc.so.6:strcspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a6540 (libc.so.6:strncasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a4f00 (libc.so.6:strcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a6680 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57c1780 (libc.so.6:wcsnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a5460 (libc.so.6:strpbrk) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a4e60 (libc.so.6:index) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a5310 (libc.so.6:strlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57ac530 (libc.so.6:memrchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a6590 (libc.so.6:strcasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a6180 (libc.so.6:memchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57c0060 (libc.so.6:wcslen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a5700 (libc.so.6:strspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a64c0 (libc.so.6:stpncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a6490 (libc.so.6:stpcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a7b50 (libc.so.6:strchrnul) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57a65e0 (libc.so.6:strncasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x5879440 (libc.so.6:__strrchr_avx2) redirected to 0x4838790 (rindex)
--3719-- REDIR: 0x5879610 (libc.so.6:__strlen_avx2) redirected to 0x4838c60 (strlen)
--3719-- REDIR: 0x5879fd0 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c790 (memset)
--3719-- REDIR: 0x57a1610 (libc.so.6:malloc) redirected to 0x4835710 (malloc)
--3719-- REDIR: 0x5879250 (libc.so.6:__strchrnul_avx2) redirected to 0x483d390 (strchrnul)
--3719-- REDIR: 0x57ba3b0 (libc.so.6:__strcpy_sse2_unaligned) redirected to 0x4838db0 (strcpy)
--3719-- REDIR: 0x57a1eb0 (libc.so.6:realloc) redirected to 0x4837d00 (realloc)
--3719-- REDIR: 0x5879b50 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c8a0 (memmove)
--3719-- REDIR: 0x57a1c60 (libc.so.6:free) redirected to 0x4836940 (free)
--3719-- REDIR: 0x57ba9e0 (libc.so.6:__strncpy_sse2_unaligned) redirected to 0x48392e0 (__strncpy_sse2_unaligned)
--3719-- REDIR: 0x5874b50 (libc.so.6:__strcmp_avx2) redirected to 0x4839d00 (strcmp)
--3719-- REDIR: 0x5875c20 (libc.so.6:__memcmp_avx2_movbe) redirected to 0x483c060 (bcmp)
--3719-- REDIR: 0x57a23e0 (libc.so.6:calloc) redirected to 0x4837ab0 (calloc)
--3719-- REDIR: 0x57a5370 (libc.so.6:strncat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--3719-- REDIR: 0x57bdc90 (libc.so.6:__strncat_sse2_unaligned) redirected to 0x4838b00 (strncat)
--3719-- REDIR: 0x5874760 (libc.so.6:__strcspn_sse42) redirected to 0x483dc00 (strcspn)
--3719-- REDIR: 0x5879020 (libc.so.6:__strchr_avx2) redirected to 0x4838910 (index)
--3719-- REDIR: 0x5879b30 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483d4a0 (mempcpy)
--3719-- REDIR: 0x57a5c20 (libc.so.6:__GI_strstr) redirected to 0x483dac0 (__strstr_sse2)
==3719== Invalid write of size 1
==3719==    at 0x579AAF5: _IO_default_xsputn (genops.c:394)
==3719==    by 0x579AAF5: _IO_default_xsputn (genops.c:370)
==3719==    by 0x576D832: vfprintf (vfprintf.c:1637)
==3719==    by 0x578F530: vsprintf (iovsprintf.c:42)
==3719==    by 0x5775913: sprintf (sprintf.c:32)
==3719==    by 0x4D50376: H5O_mtime_encode (H5Omtime.c:292)
==3719==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==3719==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==3719==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==3719==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==3719==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==3719==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==3719==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==3719==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==3719==  Address 0x5a67408 is 0 bytes after a block of size 136 alloc'd
==3719==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==3719==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==3719==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==3719==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==3719==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==3719==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==3719==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==3719==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==3719==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==3719==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==3719==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==3719==    by 0x410FFD: h5repack (h5repack.c:54)
==3719==    by 0x40931F: main (h5repack_main.c:769)
==3719== 
==3719== Invalid write of size 1
==3719==    at 0x579AAF5: _IO_default_xsputn (genops.c:394)
==3719==    by 0x579AAF5: _IO_default_xsputn (genops.c:370)
==3719==    by 0x578E49B: _IO_padn (iopadn.c:64)
==3719==    by 0x576E740: vfprintf (vfprintf.c:1637)
==3719==    by 0x578F530: vsprintf (iovsprintf.c:42)
==3719==    by 0x5775913: sprintf (sprintf.c:32)
==3719==    by 0x4D50376: H5O_mtime_encode (H5Omtime.c:292)
==3719==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==3719==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==3719==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==3719==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==3719==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==3719==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==3719==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==3719==  Address 0x5a6740c is 4 bytes after a block of size 136 alloc'd
==3719==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==3719==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==3719==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==3719==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==3719==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==3719==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==3719==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==3719==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==3719==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==3719==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==3719==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==3719==    by 0x410FFD: h5repack (h5repack.c:54)
==3719==    by 0x40931F: main (h5repack_main.c:769)
==3719== 
==3719== Invalid write of size 1
==3719==    at 0x578F53F: vsprintf (iovsprintf.c:43)
==3719==    by 0x5775913: sprintf (sprintf.c:32)
==3719==    by 0x4D50376: H5O_mtime_encode (H5Omtime.c:292)
==3719==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==3719==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==3719==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==3719==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==3719==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==3719==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==3719==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==3719==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==3719==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==3719==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==3719==  Address 0x5a6740e is 6 bytes after a block of size 136 alloc'd
==3719==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==3719==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==3719==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==3719==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==3719==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==3719==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==3719==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==3719==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==3719==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==3719==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==3719==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==3719==    by 0x410FFD: h5repack (h5repack.c:54)
==3719==    by 0x40931F: main (h5repack_main.c:769)
==3719== 
==3719== 
==3719== HEAP SUMMARY:
==3719==     in use at exit: 0 bytes in 0 blocks
==3719==   total heap usage: 3,783 allocs, 3,783 frees, 1,453,279 bytes allocated
==3719== 
==3719== All heap blocks were freed -- no leaks are possible
==3719== 
==3719== ERROR SUMMARY: 7 errors from 3 contexts (suppressed: 0 from 0)
==3719== 
==3719== 1 errors in context 1 of 3:
==3719== Invalid write of size 1
==3719==    at 0x578F53F: vsprintf (iovsprintf.c:43)
==3719==    by 0x5775913: sprintf (sprintf.c:32)
==3719==    by 0x4D50376: H5O_mtime_encode (H5Omtime.c:292)
==3719==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==3719==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==3719==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==3719==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==3719==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==3719==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==3719==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==3719==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==3719==    by 0x4AC2B27: H5F__flush_phase2 (H5Fint.c:1879)
==3719==    by 0x4AC119C: H5F__dest (H5Fint.c:1128)
==3719==  Address 0x5a6740e is 6 bytes after a block of size 136 alloc'd
==3719==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==3719==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==3719==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==3719==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==3719==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==3719==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==3719==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==3719==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==3719==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==3719==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==3719==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==3719==    by 0x410FFD: h5repack (h5repack.c:54)
==3719==    by 0x40931F: main (h5repack_main.c:769)
==3719== 
==3719== 
==3719== 1 errors in context 2 of 3:
==3719== Invalid write of size 1
==3719==    at 0x579AAF5: _IO_default_xsputn (genops.c:394)
==3719==    by 0x579AAF5: _IO_default_xsputn (genops.c:370)
==3719==    by 0x578E49B: _IO_padn (iopadn.c:64)
==3719==    by 0x576E740: vfprintf (vfprintf.c:1637)
==3719==    by 0x578F530: vsprintf (iovsprintf.c:42)
==3719==    by 0x5775913: sprintf (sprintf.c:32)
==3719==    by 0x4D50376: H5O_mtime_encode (H5Omtime.c:292)
==3719==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==3719==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==3719==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==3719==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==3719==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==3719==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==3719==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==3719==  Address 0x5a6740c is 4 bytes after a block of size 136 alloc'd
==3719==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==3719==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==3719==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==3719==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==3719==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==3719==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==3719==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==3719==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==3719==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==3719==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==3719==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==3719==    by 0x410FFD: h5repack (h5repack.c:54)
==3719==    by 0x40931F: main (h5repack_main.c:769)
==3719== 
==3719== 
==3719== 5 errors in context 3 of 3:
==3719== Invalid write of size 1
==3719==    at 0x579AAF5: _IO_default_xsputn (genops.c:394)
==3719==    by 0x579AAF5: _IO_default_xsputn (genops.c:370)
==3719==    by 0x576D832: vfprintf (vfprintf.c:1637)
==3719==    by 0x578F530: vsprintf (iovsprintf.c:42)
==3719==    by 0x5775913: sprintf (sprintf.c:32)
==3719==    by 0x4D50376: H5O_mtime_encode (H5Omtime.c:292)
==3719==    by 0x4D4E49B: H5O_msg_flush (H5Omessage.c:2187)
==3719==    by 0x4CE827D: H5O__chunk_serialize (H5Ocache.c:1660)
==3719==    by 0x4CE244A: H5O__cache_serialize (H5Ocache.c:538)
==3719==    by 0x496D198: H5C__generate_image (H5C.c:8657)
==3719==    by 0x494A52F: H5C__flush_single_entry (H5C.c:6084)
==3719==    by 0x494D94C: H5C__flush_ring (H5C.c:5871)
==3719==    by 0x494D94C: H5C_flush_cache (H5C.c:1149)
==3719==    by 0x48EAFE7: H5AC_flush (H5AC.c:731)
==3719==  Address 0x5a67408 is 0 bytes after a block of size 136 alloc'd
==3719==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==3719==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==3719==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==3719==    by 0x4B500E3: H5FL_blk_calloc (H5FL.c:989)
==3719==    by 0x4CF472E: H5O__copy_header_real (H5Ocopy.c:716)
==3719==    by 0x4CEF565: H5O__copy_header (H5Ocopy.c:1164)
==3719==    by 0x4CEF565: H5O__copy_obj (H5Ocopy.c:1220)
==3719==    by 0x4CEF565: H5O__copy (H5Ocopy.c:316)
==3719==    by 0x4CEF565: H5Ocopy (H5Ocopy.c:232)
==3719==    by 0x419A3D: do_copy_objects (h5repack_copy.c:1124)
==3719==    by 0x419A3D: copy_objects (h5repack_copy.c:353)
==3719==    by 0x410FFD: h5repack (h5repack.c:54)
==3719==    by 0x40931F: main (h5repack_main.c:769)
==3719== 
==3719== ERROR SUMMARY: 7 errors from 3 contexts (suppressed: 0 from 0)



```
---
