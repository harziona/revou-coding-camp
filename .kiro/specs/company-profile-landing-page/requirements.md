# Requirements Document

## Introduction

Fitur ini adalah sebuah **Company Profile Landing Page** berbasis HTML5 dengan desain modern dan simpel. Halaman ini bertujuan untuk memperkenalkan perusahaan kepada pengunjung secara elegan — mencakup identitas perusahaan, layanan yang ditawarkan, keunggulan, dan cara menghubungi perusahaan. Seluruh implementasi menggunakan HTML5 murni dengan CSS internal (tanpa framework eksternal) agar ringan dan mudah di-deploy.

---

## Glossary

- **Landing_Page**: Halaman web tunggal (single-page) yang menjadi titik masuk utama bagi pengunjung.
- **Hero_Section**: Bagian paling atas halaman yang menampilkan headline utama dan call-to-action.
- **Navigation_Bar**: Komponen navigasi di bagian atas halaman yang berisi tautan ke tiap seksi.
- **Services_Section**: Bagian yang menampilkan daftar layanan yang ditawarkan perusahaan.
- **About_Section**: Bagian yang menampilkan informasi ringkas tentang perusahaan.
- **Contact_Section**: Bagian yang menampilkan informasi kontak dan/atau formulir kontak.
- **Footer**: Bagian paling bawah halaman berisi informasi hak cipta dan tautan tambahan.
- **Visitor**: Pengguna yang mengakses Landing_Page melalui browser web.
- **Viewport**: Area tampilan browser pada perangkat Visitor.
- **CTA_Button**: Tombol call-to-action yang mengarahkan Visitor ke aksi yang diinginkan.

---

## Requirements

### Requirement 1: Struktur Halaman HTML5

**User Story:** Sebagai Visitor, saya ingin melihat halaman yang terstruktur dengan baik dan semantis, sehingga konten mudah dipahami dan diakses.

#### Acceptance Criteria

1. THE Landing_Page SHALL menggunakan doctype HTML5 (`<!DOCTYPE html>`) sebagai deklarasi pertama dokumen.
2. THE Landing_Page SHALL menggunakan elemen semantik HTML5 (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`) untuk mendefinisikan struktur halaman.
3. THE Landing_Page SHALL menyertakan meta tag `viewport` dengan nilai `width=device-width, initial-scale=1.0` agar Viewport menyesuaikan ukuran perangkat.
4. THE Landing_Page SHALL menyertakan meta tag `charset` dengan nilai `UTF-8` untuk mendukung karakter internasional.
5. THE Landing_Page SHALL menyertakan elemen `<title>` yang deskriptif pada bagian `<head>`.

---

### Requirement 2: Navigation Bar

**User Story:** Sebagai Visitor, saya ingin melihat navigasi yang jelas di bagian atas halaman, sehingga saya dapat dengan cepat berpindah ke seksi yang saya inginkan.

#### Acceptance Criteria

1. THE Navigation_Bar SHALL menampilkan nama atau logo perusahaan di sisi kiri.
2. THE Navigation_Bar SHALL menampilkan tautan navigasi ke seksi: About, Services, dan Contact.
3. WHEN Visitor mengklik tautan navigasi, THE Landing_Page SHALL melakukan smooth scroll ke seksi yang dituju.
4. WHILE Visitor menggulir halaman ke bawah, THE Navigation_Bar SHALL tetap terlihat di bagian atas Viewport (fixed/sticky).
5. THE Navigation_Bar SHALL memiliki tampilan yang kontras terhadap latar belakang halaman agar mudah dibaca.

---

### Requirement 3: Hero Section

**User Story:** Sebagai Visitor, saya ingin melihat perkenalan singkat dan menarik di bagian pertama halaman, sehingga saya langsung memahami identitas dan nilai utama perusahaan.

#### Acceptance Criteria

1. THE Hero_Section SHALL menampilkan headline utama yang mendeskripsikan perusahaan dalam satu kalimat singkat.
2. THE Hero_Section SHALL menampilkan sub-headline yang menjelaskan proposisi nilai perusahaan dalam maksimal dua kalimat.
3. THE Hero_Section SHALL menampilkan minimal satu CTA_Button yang mengarahkan Visitor ke Contact_Section.
4. THE Hero_Section SHALL menggunakan warna latar belakang atau gambar yang kontras dan menarik secara visual.
5. THE Hero_Section SHALL menampilkan kontennya secara terpusat (center-aligned) secara horizontal.

---

### Requirement 4: About Section

**User Story:** Sebagai Visitor, saya ingin mengetahui latar belakang dan visi perusahaan, sehingga saya dapat menilai apakah perusahaan ini sesuai dengan kebutuhan saya.

#### Acceptance Criteria

1. THE About_Section SHALL menampilkan deskripsi singkat perusahaan dalam minimal dua paragraf.
2. THE About_Section SHALL menampilkan minimal tiga poin keunggulan atau nilai perusahaan (misalnya dalam bentuk kartu atau ikon dengan teks).
3. THE About_Section SHALL menggunakan judul seksi yang jelas, yaitu "About Us" atau "Tentang Kami".
4. THE About_Section SHALL memiliki latar belakang yang berbeda secara visual dari Hero_Section untuk menciptakan pemisahan konten yang jelas.

---

### Requirement 5: Services Section

**User Story:** Sebagai Visitor, saya ingin melihat daftar layanan yang ditawarkan perusahaan, sehingga saya dapat menentukan layanan mana yang relevan dengan kebutuhan saya.

#### Acceptance Criteria

1. THE Services_Section SHALL menampilkan minimal tiga kartu layanan (service cards).
2. WHEN kartu layanan ditampilkan, THE Services_Section SHALL menyertakan judul layanan dan deskripsi singkat pada setiap kartu.
3. THE Services_Section SHALL menampilkan kartu layanan dalam tata letak grid yang responsif (minimal 1 kolom pada layar sempit, hingga 3 kolom pada layar lebar).
4. THE Services_Section SHALL menggunakan judul seksi yang jelas, yaitu "Our Services" atau "Layanan Kami".
5. WHEN Visitor mengarahkan kursor ke kartu layanan, THE Services_Section SHALL memberikan efek visual hover pada kartu tersebut.

---

### Requirement 6: Contact Section

**User Story:** Sebagai Visitor, saya ingin menemukan informasi kontak perusahaan dengan mudah, sehingga saya dapat menghubungi perusahaan sesuai kebutuhan.

#### Acceptance Criteria

1. THE Contact_Section SHALL menampilkan minimal dua metode kontak (misalnya: email dan nomor telepon).
2. THE Contact_Section SHALL menampilkan formulir kontak sederhana dengan field: nama, email, dan pesan.
3. WHEN Visitor mengisi formulir dan mengklik tombol kirim, THE Contact_Section SHALL menampilkan pesan konfirmasi atau mengarahkan Visitor ke mailto link.
4. THE Contact_Section SHALL menggunakan judul seksi yang jelas, yaitu "Contact Us" atau "Hubungi Kami".
5. IF Visitor mengosongkan field wajib pada formulir kontak, THEN THE Contact_Section SHALL menampilkan pesan validasi menggunakan HTML5 native validation.

---

### Requirement 7: Footer

**User Story:** Sebagai Visitor, saya ingin melihat informasi penutup halaman yang rapi, sehingga saya mendapatkan kesan profesional dari perusahaan.

#### Acceptance Criteria

1. THE Footer SHALL menampilkan teks hak cipta (copyright) dengan tahun yang relevan.
2. THE Footer SHALL menampilkan nama perusahaan.
3. THE Footer SHALL memiliki latar belakang gelap yang kontras dengan teks terang.

---

### Requirement 8: Desain Modern dan Responsif

**User Story:** Sebagai Visitor, saya ingin halaman terlihat modern dan dapat diakses dengan nyaman dari berbagai ukuran perangkat, sehingga pengalaman browsing saya tetap baik di mana saja.

#### Acceptance Criteria

1. THE Landing_Page SHALL menggunakan CSS internal (di dalam tag `<style>`) tanpa ketergantungan pada framework CSS eksternal.
2. THE Landing_Page SHALL menggunakan palet warna yang konsisten dan harmonis di seluruh halaman (minimal satu warna primer dan satu warna sekunder).
3. THE Landing_Page SHALL menggunakan tipografi yang mudah dibaca dengan ukuran font minimal 16px untuk body text.
4. WHEN Viewport memiliki lebar kurang dari 768px, THE Landing_Page SHALL menyesuaikan tata letak menjadi single-column menggunakan CSS media queries.
5. THE Landing_Page SHALL menggunakan properti CSS seperti `transition`, `box-shadow`, atau `border-radius` untuk memberikan tampilan modern pada elemen interaktif.
6. THE Landing_Page SHALL dapat dirender dengan benar pada browser modern (Chrome, Firefox, Safari, Edge) tanpa memerlukan plugin tambahan.
