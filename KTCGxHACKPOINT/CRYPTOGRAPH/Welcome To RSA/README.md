# 🤖 KTCG X HACKPOINT CTF
## 🌐 Cryptography Challenge: WELCOME TO RSA
### 🟢 Tingkat Kesulitan: MUDAH | 🎯 Poin: 100

# 📖 Ringkasan (Overview)
Selamat datang di challenge Cryptography, **WELCOME TO RSA**!
Dalam tantangan ini, peserta akan diperkenalkan dengan salah satu teknik kriptografi yaitu RSA
Challenge ini menguji pemahaman dasar mengenai:
Perhitungan modulus RSA (N = p × q)
Totient Euler
Perhitungan private key
Proses dekripsi RSA

# Proof of Concept
```bash
# Langkah 1: buka website https://ctf.ktcg.my.id lalu login menggunakan akun anda

# Langkah 2: masuk pada halaman challenge dan pilih challenge Cryptography lalu pilih chall WELCOME TO RSA

# Langkah 3: download file chall.enc yang telah disediakan oleh panitia lalu masukkan kode rsa itu ke dalam kode ini
(Python)
from Crypto.Util.number import *

p = (kode_milikmu)
q = (kode_milikmu)
e = 65537
c = (kode_milikmu)

n = p*q
phi = (p-1)*(q-1)

d = inverse(e, phi)

m = pow(c, d, n)

print(long_to_bytes(m).decode())

# Langkah 4: jalankan kode tadi dan
```
<h1>✅ Flag berhasil di dapatkan!</h1>
> flag: KTCG{xxx_xxxx_xxx}

# 🧠 Hasil Pembelajaran (Learning Outcomes)
1. Mempelajari bagaimana cara kerja dari enkripsi RSA
2. Memahami dan mempelajari perhitungan dasar dari rumus perhitungan RSA serta cara Mendekripsi kode tersebut

# 🛠️ Alat yang Digunakan (Opsional)
- Browser (Chrome, firefox, dll)
- Code Editor (VS code, MU Editor, dll)

# 👨‍💻 Researcher
> zoxxtzy

# 📌 Tag
#cryptography #ctf #easy #ktcg #hackpoint

# ⚠️ Sanggahan (Disclaimer)
Tantangan ini adalah bagian dari kompetisi CTF dan dibuat hanya untuk tujuan edukasi.
Jangan mencoba menerapkan teknik ini pada sistem lain tanpa izin resmi dari pemiliknya.
