# Studi Kasus: Python Wrangling pico CTF
### Pada studi kasus ini, kita diberikan beberapa file dalam direktori Downloads:
```
- ende.py (script Python untuk encrypt/decrypt file),
```
```
flag.txt.en (file terenkripsi),
```
```
pw.txt (password yang digunakan untuk dekripsi).
```
Targetnya adalah mendekripsi file flag.txt.en untuk mendapatkan flag dari tantangan CTF (Capture The Flag).

### Langkah-langkah Analisis
1. Persiapan Awal
- Pindah ke direktori Downloads:
```
cd Downloads
```
- Melihat isi direktori dengan ls:
```
Addadshashanammu  ende.py  flag.txt.en  home  pw.txt
```
2. Memeriksa Script ende.py
- Membaca isi ende.py:
    - Script ini menggunakan library cryptography.fernet untuk enkripsi dan dekripsi file.
    - Program memiliki tiga mode:
        - -e: Encrypt file.
        - -d: Decrypt file.
        - -h atau --help: Menampilkan bantuan penggunaan.
    - Password dimasukkan secara manual atau sebagai argumen tambahan.
    - Password dienkode ke Base64 sebelum digunakan sebagai key Fernet.
3. Melihat File Encrypted dan Password
- Membaca isi file flag.txt.en:
    - Berisi string acak hasil enkripsi.
- Membaca isi pw.txt:
 ```
6008014f6008014f6008014f6008014f
```
- Ini adalah password yang akan digunakan untuk dekripsi.
4. Melakukan Dekripsi File
- Menjalankan dekripsi menggunakan ende.py:
```
python3 ende.py -d flag.txt.en
```
- Program meminta password:
    - Memasukkan password yang ada di pw.txt.
- Output setelah dekripsi:
```
picoCTF{4p0110_1n_7h3_h0us3_6008014f}
```

### Hasil Akhir
```
python3 ende.py -d flag.txt.en
```


