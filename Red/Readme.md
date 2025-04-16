# Laporan Analisis Steganografi & Forensik Digital

## Identifikasi Masalah
Data yang diberikan mengandung potongan informasi tersembunyi dalam berbagai format (teks, encoding, binary). Tujuan analisis adalah mengidentifikasi flag tersembunyi dan pola mencurigakan.

---

## Metodologi Analisis
1. **Identifikasi Awal**:
   - Ekstraksi semua teks dari output.
   - Deteksi encoding (Base64, Hex, dll.).
   - Analisis pola berulang/aneh.

2. **Tools Digunakan**:
   - `base64` (decode/encode)
   - `binwalk` (analisis file binary)
   - `xxd` (hex dump)
   - `gpg` (untuk OpenPGP keys)
   - `steghide` (steganografi gambar)

---

## Hasil Analisis Lengkap

### 1. Flag Utama (Terkonfirmasi)
- **Lokasi**: `b1,rgba,lsb,xy`
- **Data Mentah**:
  ```text
  cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==