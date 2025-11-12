Tugas 7
1. Widget tree adalah struktur hierarki yang menggambarkan bagaimana widget tersusun dalam suatu aplikasi Flutter.
Setiap elemen di layar (teks, tombol, gambar, layout, dsb.) adalah widget, dan mereka saling berhubungan seperti pohon (tree).
- Parent widget adalah widget yang membungkus widget lain di dalamnya
- Child widget adalah widget yang dibungkus oleh parent
- Parent menentukan bagaimana child ditampilkan atau diatur (layout, posisi, gaya)
- Child menerima konteks dan gaya dari parent-nya (misalnya warna tema, padding, dll)

2. Widget yang digunakan:
- MaterialApp: Root widget yang menyediakan struktur dasar aplikasi berbasis Material Design
- AppBar: Menampilkan bar di bagian atas layar (judul, tombol navigasi, dsb)
- Scaffold: Menyediakan kerangka dasar halaman seperti AppBar, Body, dan FloatingActionButton
- Text: Menampilkan teks di layar
- Center: Meletakkan child widget di tengah layar
- Container: Sebagai wadah yang dapat diatur ukuran, margin, padding, warna, atau dekorasinya
- Column: Menyusun widget secara vertikal
- Icon: menampilkan simbol visual
- InkWell: mendeteksi interaksi sentuhan (seperti tap, double tap, long press) pada child-nya, dan memberikan animasi efek air (ripple) sebagai umpan balik visual

3. MaterialApp adalah widget yang menyediakan struktur dan konfigurasi dasar aplikasi flutter dengan gaya Material Design.

MaterialApp mengatur hal-hal seperti:
- title (judul aplikasi)
- theme (tema warna)
- home (halaman utama)
- routes (navigasi antar halaman)
- debugShowCheckedModeBanner (untuk menyembunyikan banner debug)

MaterialApp menyediakan context Material (seperti warna tema, ikon, dan animasi transisi) yang diperlukan oleh sebagian besar widget Flutter.
Tanpa MaterialApp, widget seperti Scaffold, AppBar, dan ElevatedButton tidak akan menampilkan gaya Material Design dengan benar.

4. Stateless Widget:
- Tidak memiliki state yang dapat berubah
- UI tidak berubah selama aplikasi berjalan
- Contoh: Text, Icon, Center

Stateful Widget:
- Memiliki state yang bisa berubah saat runtime
- UI perlu diperbarui ketika ada interaksi atau data berubah
- Contoh: Checkbox, TextField, Slider, Counter

- StatelessWidget cocok untuk tampilan statis seperti teks dan gambar
- StatefulWidget digunakan jika kita butuh interaksi pengguna (misalnya menekan tombol dan nilai berubah)

5. BuildContext adalah objek yang berisi informasi posisi widget dalam widget tree dan memungkinkan widget mengakses data dari parent-nya.
Penting karena:
- Digunakan untuk mengakses inherited widget seperti Theme, Navigator, atau MediaQuery.
- Setiap widget punya BuildContext sendiri yang dikirim sebagai parameter ke metode build()

6. Hot Reload:
- Digunakan untuk memperbarui kode dan UI tanpa kehilangan state aplikasi
- Sangat cepat karena hanya memperbarui bagian yang berubah
- Digunakan saat melakukan perubahan kecil pada tampilan atau logika UI
- State aplikasi tetap ada

Hot Restart:
- Digunakan untuk memulai ulang aplikasi dari awal dan menghapus semua state
- Lebih lambat karena seluruh aplikasi dimuat ulang
- Digunakan saat mengubah kode yang memengaruhi struktur utama atau inisialisasi variabel global
- State aplikasi hilang dan direset

Contoh:
Ubah teks atau warna tombol → gunakan hot reload.
Ubah variabel global atau menambahkan dependensi baru → gunakan hot restart

TUGAS 8
1.
- Navigator.push()
Menambahkan (push) halaman baru ke stack navigasi tanpa menghapus halaman sebelumnya.
Artinya, pengguna bisa kembali ke halaman sebelumnya menggunakan tombol Back.

Contoh kasus di Football Shop:
Saat pengguna membuka halaman create product, pengguna bisa kembali lagi ke home page

- Navigator.pushReplacement()
Mengganti (replace) halaman saat ini dengan halaman baru di stack navigasi.
Halaman lama akan dihapus dari memori, sehingga pengguna tidak bisa kembali ke sana dengan tombol Back.

Contoh kasus di Football Shop:
Setelah pengguna berhasil login, langsung ditampilkan halaman HomePage, dan tidak ingin mereka kembali ke halaman login

2. Cara penggunaan:
Scaffold → Kerangka utama setiap halaman (memuat AppBar, Drawer, dan body).
AppBar → Menampilkan judul halaman.
Drawer → Menu navigasi ke halaman lain seperti "Home" dan "Create Product

2.
- Padding
  Kelebihan: Menambah ruang di sekitar elemen agar tidak terlalu menempel ke tepi layar.
  Contoh penggunaan: Memberi jarak antar field input di product_form.dart
- SingleChildScrollView
  Kelebihan: Membuat seluruh konten bisa discroll jika terlalu panjang untuk layar.
  Contoh penggunaan: Pada halaman form dengan banyak input
- ListView
  Kelebihan: Menampilkan daftar elemen dinamis secara efisien.
  Contoh penggunaan: Menampilkan nama toko, teks, serta tombol-tombol untuk mengakses halaman lainnya pada left_drawer.dart

4. Menyesuaikan warna utama (primary color), aksen, dan latar belakang melalui ThemeData di MaterialApp.

