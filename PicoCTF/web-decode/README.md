========================================================
                    WEB DECODE
                    picoCTF
========================================================

[SUMMARY]
Web Decode adalah challenge kategori Web dari picoCTF
yang menguji kemampuan dasar dalam melakukan
inspeksi source code dan decoding string.

Challenge ini biasanya mengharuskan peserta untuk:
- Melihat source HTML
- Menemukan string tersembunyi
- Melakukan decoding (umumnya Base64)
- Mendapatkan flag dalam format picoCTF{...}


--------------------------------------------------------
[CHALLENGE INFORMATION]
--------------------------------------------------------

Nama Challenge : Web Decode
Kategori       : Web Exploitation
Platform       : picoCTF
Level          : Easy / Beginner

Format Flag    : picoCTF{...}


--------------------------------------------------------
[TOOLS YANG DIGUNAKAN]
--------------------------------------------------------

1. Browser (Chrome / Firefox)
2. DevTools (Inspect Element / View Source)
3. Base64 Decoder (CyberChef / terminal / online tool)


--------------------------------------------------------
[PROOF OF CONCEPT]
--------------------------------------------------------
bash
```
1. Buka halaman challenge yang diberikan oleh picoCTF.

2. Klik kanan → View Page Source
   atau tekan CTRL + U.

3. Cari string yang terlihat seperti encoding.
   Biasanya berbentuk seperti ini:

   cGljb0NURnt3ZWJfZGVjb2RlX2lzX2Z1bn0=

4. Decode string tersebut menggunakan Base64 decoder.

   Contoh via terminal:

   echo cGljb0NURnt3ZWJfZGVjb2RlX2lzX2Z1bn0= | base64 -d

5. Setelah di-decode, akan muncul flag:

   picoCTF{web_succ3ssfully_d3c0ded_yourformat}
```

--------------------------------------------------------
[PENJELASAN]
--------------------------------------------------------

Challenge ini mengajarkan bahwa:
- Tidak semua informasi tersembunyi benar-benar aman.
- Developer sering meninggalkan data sensitif di source code.
- Encoding ≠ Encryption.
- Base64 hanya encoding, bukan proteksi keamanan.

Selalu biasakan untuk:
- Inspect element
- View source
- Analisa komentar HTML
- Cek file tersembunyi


--------------------------------------------------------
[LESSON LEARNED]
--------------------------------------------------------

- Pahami perbedaan encoding dan encryption.
- Biasakan membaca source code.
- Jangan langsung menyerah sebelum cek DevTools.


--------------------------------------------------------
[GREETING]
--------------------------------------------------------

Terima kasih sudah membaca write-up ini.
Gunakan sebagai latihan dasar sebelum lanjut
ke challenge web exploitation yang lebih kompleks.

Keep hacking & keep learning 🔥

Hunter: @trzy

========================================================
