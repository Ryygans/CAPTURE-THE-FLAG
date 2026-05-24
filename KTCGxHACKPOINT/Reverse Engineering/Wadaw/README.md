# 🤖 KTCG X HACKPOINT CTF
## 🌐 REVERSE ENGINEERING Challenge: Wadaw
### 🟢 Tingkat Kesulitan: MUDAH | 🎯 Poin: 100

# 📖 Ringkasan (Overview)
Selamat datang di challenge reverse engineering, **Wadaw**!<br>
Dalam tantangan ini, peserta akan diperkenalkan dengan dasar Reverse Engineering. Peserta diberikan sebuah file yang mungkin itu adalah sebuah aplikasi.<br>
File tersebut harus di bedah oleh peserta untuk mendapatkan flag.

# Proof of Concept
```bash
# Langkah 1: Buka halaman website [https://ctf.ktcg.my.id/](https://ctf.ktcg.my.id/) dan login menggunakan akun anda.

# Langkah 2: Pilih menu Challenges dan pilih chall REVERSE ENGINEERING lalu pilih kembali chall Wadaw.

# Langkah 3: Download file 'beginner_auth' yang sudah panitia siapkan, lalu buka direktori download tersebut di terminal.

# Langkah 4: Berikan izin eksekusi pada file agar bisa berinteraksi atau dianalisis lebih lanjut:
chmod +x beginner_auth

# Langkah 5: Lakukan analisis statis awal menggunakan perintah 'strings' untuk melihat teks yang tertanam di dalam biner:
strings beginner_auth
# Catatan: Setelah dijalankan akan muncul banyak string. Jangan terkecoh jika kamu melihat karakter yang menyerupai flag, karena itu hanyalah jebakan (rabbit hole).

# Langkah 6: Gunakan tool 'objdump' untuk melakukan disassembly dan melihat instruksi assembly serta kode hex biner tersebut:
objdump -d beginner_auth

# Analisis: Pada hasil disassembly, ditemukan banyak instruksi pemindahan byte seperti 'cmpb' (compare byte) atau 'movb' (move byte) yang menyimpan karakter flag dalam bentuk hex ASCII secara terpisah.
# Contoh potongan hex yang ditemukan secara berurutan:
# 4b, 54, 43, 47 ...

# Langkah 7: Terjemahkan nilai hex tersebut menjadi teks ASCII yang dapat dibaca menggunakan perintah 'xxd':
echo 4b544347 | xxd -r -p
# Output: KTCG

# Langkah 8: Susun seluruh byte hex tersembunyi yang ditemukan di dalam fungsi pengecekan tersebut dari awal hingga akhir, konversikan semuanya, dan flag utuh akan langsung terkonstruksi.
```

<h1>✅FLAG BERHASIL DI DAPATKAN!</h1>
> flag: KTCG{welcome_to_reverse}

# 🧠 Hasil Pembelajaran (Learning Outcomes)
1. Memahami cara melakukan inspeksi awal pada file biner tanpa mengeksekusinya menggunakan perintah strings.

2. Mempelajari cara membaca kode mesin (assembly) menggunakan tool objdump untuk melihat alur logika program dan variabel tersembunyi.

3. Mengetahui cara menerjemahkan data mentah berupa bilangan heksadesimal menjadi karakter string yang dapat dibaca menggunakan utilitas xxd.

4. Memahami teknik obfuscation dasar seperti memecah string flag menjadi potongan byte-by-byte di dalam memori untuk menghindari deteksi alat otomatis.

# 🛠️ Alat yang Digunakan (Opsional)
- Linux Terminal / WSL (Untuk menjalankan perintah berbasis Unix)
- GNU Binutils (strings, objdump)
- xxd (Untuk konversi hexdump balik ke ASCII)
- Ghidra / IDA Pro (Alternatif opsional untuk dekompilasi yang lebih visual)

# 👨‍💻 Researcher
> zoxxtzy

# 📌 Tag
> #reverse-engineering #ctf #easy #ktcg #hackpoint #binutils #assembly

# ⚠️ Sanggahan (Disclaimer)
Tantangan ini adalah bagian dari kompetisi CTF dan dibuat hanya untuk tujuan edukasi.
Jangan mencoba menerapkan teknik ini pada sistem atau aplikasi milik orang lain tanpa izin resmi dari pemiliknya.
