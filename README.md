# Simulasi Jaringan — Kelas X

Laboratorium jaringan visual berbasis browser yang dirancang khusus untuk siswa SMA/SMK kelas X. Siswa dapat menyusun perangkat, menghubungkannya dengan kabel/nirkabel, mengisi IP, memvalidasi topologi, hingga mengirim paket data dan membaca perjalanannya secara *hop demi hop*.

Aplikasi ini berjalan **sepenuhnya offline**, tanpa perlu instalasi, backend, pendaftaran akun, maupun dependensi eksternal.

---

## 📁 Struktur Berkas

| Berkas | Fungsi |
| :--- | :--- |
| `index.html` | Aplikasi simulasi lengkap (HTML + CSS + JavaScript + ikon SVG). |
| `panduan-guru.html` | Panduan lengkap untuk pengajar (antarmuka, skenario, rubrik, kustomisasi). |
| `README.md` | Ringkasan repositori dan dokumentasi utama (file ini). |

---

## 🚀 Cara Menjalankan

1. **Unduh atau salin** folder proyek ini ke komputer Anda.
2. **Klik dua kali** file `index.html` menggunakan browser modern (Chrome, Edge, atau Firefox).
3. **Spesifikasi Layar:** Minimal lebar 1024px (sangat optimal pada resolusi 1366px atau lebih).
4. **Tanpa Koneksi:** Tidak memerlukan internet ataupun server lokal.

---

## ⏱️ Panduan Mulai Cepat

1. **Pilih Skenario:** Klik tombol **Muat Skenario** → Pilih **Lab Komputer Sekolah**.
2. **Cek Topologi:** Buka tab **Validasi** → Klik **Periksa Jaringan**. Target utama adalah mencapai skor **7/7**.
3. **Setup Simulasi:** Buka tab **Simulasi**, tentukan **PC-01** sebagai sumber dan **Internet** sebagai tujuan.
4. **Jalankan:** Klik **Kirim Paket**. Rute perjalanan paket: `PC-01` → `Switch Lab` → `Router Sekolah` → `Internet`.

---

## ⚙️ Nilai Bawaan (Default)

* **Perangkat Baru:** Memiliki nama otomatis dengan kondisi IP yang masih kosong.
* **Internet:** Dibuat tidak memiliki IP, sehingga bidang pengisian IP otomatis dinonaktifkan.
* **Skenario "Lab Komputer Sekolah":** Terdiri dari 8 perangkat, 7 tautan kabel, target validasi 7/7, dan IP 2/2.
* **Skenario "Jaringan Rumah Sederhana":** Terdiri dari 5 perangkat, 4 tautan (2 kabel, 2 nirkabel), target validasi 7/7, dan IP 2/2.

---

## 🔍 Aturan Validasi

* **Skor Utama (`x/7`):** Ditentukan oleh **7 aturan wajib** (R01–R07). IP kosong tidak akan mengurangi skor utama ini.
* **Skor IP (`x/2`):** Ditentukan oleh **2 pemeriksaan IP opsional** (R08–R09) yang ditampilkan secara terpisah.
* **Penilaian Tambahan:** Untuk menilai aspek pengalamatan secara penuh, gunakan target **7/7 + 2/2** dan lakukan pemeriksaan format IPv4 secara manual.
* **Catatan Penting:** Validasi hanya memeriksa struktur topologi dan tidak menjamin konektivitas *end-to-end*. Selalu jalankan mode **Simulasi** untuk membuktikan jalur komunikasi.

---

## ⌨️ Kontrol & Shortcut Penting

* <kbd>V</kbd> : Mode Pilih (Select)
* <kbd>L</kbd> : Hubungkan via Kabel
* <kbd>W</kbd> : Hubungkan via Nirkabel (Wireless)
* <kbd>D</kbd> atau <kbd>Delete</kbd> : Hapus perangkat atau tautan yang dipilih
* <kbd>Esc</kbd> : Membatalkan tautan / menutup jendela popover / menghentikan simulasi
* <kbd>Space</kbd> + **Seret Mouse** (atau klik tengah) : Menggeser area kerja (*Pan*)
* **Roda Mouse (Scroll):** Melakukan *Zoom In / Zoom Out* dengan rentang 45%–220%

---

## ⚠️ Batasan Aplikasi

* **Penyimpanan:** Belum mendukung *autosave*. Melakukan *refresh* atau menutup tab akan menghapus seluruh pekerjaan.
* **Ekspor data:** Tidak menyediakan fitur bawaan untuk ekspor ke format PNG atau PDF.
* **Fungsi Jaringan:** Tidak mensimulasikan protokol DNS, DHCP, NAT, subnetting, *packet loss*, ataupun *latency*.
* **Pengecekan IP:** Sistem hanya memeriksa apakah IP kosong atau duplikat, bukan keabsahan format subnet IPv4-nya.
* **Responsivitas:** Aplikasi tidak dioptimalkan untuk perangkat ponsel/smartphone.

---

## 👩‍🏫 Dokumentasi Pengajar

Buka berkas **`panduan-guru.html`** untuk panduan mengajar yang komprehensif, meliputi:
* Tur antarmuka dan visualisasi seluruh kontrol.
* Nilai bawaan (*default*) untuk setiap jenis perangkat.
* Data teknis lengkap dari kedua skenario bawaan.
* Penjelasan detail sembilan aturan validasi beserta contoh skornya.
* Pola narasi perjalanan paket untuk setiap *hop*.
* Rencana Pelaksanaan Pembelajaran (RPP), bank latihan, dan rubrik penilaian.
* Panduan kustomisasi teks UI, skenario kustom, aturan baru, dan durasi animasi.
* Solusi masalah (*troubleshooting*) beserta *checklist* serah terima laboratorium.

---

## 🛠️ Panduan Kustomisasi

Semua modifikasi dapat dilakukan langsung pada berkas `index.html` tanpa memerlukan proses *build step*. Berikut adalah titik edit utamanya:

* `const STRINGS` — Mengubah label antarmuka (UI) dan pesan notifikasi.
* `const SCENARIOS` — Mengubah atau menambahkan data skenario bawaan.
* `const RULES` — Mengatur logika dan parameter aturan validasi.
* `function narrate` — Menyesuaikan teks narasi log yang muncul per *hop*.
* `function runSimulation` / `animatePacket` — Mengatur kecepatan dan durasi animasi paket.
* Tag `:root` (CSS) — Mengubah tema warna dan jenis font aplikasi.

> 📝 **Tips Keamanan:** Selalu cadangkan (*backup*) berkas asli sebelum melakukan pengeditan. Simpan file dengan encoding **UTF-8**, lalu muat ulang halaman browser menggunakan kombinasi tombol <kbd>Ctrl</kbd> + <kbd>F5</kbd>.

Made By: Ringga for Everyone.