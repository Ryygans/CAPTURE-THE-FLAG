# Write-Up: Logon (PicoCTF)

## 📋 Summary
Tantangan ini mendemonstrasikan kerentanan pada manajemen sesi berbasis *cookie*. Peretas dapat memanipulasi nilai *cookie* di sisi klien (client-side), mengubah status `admin` dari `False` menjadi `True`. Hal ini memungkinkan akses tidak sah ke dashboard admin dan pengambilan *flag* tanpa kredensial yang valid.

## 🎯 Challenge Details

| Detail | Informasi |
| :--- | :--- |
| **Challenge Name** | Logon |
| **Platform** | PicoCTF |
| **Category** | Web Exploitation |
| **Difficulty** | Easy |
| **Vulnerability** | Session Manipulation / Cookie Tampering |

## 🛠 Tools Used
- Web Browser (Chrome/Firefox)
- Developer Tools (Built-in)

## 🚩 Proof of Concept (Write-Up)

### 1. Reconnaissance
1. Buka halaman tantangan **Logon** di platform PicoCTF.
2. Klik **Launch Instance** untuk menjalankan server target.
3. Setelah server siap, buka URL target di browser.

### 2. Analysis
1. Pada halaman login, masukkan kredensial sembarang (misalnya: `username: user`, `password: user`).
2. Sebelum menekan tombol login, buka **Developer Tools** (tekan `F12`).
3. Pergi ke tab **Network**, lakukan login, dan klik pada request yang terjadi.
4. Atau, langsung pergi ke tab **Application** > **Cookies**.
5. Anda akan menemukan cookie bernama `admin` dengan nilai `False`.
   ```text
   Name: admin
   Value: False
   ```

### 3. Exploitation
1. Masih di dalam menu **Cookies** pada Developer Tools.
2. Klik dua kali pada kolom **Value** milik cookie `admin`.
3. Ubah nilai dari `False` menjadi `True`.
   ```text
   Name: admin
   Value: True
   ```
4. Tekan `Enter` untuk menyimpan perubahan.

### 4. Flag Retrieval
1. Refresh halaman web (tekan `F5`).
2. Server akan membaca cookie baru dan menganggap Anda sebagai admin.
3. Dashboard admin akan terbuka dan **Flag** akan ditampilkan di layar.

## ⚠️ Impact
Kerentanan ini memungkinkan:
1. **Privilege Escalation:** Pengguna biasa dapat naik hak akses menjadi admin.
2. **Unauthorized Access:** Akses ke fitur sensitif yang seharusnya dibatasi.
3. **Session Hijacking:** Manipulasi sesi pengguna tanpa mengetahui password.

## 🛡 Recommendation
Untuk mencegah kerentanan serupa:
1. **Server-Side Validation:** Jangan pernah mempercayai data dari klien (cookie/header) untuk menentukan hak akses. Validasi sesi di sisi server (database/redis).
2. **Signed Cookies:** Jika data harus disimpan di cookie, gunakan tanda tangan digital (HMAC) agar cookie tidak bisa dimanipulasi tanpa kunci rahasia server.
3. **Avoid Sensitive Data:** Jangan menyimpan status sensitif (seperti `is_admin`) secara langsung di cookie dalam bentuk *plaintext*.
4. **Use Standard Session Management:** Pertimbangkan menggunakan mekanisme sesi standar yang aman atau token terenkripsi (seperti JWT dengan verifikasi signature yang ketat).

---
**Hunter:** [@zoxxtzy]
