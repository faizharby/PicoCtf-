# Studi Kasus: Analisis Binary static

### Deskripsi
Pada studi kasus ini, kita diberikan sebuah file bernama static dalam direktori Downloads. Targetnya adalah menemukan flag tersembunyi yang berkaitan dengan tantangan keamanan atau CTF (Capture The Flag).

### Langkah-langkah Analisis
1. Persiapan Awal

- Pindah ke direktori Downloads.

- Terdapat 3 file/ folder: home, static, dan warm.

- Mengubah permission file static agar bisa dieksekusi:

```
chmod +x static
```
2.  Eksekusi Binary

- Menjalankan file static:

```
./static
```
- Output:
```
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
```
- Ini mengindikasikan bahwa flag memang tersembunyi, namun tidak langsung ditampilkan.

3. Kesalahan Input
- Ada salah ketik cad static (harusnya mungkin mau cat static atau strings static), yang menghasilkan error.

4. Pencarian Manual

- Menggunakan perintah strings untuk mencari string ASCII dalam file binary:
```
strings static
```
- Output strings menemukan banyak data binari standar ELF, tetapi di antaranya ditemukan flag:
```
picoCTF{d15a5m_t34s3r_ccb2b43e}
```
5. Logging Output
- Output dari eksekusi ./static juga dicatat ke file menggunakan tee:
```
./static | tee output.txt
```

### Tools yang Digunakan
- chmod: Mengubah permission file.

- ./binary: Menjalankan file executable.

- strings: Menarik semua string ASCII printable dari file binary.

- tee: Menyimpan output ke file sambil tetap menampilkan di terminal.

## Hasil Akhir
- Flag yang ditemukan adalah:
```
picoCTF{d15a5m_t34s3r_ccb2b43e}
```
## Kesimpulan
#### Studi kasus ini mengajarkan pentingnya teknik dasar reverse engineering, seperti:

- Mengeksekusi file dengan aman.

- Menggunakan tool sederhana (strings) untuk menemukan hidden information.

- Menganalisis output executable sebelum beralih ke teknik yang lebih kompleks seperti disassembly atau debugging.

```
bash
──(kali㉿kali)-[~]
└─$ cd Downloads
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
home  static  warm
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ chmod +x static
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ ./static 
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ cad static     
Command 'cad' not found, did you mean:
  command 'yad' from deb yad
8#TT 1tt$D���o�Nfrom deb capistrano
�� � @ @ �0@)▒' p�▒V``�^y▒�                                                                                                                                                                                                                                           bi-acc-download
┌──(kali㉿kali)-[~/Downloads]
└─$ cd Downloads
cd: no such file or directory: Downloads
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ cd Downloads
cd: no such file or directory: Downloads
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
home  static  warm
8#TT 1tt$D���o�N                                                                                                                                                                                                                           
�� � @ @ �0@)▒)-p�▒V``�^y▒�                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
home  static  warm
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ chmod +x static
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ ./static | tee output.txt

Oh hai! Wait what? A flag? Yes, it's around here somewhere!
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Downloads]
└─$ strings static                                            
/lib64/ld-linux-x86-64.so.2
>1FbY]
libc.so.6
puts
__cxa_finalize
__libc_start_main
GLIBC_2.2.5
_ITM_deregisterTMCloneTable
__gmon_start__
_ITM_registerTMCloneTable
AWAVI
AUATL
[]A\A]A^A_
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
;*3$"
picoCTF{d15a5m_t34s3r_ccb2b43e}
GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.0
crtstuff.c
deregister_tm_clones
__do_global_dtors_aux
completed.7698
__do_global_dtors_aux_fini_array_entry
frame_dummy
__frame_dummy_init_array_entry
static.c
__FRAME_END__
__init_array_end
_DYNAMIC
__init_array_start
__GNU_EH_FRAME_HDR
_GLOBAL_OFFSET_TABLE_
__libc_csu_fini
_ITM_deregisterTMCloneTable
puts@@GLIBC_2.2.5
_edata
__libc_start_main@@GLIBC_2.2.5
__data_start
__gmon_start__
__dso_handle
_IO_stdin_used
__libc_csu_init
__bss_start
main
__TMC_END__
_ITM_registerTMCloneTable
flag
__cxa_finalize@@GLIBC_2.2.5
.symtab
.strtab
.shstrtab
.interp
.note.ABI-tag
.note.gnu.build-id
.gnu.hash
.dynsym
.dynstr
.gnu.version
.gnu.version_r
.rela.dyn
.rela.plt
.init
.plt.got
.text
.fini
.rodata
.eh_frame_hdr
.eh_frame
.init_array
.fini_array
.dynamic
.data
.bss
.comment
```