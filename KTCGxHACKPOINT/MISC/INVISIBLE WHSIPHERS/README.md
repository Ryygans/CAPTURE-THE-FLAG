# 🤖 KTCG X HACKPOINT CTF
## 🌐 MISC Challenge: Invisible Whisphers
### 🟢 Tingkat Kesulitan: MUDAH | 🎯 Poin: 100

# 📖 Ringkasan (Overview)
Selamat datang di challenge MISC, **Invisible Whisphers**!<br>
Dalam tantangan ini, peserta akan diperkenalkan dengan dasar MISC. Peserta diberikan sebuah deskripsi challenge yaitu:<br>
```bash
Seseorang meninggalkan laporan harian di server yang sudah dibobol.
Isinya? Biasa saja. Atau... memang terlihat biasa?

Kata orang, yang berbahaya bukan yang terlihat, tapi yang tidak terlihat.
```
File bisa download <a href="https://ctf.ktcg.my.id/files/32a67c23c9e9720335b21af90d30e786/report.txt">di sini</a>.

# Proof of Concept
```bash
# Langkah 1: Buka halaman website KTCG CTF dan login menggunakan akun Anda.

# Langkah 2: Pilih menu Challenges, pilih kategori MISC, lalu pilih tantangan Invisible Whisphers.

# Langkah 3: Setelah membaca teks deskripsi dari challenge tersebut, silakan unduh file report.txt yang tertera.

# Langkah 4: Salin kode Python di bawah ini, simpan dengan nama solver.py di direktori yang sama dengan file report.txt, lalu jalankan melalui terminal.
(Python)
#!/usr/bin/env python3
# Ganti 'report.txt' jika nama file yang kamu download berbeda
with open('report.txt', 'rb') as f:
    content = f.read().decode('utf-8', errors='ignore')
bits = []
for line in content.splitlines():
    # Ambil whitespace di akhir baris
    ws = line[len(line.rstrip()):]
    for c in ws:
        if c == '\t':
            bits.append('1')
        elif c == ' ':
            bits.append('0')

# Gabungkan bits jadi byte (8 bit per byte)
bits_str = ''.join(bits)
# Membaca sebagai biner biasa
for i in range(0, len(bits_str), 8):
    byte = bits_str[i:i+8]
    if len(byte) == 8:
        print(chr(int(byte, 2)), end='')
print()

# Langkah 5: Setelah menjalankan kode di atas, Anda akan mendapatkan flagnya di terminal.
```

<h1>✅FLAG BERHASIL DI DAPATKAN!</h1>
> flag: KTCG{wh1t3sp4c3_1s_n0t_3mpty}

# 🧠 Hasil Pembelajaran (Learning Outcomes)
1. Memahami konsep Steganografi, khususnya menyembunyikan informasi di dalam karakter yang tidak terlihat (Whitespace Steganography).

2. Mempelajari cara mengekstrak bit tersembunyi (Tab dan Spasi) menggunakan skrip otomatisasi Python.

3. Menganalisis karakteristik manipulasi file teks di luar teks yang terlihat (visible text).

# 🛠️ Alat yang Digunakan (Opsional)
- Browser (Chrome, Firefox, dll)

- Python 3 (Untuk menjalankan skrip solver)

- Text Editor (VS Code, Notepad++, atau Nano)

# 👨‍💻 Researcher
> zoxxtzy

# 📌 Tag
> #steganography #misc #ctf #easy #ktcg #hackpoint

# ⚠️ Sanggahan (Disclaimer)
Tantangan ini adalah bagian dari kompetisi CTF dan dibuat hanya untuk tujuan edukasi.
Jangan mencoba menerapkan teknik ini pada sistem atau aplikasi milik orang lain tanpa izin resmi dari pemiliknya.
