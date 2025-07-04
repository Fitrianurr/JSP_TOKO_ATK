# JSP_TOKO_ATK
# 🛒 Toko ATK - Sistem Manajemen Penjualan & Stok Barang

Sistem web sederhana untuk manajemen penjualan dan stok barang pada Toko ATK (Alat Tulis Kantor), berbasis JSP dan Java Servlet. Fitur-fitur yang tersedia antara lain CRUD barang, pengelolaan transaksi penjualan, dan pelacakan stok secara otomatis. 

## 📁 Struktur Proyek

```
Toko_ATK/
├── src/
│   └── controller/
│       ├── BarangController.java
│       ├── SalesController.java
│       └── ...
├── web/
│   ├── barang/
│   │   ├── barang.jsp
│   │   ├── barangtambah.jsp
│   │   └── barangedit.jsp
│   ├── sales/
│   │   ├── saleslist.view.jsp
│   │   ├── salesdetail.view.jsp
│   │   └── ...
│   ├── api/
│   │   ├── barangapi.jsp
│   │   └── salesapi.jsp
│   ├── css/
│   │   └── style.css
│   └── index.jsp
├── WEB-INF/
│   └── web.xml
├── database/
│   └── toko_atk.sql
└── README.md
```
## 📌 Tujuan Proyek

Proyek ini dirancang untuk memenuhi kebutuhan:

* Pengelolaan data barang
* Otomatisasi stok berdasarkan transaksi
* Pencatatan dan pelaporan penjualan
* Implementasi REST API dasar

## 🚀 Fitur-Fitur

### 🔹 Manajemen Barang

* Tambah/Edit/Hapus barang
* Validasi stok sebelum penghapusan
* Cek riwayat penggunaan barang dalam transaksi

### 🔹 Manajemen Transaksi Penjualan

* Buat transaksi baru (otomatis generate ID)
* Tambahkan item ke transaksi
* Hapus item dalam transaksi (stok otomatis dikembalikan)
* Selesaikan transaksi (mengunci data)

### 🔹 Stok Otomatis

* Pengurangan stok hanya melalui transaksi
* Tidak bisa manipulasi stok manual dari tabel barang
* Semua perubahan stok tercatat lewat tabel `sales` dan `sales_detail`

### 🔹 REST API (Versi Awal)

* `GET /api/barang` → Ambil semua data barang
* `GET /api/sales` → Ambil semua data penjualan
* `GET /api/sales/detail?id=...` → Ambil detail transaksi
* `DELETE /api/barang?id=...` → Hapus barang (dengan validasi stok & transaksi)

## 🛠️ Teknologi yang Digunakan

| Teknologi    | Keterangan                         |
| ------------ | ---------------------------------- |
| Java Servlet | Backend logic                      |
| JSP & JSTL   | Templating & rendering UI          |
| MySQL        | Database utama                     |
| Bootstrap    | Tampilan antarmuka                 |
| SweetAlert2  | Notifikasi & konfirmasi interaktif |
| JavaScript   | Validasi form, AJAX, dan interaksi |

## 🏁 Cara Menjalankan Proyek
1. **Import ke IDE**
   * Gunakan IDE seperti NetBeans atau IntelliJ (support Java Web).
   * Pastikan sudah konfigurasi Apache Tomcat.

2. **Setup Database**
   * Buat database `toko_atk` di MySQL.
   * Import file SQL: `database/toko_atk.sql`.

3. **Konfigurasi Database**
   * Cek koneksi database di file `Koneksi.java` jika diperlukan.

4. **Jalankan Project**
   * Deploy ke Tomcat dan buka di browser: `http://localhost:8080/Toko_ATK/`
