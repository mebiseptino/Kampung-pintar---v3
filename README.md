# Kampung Pintar v3: Secure Data Platform for 909 Nagari (FastAPI & AES-256)

[![Python](https://shields.io)](https://python.org)
[![Framework](https://shields.io)](https://tiangolo.com)
[![Compliance](https://shields.io)](https://wikipedia.org)
[![Security](https://shields.io)]()

**Kampung Pintar v3** adalah platform keamanan data (*secure data platform*) tingkat lanjut yang dirancang khusus untuk mengamankan integrasi data kependudukan (NIK dan Kartu Keluarga) di **909 Nagari (Desa Adat) di Provinsi Sumatera Barat**. 

Platform ini dibangun menggunakan framework **Python FastAPI**, validasi data super ketat dari **Pydantic**, serta arsitektur kontainerisasi **Docker**. Mengadaptasi *Meta Applied AI Pattern*, platform ini memastikan pertukaran data publik berjalan dengan p95 latency di bawah 250ms tanpa mengorbankan aspek kepatuhan terhadap regulasi nasional.

---

## 🎯 Fitur Utama & Solusi Keamanan

### 1. Kepatuhan Penuh UU PDP (Perlindungan Data Pribadi)
Sistem ini dirancang dari dasar dengan prinsip *Privacy by Design* untuk mematuhi regulasi UU PDP Indonesia. Menggunakan enkripsi **AES-256 pada fase penyimpanan (*at rest*)** dan protokol **TLS pada saat pengiriman (*in transit*)** guna memastikan data NIK/KK warga Nagari tidak dapat dieksploitasi oleh pihak ketiga.

### 2. Validasi Data Kaku dengan Pydantic
Setiap *endpoint* API dilengkapi dengan validator Pydantic yang kaku untuk melakukan sanitasi instan terhadap input dokumen kependudukan. Ini secara efektif mencegah serangan injeksi SQL (*SQL Injection*), *Cross-Site Scripting* (XSS), dan kebocoran format data kotor.

### 3. Sandbox Docker Terisolasi untuk Normalisasi Excel
Proses unggah dan normalisasi data berbasis file format Excel dikarantina di dalam lingkungan *sandbox* kontainer Docker terisolasi. Langkah isolasi ini mencegah eksekusi kode berbahaya (*Remote Code Execution*) dari file dokumen yang diunggah oleh pengguna instansi lokal.

### 4. Sistem Kendali Akses Berbasis Peran (RBAC) & Audit Log
Manajemen hak akses yang ketat mengontrol siapa saja yang berhak melihat, memperbarui, atau menghapus data warga. Setiap aktivitas di dalam platform dicatat secara kronologis dalam sistem *Audit Logs* yang tidak dapat dimanipulasi (*tamper-proof*).

### 5. LLM Security & Prompt Injection Guardrails
Menyediakan fitur asisten cerdas berbasis kecerdasan buatan (*Secure LLM-assist*) untuk membantu tugas administratif Wali Nagari. Fitur ini dilengkapi dengan lapisan pertahanan *Prompt Injection Guardrails* guna menangkal instruksi manipulatif yang mencoba membobol basis data melalui perintah teks AI.

---

## 🏗️ Arsitektur Teknologi & Spec Stack

Platform ini menggabungkan teknologi modern untuk performa tinggi dan latensi rendah:
* **Bahasa Pemrograman:** Python 3.x
* **Web Framework:** FastAPI (Asynchronous Server Gateway Interface)
* **Validasi & AI Agent:** Pydantic & Pydantic-AI
* **Database & Penyimpanan:** PostgreSQL dengan enkripsi kolom
* **Infrastruktur:** Docker & Docker-Compose (Isolasi Lingkungan)

---

## 🚀 Cara Menjalankan Platform (Quick Start)

### Prasyarat System
Pastikan perangkat Anda sudah terinstal:
* Docker
* Docker-Compose

### Langkah Instalasi

1. **Kloning Repositori:**
   ```bash
   git clone https://github.com
   cd Kampung-pintar---v3
   ```

2. **Konfigurasi Environment (.env):**
   Buat file `.env` di direktori utama dan lengkapi kredensial keamanan:
   ```env
   DATABASE_URL=postgresql://user:password@db:5432/kampung_pintar
   SECRET_KEY=masukkan_kunci_aes_256_anda_disini
   ALLOWED_HOSTS=localhost,127.0.0.1
   ```

3. **Build dan Jalankan dengan Docker-Compose:**
   ```bash
   docker-compose up --build -d
   ```
   Aplikasi akan berjalan dan dapat diakses melalui `http://localhost:8000`. Dokumentasi API otomatis (Swagger UI) dapat langsung diakses di `http://localhost:8000/docs`.

---

## 📈 Desentralisasi & Dampak Sosial

Proyek **Kampung Pintar v3** ini merupakan kelanjutan dari inisiatif digitalisasi akar rumput mandiri di Sumatera Barat. Dengan membangun identitas digital resmi dan mengamankan jalur pertukaran data publik menggunakan infrastruktur modern terenkripsi, platform ini menjadi jembatan kredibilitas agar administrasi pemerintahan tingkat Nagari di Indonesia dapat diakui secara valid, aman, dan siap berkolaborasi dengan ekosistem digital nasional yang lebih luas.

---
*Dikembangkan secara mandiri sebagai portofolio teknologi keamanan siber dan rekayasa perangkat lunak oleh [Mebi Septino](https://github.com/mebiseptino).*
