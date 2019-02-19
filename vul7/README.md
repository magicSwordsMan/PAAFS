## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by godlovevampire@gmail.com, please send email to godlovevampire@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5VM_memcpyvv_invalid-read-memory-access

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack Fuzzout/crashes/H5VM_memcpyvv_invalid-read-memory-access test
==2329== Memcheck, a memory error detector
==2329== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==2329== Using Valgrind-3.14.0-353a3587bb-20181007X and LibVEX; rerun with -h for copyright info
==2329== Command: ./h5repack Fuzzout/crashes/H5VM_memcpyvv_invalid-read-memory-access test
==2329== 
--2329-- Valgrind options:
--2329--    -v
--2329--    --tool=memcheck
--2329--    --leak-check=full
--2329-- Contents of /proc/version:
--2329--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--2329-- 
--2329-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--2329-- Page sizes: currently 4096, max supported 4096
--2329-- Valgrind library directory: /usr/lib/x86_64-linux-gnu/valgrind
--2329-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--2329-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.28.so
--2329--   Considering /usr/lib/debug/.build-id/dd/8026f43793facd0aa3924fb2dd6b0033b7b431.debug ..
--2329--   .. build-id is valid
--2329-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/memcheck-amd64-linux
--2329--   Considering /usr/lib/debug/.build-id/93/5efea22a69d45c080fd7ebab50cfe06d56e7af.debug ..
--2329--   .. build-id is valid
--2329--    object doesn't have a dynamic symbol table
--2329-- Scheduler: using generic scheduler lock implementation.
--2329-- Reading suppressions file: /usr/lib/x86_64-linux-gnu/valgrind/default.supp
==2329== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-2329-by-root-on-???
==2329== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-2329-by-root-on-???
==2329== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-2329-by-root-on-???
==2329== 
==2329== TO CONTROL THIS PROCESS USING vgdb (which you probably
==2329== don't want to do, unless you know exactly what you're doing,
==2329== or are doing some strange experiment):
==2329==   /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=2329 ...command...
==2329== 
==2329== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==2329==   /path/to/gdb ./h5repack
==2329== and then give GDB the following command
==2329==   target remote | /usr/lib/x86_64-linux-gnu/valgrind/../../bin/vgdb --pid=2329
==2329== --pid is optional if only one valgrind process is running
==2329== 
--2329-- REDIR: 0x401e350 (ld-linux-x86-64.so.2:strlen) redirected to 0x580c97f2 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--2329-- REDIR: 0x401e130 (ld-linux-x86-64.so.2:index) redirected to 0x580c980c (vgPlain_amd64_linux_REDIR_FOR_index)
--2329-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_core-amd64-linux.so
--2329--   Considering /usr/lib/debug/.build-id/3d/5115a2ef08a4077609b25d33f892f9260b8b5b.debug ..
--2329--   .. build-id is valid
--2329-- Reading syms from /usr/lib/x86_64-linux-gnu/valgrind/vgpreload_memcheck-amd64-linux.so
--2329--   Considering /usr/lib/debug/.build-id/19/fb020e170903e05352b43e84af203f8f9ed2d8.debug ..
--2329--   .. build-id is valid
==2329== WARNING: new redirection conflicts with existing -- ignoring it
--2329--     old: 0x0401e350 (strlen              ) R-> (0000.0) 0x580c97f2 vgPlain_amd64_linux_REDIR_FOR_strlen
--2329--     new: 0x0401e350 (strlen              ) R-> (2007.0) 0x04838d80 strlen
--2329-- REDIR: 0x401ab70 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839e40 (strcmp)
--2329-- REDIR: 0x401e890 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d860 (mempcpy)
--2329-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--2329-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--2329--    object doesn't have a symbol table
--2329-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.28.so
--2329--   Considering /usr/lib/debug/.build-id/60/1c7068f7cbc26814db9cbca61b1a2c00f5d66d.debug ..
--2329--   .. build-id is valid
--2329-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.28.so
--2329--   Considering /usr/lib/debug/.build-id/86/be4b7815704459f8a32170db4266066980289f.debug ..
--2329--   .. build-id is valid
--2329-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.28.so
--2329--   Considering /usr/lib/debug/.build-id/cd/ae5bb84a51c364471bdd287dbe9df7d1d235f3.debug ..
--2329--   .. build-id is valid
--2329-- REDIR: 0x57a6210 (libc.so.6:memmove) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a5400 (libc.so.6:strncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a64f0 (libc.so.6:strcasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a4e30 (libc.so.6:strcat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a5430 (libc.so.6:rindex) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a7b20 (libc.so.6:rawmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57c04e0 (libc.so.6:wmemchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57bff80 (libc.so.6:wcscmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a6380 (libc.so.6:mempcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a61b0 (libc.so.6:bcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a53a0 (libc.so.6:strncmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a4ea0 (libc.so.6:strcmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a62e0 (libc.so.6:memset) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57bff50 (libc.so.6:wcschr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a5340 (libc.so.6:strnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a4f30 (libc.so.6:strcspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a6540 (libc.so.6:strncasecmp) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a4f00 (libc.so.6:strcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a6680 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57c1780 (libc.so.6:wcsnlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a5460 (libc.so.6:strpbrk) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a4e60 (libc.so.6:index) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a5310 (libc.so.6:strlen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57ac530 (libc.so.6:memrchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a6590 (libc.so.6:strcasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a6180 (libc.so.6:memchr) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57c0060 (libc.so.6:wcslen) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a5700 (libc.so.6:strspn) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a64c0 (libc.so.6:stpncpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a6490 (libc.so.6:stpcpy) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a7b50 (libc.so.6:strchrnul) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57a65e0 (libc.so.6:strncasecmp_l) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x5879440 (libc.so.6:__strrchr_avx2) redirected to 0x4838790 (rindex)
--2329-- REDIR: 0x5879610 (libc.so.6:__strlen_avx2) redirected to 0x4838c60 (strlen)
--2329-- REDIR: 0x5879fd0 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c790 (memset)
--2329-- REDIR: 0x57a1610 (libc.so.6:malloc) redirected to 0x4835710 (malloc)
--2329-- REDIR: 0x5879250 (libc.so.6:__strchrnul_avx2) redirected to 0x483d390 (strchrnul)
--2329-- REDIR: 0x57ba3b0 (libc.so.6:__strcpy_sse2_unaligned) redirected to 0x4838db0 (strcpy)
--2329-- REDIR: 0x57a1eb0 (libc.so.6:realloc) redirected to 0x4837d00 (realloc)
--2329-- REDIR: 0x5879b50 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c8a0 (memmove)
--2329-- REDIR: 0x57a1c60 (libc.so.6:free) redirected to 0x4836940 (free)
--2329-- REDIR: 0x57ba9e0 (libc.so.6:__strncpy_sse2_unaligned) redirected to 0x48392e0 (__strncpy_sse2_unaligned)
--2329-- REDIR: 0x5874b50 (libc.so.6:__strcmp_avx2) redirected to 0x4839d00 (strcmp)
--2329-- REDIR: 0x5875c20 (libc.so.6:__memcmp_avx2_movbe) redirected to 0x483c060 (bcmp)
--2329-- REDIR: 0x57a23e0 (libc.so.6:calloc) redirected to 0x4837ab0 (calloc)
--2329-- REDIR: 0x57a5370 (libc.so.6:strncat) redirected to 0x482b1b0 (_vgnU_ifunc_wrapper)
--2329-- REDIR: 0x57bdc90 (libc.so.6:__strncat_sse2_unaligned) redirected to 0x4838b00 (strncat)
--2329-- REDIR: 0x5874760 (libc.so.6:__strcspn_sse42) redirected to 0x483dc00 (strcspn)
==2329== Invalid read of size 2
==2329==    at 0x483C9E7: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x4D325FD: H5O__layout_decode (H5Olayout.c:213)
==2329==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2329==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2329==    by 0x4A258AA: H5D__layout_oh_read (H5Dlayout.c:634)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==2329==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a5e898 is 0 bytes after a block of size 280 alloc'd
==2329==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2329==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==2329==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==2329==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==2329==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==2329==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==2329==    by 0x495AE26: H5C_protect (H5C.c:2357)
==2329==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==2329==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==2329==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==2329==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==2329==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==2329==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==2329==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==2329== 
==2329== Invalid read of size 2
==2329==    at 0x483C9D8: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x4D325FD: H5O__layout_decode (H5Olayout.c:213)
==2329==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2329==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2329==    by 0x4A258AA: H5D__layout_oh_read (H5Dlayout.c:634)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==2329==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a5e89e is 6 bytes after a block of size 280 alloc'd
==2329==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2329==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==2329==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==2329==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==2329==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==2329==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==2329==    by 0x495AE26: H5C_protect (H5C.c:2357)
==2329==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==2329==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==2329==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==2329==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==2329==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==2329==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==2329==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==2329== 
--2329-- REDIR: 0x5879b30 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483d4a0 (mempcpy)
==2329== Invalid read of size 8
==2329==    at 0x483C93F: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x52238E8: H5VM_memcpyvv (H5VM.c:1712)
==2329==    by 0x49D9BAA: H5D__compact_readvv (H5Dcompact.c:294)
==2329==    by 0x4A3453D: H5D__select_io (H5Dselect.c:215)
==2329==    by 0x4A33630: H5D__select_read (H5Dselect.c:281)
==2329==    by 0x49DDCFA: H5D__contig_read (H5Dcontig.c:595)
==2329==    by 0x4A1C26B: H5D__read (H5Dio.c:600)
==2329==    by 0x4A1AF28: H5Dread (H5Dio.c:198)
==2329==    by 0x431F0C: do_copy_refobjs (h5repack_refs.c:240)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a88c28 is 0 bytes after a block of size 1,400 alloc'd
==2329==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2329==    by 0x4D37D2B: H5O__layout_copy (H5Olayout.c:741)
==2329==    by 0x4D452C1: H5O_msg_read_oh (H5Omessage.c:548)
==2329==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2329==    by 0x4A258AA: H5D__layout_oh_read (H5Dlayout.c:634)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x430BF6: do_copy_refobjs (h5repack_refs.c:106)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329== 
==2329== Invalid read of size 8
==2329==    at 0x483C924: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x52238E8: H5VM_memcpyvv (H5VM.c:1712)
==2329==    by 0x49D9BAA: H5D__compact_readvv (H5Dcompact.c:294)
==2329==    by 0x4A3453D: H5D__select_io (H5Dselect.c:215)
==2329==    by 0x4A33630: H5D__select_read (H5Dselect.c:281)
==2329==    by 0x49DDCFA: H5D__contig_read (H5Dcontig.c:595)
==2329==    by 0x4A1C26B: H5D__read (H5Dio.c:600)
==2329==    by 0x4A1AF28: H5Dread (H5Dio.c:198)
==2329==    by 0x431F0C: do_copy_refobjs (h5repack_refs.c:240)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a88c30 is 8 bytes after a block of size 1,400 alloc'd
==2329==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2329==    by 0x4D37D2B: H5O__layout_copy (H5Olayout.c:741)
==2329==    by 0x4D452C1: H5O_msg_read_oh (H5Omessage.c:548)
==2329==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2329==    by 0x4A258AA: H5D__layout_oh_read (H5Dlayout.c:634)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x430BF6: do_copy_refobjs (h5repack_refs.c:106)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329== 
==2329== Invalid read of size 8
==2329==    at 0x483C92F: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x52238E8: H5VM_memcpyvv (H5VM.c:1712)
==2329==    by 0x49D9BAA: H5D__compact_readvv (H5Dcompact.c:294)
==2329==    by 0x4A3453D: H5D__select_io (H5Dselect.c:215)
==2329==    by 0x4A33630: H5D__select_read (H5Dselect.c:281)
==2329==    by 0x49DDCFA: H5D__contig_read (H5Dcontig.c:595)
==2329==    by 0x4A1C26B: H5D__read (H5Dio.c:600)
==2329==    by 0x4A1AF28: H5Dread (H5Dio.c:198)
==2329==    by 0x431F0C: do_copy_refobjs (h5repack_refs.c:240)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a88c38 is 16 bytes after a block of size 1,400 alloc'd
==2329==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2329==    by 0x4D37D2B: H5O__layout_copy (H5Olayout.c:741)
==2329==    by 0x4D452C1: H5O_msg_read_oh (H5Omessage.c:548)
==2329==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2329==    by 0x4A258AA: H5D__layout_oh_read (H5Dlayout.c:634)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x430BF6: do_copy_refobjs (h5repack_refs.c:106)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329== 
==2329== Invalid read of size 8
==2329==    at 0x483C937: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x52238E8: H5VM_memcpyvv (H5VM.c:1712)
==2329==    by 0x49D9BAA: H5D__compact_readvv (H5Dcompact.c:294)
==2329==    by 0x4A3453D: H5D__select_io (H5Dselect.c:215)
==2329==    by 0x4A33630: H5D__select_read (H5Dselect.c:281)
==2329==    by 0x49DDCFA: H5D__contig_read (H5Dcontig.c:595)
==2329==    by 0x4A1C26B: H5D__read (H5Dio.c:600)
==2329==    by 0x4A1AF28: H5Dread (H5Dio.c:198)
==2329==    by 0x431F0C: do_copy_refobjs (h5repack_refs.c:240)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a88c40 is 16 bytes after a block of size 1,408 in arena "client"
==2329== 
==2329== Invalid read of size 8
==2329==    at 0x483C97D: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x52238E8: H5VM_memcpyvv (H5VM.c:1712)
==2329==    by 0x49D9BAA: H5D__compact_readvv (H5Dcompact.c:294)
==2329==    by 0x4A3453D: H5D__select_io (H5Dselect.c:215)
==2329==    by 0x4A33630: H5D__select_read (H5Dselect.c:281)
==2329==    by 0x49DDCFA: H5D__contig_read (H5Dcontig.c:595)
==2329==    by 0x4A1C26B: H5D__read (H5Dio.c:600)
==2329==    by 0x4A1AF28: H5Dread (H5Dio.c:198)
==2329==    by 0x431F0C: do_copy_refobjs (h5repack_refs.c:240)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a89010 is 928 bytes inside a block of size 2,256 free'd
==2329==    at 0x48369AB: free (vg_replace_malloc.c:530)
==2329==    by 0x4CA854D: H5MM_xfree (H5MM.c:560)
==2329==    by 0x4DFD463: H5P__set_plist_cb (H5Pint.c:2905)
==2329==    by 0x4DFBE2E: H5P__do_prop (H5Pint.c:2640)
==2329==    by 0x4DFCBBE: H5P_set (H5Pint.c:3042)
==2329==    by 0x4A25F4D: H5D__layout_oh_read (H5Dlayout.c:666)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x430BF6: do_copy_refobjs (h5repack_refs.c:106)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==  Block was alloc'd at
==2329==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2329==    by 0x4DFCEFC: H5P__set_plist_cb (H5Pint.c:2877)
==2329==    by 0x4DFBE2E: H5P__do_prop (H5Pint.c:2640)
==2329==    by 0x4DFCBBE: H5P_set (H5Pint.c:3042)
==2329==    by 0x4A25F4D: H5D__layout_oh_read (H5Dlayout.c:666)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x430BF6: do_copy_refobjs (h5repack_refs.c:106)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329== 
==2329== Invalid read of size 8
==2329==    at 0x483C98B: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x52238E8: H5VM_memcpyvv (H5VM.c:1712)
==2329==    by 0x49D9BAA: H5D__compact_readvv (H5Dcompact.c:294)
==2329==    by 0x4A3453D: H5D__select_io (H5Dselect.c:215)
==2329==    by 0x4A33630: H5D__select_read (H5Dselect.c:281)
==2329==    by 0x49DDCFA: H5D__contig_read (H5Dcontig.c:595)
==2329==    by 0x4A1C26B: H5D__read (H5Dio.c:600)
==2329==    by 0x4A1AF28: H5Dread (H5Dio.c:198)
==2329==    by 0x431F0C: do_copy_refobjs (h5repack_refs.c:240)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a89020 is 944 bytes inside a block of size 2,256 free'd
==2329==    at 0x48369AB: free (vg_replace_malloc.c:530)
==2329==    by 0x4CA854D: H5MM_xfree (H5MM.c:560)
==2329==    by 0x4DFD463: H5P__set_plist_cb (H5Pint.c:2905)
==2329==    by 0x4DFBE2E: H5P__do_prop (H5Pint.c:2640)
==2329==    by 0x4DFCBBE: H5P_set (H5Pint.c:3042)
==2329==    by 0x4A25F4D: H5D__layout_oh_read (H5Dlayout.c:666)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x430BF6: do_copy_refobjs (h5repack_refs.c:106)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==  Block was alloc'd at
==2329==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2329==    by 0x4DFCEFC: H5P__set_plist_cb (H5Pint.c:2877)
==2329==    by 0x4DFBE2E: H5P__do_prop (H5Pint.c:2640)
==2329==    by 0x4DFCBBE: H5P_set (H5Pint.c:3042)
==2329==    by 0x4A25F4D: H5D__layout_oh_read (H5Dlayout.c:666)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x430BF6: do_copy_refobjs (h5repack_refs.c:106)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329== 
==2329== Invalid read of size 8
==2329==    at 0x4E4BA0F: H5S_close (H5S.c:448)
==2329==    by 0x48DB2B0: H5A__free (H5Aint.c:1166)
==2329==    by 0x4CCF6CF: H5O_attr_decode (H5Oattr.c:253)
==2329==    by 0x4CCF6CF: H5O_attr_shared_decode (H5Oshared.h:82)
==2329==    by 0x4D49613: H5O__msg_iterate_real (H5Omessage.c:1288)
==2329==    by 0x48DC6B1: H5A__compact_build_table (H5Aint.c:1544)
==2329==    by 0x4CD7C2F: H5O_attr_iterate_real (H5Oattribute.c:1283)
==2329==    by 0x4CD6DB0: H5O__attr_open_by_idx (H5Oattribute.c:611)
==2329==    by 0x48D6A92: H5A__open_by_idx (H5Aint.c:537)
==2329==    by 0x48B4F71: H5Aopen_by_idx (H5A.c:570)
==2329==    by 0x412A96: copy_attr (h5repack.c:364)
==2329==    by 0x432FFE: do_copy_refobjs (h5repack_refs.c:303)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==  Address 0x18 is not stack'd, malloc'd or (recently) free'd
==2329== 
==2329== 
==2329== Process terminating with default action of signal 11 (SIGSEGV)
==2329==  Access not within mapped region at address 0x18
==2329==    at 0x4E4BA0F: H5S_close (H5S.c:448)
==2329==    by 0x48DB2B0: H5A__free (H5Aint.c:1166)
==2329==    by 0x4CCF6CF: H5O_attr_decode (H5Oattr.c:253)
==2329==    by 0x4CCF6CF: H5O_attr_shared_decode (H5Oshared.h:82)
==2329==    by 0x4D49613: H5O__msg_iterate_real (H5Omessage.c:1288)
==2329==    by 0x48DC6B1: H5A__compact_build_table (H5Aint.c:1544)
==2329==    by 0x4CD7C2F: H5O_attr_iterate_real (H5Oattribute.c:1283)
==2329==    by 0x4CD6DB0: H5O__attr_open_by_idx (H5Oattribute.c:611)
==2329==    by 0x48D6A92: H5A__open_by_idx (H5Aint.c:537)
==2329==    by 0x48B4F71: H5Aopen_by_idx (H5A.c:570)
==2329==    by 0x412A96: copy_attr (h5repack.c:364)
==2329==    by 0x432FFE: do_copy_refobjs (h5repack_refs.c:303)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==  If you believe this happened as a result of a stack
==2329==  overflow in your program's main thread (unlikely but
==2329==  possible), you can try to increase the size of the
==2329==  main thread stack using the --main-stacksize= flag.
==2329==  The main thread stack size used in this run was 8388608.
==2329== 
==2329== HEAP SUMMARY:
==2329==     in use at exit: 1,432,427 bytes in 3,349 blocks
==2329==   total heap usage: 7,306 allocs, 3,957 frees, 1,668,297 bytes allocated
==2329== 
==2329== Searching for pointers to 3,349 not-freed blocks
==2329== Checked 1,495,200 bytes
==2329== 
==2329== LEAK SUMMARY:
==2329==    definitely lost: 0 bytes in 0 blocks
==2329==    indirectly lost: 0 bytes in 0 blocks
==2329==      possibly lost: 0 bytes in 0 blocks
==2329==    still reachable: 1,432,427 bytes in 3,349 blocks
==2329==                       of which reachable via heuristic:
==2329==                         length64           : 9,732 bytes in 38 blocks
==2329==                         newarray           : 112 bytes in 7 blocks
==2329==         suppressed: 0 bytes in 0 blocks
==2329== Reachable blocks (those to which a pointer was found) are not shown.
==2329== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==2329== 
==2329== ERROR SUMMARY: 337 errors from 9 contexts (suppressed: 0 from 0)
==2329== 
==2329== 1 errors in context 1 of 9:
==2329== Invalid read of size 8
==2329==    at 0x4E4BA0F: H5S_close (H5S.c:448)
==2329==    by 0x48DB2B0: H5A__free (H5Aint.c:1166)
==2329==    by 0x4CCF6CF: H5O_attr_decode (H5Oattr.c:253)
==2329==    by 0x4CCF6CF: H5O_attr_shared_decode (H5Oshared.h:82)
==2329==    by 0x4D49613: H5O__msg_iterate_real (H5Omessage.c:1288)
==2329==    by 0x48DC6B1: H5A__compact_build_table (H5Aint.c:1544)
==2329==    by 0x4CD7C2F: H5O_attr_iterate_real (H5Oattribute.c:1283)
==2329==    by 0x4CD6DB0: H5O__attr_open_by_idx (H5Oattribute.c:611)
==2329==    by 0x48D6A92: H5A__open_by_idx (H5Aint.c:537)
==2329==    by 0x48B4F71: H5Aopen_by_idx (H5A.c:570)
==2329==    by 0x412A96: copy_attr (h5repack.c:364)
==2329==    by 0x432FFE: do_copy_refobjs (h5repack_refs.c:303)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==  Address 0x18 is not stack'd, malloc'd or (recently) free'd
==2329== 
==2329== 
==2329== 1 errors in context 2 of 9:
==2329== Invalid read of size 8
==2329==    at 0x483C98B: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x52238E8: H5VM_memcpyvv (H5VM.c:1712)
==2329==    by 0x49D9BAA: H5D__compact_readvv (H5Dcompact.c:294)
==2329==    by 0x4A3453D: H5D__select_io (H5Dselect.c:215)
==2329==    by 0x4A33630: H5D__select_read (H5Dselect.c:281)
==2329==    by 0x49DDCFA: H5D__contig_read (H5Dcontig.c:595)
==2329==    by 0x4A1C26B: H5D__read (H5Dio.c:600)
==2329==    by 0x4A1AF28: H5Dread (H5Dio.c:198)
==2329==    by 0x431F0C: do_copy_refobjs (h5repack_refs.c:240)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a89020 is 944 bytes inside a block of size 2,256 free'd
==2329==    at 0x48369AB: free (vg_replace_malloc.c:530)
==2329==    by 0x4CA854D: H5MM_xfree (H5MM.c:560)
==2329==    by 0x4DFD463: H5P__set_plist_cb (H5Pint.c:2905)
==2329==    by 0x4DFBE2E: H5P__do_prop (H5Pint.c:2640)
==2329==    by 0x4DFCBBE: H5P_set (H5Pint.c:3042)
==2329==    by 0x4A25F4D: H5D__layout_oh_read (H5Dlayout.c:666)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x430BF6: do_copy_refobjs (h5repack_refs.c:106)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==  Block was alloc'd at
==2329==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2329==    by 0x4DFCEFC: H5P__set_plist_cb (H5Pint.c:2877)
==2329==    by 0x4DFBE2E: H5P__do_prop (H5Pint.c:2640)
==2329==    by 0x4DFCBBE: H5P_set (H5Pint.c:3042)
==2329==    by 0x4A25F4D: H5D__layout_oh_read (H5Dlayout.c:666)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x430BF6: do_copy_refobjs (h5repack_refs.c:106)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329== 
==2329== 
==2329== 2 errors in context 3 of 9:
==2329== Invalid read of size 8
==2329==    at 0x483C97D: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x52238E8: H5VM_memcpyvv (H5VM.c:1712)
==2329==    by 0x49D9BAA: H5D__compact_readvv (H5Dcompact.c:294)
==2329==    by 0x4A3453D: H5D__select_io (H5Dselect.c:215)
==2329==    by 0x4A33630: H5D__select_read (H5Dselect.c:281)
==2329==    by 0x49DDCFA: H5D__contig_read (H5Dcontig.c:595)
==2329==    by 0x4A1C26B: H5D__read (H5Dio.c:600)
==2329==    by 0x4A1AF28: H5Dread (H5Dio.c:198)
==2329==    by 0x431F0C: do_copy_refobjs (h5repack_refs.c:240)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a89010 is 928 bytes inside a block of size 2,256 free'd
==2329==    at 0x48369AB: free (vg_replace_malloc.c:530)
==2329==    by 0x4CA854D: H5MM_xfree (H5MM.c:560)
==2329==    by 0x4DFD463: H5P__set_plist_cb (H5Pint.c:2905)
==2329==    by 0x4DFBE2E: H5P__do_prop (H5Pint.c:2640)
==2329==    by 0x4DFCBBE: H5P_set (H5Pint.c:3042)
==2329==    by 0x4A25F4D: H5D__layout_oh_read (H5Dlayout.c:666)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x430BF6: do_copy_refobjs (h5repack_refs.c:106)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==  Block was alloc'd at
==2329==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2329==    by 0x4DFCEFC: H5P__set_plist_cb (H5Pint.c:2877)
==2329==    by 0x4DFBE2E: H5P__do_prop (H5Pint.c:2640)
==2329==    by 0x4DFCBBE: H5P_set (H5Pint.c:3042)
==2329==    by 0x4A25F4D: H5D__layout_oh_read (H5Dlayout.c:666)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x430BF6: do_copy_refobjs (h5repack_refs.c:106)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329== 
==2329== 
==2329== 31 errors in context 4 of 9:
==2329== Invalid read of size 8
==2329==    at 0x483C937: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x52238E8: H5VM_memcpyvv (H5VM.c:1712)
==2329==    by 0x49D9BAA: H5D__compact_readvv (H5Dcompact.c:294)
==2329==    by 0x4A3453D: H5D__select_io (H5Dselect.c:215)
==2329==    by 0x4A33630: H5D__select_read (H5Dselect.c:281)
==2329==    by 0x49DDCFA: H5D__contig_read (H5Dcontig.c:595)
==2329==    by 0x4A1C26B: H5D__read (H5Dio.c:600)
==2329==    by 0x4A1AF28: H5Dread (H5Dio.c:198)
==2329==    by 0x431F0C: do_copy_refobjs (h5repack_refs.c:240)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a88c40 is 16 bytes after a block of size 1,408 in arena "client"
==2329== 
==2329== 
==2329== 31 errors in context 5 of 9:
==2329== Invalid read of size 8
==2329==    at 0x483C92F: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x52238E8: H5VM_memcpyvv (H5VM.c:1712)
==2329==    by 0x49D9BAA: H5D__compact_readvv (H5Dcompact.c:294)
==2329==    by 0x4A3453D: H5D__select_io (H5Dselect.c:215)
==2329==    by 0x4A33630: H5D__select_read (H5Dselect.c:281)
==2329==    by 0x49DDCFA: H5D__contig_read (H5Dcontig.c:595)
==2329==    by 0x4A1C26B: H5D__read (H5Dio.c:600)
==2329==    by 0x4A1AF28: H5Dread (H5Dio.c:198)
==2329==    by 0x431F0C: do_copy_refobjs (h5repack_refs.c:240)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a88c38 is 16 bytes after a block of size 1,400 alloc'd
==2329==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2329==    by 0x4D37D2B: H5O__layout_copy (H5Olayout.c:741)
==2329==    by 0x4D452C1: H5O_msg_read_oh (H5Omessage.c:548)
==2329==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2329==    by 0x4A258AA: H5D__layout_oh_read (H5Dlayout.c:634)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x430BF6: do_copy_refobjs (h5repack_refs.c:106)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329== 
==2329== 
==2329== 31 errors in context 6 of 9:
==2329== Invalid read of size 8
==2329==    at 0x483C924: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x52238E8: H5VM_memcpyvv (H5VM.c:1712)
==2329==    by 0x49D9BAA: H5D__compact_readvv (H5Dcompact.c:294)
==2329==    by 0x4A3453D: H5D__select_io (H5Dselect.c:215)
==2329==    by 0x4A33630: H5D__select_read (H5Dselect.c:281)
==2329==    by 0x49DDCFA: H5D__contig_read (H5Dcontig.c:595)
==2329==    by 0x4A1C26B: H5D__read (H5Dio.c:600)
==2329==    by 0x4A1AF28: H5Dread (H5Dio.c:198)
==2329==    by 0x431F0C: do_copy_refobjs (h5repack_refs.c:240)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a88c30 is 8 bytes after a block of size 1,400 alloc'd
==2329==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2329==    by 0x4D37D2B: H5O__layout_copy (H5Olayout.c:741)
==2329==    by 0x4D452C1: H5O_msg_read_oh (H5Omessage.c:548)
==2329==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2329==    by 0x4A258AA: H5D__layout_oh_read (H5Dlayout.c:634)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x430BF6: do_copy_refobjs (h5repack_refs.c:106)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329== 
==2329== 
==2329== 32 errors in context 7 of 9:
==2329== Invalid read of size 8
==2329==    at 0x483C93F: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x52238E8: H5VM_memcpyvv (H5VM.c:1712)
==2329==    by 0x49D9BAA: H5D__compact_readvv (H5Dcompact.c:294)
==2329==    by 0x4A3453D: H5D__select_io (H5Dselect.c:215)
==2329==    by 0x4A33630: H5D__select_read (H5Dselect.c:281)
==2329==    by 0x49DDCFA: H5D__contig_read (H5Dcontig.c:595)
==2329==    by 0x4A1C26B: H5D__read (H5Dio.c:600)
==2329==    by 0x4A1AF28: H5Dread (H5Dio.c:198)
==2329==    by 0x431F0C: do_copy_refobjs (h5repack_refs.c:240)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a88c28 is 0 bytes after a block of size 1,400 alloc'd
==2329==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2329==    by 0x4D37D2B: H5O__layout_copy (H5Olayout.c:741)
==2329==    by 0x4D452C1: H5O_msg_read_oh (H5Omessage.c:548)
==2329==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2329==    by 0x4A258AA: H5D__layout_oh_read (H5Dlayout.c:634)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x430BF6: do_copy_refobjs (h5repack_refs.c:106)
==2329==    by 0x41FF8F: copy_objects (h5repack_copy.c:361)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329== 
==2329== 
==2329== 52 errors in context 8 of 9:
==2329== Invalid read of size 2
==2329==    at 0x483C9D8: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x4D325FD: H5O__layout_decode (H5Olayout.c:213)
==2329==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2329==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2329==    by 0x4A258AA: H5D__layout_oh_read (H5Dlayout.c:634)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==2329==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a5e89e is 6 bytes after a block of size 280 alloc'd
==2329==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2329==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==2329==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==2329==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==2329==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==2329==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==2329==    by 0x495AE26: H5C_protect (H5C.c:2357)
==2329==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==2329==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==2329==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==2329==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==2329==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==2329==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==2329==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==2329== 
==2329== 
==2329== 156 errors in context 9 of 9:
==2329== Invalid read of size 2
==2329==    at 0x483C9E7: memmove (vg_replace_strmem.c:1270)
==2329==    by 0x4D325FD: H5O__layout_decode (H5Olayout.c:213)
==2329==    by 0x4D44FC9: H5O_msg_read_oh (H5Omessage.c:541)
==2329==    by 0x4D44834: H5O_msg_read (H5Omessage.c:480)
==2329==    by 0x4A258AA: H5D__layout_oh_read (H5Dlayout.c:634)
==2329==    by 0x4A097D0: H5D__open_oid (H5Dint.c:1489)
==2329==    by 0x4A097D0: H5D_open (H5Dint.c:1281)
==2329==    by 0x4A08528: H5D__open_name (H5Dint.c:1215)
==2329==    by 0x4996485: H5Dopen2 (H5D.c:291)
==2329==    by 0x4195D8: do_copy_objects (h5repack_copy.c:764)
==2329==    by 0x4195D8: copy_objects (h5repack_copy.c:353)
==2329==    by 0x410FFD: h5repack (h5repack.c:54)
==2329==    by 0x40931F: main (h5repack_main.c:769)
==2329==  Address 0x5a5e898 is 0 bytes after a block of size 280 alloc'd
==2329==    at 0x483577F: malloc (vg_replace_malloc.c:299)
==2329==    by 0x4B4FD63: H5FL_malloc (H5FL.c:243)
==2329==    by 0x4B4FD63: H5FL_blk_malloc (H5FL.c:921)
==2329==    by 0x4CE5CBA: H5O__chunk_deserialize (H5Ocache.c:1350)
==2329==    by 0x4CE14B5: H5O__cache_deserialize (H5Ocache.c:355)
==2329==    by 0x495AE26: H5C_load_entry (H5C.c:6725)
==2329==    by 0x495AE26: H5C_protect (H5C.c:2357)
==2329==    by 0x48EEB4F: H5AC_protect (H5AC.c:1624)
==2329==    by 0x4D28200: H5O_protect (H5Oint.c:1099)
==2329==    by 0x4D2CC3F: H5O_get_info (H5Oint.c:2243)
==2329==    by 0x4BAAF1A: H5G_loc_info_cb (H5Gloc.c:687)
==2329==    by 0x4BD9ECF: H5G__traverse_real (H5Gtraverse.c:626)
==2329==    by 0x4BD71F7: H5G_traverse (H5Gtraverse.c:850)
==2329==    by 0x4BAAC30: H5G_loc_info (H5Gloc.c:730)
==2329== 
==2329== ERROR SUMMARY: 337 errors from 9 contexts (suppressed: 0 from 0)
Segmentation fault






```
---
