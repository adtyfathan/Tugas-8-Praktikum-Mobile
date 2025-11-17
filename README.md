# Data Diri

Nama        : Aditya Fathan Naufaldi<br>
NIM         : H1D023076<br>
Shift Lama  : F<br>
Shift Baru  : B

# Screenshot Aplikasi

<img width="386" height="827" alt="Screenshot 2025-11-17 183615" src="https://github.com/user-attachments/assets/c73b5c41-d138-448a-ae86-508d6c25db43" />
<img width="382" height="822" alt="Screenshot 2025-11-17 183646" src="https://github.com/user-attachments/assets/64e909ca-22c0-4cb4-a270-7c916e1f5c99" />
<img width="387" height="827" alt="Screenshot 2025-11-17 184837" src="https://github.com/user-attachments/assets/f23f9054-d6b0-491b-a16f-b5d4a599c303" />
<img width="381" height="824" alt="Screenshot 2025-11-17 184845" src="https://github.com/user-attachments/assets/3769a8ef-bf15-4ec1-87f9-cf81a1eb29f3" />
<img width="384" height="825" alt="Screenshot 2025-11-17 184856" src="https://github.com/user-attachments/assets/b176e2fa-fefb-418f-a8f6-39e9cfd77a29" />
<img width="380" height="822" alt="Screenshot 2025-11-17 184907" src="https://github.com/user-attachments/assets/aba82151-3a2a-49ee-83ce-681fb82a4566" />

# Penjelasan

Aplikasi Flutter **TokoKita** adalah aplikasi sederhana yang terhubung ke **REST API CodeIgniter 4** untuk melakukan proses:

* Registrasi pengguna
* Login
* CRUD Produk

Modul ini menjelaskan setiap file Flutter yang digunakan dalam project TokoKita.

---

# 📂 **Struktur Folder Utama**

```
lib/
│
├── model/
│   ├── login.dart
│   ├── registrasi.dart
│   └── produk.dart
│
├── ui/
│   ├── registrasi_page.dart
│   ├── login_page.dart
│   ├── produk_page.dart
│   ├── produk_form.dart
│   └── produk_detail.dart
│
└── main.dart
```

---

# 📁 **Penjelasan Setiap File**

## 1️⃣ **main.dart**

File utama aplikasi yang pertama kali dijalankan.

Berisi:

* Inisialisasi aplikasi Flutter
* Menentukan halaman awal (`home:`)
* Mengatur `MaterialApp`, tema dan konfigurasi dasar aplikasi

Contoh:

* `home: RegistrasiPage()`
* `home: LoginPage()`
* `home: ProdukPage()`

Modul akan mengubah halaman home sesuai bagian yang sedang dipelajari.

---

# 📂 **FOLDER: model/**

Folder ini menyimpan **struktur data** yang didapat dari API (JSON → Dart).

## 2️⃣ **model/login.dart**

Digunakan untuk menampung response login dari API.

Field utamanya:

* code
* status
* token
* userID
* userEmail

Terdapat factory constructor `Login.fromJson()` untuk parsing JSON.

---

## 3️⃣ **model/registrasi.dart**

Model untuk response saat registrasi.

Berisi:

* code
* status
* data (pesan sukses/gagal)

---

## 4️⃣ **model/produk.dart**

Model produk yang digunakan baik di list, detail, maupun form.

Field:

* id
* kodeProduk
* namaProduk
* hargaProduk

Digunakan pada semua UI produk.

---

# 📂 **FOLDER: ui/**

Folder ini berisi **tampilan atau halaman** aplikasi.

---

## 5️⃣ **ui/registrasi_page.dart**

Halaman untuk **registrasi member baru**.

Isi utamanya:

* Form nama
* Form email
* Form password
* Form konfirmasi password
* Validasi form
* Tombol registrasi (belum terhubung API dalam modul ini)

Menjadi halaman pertama yang dipelajari pada modul.

---

## 6️⃣ **ui/login_page.dart**

Halaman login pengguna.

Berisi:

* Form email
* Form password
* Tombol login
* Link menuju halaman registrasi

Fitur login belum terhubung ke API (akan dibahas di modul lanjutan).

---

## 7️⃣ **ui/produk_page.dart**

Halaman untuk menampilkan **list produk**.

Tampilan terdiri dari:

* AppBar + tombol tambah (add)
* Drawer (logout)
* List produk menggunakan widget `ItemProduk`
* Navigasi ke halaman detail produk

Pada modul, daftar produk masih **hard-coded**, belum dari API.

---

## 8️⃣ **ui/produk_form.dart**

Digunakan untuk:

* Menambah produk baru
* Mengubah produk yang sudah ada

Form ini berisi:

* Input kode produk
* Input nama produk
* Input harga
* Tombol simpan/ubah

Form secara otomatis berubah judulnya:

* **TAMBAH PRODUK** jika produk null
* **UBAH PRODUK** jika produk dikirim dari detail

Namun API belum terhubung di modul ini.

---

## 9️⃣ **ui/produk_detail.dart**

Halaman untuk menampilkan detail 1 produk tertentu.

Menampilkan:

* Kode produk
* Nama produk
* Harga

Memiliki dua tombol:

* **EDIT** → membuka ProdukForm
* **DELETE** → dialog konfirmasi

Modul belum menyediakan class `ProdukBloc` dan `WarningDialog`, sehingga tombol delete belum dapat digunakan.
