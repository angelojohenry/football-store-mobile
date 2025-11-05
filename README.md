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

3. 
