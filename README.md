# Smart Frozen Food Ordering & Inventory Management System
## Deskripsi
UMKM *frozen food* umumnya mengandalkan pemesanan manual via WhatsApp. Pola ini memicu berbagai masalah seperti risiko *overselling* akibat pencatatan stok yang tidak *real-time*, proses kalkulasi total tagihan yang lambat, hingga keterlambatan *restock* karena ketidakmampuan memantau batas minimum stok secara otomatis.

## Struktur Project
Menyediakan sistem pemesanan berbasis Web-to-WhatsApp yang terintegrasi dengan otomatisasi *backend* (n8n) dan basis data. Sistem ini memungkinkan pelanggan melihat katalog visual, mengecek stok secara *real-time*, dan melakukan *checkout* otomatis yang langsung mengarahkan ke WhatsApp admin via *deep link* (`wa.me`). Selain itu, sistem secara otomatis mengunci/memotong stok, mencatat transaksi, dan mengirimkan notifikasi *low-stock alert* ke admin.

- **frontend**: Berisi antarmuka website (Katalog produk, Keranjang belanja, dan Generator *link* WhatsApp otomatis).
- **backend**: Alur kerja (*workflows*) n8n lokal dan skrip penanganan API untuk pemrosesan logika bisnis (*auto-deduction* stok, kalkulasi pesanan, dan *trigger* notifikasi).
- **data**: Skema basis data (PostgreSQL/MySQL) untuk menyimpan informasi produk, sisa stok, dan histori transaksi.
- **docs**: Dokumentasi alur sistem (*workflow diagram*), panduan integrasi, dan laporan praktikum.
- **tests**: Skrip pengujian otomatis untuk memverifikasi alur pengurangan stok dan validasi kalkulasi harga.

## Setup
1. Clone repository
   `git clone https://github.com/kiyo090205/mlops-g23.git`
   `cd mlops-g23`

2. Buat virtual environment
   `python -m venv venv`
   `source venv/bin/activate`  # Untuk Linux/Mac
   # atau: `venv\Scripts\activate`  # Untuk Windows

3. Install requirements
   `pip install -r requirement.txt`

## Cara Menjalankan
1. Pastikan server Database (PostgreSQL/MySQL) sudah aktif dan skema di direktori data/ telah diimpor.
2. Jalankan instance n8n lokal.
3. Jalankan local web server: `python -m http.server 8000`.
4. Akses katalog melalui browser di `http://localhost:8000`.

## Tech Stack
1. Language & Runtime: Python, JavaScript (ES6+)
2. Frontend: HTML5, CSS3, JavaScript (Fetch API & Web-to-WhatsApp Integration)
3. Backend & Automation: n8n (Self-hosted / Lokal)
4. Database: PostgreSQL / MySQL
5. Notification System: Telegram Bot API (untuk Low-Stock Alert ke admin)
6. Version Control: Git, GitHub

## Team
- Jonathan Kiyosaki Sigalingging (2357301059)
- Wahyu Apriliana (2357301133)

## Development Workflow
- Gunakan branch fitur untuk setiap pengembangan baru.
- Lakukan commit dengan pesan yang bermakna.
- Buat Pull Request (PR) dan lakukan merge ke branch main setelah melalui proses code review.