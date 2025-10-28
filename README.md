# Praktikum 6: Twitter Bootstrap

## Informasi Praktikum
- **Mata Kuliah**: Pemrograman Web
- **Topik**: Twitter Bootstrap - CSS Framework
- **Nama**: Abdi Putra Perdana
- **NIM**: 312410426
- **Kelas**: TI 24 A3

---

## Tujuan Praktikum

1. Memahami konsep CSS Framework
2. Memahami apa itu Twitter Bootstrap dan kegunaannya
3. Menyertakan library Bootstrap ke dalam halaman web menggunakan CDN
4. Memahami dan mengimplementasikan Bootstrap Grid System untuk membuat layout responsive
5. Menggunakan komponen-komponen dasar Bootstrap (Button, Navbar, Card, Form)
6. Membuat layout web sederhana dengan cepat menggunakan Bootstrap

---

## Langkah-Langkah Praktikum

### 1. Setup Bootstrap (Menggunakan CDN)

Bootstrap disertakan melalui CDN (Content Delivery Network). Tambahkan kode berikut di `<head>`:

```
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
```

Dan JavaScript di akhir `<body>`:

```
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
```

**Penjelasan:**
- CDN memungkinkan kita menggunakan Bootstrap tanpa perlu mendownload file
- Tag `<meta name="viewport">` penting untuk responsive design di mobile
- File CSS dimuat di `<head>` agar styling langsung diterapkan
- File JS dimuat di akhir `<body>` agar halaman load lebih cepat

---

### 2. Container Bootstrap

Bootstrap memiliki 2 jenis container:
- `.container`: Lebar tetap (fixed-width) yang responsif
- `.container-fluid`: Lebar penuh 100%

```html
<div class="container">
    <h1>Halo, Bootstrap!</h1>
</div>
```

**Penjelasan:**
- Container memberikan padding otomatis di kiri dan kanan
- Lebar container menyesuaikan ukuran layar (responsive breakpoints)
- Semua konten Bootstrap sebaiknya dibungkus dalam container

---

### 3. Grid System (Sistem Grid 12 Kolom)

Grid system adalah fitur inti Bootstrap yang menggantikan `float` manual.

**Contoh 3 kolom sama lebar:**

```html
<div class="container">
    <div class="row">
        <div class="col-4">Kolom 1</div>
        <div class="col-4">Kolom 2</div>
        <div class="col-4">Kolom 3</div>
    </div>
</div>
```

**Penjelasan:**
- Bootstrap menggunakan sistem 12 kolom
- `.row` = pembungkus untuk kolom
- `.col-4` = 4/12 = 33.33% lebar (1/3)
- Tidak perlu `float` atau `clearfix` lagi!

---

**Contoh Layout 8:4 (Main Content + Sidebar):**

```html
<div class="row">
    <div class="col-md-8">Main Content (8 kolom)</div>
    <div class="col-md-4">Sidebar (4 kolom)</div>
</div>
```

**Penjelasan:**
- `.col-md-8` = 8 kolom di layar medium (≥768px)
- `.col-md-4` = 4 kolom di layar medium
- Di layar kecil (<768px), otomatis jadi 100% dan menumpuk vertikal
- Ini yang membuat layout responsive!

---

### 4. Komponen: Button

Bootstrap menyediakan berbagai style tombol siap pakai:

```html
<button class="btn btn-primary">Primary</button>
<button class="btn btn-secondary">Secondary</button>
<button class="btn btn-success">Success</button>
<button class="btn btn-danger">Danger</button>
<button class="btn btn-warning">Warning</button>
```

**Penjelasan:**
- Class `.btn` = style dasar tombol
- Class kedua (`.btn-primary`, dll) = warna/tema tombol
- Bisa diterapkan ke `<button>`, `<a>`, atau `<input type="button">`

---

### 5. Komponen: Navbar (Navigasi)

Navbar responsive yang otomatis jadi hamburger menu di mobile:

```html
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container-fluid">
        <a class="navbar-brand" href="#">Praktikum 6</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" 
                data-bs-target="#navbarNav">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav">
                <li class="nav-item">
                    <a class="nav-link active" href="#">Home</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Artikel</a>
                </li>
            </ul>
        </div>
    </div>
</nav>
```

**Penjelasan:**
- `.navbar-expand-lg` = expand di layar large (≥992px)
- `.navbar-dark bg-dark` = tema gelap
- `.navbar-toggler` = tombol hamburger untuk mobile
- `data-bs-toggle="collapse"` = JavaScript Bootstrap untuk toggle menu

---

### 6. Komponen: Card

Card adalah container konten yang fleksibel:

```html
<div class="card" style="width: 18rem;">
    <img src="gambar.jpg" class="card-img-top" alt="...">
    <div class="card-body">
        <h5 class="card-title">Judul Card</h5>
        <p class="card-text">Deskripsi singkat di dalam card.</p>
        <a href="#" class="btn btn-primary">Lihat Detail</a>
    </div>
</div>
```

**Penjelasan:**
- Card menggantikan `.widget-box` atau `.box` dari praktikum sebelumnya
- Struktur: gambar (opsional) + body + button (opsional)
- Sangat cocok untuk portfolio, artikel, produk, dll

---

### 7. Komponen: Form

Form Bootstrap terlihat rapi dan konsisten:

```html
<div class="mb-3">
    <label for="emailInput" class="form-label">Alamat Email</label>
    <input type="email" class="form-control" id="emailInput" 
           placeholder="nama@contoh.com">
</div>

<div class="mb-3">
    <label for="pesanText" class="form-label">Pesan</label>
    <textarea class="form-control" id="pesanText" rows="3"></textarea>
</div>

<button type="submit" class="btn btn-primary">Kirim</button>
```

**Screenshot:**
![Cuplikan layar_28-10-2025_19725_](https://github.com/user-attachments/assets/4f5a5b58-e59e-4515-83ac-51a1281167e1)



**Penjelasan:**
- `.form-label` = styling untuk `<label>`
- `.form-control` = styling untuk input, textarea, select
- `.mb-3` = margin-bottom 3 (utility class untuk spacing)
- Jauh lebih mudah daripada styling manual!

---

## Tugas 1: Refactor Layout Praktikum 4

**Tugas:**
Buat ulang layout dari Praktikum 4 menggunakan Bootstrap Grid System.

**Persyaratan:**
-  Gunakan `<nav>` Bootstrap untuk navigasi
-  Gunakan `.row` dan `.col-md-8` untuk main content
-  Gunakan `.col-md-4` untuk sidebar
-  Gunakan `.card` untuk widget-box
-  TIDAK boleh pakai CSS `float` atau `clear` manual

**Screenshot:**

<img width="1656" height="4167" alt="image" src="https://github.com/user-attachments/assets/d34a05b2-7019-4619-80b5-81bbfb2e4130" />

**Penjelasan Implementasi:**

1. **Navbar**: Menggunakan `navbar-expand-lg` untuk responsive menu
2. **Header**: Section hero dengan gradient background
3. **Grid 3 Kolom**: Menggunakan `.col-md-4` untuk 3 card di baris pertama
4. **Grid 8:4**: Main content (artikel) dan sidebar
5. **Card Components**: Menggantikan `.widget-box` dengan `.card` Bootstrap

**Kode Penting:**

```html
<!-- Grid 3 kolom -->
<div class="row">
    <div class="col-md-4"><div class="card">...</div></div>
    <div class="col-md-4"><div class="card">...</div></div>
    <div class="col-md-4"><div class="card">...</div></div>
</div>

<!-- Grid 8:4 (Main + Sidebar) -->
<div class="row">
    <div class="col-md-8"><!-- Artikel --></div>
    <div class="col-md-4"><!-- Sidebar --></div>
</div>
```

---

## Tugas 2: Refactor Form Praktikum 5

**Tugas:**
Buat ulang form dari Praktikum 5 dengan styling Bootstrap.

**Persyaratan:**
-  Gunakan `.form-control` untuk input
-  Gunakan `.form-label` untuk label
-  Gunakan `.btn` untuk button
-  Form harus terlihat rapi dan konsisten

**Screenshot:**

<img width="1656" height="2411" alt="image" src="https://github.com/user-attachments/assets/bdc6a35f-6526-4b3e-97f8-fa4e3bd1940d" />

**Penjelasan Implementasi:**

1. **Input Text**: Menggunakan `.form-control` untuk styling otomatis
2. **Radio Button**: Menggunakan `.form-check` dan `.form-check-input`
3. **Checkbox**: Sama dengan radio, menggunakan `.form-check`
4. **Select**: Menggunakan `.form-select` untuk dropdown
5. **Textarea**: Menggunakan `.form-control` dengan `rows`
6. **File Upload**: Menggunakan `.form-control` untuk input file
7. **Spacing**: Menggunakan `.mb-3` (margin-bottom) untuk jarak antar field

**Kode Penting:**

```html
<!-- Input Text -->
<div class="mb-3">
    <label for="nama" class="form-label">Nama</label>
    <input type="text" class="form-control" id="nama">
</div>

<!-- Radio Button -->
<div class="form-check">
    <input class="form-check-input" type="radio" name="gender" id="laki">
    <label class="form-check-label" for="laki">Laki-laki</label>
</div>

<!-- Button -->
<button type="submit" class="btn btn-primary">Daftar</button>
```

---

## Tugas 3: Halaman Portfolio

### File: `portfolio.html`

**Tugas:**
Buat halaman portfolio pribadi lengkap.

**Persyaratan:**
- Navbar di bagian atas
- Section "Tentang Saya" dengan 2 kolom:
- Kolom kiri (`.col-md-4`): Foto profil dengan `.img-fluid`
- Kolom kanan (`.col-md-8`): Nama dan deskripsi diri
- Section "Portfolio Saya" dengan 3 kolom (`.col-md-4`):
- Setiap kolom berisi `.card` untuk proyek

**Screenshot Full Page:**

![Cuplikan layar_28-10-2025_19233_](https://github.com/user-attachments/assets/db3ce995-678c-4571-8a2d-3c5969ee5319)



**Penjelasan Implementasi:**

### 1. Hero Section
```html
<section class="hero-section text-center">
    <div class="container">
        <h1 class="display-3">Halo, Saya [Nama]</h1>
        <p class="lead">Web Developer | Designer | Student</p>
    </div>
</section>
```
- `.display-3` = heading besar
- `.lead` = teks emphasis

### 2. Section Tentang (Grid 4:8)
```html
<div class="row">
    <div class="col-md-4">
        <img src="foto.jpg" class="img-fluid" alt="Profil">
    </div>
    <div class="col-md-8">
        <h3>Tentang Saya</h3>
        <p>Deskripsi...</p>
    </div>
</div>
```
- `.img-fluid` = gambar responsive (max-width: 100%)
- Grid 4:8 memberikan proporsi yang bagus

### 3. Section Portfolio (Grid 3 Kolom)
```html
<div class="row">
    <div class="col-md-4">
        <div class="card">
            <img src="proyek1.jpg" class="card-img-top">
            <div class="card-body">
                <h5 class="card-title">Proyek 1</h5>
                <p class="card-text">Deskripsi...</p>
                <a href="#" class="btn btn-primary">Lihat Detail</a>
            </div>
        </div>
    </div>
    <!-- 2 kolom lagi -->
</div>
```
- 3 kolom `col-md-4` = 4+4+4 = 12 kolom (penuh)
- Di mobile otomatis stack vertikal

---

## Keuntungan Menggunakan Bootstrap

### Sebelum Bootstrap (Praktikum 4)
```css
/* Harus menulis CSS manual */
.box {
    width: 33.33%;
    float: left;
    padding: 10px;
}
.clearfix::after {
    content: "";
    display: table;
    clear: both;
}
```

### Dengan Bootstrap
```html
<!-- Cukup tambahkan class -->
<div class="row">
    <div class="col-4">Box 1</div>
    <div class="col-4">Box 2</div>
    <div class="col-4">Box 3</div>
</div>
```

### Perbandingan:
| Aspek | Manual CSS | Bootstrap |
|-------|-----------|-----------|
| **Kecepatan** | Lambat (tulis dari nol) | Cepat (tinggal pakai class) |
| **Responsive** | Harus tulis media query | Otomatis responsive |
| **Konsistensi** | Bisa beda-beda | Konsisten di semua komponen |
| **Maintenance** | Sulit | Mudah |
| **Cross-browser** | Harus test manual | Sudah compatible |

---

## Tips dan Best Practices

1. **Selalu gunakan Container**
   ```html
   <div class="container">
       <!-- Konten di sini -->
   </div>
   ```

2. **Gunakan Grid System yang Tepat**
   - `col-12` = Full width
   - `col-6` = Setengah layar
   - `col-4` = Sepertiga layar (untuk 3 kolom)
   - `col-md-8` + `col-md-4` = Main content + sidebar

3. **Manfaatkan Utility Classes**
   - `mb-3` = margin-bottom
   - `mt-4` = margin-top
   - `text-center` = center text
   - `d-flex` = flexbox
   - `justify-content-center` = center content

4. **Responsive Breakpoints**
   - `col-` = Extra small (<576px)
   - `col-sm-` = Small (≥576px)
   - `col-md-` = Medium (≥768px)
   - `col-lg-` = Large (≥992px)
   - `col-xl-` = Extra large (≥1200px)

---

## Kesimpulan

Praktikum ini berhasil menunjukkan bahwa:

1. **Bootstrap mempercepat development** - Tidak perlu menulis CSS dari nol
2. **Grid System sangat powerful** - Layout responsive otomatis tanpa media query kompleks
3. **Komponen siap pakai** - Navbar, Card, Form, Button sudah tersedia
4. **Mobile-first approach** - Semua komponen responsive by default
5. **Konsistensi desain** - Tampilan seragam di semua bagian website

Bootstrap adalah tool yang wajib dikuasai untuk web developer modern!

---

**Dibuat oleh: [Nama Anda]**  
**Tanggal: 28 Oktober 2025**
