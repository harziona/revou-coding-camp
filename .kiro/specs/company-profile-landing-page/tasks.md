# Implementation Plan: Company Profile Landing Page

## Overview

Implementasi `index.html` tunggal dengan CSS internal — tidak ada framework eksternal. Setiap task membangun di atas task sebelumnya secara incremental, dimulai dari struktur dasar HTML5, kemudian setiap section, lalu polish visual dan responsivitas.

## Tasks

- [x] 1. Set up struktur dasar HTML5 dan design tokens
  - Buat file `index.html` dengan doctype HTML5 (`<!DOCTYPE html>`)
  - Tambahkan `<head>` dengan meta tag `charset="UTF-8"`, `viewport`, dan `<title>` deskriptif
  - Tambahkan tag `<style>` di `<head>` dengan CSS custom properties (design tokens): `--color-primary`, `--color-secondary`, `--color-dark`, `--color-light`, `--color-white`, `--color-text`, `--color-text-muted`, variabel tipografi, spacing, dan efek
  - Tambahkan CSS reset/base: `*, box-sizing: border-box`, `body` font, `html { scroll-behavior: smooth }`
  - Buat skeleton `<body>` dengan elemen semantik: `<header>`, `<main>`, `<footer>`
  - Di dalam `<main>`, tambahkan placeholder `<section id="hero">`, `<section id="about">`, `<section id="services">`, `<section id="contact">`
  - _Requirements: 1.1, 1.2, 1.3, 1.4, 1.5, 8.1, 8.2, 8.3_

- [x] 2. Implementasi Navigation Bar
  - [x] 2.1 Buat HTML Navigation Bar
    - Di dalam `<header>`, tambahkan `<nav aria-label="Main navigation">`
    - Tambahkan nama/logo perusahaan di sisi kiri (elemen `<span>` atau `<a>` dengan class `brand`)
    - Tambahkan tautan navigasi: `<a href="#about">`, `<a href="#services">`, `<a href="#contact">`
    - _Requirements: 2.1, 2.2_
  - [x] 2.2 Styling Navigation Bar
    - Terapkan `position: sticky; top: 0; z-index: 100` pada `<header>`
    - Gunakan flexbox untuk layout logo kiri dan nav kanan
    - Terapkan warna latar belakang `var(--color-primary)` dengan teks terang
    - Tambahkan padding dan `box-shadow` untuk visual
    - _Requirements: 2.4, 2.5, 8.5_

- [x] 3. Implementasi Hero Section
  - [x] 3.1 Buat HTML Hero Section
    - Di dalam `<section id="hero">`, tambahkan `<h1>` headline utama
    - Tambahkan `<p>` sub-headline (maksimal dua kalimat)
    - Tambahkan `<a href="#contact" class="btn-cta">` sebagai CTA button
    - _Requirements: 3.1, 3.2, 3.3_
  - [x] 3.2 Styling Hero Section
    - Terapkan `min-height: 100vh`, flexbox column, dan center alignment
    - Gunakan `var(--color-primary)` atau gradient sebagai latar belakang
    - Style `<h1>` dengan `var(--font-size-h1)` (clamp) dan warna terang
    - Style `.btn-cta` dengan warna `var(--color-secondary)`, border-radius, padding, dan transition hover
    - _Requirements: 3.4, 3.5, 8.2, 8.5_

- [x] 4. Implementasi About Section
  - [x] 4.1 Buat HTML About Section
    - Di dalam `<section id="about">`, tambahkan `<h2>About Us</h2>` (atau "Tentang Kami")
    - Tambahkan minimal dua `<p>` deskripsi perusahaan
    - Tambahkan container grid dengan minimal tiga `.feature-card`, masing-masing berisi ikon (emoji/SVG), `<h3>` judul, dan `<p>` deskripsi singkat
    - _Requirements: 4.1, 4.2, 4.3_
  - [x] 4.2 Styling About Section
    - Terapkan latar belakang `var(--color-light)` (berbeda dari Hero Section)
    - Terapkan `padding: var(--section-padding)` dan `max-width: var(--container-max-width)` pada container
    - Style grid kartu: `display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr))`
    - Style `.feature-card` dengan `var(--box-shadow)` dan `var(--border-radius)`
    - _Requirements: 4.4, 8.2, 8.5_

- [x] 5. Implementasi Services Section
  - [x] 5.1 Buat HTML Services Section
    - Di dalam `<section id="services">`, tambahkan `<h2>Our Services</h2>` (atau "Layanan Kami")
    - Tambahkan minimal tiga `.service-card`, masing-masing berisi `<h3>` judul layanan dan `<p>` deskripsi
    - Opsional: tambahkan ikon/emoji pada setiap card
    - _Requirements: 5.1, 5.2, 5.4_
  - [x] 5.2 Styling Services Section dan hover effect
    - Style grid: `display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))`
    - Style `.service-card` dengan background putih, `var(--box-shadow)`, `var(--border-radius)`, dan padding
    - Tambahkan CSS hover effect: `.service-card:hover { transform: translateY(-4px); box-shadow: ...; }` dengan `transition: var(--transition)`
    - _Requirements: 5.3, 5.5, 8.5_

- [x] 6. Checkpoint — Struktur dan layout dasar
  - Buka `index.html` di browser, verifikasi semua section tampil dengan benar
  - Pastikan sticky nav berfungsi saat scroll
  - Pastikan smooth scroll aktif saat klik tautan nav
  - Ensure all tests pass, ask the user if questions arise.

- [x] 7. Implementasi Contact Section
  - [x] 7.1 Buat HTML Contact Section
    - Di dalam `<section id="contact">`, tambahkan `<h2>Contact Us</h2>` (atau "Hubungi Kami")
    - Tambahkan info kontak: `<a href="mailto:...">` dan `<a href="tel:...">`
    - Tambahkan `<form>` dengan:
      - `<label for="name">` + `<input type="text" id="name" name="name" required>`
      - `<label for="email">` + `<input type="email" id="email" name="email" required>`
      - `<label for="message">` + `<textarea id="message" name="message" required></textarea>`
      - `<button type="submit">`
    - Terapkan `action="mailto:info@perusahaan.com" method="POST" enctype="text/plain"` pada form
    - _Requirements: 6.1, 6.2, 6.3, 6.4_
  - [x] 7.2 Styling Contact Section dan form
    - Style section dengan `padding: var(--section-padding)` dan latar belakang berbeda
    - Style setiap `<label>` + `<input>`/`<textarea>` sebagai block dengan margin, padding, border, dan `border-radius`
    - Style tombol submit dengan warna `var(--color-primary)`, hover effect, dan transition
    - Tambahkan `:focus` outline yang terlihat jelas untuk aksesibilitas keyboard
    - _Requirements: 6.5, 8.5_

- [x] 8. Implementasi Footer
  - [x] 8.1 Buat HTML Footer
    - Di dalam `<footer>`, tambahkan nama perusahaan dan teks copyright: `© 2025 [Nama Perusahaan]. All rights reserved.`
    - _Requirements: 7.1, 7.2_
  - [x] 8.2 Styling Footer
    - Terapkan `background-color: var(--color-dark)` dan warna teks terang
    - Tambahkan padding yang cukup dan text-align center
    - _Requirements: 7.3_

- [x] 9. Responsivitas dan media queries
  - [x] 9.1 Implementasi mobile-first media queries
    - Tambahkan media query `@media (max-width: 767px)`:
      - Navigation: stack logo dan nav secara vertikal atau hide nav links (hamburger bukan required — cukup flex-wrap atau stack)
      - `.feature-card` dan `.service-card` grid: pastikan single-column pada layar sempit
      - Hero `<h1>` font size: verifikasi clamp bekerja dengan baik
      - Form fields: `width: 100%`
    - _Requirements: 8.4_
  - [x] 9.2 Verifikasi tampilan di berbagai breakpoint
    - Buka DevTools browser, uji di viewport 375px, 768px, dan 1280px
    - Verifikasi service cards: 1 kolom di mobile, 2 kolom di tablet, 3 kolom di desktop
    - _Requirements: 5.3, 8.4_

- [x] 10. Final checkpoint — Verifikasi menyeluruh
  - Validasi HTML di [validator.w3.org](https://validator.w3.org) — tidak ada error
  - Verifikasi semua section memiliki id anchor yang benar (`#hero`, `#about`, `#services`, `#contact`)
  - Verifikasi smooth scroll berfungsi untuk semua tautan nav
  - Verifikasi form validation native: submit form kosong → browser menampilkan pesan validasi
  - Verifikasi hover effect pada `.service-card`
  - Ensure all tests pass, ask the user if questions arise.

## Notes

- Tasks bertanda `*` bersifat opsional dan dapat dilewati untuk implementasi MVP yang lebih cepat
- Tidak ada JavaScript framework atau CSS framework eksternal — semua menggunakan HTML5 native dan CSS internal
- Desain menggunakan CSS custom properties (design tokens) yang didefinisikan di task 1 untuk konsistensi
- Smooth scroll diimplementasikan murni melalui CSS (`scroll-behavior: smooth` pada `html`)
- Form validation menggunakan HTML5 native validation (`required`, `type="email"`) tanpa JavaScript tambahan
- Setiap task mereferensikan requirements spesifik untuk traceability

## Task Dependency Graph

```json
{
  "waves": [
    { "id": 0, "tasks": ["1"] },
    { "id": 1, "tasks": ["2.1", "3.1", "4.1", "5.1", "7.1", "8.1"] },
    { "id": 2, "tasks": ["2.2", "3.2", "4.2", "5.2", "7.2", "8.2"] },
    { "id": 3, "tasks": ["9.1"] },
    { "id": 4, "tasks": ["9.2"] }
  ]
}
```
