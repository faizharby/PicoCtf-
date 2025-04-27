# Studi Kasus: Magikarp Ground Mission Pico CTF
Dalam tantangan ini, pemain diminta untuk terhubung ke server CTF melalui SSH, lalu mengikuti petunjuk untuk mengumpulkan potongan flag dari beberapa file yang tersebar di filesystem Linux.
Langkah-langkah melibatkan navigasi dasar filesystem (cd, ls, cat) serta pemahaman penggunaan direktori seperti / (root) dan ~ (home).

### Langkah-Langkah yang Dilakukan
1. Login sebagai root user (opsional, untuk setup lokal):
```
sudo su
```
2. SSH ke server remote:
```
ssh ctf-player@venus.picoctf.net -p 59388
```
- Menambahkan fingerprint SSH untuk koneksi pertama kali.

- Login dengan password ctf-player yang diberikan.
3. Melihat daftar file di direktori awal (ls):
- Menemukan:
```
1of3.flag.txt
```
```
instructions-to-2of3.txt
```
4. Membaca isi file 1of3.flag.txt:
```
cat 1of3.flag.txt
```
- Output: picoCTF{xxsh_
5. Membaca instruksi untuk tahap berikutnya:
```
cat instructions-to-2of3.txt
```
- Petunjuk: "Next, go to the root of all things, more succinctly /"
6. Pindah ke direktori root (/) dan melihat file baru:
```
cd /
ls
```
- Menemukan:
```
\2of3.flag.txt
```
```
instructions-to-3of3.txt
```
7. Membaca isi file 2of3.flag.txt:
```
cat 2of3.flag.txt
```
- Output: 0ut_0f_\/\/4t3r_
8. Membaca instruksi terakhir:
```
cat instructions-to-3of3.txt
```
- Petunjuk: "go home... more succinctly ~
9. Navigasi ke home directory ~:
```
cd ~
pwd
```
- Berada di /home/ctf-player/
10. Melihat dan membaca file terakhir 3of3.flag.txt:
```
cat 3of3.flag.txt
```
- Output: c1754242}

### Flag Akhir
- Jika semua bagian digabungkan:
```
picoCTF{xxsh_0ut_0f_\/\/4t3r_c1754242}
```

Ringkasan Struktur File
```
Lokasi  	        File            	Isi
~/  	            1of3.flag.txt	picoCTF{xxsh_
/	                2of3.flag.txt	0ut_0f_\/\/4t3r_
/home/ctf-player/	3of3.flag.txt	c1754242}
```
### Skill yang Dipelajari
- Menggunakan ssh untuk remote access.

- Navigasi file system Linux (cd, ls, pwd, cat).

- Membaca dan mengikuti instruksi berbasis teks.

- Menyusun informasi dari beberapa sumber untuk membentuk satu jawaban utuh (flag).