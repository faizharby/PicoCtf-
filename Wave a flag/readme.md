# Studi Kasus: Wave a flag pico CTF
Dalam studi kasus ini, kita menganalisis sebuah file biner bernama warm, yang ditemukan di direktori Downloads.
File ini merupakan file tipe ELF (Executable and Linkable Format) — format standar untuk file eksekusi di sistem berbasis Linux.

File warm ini berisi pesan interaktif, dan sebuah flag tersembunyi yang dapat ditemukan dengan memberikan argumen tertentu saat menjalankan file.

-  Struktur File
```
Downloads/
├── Addadshashanammu/
├── home/
├── warm
```
###  Langkah Eksekusi
1. Cek daftar file:
```
ls
```
2. Lihat isi file warm:
```
cat warm
```
-  Output berupa data biner yang tidak terbaca manusia (karena itu file eksekusi ELF).
3. Beri izin eksekusi:
```
chmod +x warm
```
-  Ini membuat file warm dapat dijalankan.
4. Jalankan file:
```
./warm
```
-  Output:
```
Hello user! Pass me a -h to learn what I can do!
```
5. Coba jalankan dengan parameter -h:
```
./warm -h
```
-  Output:
```
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}
```

### Flag
```
picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}
```