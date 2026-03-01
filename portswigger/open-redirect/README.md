========================================================
                  DOM-BASED OPEN REDIRECT
========================================================

# [SUMMARY]
Open Redirect adalah kerentanan keamanan yang terjadi<br>
ketika aplikasi web melakukan redirect ke URL lain<br>
tanpa validasi yang tepat.<br>

Pada DOM Open Redirect, proses redirect dilakukan<br>
menggunakan JavaScript di sisi client (browser),<br>
bukan langsung dari server.<br>

Akibatnya, attacker dapat memanipulasi parameter URL<br>
untuk mengarahkan korban ke website berbahaya.<br>


--------------------------------------------------------
# [CHALLENGE INFORMATION]
--------------------------------------------------------

Nama Bug       : Open Redirect<br>
Nama Challenge : DOM-BASED Open Redirect<br>
Platform       : PortSwigger Web Security Academy<br>
Level          : Apprentice (Mudah)<br>

Link Lab:<br>
https://portswigger.net/web-security/dom-based/open-redirection/lab-dom-open-redirection


--------------------------------------------------------
# [PREPARATION]
--------------------------------------------------------

1. Exploit Server
   (Klik "Go To Exploit Server" pada halaman lab)

2. Lab instance milik kamu


--------------------------------------------------------
# [PROOF OF CONCEPT]
--------------------------------------------------------
```
1. Buka lab kamu.
   Contoh format:
   https://LAB-ID-KAMU.web-security-academy.net/

2. Pilih salah satu postingan.

3. Buka DevTools dan cari script redirect
   pada tombol "Back to Blog".

   Contoh kode rentan:
   returnUrl = /url=(https?:\/\/.+)/.exec(location);
   if (returnUrl) {
       location.href = returnUrl[1];
   } else {
       location.href = "/";
   }

   Penjelasan:
   Script mengambil parameter "url=" dari query string
   lalu langsung melakukan redirect tanpa validasi.
4. Tambahkan parameter url secara manual.

   Struktur URL rentan:
   https://LAB-ID-KAMU.web-security-academy.net/post?postId=4&url=https://EXPLOIT-SERVER-ID.exploit-server.net/

5. Jika berhasil, halaman akan redirect
   ke domain attacker (Exploit Server).
```

--------------------------------------------------------
# [WHY THIS IS VULNERABLE]
--------------------------------------------------------

- Tidak ada validasi terhadap parameter "url"
- Tidak ada whitelist domain
- location.href digunakan langsung dari input user

Seharusnya developer:
- Membatasi redirect hanya ke domain internal
- Menggunakan allowlist
- Melakukan validasi sebelum redirect


--------------------------------------------------------
# [IMPACT]
--------------------------------------------------------

- Phishing
- Credential Harvesting
- Social Engineering
- Reputasi domain bisa disalahgunakan


--------------------------------------------------------
# [GREETING]
--------------------------------------------------------

Terima kasih sudah membaca write-up ini.
Gunakan sebagai pembelajaran untuk meningkatkan
keamanan aplikasi web.

Hunter: @zoxxtzy
========================================================
