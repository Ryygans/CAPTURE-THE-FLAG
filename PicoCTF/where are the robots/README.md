========================================================<br>
                 SECURITY REPORT<br>
            WHERE ARE THE ROBOTS<br>
========================================================<br>
<img src="robots.jpg" width=350 height=450>
<br>
[EXECUTIVE SUMMARY]<br>
Challenge ini menunjukkan bagaimana file robots.txt<br>
dapat mengungkap path sensitif jika tidak disertai<br>
mekanisme kontrol akses yang memadai.<br>
<br>
robots.txt bukan sistem keamanan, melainkan hanya<br>
petunjuk untuk crawler mesin pencari.<br>
<br>
========================================================<br>
<br>
[CHALLENGE DETAILS]<br>
Challenge Name : Where Are The Robots<br>
Platform       : picoCTF<br>
Category       : Web Exploitation<br>
Difficulty     : Easy<br>
Flag Format    : picoCTF{...}<br>
<br>
========================================================<br>
<br>
[METHODOLOGY]<br>
1. Melakukan enumerasi awal terhadap target.<br>
2. Mengakses endpoint umum yang sering digunakan<br>
   untuk discovery informasi tersembunyi.<br>
3. Menganalisis isi file robots.txt.<br>
4. Mengakses path yang ditemukan.<br>
<br>
========================================================<br>
<br>
[TECHNICAL ANALYSIS]<br>
Langkah-langkah eksploitasi:<br>
<br>
1. Launch instance challenge.<br>
2. Buka URL target yang diberikan.<br>
3. Tambahkan endpoint berikut:<br>
<br>
   /robots.txt<br>
<br>
Contoh:<br>
https://target-url.com/robots.txt<br>
<br>
4. File robots.txt menampilkan path tersembunyi:<br>
<br>
   Disallow: /hidden-path/<br>
<br>
5. Akses path tersebut melalui browser.<br>
6. Halaman yang terbuka berisi flag challenge.<br>
<br>
========================================================<br>
<br>
[IMPACT ANALYSIS]<br>
Jika dalam sistem nyata developer menyimpan<br>
informasi sensitif hanya dengan menyembunyikannya<br>
di dalam robots.txt tanpa autentikasi server-side,<br>
maka data tersebut dapat diakses oleh publik.<br>
<br>
Potensi risiko:<br>
- Information Disclosure<br>
- Exposure of Sensitive Files<br>
- Increased Attack Surface<br>
<br>
========================================================<br>
<br>
[RECOMMENDATION]<br>
- Jangan mengandalkan robots.txt untuk keamanan.<br>
- Terapkan autentikasi dan otorisasi yang benar.<br>
- Batasi akses file sensitif melalui konfigurasi server.<br>
<br>
========================================================<br>
<br>
# Hunter: trzy
