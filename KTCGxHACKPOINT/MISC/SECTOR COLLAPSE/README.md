# 🤖 KTCG X HACKPOINT CTF

## 🌐 MISC Challenge: Sector-Collapse
### 🟢 Tingkat Kesulitan: MUDAH | 🎯 Poin: 100

---

## 📖 Ringkasan (Overview)
Selamat datang di challenge MISC, **Sector-Collapse**!

Dalam tantangan ini, peserta diminta untuk memulihkan pesan tersembunyi dari sebuah fragmen data yang rusak atau terhapus. Berdasarkan petunjuk yang diberikan, data tersebut tidak benar-benar hilang, melainkan disamarkan menggunakan manipulasi logika bitwise (XOR satu byte).

* **Deskripsi:** > A damaged storage device was recovered after a failed cleanup attempt. Most of the original data appears corrupted, partially overwritten, or missing entirely. However, some fragments may still contain traces of the original message. Can you recover what was lost?
* **Format Flag:** `KTCG{...}`
* **Author:** KTCG Community

### 💡 Petunjuk (Hint 1)
> *Try recovering the data with a single-byte XOR key.* (Coba pulihkan data menggunakan kunci XOR satu byte).

---

## 💻 Proof of Concept

* **Langkah 1:** Unduh berkas data mentah yang disediakan pada halaman tantangan.
* **Langkah 2:** Karena tantangan MISC ini memberikan petunjuk penggunaan *Single-Byte XOR*, kita bisa mencari kunci (key) antara nilai `0` sampai `255` yang jika di-XOR dengan data tersebut akan mengembalikan teks ke bentuk semula (berawalan `KTCG{`).
* **Langkah 3:** Salin skrip otomatisasi Python di bawah ini untuk melakukan pemindaian kunci secara cepat:

```python
#!/usr/bin/env python3

# Ganti 'file_tantangan.bin' dengan nama file yang kamu unduh
try:
    with open('file_tantangan.bin', 'rb') as f:
        data = f.read()
except FileNotFoundError:
    data = b'' 

print("[*] Mengekstrak data menggunakan teknik Single-Byte XOR...")

# Mencari semua kemungkinan kunci (0-255)
for key in range(256):
    decrypted = bytearray()
    for byte in data:
        decrypted.append(byte ^ key)
    
    # Memeriksa apakah hasil dekripsi memuat format flag
    try:
        result = decrypted.decode('utf-8', errors='ignore')
        if "KTCG{" in result:
            print(f"\n[+] Kunci Ditemukan! Key: {hex(key)} ({key})")
            print(f"[+] Flag: {result.strip()}")
            break
    except Exception:
        continue
```

* **Langkah 4**: Jalankan skrip tersebut di terminal untuk menyaring hasil secara otomatis dan memunculkan flag-nya.

<h1>✅ FLAG BERHASIL DIDAPATKAN!</h1>
> flag: KTCG{REDACTED}

## 🧠 Hasil Pembelajaran (Learning Outcomes)
1. Memahami fleksibilitas kategori MISC dalam CTF, di mana teknik manipulasi data dasar seperti XOR sering digunakan untuk menyembunyikan informasi.

2. Mempelajari logika dasar operasi bitwise XOR ($A \oplus B = C$) untuk melakukan pemulihan data (data recovery) sederhana pada fragmen teks/berkas digital.

3. Melatih kemampuan pembuatan skrip Python sederhana untuk mengotomatisasi pemecahan masalah (skrip solver) daripada melakukan dekripsi manual secara satu per satu.

## 🛠️ Alat yang Digunakan
- Browser (Chrome, Firefox, dll)

- Python 3 Interpreter (Untuk mengeksekusi skrip pemulihan data)

- Alat bantu opsional: CyberChef (Gunakan opsi XOR Brute Force)

# 👨‍💻 Researcher
> zoxxtzy

## 📌 Tag
> #misc #ctf #easy #xor-manipulation #ktcg #hackpoint

# ⚠️ Sanggahan (Disclaimer)
Tantangan ini adalah bagian dari kompetisi CTF dan dibuat hanya untuk tujuan edukasi. Jangan mencoba menerapkan teknik pemulihan atau manipulasi data ini pada sistem milik orang lain tanpa izin resmi.
