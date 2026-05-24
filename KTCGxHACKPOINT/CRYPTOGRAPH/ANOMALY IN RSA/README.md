# 🤖 KTCG X HACKPOINT CTF
## 🌐 Cryptography Challenge: ANOMALY IS RSA
### 🟢 Tingkat Kesulitan: MUDAH | 🎯 Poin: 100

# 📖 Ringkasan (Overview)
Selamat datang di challenge Cryptography, **ANOMALY IN RSA**!<br>
Dalam tantangan ini, peserta akan diberikan kode RSA kembali namun kode tersebut nampak berbeda karena harus di faktorisasi terlebih dahulu sebelum<br>
dapat dijalankan dan mendapatkan flagnya.

# Proof of Concept
```
# Langkah 1: buka website https://ctf.ktcg.my.id lalu login menggunakan akun anda

# Langkah 2: masuk pada halaman challenge dan pilih challenge Cryptography lalu pilih chall WELCOME TO RSA

# Langkah 3: download file chall.enc yang telah disediakan oleh panitia lalu masukkan kode rsa itu ke dalam kode ini
(Python)
from Crypto.Util.number import *

p = 153919420601446755490223746618451842323214555800455799981440742137537330752539
q = 171858826725345759160538740176378135899732704771146654271374529324029272379378
e = 65537
c = 5735343971087544432347819427681018325493421110116101269342696708457714448009933361858073988005170184346715596771709658832500660155785371410044594233918001

n = p*q
phi = (p-1)*(q-1)

d = inverse(e, phi)

m = pow(c, d, n)

print(long_to_bytes(m).decode())

# Langkah 4: jalankan kode tadi dan flag/pesan rahasia yang tersembunyi akan langsung muncul di terminal atau layar output kamu.
Copy flag tersebut dan submit ke dalam kolom pengumpulan flag di website CTF.
```
<h1>✅FLAG BERHASIL DI DAPATKAN!</h1>
> flag: KTCG{xxxxx_xxx_xxx_xxxxxx}

# 🧠 Hasil Pembelajaran (Learning Outcomes)
1. Mempelajari bagaimana cara kerja dari enkripsi RSA
2. Memahami dan mempelajari perhitungan dasar dari rumus perhitungan RSA serta cara Mendekripsi kode tersebut

# 🛠️ Alat yang Digunakan (Opsional)
- Browser (Chrome, firefox, dll)
- Code Editor (VS code, MU Editor, dll)
- Factordb (Untuk memfaktorkan nilai $N$ yang lemah)
  
# 👨‍💻 Researcher
> zoxxtzy

#📌 Tag
> #cryptography #ctf #easy #ktcg #hackpoint
# ⚠️ Sanggahan (Disclaimer)
Tantangan ini adalah bagian dari kompetisi CTF dan dibuat hanya untuk tujuan edukasi.<br>
Jangan mencoba menerapkan teknik ini pada sistem lain tanpa izin resmi dari pemiliknya.
