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