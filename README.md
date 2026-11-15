## Informasi Mahasiswa & Proyek

- **Nama Lengkap:** Thoriq Abdurrohman Taqy
- **NIM:** 103022430006
- **Kelas:** SE-48-04
- **Program Studi:** S1 Rekayasa Perangkat Lunak (Software Engineering)
- **Mata Kuliah:** Perancangan dan Pemrograman Web (CCK3DAB3)
- **Nama Aplikasi Pribadi:** **Bengkelin** (Sistem Manajemen Servis Motor Konvensional & Motor Listrik)
- **Repositori GitHub:** [https://github.com/Thbetyfu/PENGWEB-Week9-Backend.git](https://github.com/Thbetyfu/PENGWEB-Week9-Backend.git) tadi saya lupa gak baca bapak, jadi ini baru buat lagi setelah push di repo lama

---

# Bengkelin — Fullstack Monorepo Web Application

**Bengkelin** adalah aplikasi web komprehensif yang dirancang untuk mengelola antrean pemesanan jadwal perawatan, estimasi biaya, pemilihan bengkel mitra, dan riwayat pemeliharaan berkala untuk sepeda motor bermesin konvensional (bensin) maupun motor listrik (*Electric Vehicle / EV*).

Proyek ini merupakan **aplikasi pribadi berkelanjutan yang dibangun secara berkesinambungan sejak Pekan 2**, bertransformasi melalui berbagai paradigma arsitektur rekayasa web:

1. **Pekan 2**: Struktur dasar web berbasis **Semantic HTML5** murni dan kepatuhan standar aksesibilitas.
2. **Pekan 3**: Desain antarmuka visual berbasis **CSS Native** murni dengan CSS Custom Properties dan *@media queries* responsif.
3. **Pekan 4**: Refaktor antarmuka modern menggunakan kerangka utilitas **Tailwind CSS**.
4. **Pekan 5**: Penerapan interaktivitas sisi klien (*client-side*) menggunakan **Vanilla JavaScript** dan **jQuery**.
5. **Pekan 6**: Transformasi menyeluruh menjadi *Single Page Application* (SPA) berbasis **React 19 + Vite** dengan arsitektur komponen modular dan *state lifting*.
6. **Pekan 7**: Integrasi konsumsi API eksternal asinkron (**AJAX / Fetch API**) dengan penanganan 3 kondisi antarmuka (*loading*, *success*, *error*) dan tombol *retry*.
7. **Pekan 8**: Fase Tugas Besar I (UTS Frontend) berfokus pada kolaborasi tim aplikasi e-commerce *EchoMarket*.
8. **Pekan 9**: Restrukturisasi monorepo penuh (**Frontend & Backend Terpisah**) dengan pembangunan backend RESTful API berbasis **NestJS** mengikuti pola arsitektur **Model-View-Controller (MVC)**, validasi DTO dengan *class-validator*, penanganan eksepsi bawaan (*NotFoundException* & *ConflictException*), pengujian *REST Client*, dan integrasi *fullstack* langsung.
=======
Aplikasi web modern untuk manajemen booking jadwal dan riwayat servis sepeda motor (konvensional & motor listrik). Proyek ini merupakan kelanjutan aplikasi pribadi **Bengkelin** yang telah dibangun sejak Pekan 2, bertransformasi menjadi Single Page Application (SPA) berbasis **React** di Pekan 6 & 7, dan kini direfaktor secara rapi menjadi arsitektur **Fullstack Monorepo (Frontend & Backend Terpisah)** dengan fondasi **NestJS (Model-View-Controller)** pada **Tugas Perkuliahan week 9**.

---

## 🧭 Tabel Rekapitulasi Progres Kumulatif Per Pekan

|       Pekan       | Topik Modul Perkuliahan       | Paradigma / Arsitektur             | Teknologi Utama                                  |  Status Implementasi  |
| :---------------: | :---------------------------- | :--------------------------------- | :----------------------------------------------- | :--------------------: |
| **Week 02** | Fondasi Web & Semantic HTML   | Multi-Page Static Site (4 Halaman) | HTML5 Semantic, Accessibility                    | **100% Selesai** |
| **Week 03** | Styling & Responsive Design   | CSS Native (No Framework)          | CSS3, Flexbox/Grid, Media Queries                | **100% Selesai** |
| **Week 04** | Modern Frontend Skeleton      | Utility-First CSS                  | Tailwind CSS (CDN), Custom Tokens                | **100% Selesai** |
| **Week 05** | Interaktivitas Client-Side    | DOM Manipulation & Animations      | Vanilla JavaScript (ES6+), jQuery                | **100% Selesai** |
| **Week 06** | React Dasar: Komponen & State | Single Page Application (SPA)      | React 19, Vite 8, Hooks (useState)               | **100% Selesai** |
| **Week 07** | AJAX & Konsumsi Mock API      | Asynchronous Data Fetching         | Fetch API, DummyJSON, 3 UI States                | **100% Selesai** |
| **Week 08** | Tugas Besar I (UTS Frontend)  | Tim Kolaboratif (EchoMarket)       | React SPA, Multi-page Routing                    | **100% Selesai** |
| **Week 09** | NestJS Dasar + Struktur MVC   | Fullstack Monorepo (FE & BE)       | NestJS 11, TypeScript, class-validator, React 19 | **100% Selesai** |

---

## 🚀 Struktur Direktori Monorepo Terkini (Refactored FE & BE)

Untuk mempermudah pemahaman arsitektur dan pemisahan tanggung jawab (*Separation of Concerns*), repositori direfaktor ke dalam struktur **Monorepo** yang memisahkan sisi antarmuka pengguna (`frontend/`) dan sisi peladen API (`backend/`):

```text
PENGWEB-Week9-Backend/
│
├── frontend/                            # [FE] SISI KLIEN / VIEW (React 19 + Vite)
│   ├── public/                         # Aset statis & logo
│   ├── src/
│   │   ├── components/                 # Komponen UI modular
│   │   │   ├── Header.jsx              # Identitas brand & status navigasi
│   │   │   ├── RingkasanStatistik.jsx  # Kartu metrik antrean & biaya
│   │   │   ├── FormTambahServis.jsx    # Controlled component formulir booking
│   │   │   ├── DaftarServis.jsx        # Rendering daftar kartu antrean
│   │   │   ├── KartuServis.jsx         # Kartu individual servis & aksi CRUD
│   │   │   └── ReferensiMotor.jsx      # Konsumsi API eksternal (3 UI States)
│   │   ├── services/
│   │   │   └── api.js                  # Fetch API ke NestJS API (Port 3001)
│   │   ├── data/
│   │   │   └── servisAwal.js           # Fallback data awal klien
│   │   ├── App.jsx                     # State lifting & Full CRUD Lifecycle
│   │   ├── main.jsx                    # Entry point React
│   │   └── index.css                   # Styling modern UI
│   ├── index.html                      # Root HTML SPA
│   ├── package.json                    # Dependensi frontend
│   └── vite.config.js                  # Konfigurasi bundler Vite
│
├── backend/                             # [BE] SISI SERVER / RESTful API (NestJS 11 MVC)
│   ├── src/
│   │   ├── main.ts                     # Entry point (ValidationPipe, CORS, Port 3001)
│   │   ├── app.module.ts               # Root application module
│   │   └── servis/                     # Modul domain Servis (MVC Resource)
│   │       ├── servis.module.ts        # Deklarasi controller & provider
│   │       ├── servis.controller.ts    # Controller (C) via Constructor DI
│   │       ├── servis.service.ts       # Service Logic (M) CRUD in-memory + Exceptions
│   │       ├── dto/
│   │       │   ├── create-servis.dto.ts# Skema validasi input (8 aturan class-validator)
│   │       │   └── update-servis.dto.ts# Skema pembaruan bertahap (PartialType)
│   │       └── entities/
│   │           └── servis.entity.ts    # Model Entitas Servis (9 field bervariasi)
│   ├── servis.http                     # Berkas pengujian REST Client (9 skenario)
│   ├── package.json                    # Dependensi backend (NestJS, class-validator)
│   └── tsconfig.json                   # Konfigurasi TypeScript compiler
│
├── docs/
│   └── screenshots/                    # Arsip lengkap tangkapan layar pengujian
│       ├── pekan-2/                    # Tangkapan layar Pekan 2 (HTML Semantic)
│       ├── pekan-3/                    # Tangkapan layar Pekan 3 (CSS Native)
│       ├── pekan-4/                    # Tangkapan layar Pekan 4 (Tailwind CSS)
│       ├── pekan-5/                    # Tangkapan layar Pekan 5 (JS & jQuery)
│       ├── pekan-7/                    # Tangkapan layar Pekan 7 (AJAX 3 States)
│       ├── 01_terminal_npm_run_dev.png # Pekan 6 React SPA
│       ├── ...                         # Pekan 9 NestJS MVC & REST Client (01 - 22)
│
├── package.json                        # Root Monorepo runner scripts
├── .gitignore                          # Standard git ignore (node_modules, dist)
└── README.md                           # Dokumentasi komprehensif proyek
```

---

## ⚡ Panduan Menjalankan Proyek Secara Lokal (Quickstart)

### 1. Prasyarat Sistem

- **Node.js**: v20.x atau lebih baru
- **npm**: v10.x atau lebih baru

### 2. Kloning Repositori

```bash
git clone https://github.com/Thbetyfu/PENGWEB-Week9-Backend.git
cd PENGWEB-Week9-Backend
```

### 3. Menjalankan Backend API (NestJS)

Buka terminal khusus untuk backend:

```bash
cd backend
npm install
npm run start:dev
```

> **Backend Aktif di:** `http://localhost:3001`
> **Endpoint Servis:** `http://localhost:3001/servis`

### 4. Menjalankan Frontend Web (React Vite)

Buka terminal terpisah untuk frontend:

```bash
cd frontend
npm install
npm run dev
```

> **Frontend Aktif di:** `http://localhost:5173`

---

# 📦 DOKUMENTASI DETAIL PER PEKAN (WEEK 2 — WEEK 9)

---

## PEKAN 09: Fondasi Backend RESTful API NestJS & Struktur MVC

Pada pekan ini, dibangun fondasi backend RESTful API menggunakan framework **NestJS** dengan pola arsitektur **Model-View-Controller (MVC)** yang terintegrasi langsung dengan antarmuka frontend React.

### 1. Entitas Data Utama (`Servis`)

Entitas didefinisikan pada `backend/src/servis/entities/servis.entity.ts` dengan **9 field** bervariasi:

- `id` (`string`): Kode unik transaksi servis (format `SRV-XXX`).
- `kendaraan` (`string`): Model motor (misal: "Honda Vario 160", "Gesits Raya G").
- `platNomor` (`string`): Nomor registrasi kendaraan bermotor.
- `jenisMotor` (`'Konvensional' | 'Listrik'`): Kategori teknologi motor.
- `bengkel` (`string`): Nama bengkel rekanan yang menangani perawatan.
- `layanan` (`string`): Jenis paket servis yang dipilih pelanggan.
- `biaya` (`number`): Estimasi biaya servis dalam mata uang Rupiah.
- `tanggal` (`string`): Tanggal booking servis (format ISO YYYY-MM-DD).
- `status` (`'Dijadwalkan' | 'Selesai'`): Status antrean pengerjaan.

### 2. Data Transfer Object (DTO) & Validasi Global

Validasi input diatur pada `create-servis.dto.ts` menggunakan library `class-validator` dengan 8 decorator:

- `@IsNotEmpty()`, `@IsString()`, `@MinLength(3)` pada nama kendaraan dan layanan.
- `@Matches(/^[A-Z]{1,2}\s\d{1,4}\s[A-Z]{1,3}$/)` untuk plat nomor Indonesia.
- `@IsIn(['Konvensional', 'Listrik'])` untuk jenis motor.
- `@IsNumber()`, `@Min(10000)` untuk biaya servis.
- `@IsDateString()` untuk validasi format tanggal ISO.
- `ValidationPipe` global diaktifkan pada `main.ts` dengan opsi `whitelist: true`, `forbidNonWhitelisted: true`, dan `transform: true`.

### 3. In-Memory CRUD Service & Exception Handling

Logika bisnis pada `servis.service.ts` mengelola data dalam memori (`private servisList: Servis[]`) dengan 2 skenario eksepsi bawaan NestJS:

- `NotFoundException` (HTTP 404): Dilempar jika ID servis tidak ditemukan pada saat pencarian, pembaruan, atau penghapusan data.
- `ConflictException` (HTTP 409): Dilempar saat pembuatan data jika plat nomor kendaraan yang sama sudah terdaftar di tanggal yang sama.

### 4. Controller & Dependency Injection

`servis.controller.ts` memetakan rute HTTP `@Get()`, `@Get(':id')`, `@Post()`, `@Patch(':id')`, dan `@Delete(':id')` dengan memanggil `ServisService` melalui *Constructor Dependency Injection* murni.

### 5. Pengujian REST Client (`servis.http`)

Seluruh 9 skenario request-response berhasil diuji dengan status code yang tepat:

1. `GET /servis` -> 200 OK (Semua data)
2. `GET /servis/SRV-101` -> 200 OK (Detail data valid)
3. `GET /servis/SRV-999` -> 404 Not Found (`NotFoundException`)
4. `POST /servis` (Valid) -> 201 Created (Data baru tersimpan)
5. `POST /servis` (Duplikat) -> 409 Conflict (`ConflictException`)
6. `POST /servis` (Payload Kosong/Invalid) -> 400 Bad Request (`ValidationPipe`)
7. `PATCH /servis/SRV-102` -> 200 OK (Pembaruan status/biaya)
8. `DELETE /servis/SRV-104` -> 200 OK (Data berhasil dihapus)
9. `DELETE /servis/SRV-999` -> 404 Not Found (`NotFoundException`)

### 6. Integrasi Fullstack dengan Frontend React

Frontend React terhubung ke NestJS API port 3001 via `frontend/src/services/api.js`. Operasi membaca data awal, menambah antrean baru via formulir, mengubah status servis (PATCH), dan menghapus antrean (DELETE) berjalan lancar secara asinkron.

### 📸 Lampiran Tangkapan Layar Pekan 09

#### A. Kode Sumber Backend NestJS MVC

- **Struktur Folder NestJS MVC**:![Struktur Folder Nest MVC](docs/screenshots/01_struktur_folder_nest_mvc.png)
- **Model Entitas Servis (9 Field)**:![Entity Servis](docs/screenshots/02_entity_servis.png)
- **DTO dengan 8 Aturan Class-Validator**:![DTO Class Validator](docs/screenshots/03_dto_class_validator.png)
- **Service CRUD In-Memory & Exception Handling**:![Service In Memory](docs/screenshots/04_service_crud_in_memory.png)
- **Controller Dependency Injection**:![Controller DI](docs/screenshots/05_controller_dependency_injection.png)
- **Global ValidationPipe & CORS (main.ts)**:
  ![Main Validation Pipe](docs/screenshots/06_main_validation_pipe_cors.png)

#### B. Pengujian REST Client

- **GET All Servis (200 OK)**:![GET All](docs/screenshots/07_rest_client_get_all.png)
- **GET Servis by ID Valid (200 OK)**:![GET One](docs/screenshots/08_rest_client_get_by_id_success.png)
- **GET Servis by ID 404 (NotFoundException)**:![GET 404](docs/screenshots/09_rest_client_get_by_id_404_not_found.png)
- **POST Create Servis Sukses (201 Created)**:![POST Success](docs/screenshots/10_rest_client_post_success.png)
- **POST Create Duplikat 409 (ConflictException)**:![POST 409](docs/screenshots/11_rest_client_post_409_conflict.png)
- **POST Create Validasi Gagal 400 (Bad Request)**:![POST 400](docs/screenshots/12_rest_client_post_400_validation_error.png)
- **PATCH Update Servis (200 OK)**:![PATCH Success](docs/screenshots/13_rest_client_patch_success.png)
- **DELETE Servis Sukses (200 OK)**:![DELETE Success](docs/screenshots/14_rest_client_delete_success.png)
- **DELETE Servis 404 (NotFoundException)**:
  ![DELETE 404](docs/screenshots/15_rest_client_delete_404_not_found.png)

#### C. Pengujian Integrasi Frontend React

- **Frontend Terhubung ke Backend NestJS**:![Frontend Terhubung](docs/screenshots/16_frontend_terhubung_backend.png)
- **Alur Tambah Data Servis**:![Tambah Servis](docs/screenshots/17_frontend_alur_tambah_servis.png)
- **Alur Update Status Servis (PATCH)**:![Update Status](docs/screenshots/18_frontend_alur_update_status.png)
- **Alur Hapus Servis (DELETE)**:
  ![Hapus Servis](docs/screenshots/19_frontend_alur_hapus_servis.png)

#### D. Bukti Pengujian Langsung di Browser (Live User Verification)

- **Respon JSON Endpoint Backend `/servis` di Browser**:![Respon JSON Backend](docs/screenshots/20_browser_json_endpoint_servis.png)
- **Tampilan Antarmuka Frontend dengan Banner Hijau Status Fullstack & Toast**:![Banner Status & Toast](docs/screenshots/21_frontend_terhubung_banner_dan_toast.png)
- **Tampilan Grid Antrean Kartu Servis dari Backend**:
  ![Grid Kartu Servis](docs/screenshots/22_frontend_grid_kartu_servis.png)

---

## PEKAN 07: AJAX & Konsumsi API Eksternal/Mock

Pada pekan ini, aplikasi Bengkelin diperluas dengan fitur konsumsi data asinkron dari API publik DummyJSON untuk memuat daftar katalog referensi spesifikasi motor pelanggan.

### Rincian Implementasi

1. **Asynchronous Fetching**: Menggunakan fungsi bawaan `fetch()` dengan sintaks modern `async/await` di dalam service `src/services/api.js`.
2. **Implementasi 3 State UI**:
   - **Loading State**: Menampilkan indikator animasi pemuatan data yang informatif.
   - **Success State**: Merender grid katalog referensi motor lengkap dengan foto, nama model, dan badge kategori.
   - **Error State**: Menampilkan kotak peringatan apabila koneksi gagal atau terputus, dilengkapi tombol interaktif **"Coba Lagi"** (*retry mechanism*).
3. **Pencegahan Memory Leak**: Menggunakan `AbortController` di dalam hook `useEffect()` untuk membatalkan proses fetch data yang belum selesai jika komponen di-unmount.

### 📸 Lampiran Tangkapan Layar Pekan 07

- **Kondisi 1: Loading State**:![Kondisi Loading](docs/screenshots/pekan-7/01_kondisi_loading.png)
- **Kondisi 2: Success State**:![Kondisi Success](docs/screenshots/pekan-7/02_kondisi_success.png)
- **Kondisi 3: Error State & Tombol Coba Lagi**:
  ![Kondisi Error](docs/screenshots/pekan-7/03_kondisi_error.png)

---

## PEKAN 06: Transformasi ke Single Page Application (SPA) React Dasar

Pada pekan ini, seluruh kerangka halaman web dikonversi menjadi *Single Page Application* (SPA) menggunakan library modern **React 19** dan bundler **Vite 8**.

### Rincian Implementasi

1. **Arsitektur Komponen Modular (6 Komponen)**:
   - `Header.jsx`: Identitas logo, judul, dan navigasi.
   - `RingkasanStatistik.jsx`: Ringkasan metrik (Total Servis, Motor Listrik, Motor Konvensional, Total Biaya).
   - `FormTambahServis.jsx`: *Controlled component* formulir booking dengan validasi input.
   - `DaftarServis.jsx`: Wadah rendering daftar servis menggunakan `.map()` dengan *unique key*.
   - `KartuServis.jsx`: Kartu visual servis individual berbasis *props* dengan pembedaan badge warna.
   - `ReferensiMotor.jsx`: Komponen katalog referensi motor eksternal.
2. **Pengelolaan State (*State Lifting*)**:
   - Seluruh data transaksi servis dikelola secara terpusat di `App.jsx` menggunakan hook `useState`.
   - Perubahan data (tambah antrean baru, ubah status pengerjaan, hapus antrean) dipicu secara reaktif tanpa me-refresh halaman browser.
3. **Controlled Form & Conditional Rendering**:
   - Formulir booking menangani event `onSubmit` dan `onChange` secara terkendali.
   - Menampilkan tampilan visual khusus (*Empty State*) apabila daftar antrean servis kosong.

### 📸 Lampiran Tangkapan Layar Pekan 06

- **Terminal Development Server (localhost:5173)**:![Terminal Dev Server](docs/screenshots/01_terminal_npm_run_dev.png)
- **Tampilan Halaman Utama & Komponen Data**:![Halaman Utama](docs/screenshots/02_halaman_utama_komponen_data.png)
- **Penambahan Data Baru via Controlled Form**:![Tambah Data Baru](docs/screenshots/03_tambah_data_dan_render_kartu_baru.png)
- **Implementasi Conditional Rendering (Data Kosong)**:
  ![Empty State](docs/screenshots/04_conditional_rendering_data_kosong.png)

---

## PEKAN 05: Interaktivitas Client-Side (Vanilla JavaScript & jQuery)

Pada pekan ini, kerangka tampilan HTML statis diberikan interaktivitas dinamis pada sisi klien (*client-side*) menggunakan kombinasi **Vanilla JavaScript (ES6+)** dan pustaka **jQuery**.

### Rincian Implementasi

1. **Penerapan JavaScript Murni (Vanilla JS)**:
   - Array of objects `dataRiwayatServis` menyimpan atribut lengkap antrean servis.
   - Fungsi kalkulasi ringkasan biaya: `hitungRingkasanServis(daftar)`.
   - Fungsi penyaringan dan pengurutan multi-kriteria: `prosesFilterDanUrutkanServis()`.
   - Fungsi utilitas pemformatan Rupiah (`formatRupiah`) dan tanggal Indonesia (`formatTanggalIndonesia`).
   - Perulangan dinamis `for` dan percabangan `if/else` untuk merender baris tabel riwayat servis.
2. **Penerapan Pustaka jQuery**:
   - Efek animasi `slideToggle()` untuk menyembunyikan/menampilkan kartu pengingat servis berikutnya dan panel form cepat.
   - Animasi `fadeIn()` dan `fadeOut()` saat menambahkan, memfilter, atau menghapus baris tabel data servis.
   - Validasi formulir booking interaktif: menampilkan pesan kesalahan jika ada field kosong, atau memunculkan dialog ringkasan estimasi biaya jika berhasil.
   - Filter kartu bengkel mitra berdasarkan kategori kendaraan (Semua, Motor Konvensional, Motor Listrik).
3. **Demo Video Pendek Interaktivitas**:
   - Tautan Video Google Drive: [Demo Interaktivitas Bengkelin Pekan 5](https://drive.google.com/file/d/1vnkke_vci7sBdoqBC_mxxnoLUvFQIrUN/view?usp=sharing)

### 📸 Lampiran Tangkapan Layar Pekan 05

- **Beranda Sebelum & Sesudah Toggle Pengingat**:![Beranda Sebelum](docs/screenshots/pekan-5/01-beranda-sebelum-interaksi.png)![Beranda Toggle](docs/screenshots/pekan-5/02-beranda-toggle-pengingat.png)
- **Tambah Data Baru, Filter Listrik, & Hapus Baris Data**:![Tambah Data](docs/screenshots/pekan-5/03-beranda-sesudah-tambah-data.png)![Filter Listrik](docs/screenshots/pekan-5/04-beranda-sesudah-filter-listrik.png)![Hapus Data](docs/screenshots/pekan-5/05-beranda-sesudah-hapus-data.png)
- **Form Booking: Validasi Kosong & Estimasi Biaya Otomatis**:![Booking Sebelum](docs/screenshots/pekan-5/06-booking-sebelum-interaksi.png)![Booking Gagal](docs/screenshots/pekan-5/07-booking-validasi-kosong.png)![Booking Berhasil](docs/screenshots/pekan-5/08-booking-validasi-berhasil.png)
- **Filter Kartu Bengkel Motor Listrik**:
  ![Filter Bengkel](docs/screenshots/pekan-5/09-bengkel-filter-listrik.png)

---

## PEKAN 04: Frontend Skeleton Modern (Tailwind CSS)

Pada pekan ini, antarmuka aplikasi Bengkelin direfaktor menggunakan framework **Tailwind CSS** untuk menghasilkan kerangka tampilan (*frontend skeleton*) yang modern, bersih, dan sepenuhnya responsif.

### Rincian Implementasi

1. **Refaktor 4 Halaman Utama**: Seluruh halaman (`index.html`, `booking.html`, `detail.html`, `bengkel.html`) direfaktor menggunakan kelas-kelas utilitas Tailwind CSS.
2. **Navigasi Responsif**: Menu navigasi horizontal pada layar desktop dan tombol *hamburger toggle dropdown* interaktif pada perangkat seluler.
3. **Alasan Pemilihan Tailwind CSS**:
   - **Fleksibilitas Palet Identitas**: Mempermudah pembedaan tematik antara motor konvensional (aksen amber/oranye) dan motor listrik (aksen emerald/hijau) tanpa perlu menimpa style bawaan framework komponen.
   - **Kontrol Breakpoint Presisi**: Pengaturan responsivitas langsung di markup HTML (`sm:`, `md:`, `lg:`), misalnya grid 3 kolom pada desktop dan 1 kolom pada ponsel.
   - **Zero-Dependency Tooling**: Mudah dijalankan pada tahap skeleton awal tanpa konfigurasi bundler yang kompleks.

### 📸 Lampiran Tangkapan Layar Pekan 04

- **Beranda (Desktop & Mobile)**:![Beranda Desktop](docs/screenshots/pekan-4/01-beranda-desktop.png)![Beranda Mobile](docs/screenshots/pekan-4/01-beranda-mobile.png)
- **Form Booking Servis (Desktop & Mobile)**:![Booking Desktop](docs/screenshots/pekan-4/02-booking-desktop.png)![Booking Mobile](docs/screenshots/pekan-4/02-booking-mobile.png)
- **Detail Servis (Desktop & Mobile)**:![Detail Desktop](docs/screenshots/pekan-4/03-detail-desktop.png)![Detail Mobile](docs/screenshots/pekan-4/03-detail-mobile.png)
- **Daftar Bengkel Mitra (Desktop & Mobile)**:
  ![Bengkel Desktop](docs/screenshots/pekan-4/04-daftar-bengkel-desktop.png)
  ![Bengkel Mobile](docs/screenshots/pekan-4/04-daftar-bengkel-mobile.png)

---

## PEKAN 03: Styling CSS Native & Responsive Web Design

Pada pekan ini, struktur HTML murni dari Pekan 2 diberi styling menggunakan **CSS Native murni** tanpa pustaka atau framework pihak ketiga, berpusat pada satu berkas eksternal `assets/css/style.css`.

### Rincian Implementasi

1. **Desain Sistem & Variabel CSS**:
   - Pendefinisian variabel `:root` untuk warna identitas (Biru `#1f6feb`, Aksen Kuning `#ffd33d`, Teks `#1f2937`).
   - Skala tipografi yang konsisten menggunakan `--font-teks` dan `--font-judul`.
2. **Tata Letak & Responsivitas (`@media` Queries)**:
   - Breakpoint `max-width: 900px`: Halaman booking bertransformasi dari 2 kolom menjadi 1 kolom vertikal.
   - Breakpoint `max-width: 768px`: Menu navigasi bertransformasi dari baris horizontal menjadi susunan vertikal bertumpuk, kartu bengkel menjadi satu kolom.
   - Breakpoint `max-width: 480px`: Pasangan label-nilai `<dl>` ditumpuk secara vertikal untuk kenyamanan layar kecil.
   - Tabel riwayat dibungkus pembungkus `.table-wrapper` dengan `overflow-x: auto` agar aman digeser pada layar sempit.

### 📸 Lampiran Tangkapan Layar Pekan 03

- **Beranda (Desktop & Mobile)**:![Beranda Native Desktop](docs/screenshots/pekan-3/01-beranda-desktop.png)![Beranda Native Mobile](docs/screenshots/pekan-3/01-beranda-mobile.png)
- **Form Booking Servis (Desktop & Mobile)**:![Booking Native Desktop](docs/screenshots/pekan-3/02-booking-desktop.png)![Booking Native Mobile](docs/screenshots/pekan-3/02-booking-mobile.png)
- **Detail Servis (Desktop & Mobile)**:![Detail Native Desktop](docs/screenshots/pekan-3/03-detail-desktop.png)![Detail Native Mobile](docs/screenshots/pekan-3/03-detail-mobile.png)
- **Daftar Bengkel Mitra (Desktop & Mobile)**:
  ![Bengkel Native Desktop](docs/screenshots/pekan-3/04-daftar-bengkel-desktop.png)
  ![Bengkel Native Mobile](docs/screenshots/pekan-3/04-daftar-bengkel-mobile.png)

---

## PEKAN 02: Fondasi Struktur Semantic HTML5 & Aksesibilitas

Pada pekan ini, diletakkan fondasi awal aplikasi Bengkelin berupa **struktur HTML murni** tanpa CSS dan tanpa JavaScript, dengan fokus pada semantik standar HTML5 dan prinsip aksesibilitas web.

### Rincian Implementasi

1. **4 Halaman Terstruktur**:
   - `index.html`: Beranda yang memuat pengingat servis, tabel riwayat, daftar kendaraan saya, dan tips pemeliharaan.
   - `booking.html`: Formulir booking lengkap (data motor, pilihan bengkel dan paket servis, tanggal/jam, kontak pelanggan).
   - `detail.html`: Informasi rinci satu transaksi servis (data kendaraan, catatan teknisi, rincian biaya tabular).
   - `bengkel.html`: Direktori mitra bengkel motor konvensional dan motor listrik.
2. **Penerapan Elemen Semantic HTML5**:
   - Penggunaan tag `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`, `<figure>`, `<figcaption>`, `<time>`, `<dl>`, `<dt>`, `<dd>`, dan `<table>` dengan hierarki yang tepat.
3. **Kepatuhan Aksesibilitas (WCAG)**:
   - Atribut `<html lang="id">` untuk pelafalan pembaca layar (*screen reader*).
   - Seluruh tag `<img>` memiliki teks `alt` deskriptif.
   - Seluruh elemen formulir terhubung tepat dengan satu `<label for="...">`.
   - Lolos validasi standar `html-validate:recommended`.

### 📸 Lampiran Tangkapan Layar Pekan 02

- **01. Beranda (`index.html`)**:![Beranda HTML Unstyled](docs/screenshots/pekan-2/01-beranda.png)
- **02. Form Booking Servis (`booking.html`)**:![Booking HTML Unstyled](docs/screenshots/pekan-2/02-booking.png)
- **03. Detail Servis (`detail.html`)**:![Detail HTML Unstyled](docs/screenshots/pekan-2/03-detail.png)
- **04. Daftar Bengkel Mitra (`bengkel.html`)**:
  ![Bengkel HTML Unstyled](docs/screenshots/pekan-2/04-daftar-bengkel.png)

---

### Catatan Penggunaan AI (AI Usage Transparency)

- **Pekan 2 — Pekan 5**: readme menggunakan gemini, untuk kode menggunaka vs code code complition
- **Pekan 6 — Pekan 7**: readme dan vs code untuk code complition
- **Pekan 9**: vs code untuk code complition saja

belum menggunakna AI agent kayak antigravity maupun copilot github untuk week ini
