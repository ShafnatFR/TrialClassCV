# Modul Kelas: Membuat CV Sederhana dengan HTML & CSS

Pada praktikum kali ini, kita akan membuat halaman *Curriculum Vitae* (CV) sederhana. Pembuatan web ini terbagi menjadi dua tahap utama: menyusun kerangka konten menggunakan **HTML**, dan mempercantik tampilannya menggunakan **CSS**.

**Persiapan Awal:** Buatlah sebuah folder baru, lalu di dalamnya buat dua buah file bernama `index.html` dan `style.css`.

---

## Bagian 1: Menyusun Struktur dengan HTML (`index.html`)

### Langkah 1: Kerangka Dasar HTML

Pertama, kita siapkan pondasi halaman web. Kode ini memberitahu *browser* bahwa kita menggunakan HTML5 dan menghubungkan file HTML kita dengan file CSS.

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CV - Shafnat Fuaini Ramadhan</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
    </div>
</body>
</html>

```

### Langkah 2: Membuat Bagian Header (Identitas Diri)

Di dalam `<div class="container">`, tambahkan bagian `<header>`. Bagian ini digunakan untuk menampilkan nama lengkap, gelar/profesi, dan informasi kontak dasar.

```html
        <header>
            <h1>Shafnat Fuaini Ramadhan</h1>
            <h2>Full-Stack Developer & Mahasiswa Sistem Informasi</h2>
            <p class="contact-info" style="text-align: center;">Babelan, Bekasi, Jawa Barat | shafnatfuainiramadhan@gmail.com | github.com/ShafnatFR</p>
        </header>

```

### Langkah 3: Menambahkan Profil dan Pengalaman Kerja

Gunakan tag `<section>` untuk memisahkan setiap kategori informasi. Pada bagian pengalaman, kita menggunakan daftar tidak berurut (`<ul>` dan `<li>`) untuk menjabarkan tanggung jawab pekerjaan.

```html
        <section class="section">
            <h3 class="section-title">Profil</h3>
            <p>Mahasiswa D3 Sistem Informasi di Telkom University yang berdedikasi tinggi dengan minat mendalam pada pengembangan perangkat lunak full-stack dan integrasi AI. Berpengalaman sebagai Asisten Laboratorium dan aktif dalam mengembangkan solusi teknologi inovatif, menguasai ekosistem pengembangan modern.</p>
        </section>

        <section class="section">
            <h3 class="section-title">Pengalaman</h3>
            <div class="item">
                <div class="item-header">
                    <h4>Asisten Laboratorium (Asprak) Komputer</h4>
                    <span class="institution">Telkom University</span>
                </div>
                <ul class="item-details">
                    <li>Mengelola SOP laboratorium dan mendampingi pelaksanaan praktikum mahasiswa.</li>
                    <li>Menyusun modul pembelajaran dan menjalankan tugas administratif laboratorium.</li>
                    <li>Membantu mahasiswa dalam troubleshooting dan pemahaman fundamental komputer.</li>
                </ul>
            </div>
        </section>

```

### Langkah 4: Memasukkan Proyek Utama dan Pendidikan

Lanjutkan dengan menambahkan bagian proyek dan riwayat pendidikan menggunakan struktur `<section>` dan `<div class="item">` yang senada.

```html
        <section class="section">
            <h3 class="section-title">Proyek Utama</h3>
            <div class="item">
                <div class="item-header">
                    <h4>Food AI Rescue (FAR)</h4>
                </div>
                <p>Aplikasi inovasi sosial berbasis React.js dan integrasi Gemini API yang bertujuan mendistribusikan makanan berlebih ke masyarakat guna mencegah stunting. Dirancang dengan pemodelan BPMN dan skema SQL yang terstruktur.</p>
            </div>
        </section>

        <section class="section">
            <h3 class="section-title">Pendidikan</h3>
            <div class="item edu-item">
                <div class="item-header">
                    <h4>D3 Sistem Informasi</h4>
                    <span class="institution">Telkom University</span>
                </div>
            </div>
            <div class="item edu-item">
                <div class="item-header">
                    <h4>Ilmu Pengetahuan Sosial</h4>
                    <span class="institution">SMAS BPS&K 1 Jakarta Timur</span>
                </div>
            </div>
        </section>

```

### Langkah 5: Menambahkan Label Keahlian (Skills)

Untuk bagian keahlian, kita membungkus setiap *skill* menggunakan elemen `<span>` dengan *class* `skill-badge` agar nanti mudah dihias menjadi bentuk tombol/label menggunakan CSS.

```html
        <section class="section">
            <h3 class="section-title">Keahlian</h3>
            <div class="skills-container">
                <span class="skill-badge">Odoo</span>
                <span class="skill-badge">SQL</span>
                <span class="skill-badge">Prompt Engineering (LLM/Gemini)</span>
                <span class="skill-badge">GitHub</span>
                <span class="skill-badge">LaTeX</span>
                <span class="skill-badge">Linux</span>
            </div>
        </section>

```

---

## Bagian 2: Mempercantik Tampilan dengan CSS (`style.css`)

Setelah kerangka HTML selesai, halamannya masih terlihat polos. Buka file `style.css` untuk mulai menghiasnya.

### Langkah 6: Reset CSS dan Styling Background

Langkah pertama dalam CSS adalah menghilangkan *margin* dan *padding* bawaan *browser* agar ukuran elemen lebih konsisten. Setelah itu, kita atur warna latar belakang halaman web.

```css
/* Reset CSS dasar */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

/* Mengatur latar belakang halaman */
body {
    background-color: #f4f7f6;
    color: #333;
    line-height: 1.6;
    padding: 40px 20px;
}

```

### Langkah 7: Membuat Efek "Kertas" untuk CV

Kita ingin CV ini terlihat seperti dokumen kertas di tengah layar. *Class* `.container` diberikan batas lebar (`max-width`), warna putih (`#fff`), serta sedikit efek bayangan (`box-shadow`).

```css
/* Kontainer utama menyerupai kertas A4/dokumen */
.container {
    max-width: 800px;
    margin: 0 auto;
    background: #fff;
    padding: 40px 50px;
    border-radius: 8px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
}

```

### Langkah 8: Merapikan Header dan Judul section

Agar informasi nama dan judul terlihat profesional, kita pusatkan posisinya dan tambahkan garis pemisah di bagian bawah *header* serta judul setiap *section*.

```css
/* Header Profil */
header {
    text-align: center;
    border-bottom: 2px solid #2c3e50;
    padding-bottom: 20px;
    margin-bottom: 30px;
}

header h1 {
    color: #2c3e50;
    font-size: 2.5rem;
    margin-bottom: 5px;
    letter-spacing: 0.5px;
}

header h2 {
    color: #34495e;
    font-size: 1.2rem;
    font-weight: 500;
    margin-bottom: 10px;
}

.contact-info {
    font-size: 0.95rem;
    color: #7f8c8d;
}

/* Jarak antar section dan Judul */
.section {
    margin-bottom: 30px;
}

.section-title {
    color: #2c3e50;
    font-size: 1.3rem;
    border-bottom: 1px solid #eaeaea;
    padding-bottom: 8px;
    margin-bottom: 15px;
    text-transform: uppercase;
    letter-spacing: 1px;
}

```

### Langkah 9: Mengatur Tata Letak Detail Item dengan Flexbox

Untuk membuat posisi "Nama Posisi/Jurusan" berada di sebelah kiri dan "Nama Institusi" di sebelah kanan dalam satu baris yang sama, kita memanfaatkan `display: flex` dan `justify-content: space-between`.

```css
/* Konten di dalam section */
.item {
    margin-bottom: 20px;
}

.item-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    margin-bottom: 8px;
}

.item-header h4 {
    font-size: 1.15rem;
    color: #2980b9;
}

.institution {
    font-weight: 600;
    color: #7f8c8d;
    font-size: 0.95rem;
}

.item-details {
    list-style-type: square;
    margin-left: 20px;
    color: #444;
}

.item-details li {
    margin-bottom: 5px;
}

p {
    color: #444;
    text-align: justify;
}

.edu-item {
    margin-bottom: 10px;
}

```

### Langkah 10: Membentuk Elemen Badge untuk Keahlian

Keahlian yang tadi dibungkus dengan `<span>` sekarang diubah menjadi elemen visual berbentuk kapsul (*badge*) dengan memberi lekukan sudut menggunakan `border-radius` serta memberikan efek interaktif saat kursor diarahkan ke atasnya (`:hover`).

```css
/* Kontainer untuk label keahlian */
.skills-container {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
}

/* Desain label (badge) untuk keahlian */
.skill-badge {
    background-color: #ecf0f1;
    color: #2c3e50;
    padding: 6px 14px;
    border-radius: 20px;
    font-size: 0.9rem;
    font-weight: 600;
    border: 1px solid #bdc3c7;
    transition: all 0.3s ease;
}

.skill-badge:hover {
    background-color: #2c3e50;
    color: #ecf0f1;
}

```

### Langkah 11: Membuat Tampilan Responsif (Media Query)

Langkah terakhir dan krusial agar CV tetap nyaman dibaca saat dibuka melalui layar kecil atau ponsel. Kita mengatur agar tata letaknya menyesuaikan menjadi format vertikal (kolom).

```css
/* Media Query untuk membuat tampilan responsif di layar ponsel */
@media (max-width: 600px) {
    .container {
        padding: 20px;
    }
    
    .item-header {
        flex-direction: column;
    }
    
    .institution {
        margin-top: 4px;
        font-size: 0.9rem;
    }
    
    header h1 {
        font-size: 2rem;
    }
}

```
