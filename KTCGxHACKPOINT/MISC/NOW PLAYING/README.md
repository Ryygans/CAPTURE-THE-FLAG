# 🤖 KTCG X HACKPOINT CTF

## 🌐 MISC Challenge: Now Playing...
### 🟢 Tingkat Kesulitan: MUDAH | 🎯 Poin: 100

---

## 📖 Ringkasan (Overview)
Selamat datang di challenge MISC, **Now Playing...**!

Tantangan ini mengajak peserta untuk bersantai sejenak mendengarkan musik, namun tetap harus jeli. Peserta diberikan sebuah tautan *playlist* Spotify dan diminta untuk menemukan pesan rahasia yang tersembunyi di dalam daftar lagu tersebut.

* **Deskripsi:** > Coba aja buka si bang. Kamu mungkin suka deh.
* **Tautan Musik:** [Spotify Playlist](https://open.spotify.com/playlist/4rOrlzl4RmDoyPYdBUUkFW?si=UAPzfz2LQsi45Jp5AGbRKQ&pi=X-zqnvssTUe17&nd=1&dlsi=6769bc8b43144d60)
* **Format Flag:** `KTCG{...}`

---

## 💻 Proof of Concept

* **Langkah 1:** Buka tautan *playlist* Spotify yang telah disediakan di dalam deskripsi *challenge*.
* **Langkah 2:** Perhatikan urutan judul lagu yang ada di dalam *playlist* tersebut dari atas ke bawah.
* **Langkah 3:** Gunakan teknik **Acrostic**, yaitu mengambil huruf pertama dari setiap judul lagu secara berurutan dengan memperhatikan sensitivitas huruf kapital dan huruf kecil (*case-sensitive*).
* **Langkah 4:** Sebagai ilustrasi, susunan huruf awal dari setiap lagu di *playlist* tersebut akan membentuk kata:
  * Lagu 1 dimulai dengan huruf: **L**
  * Lagu 2 dimulai dengan huruf: **I**
  * Lagu 3 dimulai dengan huruf: **S**
  * ... *(dan seterusnya)*
* **Langkah 5:** Bungkus kumpulan huruf yang berhasil tersusun ke dalam format flag `KTCG{...}`.

### ✅ FLAG BERHASIL DIDAPATKAN!
> **Flag:** `KTCG{LISTEN_cLOSELY}`

---

## 🧠 Hasil Pembelajaran (Learning Outcomes)
1. Memahami konsep **Acrostic Puzzle**, sebuah teknik klasik menyembunyikan pesan rahasia menggunakan huruf pertama dari tiap baris teks, daftar kata, atau judul lagu.
2. Melatih kemampuan analisis dan kejelian (*attention to detail*) dalam mengenali pola tidak biasa pada platform pihak ketiga (Spotify) yang sering digunakan dalam tantangan MISC/OSINT.
3. Menyadari bahwa dalam CTF, petunjuk dan informasi sensitif bisa disembunyikan di media apa saja, termasuk media hiburan seperti *playlist* musik.

---

## 🛠️ Alat yang Digunakan
* Browser (Chrome, Firefox, dll)
* Aplikasi Spotify atau Web Player
* Notepad / Text Editor (Untuk mencatat dan menyusun huruf)

---

## 👨‍💻 Researcher
> zoxxtzy

---

## 📌 Tag
> `#misc` `#osint` `#acrostic` `#puzzle` `#easy` `#ktcg` `#hackpoint`

---

## ⚠️ Sanggahan (Disclaimer)
Tantangan ini adalah bagian dari kompetisi CTF dan dibuat hanya untuk tujuan edukasi. Jangan mencoba menerapkan teknik pengumpulan informasi ini untuk mengganggu privasi atau hak milik orang lain tanpa izin resmi.
