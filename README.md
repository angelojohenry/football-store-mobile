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

TUGAS 9

1. Model Dart memberikan:
  a. Validasi tipe (type safety)
    - Model memiliki tipe data yang jelas: int, String, bool, dll.
    - Jika API berubah atau tipe tidak sesuai, compile-time akan memberi peringatan.
  b. Null-safety yang jelas
    - Dengan model, kita dapat menandai apakah field boleh null (String?) atau wajib (String).
    - Tanpa model, semua data dianggap dynamic → null-safety hilang.
  c. Maintainability & readability
    - Model mencegah magic string seperti json["field"].
    - Kode lebih bersih: product.name lebih aman dan jelas dibanding data["name"].
  d. Skalabilitas
    - Data kompleks (nested JSON, list of objects) jauh lebih mudah dengan model.
Konsekuensi jika hanya memakai Map<String, dynamic>:
  - Tidak ada jaminan tipe, rawan bug.
  - Null-safety hilang → NPE (Null Pointer Error).
  - Sulit refactor jika API berubah.
  - Kode cepat berantakan.

2. Perbedaan http dan CookieRequest:
  a. http
    - Digunakan untuk request standar: GET, POST, PUT, DELETE.
    - Tidak menyimpan session atau cookies secara otomatis.
    - Cocok untuk API publik yang tidak memerlukan autentikasi berbasis session.

  b. CookieRequest
    - Bagian dari pbp_django_auth.
    - Dirancang khusus agar Flutter dapat login ke Django yang memakai session-based auth.
    - Menyimpan cookie sessionid secara otomatis.
    - Semua request berikutnya otomatis membawa cookie untuk autentikasi.

3. Mengapa instance CookieRequest harus dibagikan ke semua komponen Flutter?
  Karena:
  - Session harus konsisten
    Jika setiap layar membuat instance baru, maka cookie baru dibuat → user ter-logout.
  - Autentikasi terpusat
    Dengan satu instance (misalnya melalui Provider), semua halaman berbagi session yang sama.
  - State login tersinkronisasi
    Jika user login, seluruh UI dapat membaca status login dari instance yang sama.

4. a. Mengapa menambahkan 10.0.2.2 ke ALLOWED_HOSTS?
  - Emulator Android tidak bisa mengakses localhost.
  - 10.0.2.2 adalah “jembatan” khusus untuk mengakses host mesin dari emulator.
  Jika tidak ditambahkan:
  - Django menolak request (403 DisallowedHost).
  b. Mengaktifkan CORS
    - Flutter adalah aplikasi berbeda domain/hanya mirip web environment.
    - Django harus mengizinkan domain Flutter agar request diterima.
    Jika tidak dilakukan:
    - Request akan ditolak (CORS policy error).
  c. Mengatur cookie, SameSite=None, dan CSRF
    - Untuk session Django agar bisa dipakai Flutter:
    - Cookie harus boleh dikirim lintas domain.
    - CSRF harus dimatikan atau di-handle khusus karena Flutter bukan browser.
    Jika tidak:
    - Login selalu gagal karena cookie tidak dikirim atau diblokir.
  d. Izin akses di android (ditambahkan pada AndroidManifest.xml)
    Jika tidak:
    - Flutter tidak bisa melakukan request ke API sama sekali.

5. Mekanisme pengiriman data dari input hingga ditampilkan di Flutter
- User mengisi form di Flutter
- Data dikumpulkan ke variabel/model.
- Flutter mengirim data (POST) ke Django (via CookieRequest).
- Django memproses
  - Menyimpan ke database
  - Atau mengembalikan JSON hasil proses
- Django mengirim response JSON kembali ke Flutter
- Flutter menerima JSON
- JSON → Model Dart
- Model ditampilkan di UI melalui widget.

6. Mekanisme autentikasi
A. Register
   - Flutter mengirim data username/password.
   - Django membuat user baru dengan sistem auth.
   - Django mengirim response (success/failed) ke Flutter.
   - Flutter menampilkan status registrasi.
B. Login
  - User memasukkan username & password di Flutter.
  - Flutter mengirim request ke endpoint Django login via CookieRequest.
  Django:
    - Mengecek username & password.
    - Menghasilkan session baru.
    - Mengirim cookie sessionid ke Flutter.
  - CookieRequest menyimpan cookie tersebut.
  - Flutter menampilkan menu utama karena session sudah valid.
C. Logout
  - Flutter memanggil endpoint logout Django.
  - Django menghapus session di server.
  - Cookie session di Flutter dibersihkan.
  - Flutter kembali ke halaman login.

7. Penyelesaian checklist:
   1. Membuat app django baru bernapa authentication
   2. menambahkan authentication dan corsheaders ke INSTALLED_APPS settings.py
   3. menambahkan beberapa variabel baru di settings.py
   4. menambah allowed hosts
   5. membuat metode view untuk login dan register di authentication
   6. install package provider dan pbp_django_auth
   7. membuat halaman login dan register
   8. membuat model kustom dengan data json
   9. menambahkan dependensi http pada AndroidManifest.xml
   10. menambahkan fungsi proxy_image di views.py pada main
   11. membuat product_entry_card.dart
   12. membuat halaman list produk (product_entry_list.dart)
   13. membuat halaman untuk detail produk (product_detail.dart)

