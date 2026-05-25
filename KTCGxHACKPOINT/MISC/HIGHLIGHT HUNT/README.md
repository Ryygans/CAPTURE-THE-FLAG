# 🤖 KTCG X HACKPOINT CTF
## 🌐 OSINT Challenge: Highlight Hunt
### 🟢 Tingkat Kesulitan: MUDAH | 🎯 Poin: 100

# 📖 Ringkasan (Overview)
Selamat datang di challenge osint, **Royal Command**!<br>
Dalam tantangan ini, peserta akan diperkenalkan dengan dasar OSINT. Peserta diberikan sebuah petunjuk yaitu:<br>
```bash
Kamu udah follow belum?

Mungkin ada sesuatu yang menarik di sana.
```
Clue yang cukup ambigu, follow apa dan di mana? tapi itulah challenge-nya!

# Proof of Concept
```bash
# Langkah 1: Buka halaman website [https://ctf.ktcg.my.id/](https://ctf.ktcg.my.id/) dan login menggunakan akun anda.

# Langkah 2: Pilih menu Challenges dan pilih chall OSINT lalu pilih kembali chall Higlight Hunt.

# Langkah 3: Setelah membaca teks deksripsi dari challenge tersebut, buka tab baru pada browser
kemudian cari Instagram dari KTCG Community

# Langkah 4: Pada postingan yang di sematkan terdapat kalimat acak seperti ini
"U29tZXdoZXJlLCB0aGVyZSdzIGEgZmxhZyB3YWl0aW5nLg==" (base64)
yang setelah di decode berupa clue lagi yaitu:
"Somewhere, there's a flag waiting."

saya berasumsi mungkin flagnya masih disimpan pada postingan yang ada, mungkin bisa saja di kolom komentar tapi ternyata tidak.

# Langkah 4: Buka Sorotan dengan title "Beginner CTF" dan lihat komentar pada postingan pertama.
Terdapat sebuah string aneh yang acak sepertinya adalah sebuah vigenere encode.
Setelah di decode maka akan muncul flag aslinya dan tinggal submit
```

<h1>✅FLAG BERHASIL DI DAPATKAN!</h1>
> flag: KTCG{st0ry_h1ghl1ght_n3v3r_f0rg3ts}

# 🧠 Hasil Pembelajaran (Learning Outcomes)
1. Memahami cara melakukan pencarian secara spesifik dan mendalam pada sebuah informasi secara umum

2. Mempelajari bagaimana cara menemukan informasi penting pada sebuah kata yang diubah agar sulit terbaca (enkripsi)

3. Mempelajari bagaimana cara mengubah dan membuat pesan tersembunyi menggunakan Vigenere Cipher

# 🛠️ Alat yang Digunakan (Opsional)
- Browser (Chrome, Firefox, dll)
- Tools Vigenere Decode (https://www.dcode.fr/vigenere-cipher)
- Akun Instagram (wajib karena clue dan enkripsi flag di sana)

# 👨‍💻 Researcher
> zoxxtzy

# 📌 Tag
> #osint #ctf #easy #ktcg #hackpoint

# ⚠️ Sanggahan (Disclaimer)
Tantangan ini adalah bagian dari kompetisi CTF dan dibuat hanya untuk tujuan edukasi.
Jangan mencoba menerapkan teknik ini pada sistem atau aplikasi milik orang lain tanpa izin resmi dari pemiliknya.
