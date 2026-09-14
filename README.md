# Ayjo Ventures Sdn. Bhd. - Web Development Documentation

## 📌 Pengenalan
Projek ini adalah migrasi laman web korporat Ayjo Ventures Sdn. Bhd. daripada sistem pengurusan kandungan (CMS) WordPress yang lama kepada laman web statik (Static HTML) yang dikuasakan oleh **Tailwind CSS**. 

Objektif utama migrasi ini adalah untuk:
- Memotong kos langganan *hosting* WordPress.
- Meningkatkan kelajuan muat turun (*loading speed*) laman web.
- Mengurangkan risiko keselamatan (bebas dari ancaman *malware/plugin* WordPress).
- Memudahkan pengurusan kod dan integrasi pelayan awan menggunakan **GitHub** dan **Cloudflare Pages**.

---

## 🛠️ Tech Stack
- **HTML5**: Struktur teras laman web.
- **Tailwind CSS (via CDN)**: Digunakan untuk penggayaan pantas (*rapid styling*), susun atur responsif (*responsive layout*), dan rekaan moden (*glassmorphism*).
- **GitHub**: Pengurusan versi (*Version Control System*) dan repositori pusat kod.
- **Cloudflare Pages**: Platform *hosting* percuma untuk laman web statik yang menyediakan integrasi DNS terus kepada domain `ayjo.my` serta sijil SSL (HTTPS) automatik.

---

## 📂 Struktur Fail & Halaman Utama

### 1. `index.html` (Laman Utama / Landing Page)
Halaman profil korporat rasmi yang menampilkan rekaan satu halaman (*single-page layout*).
- **Hero Section:** Pengenalan dan butang seruan tindak (Call-to-Action) untuk "Dapatkan Sebut Harga".
- **Perkhidmatan Kami:** Grid menyenaraikan kepakaran teras (Pembinaan, Renovasi, Mekanikal & Elektrikal).
- **Tentang Kami:** Latar belakang dan visi Ayjo Ventures.
- **Rekod Prestasi & Kenapa Pilih Kami:** Memaparkan legasi 20 tahun, jaminan kualiti, dan integrasi bekalan bahan terus dari anak syarikat (Galeri Mozek).
- **Hubungi Kami:** Alamat fizikal, e-mel, nombor telefon dan pembenaman peta lokasi dari Google Maps.

### 2. `bio.html` (Link-in-Bio / Pautan Pintas)
Halaman khusus yang direka ala "Linktree" untuk diletakkan di bio media sosial (seperti Instagram & TikTok).
- **Konsep Rekaan:** *Dark theme* dengan kesan kaca tembus pandang (*Glassmorphism panel*).
- **Latar Belakang:** Imej rumah skrin penuh dengan lapisan gelap (*dark overlay*).
- **Ikon & Menu:** Pautan pantas ke Galeri Mozek, Kedai Logam, Promosi, Buat Rumah, Elektrikal, dan Penghawa Dingin.
- **Elemen Khas:**
  - Badge reben "Akademi" (direka menggunakan *absolute positioning* dan SVG).
  - Teks pra-isi (*pre-filled text*) untuk pautan WhatsApp ("Assalamualaikum/Hi, Saya berminat bina rumah...").
  - Pautan ikon media sosial rasmi (Instagram, Facebook, TikTok).

### 3. `promosi.html` (Sedang Dalam Pembinaan)
- Bertindak sebagai fail *placeholder* rasmi apabila pengguna menekan menu "Promosi" dari halaman `bio.html`.
- Mengekalkan konsistensi rekaan (latar belakang gelap & *glassmorphism*).
- Memaparkan mesej "Sedang Dalam Pembinaan" berserta butang kembali ke Laman Utama.

### 4. Folder `assets/`
Menyimpan semua fail media statik termasuk `hero-house.jpg`, gambar perkhidmatan, pameran (showroom), dan logo rasmi (`ayjo-logo.png`).

---

## 🚀 Aliran Kerja Pengerjaan (Deployment Workflow)

Bagi memastikan persekitaran yang selamat dan tersusun, proses muat naik kod (*deployment*) dibahagikan kepada dua repositori:

1. **Repositori Utama (Staging):** `ayjo-my/w1`
   - Diuruskan oleh *developer* utama. Segala penambahan kod, fail baru, dan pembetulan (*bug fixes*) dimuat naik di sini dahulu.
2. **Repositori Produksi (Live):** `amiruldevkun/w1` (Fork)
   - Diuruskan oleh pengurus Cloudflare. Ia adalah cawangan (*fork*) dari repositori utama.
   - Dipautkan secara terus (auto-deploy) ke Cloudflare Pages untuk domain rasmi `ayjo.my`.

### Cara Kemas Kini Laman Web (Update Process)
1. Perubahan dilakukan dan di-*commit* ke repositori utama (`ayjo-my/w1`).
2. Penciptaan **Pull Request (PR)** dilakukan dari `ayjo-my/w1` ke cawangan utama *fork* `amiruldevkun/w1`. 
   *(Alternatif: Amirul boleh menekan butang "Sync fork" di GitHub miliknya).*
3. Apabila PR disahkan (*merged*) oleh penerima, Cloudflare Pages akan mengesan perubahan tersebut.
4. Laman web akan dikemas kini (build & deploy) secara automatik dalam masa beberapa saat.

14 September 2026
