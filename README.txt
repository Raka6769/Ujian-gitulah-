WEB UJIAN CBT - PETUNJUK HOSTING
================================

Isi paket:
- index.html  : seluruh aplikasi (HTML + CSS + JavaScript dalam satu file)

CARA HOSTING
1. Hosting biasa (cPanel / shared hosting):
   - Login cPanel > File Manager > folder public_html
   - Upload index.html (atau buat subfolder, misal public_html/ujian)
   - Buka https://domainanda.com/  (atau /ujian/)

2. Gratis (Netlify / Vercel / Cloudflare Pages / GitHub Pages):
   - Upload folder ini atau seluruh isi zip, lalu deploy.

3. Uji lokal: klik dua kali index.html di browser.

HTTPS
Disarankan memakai HTTPS (aktifkan SSL di hosting Anda). Aplikasi ini
tidak memakai mode layar penuh.

YANG PERLU DIUBAH (di dalam index.html, bagian <script>)
- MAX_WARN   : batas peringatan (default 3)
- DURATION   : durasi ujian dalam menit (default 30)
- ADMIN_PIN  : PIN pengawas untuk membuka blokir (default "admin123")
               GANTI sebelum dipakai!
- Q          : daftar soal. Format:
               {q:"Pertanyaan", o:["A","B","C","D"], a:1}
               a = nomor jawaban benar, dimulai dari 0 (0=A, 1=B, dst.)

BATASAN PENTING
- Status blokir, jawaban, dan skor hanya tersimpan di browser peserta
  (localStorage). Peserta bisa menghapus data browser atau pindah
  perangkat untuk lolos, dan hasil tidak terkirim ke Anda.
- Untuk ujian sungguhan, simpan soal, jawaban, skor, dan status blokir
  di server (misalnya PHP + MySQL).
- Deteksi bekerja lewat: pindah tab/aplikasi, hilangnya fokus jendela
  (floating app, split screen), dan jendela yang mengecil >25% dari
  ukuran awal ujian. Browser tidak bisa mendeteksi aplikasi lain yang
  tidak mengambil fokus, jadi tidak ada deteksi yang 100% sempurna.
