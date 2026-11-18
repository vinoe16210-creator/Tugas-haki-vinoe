<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GnR PetHouse - Aplikasi Kasir & Manajemen Stok Pet Shop</title>
    <style>
        /* Reset & Variabel Warna (Tema Hitam & Putih) */
        :root {
            --bg-primary: #ffffff;
            --bg-secondary: #f5f5f5;
            --text-primary: #111111;
            --text-secondary: #4a4a4a;
            --border-color: #dddddd;
            --accent-black: #000000;
            --accent-white: #ffffff;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
        }

        body {
            background-color: var(--bg-secondary);
            color: var(--text-primary);
            line-height: 1.6;
        }

        /* Header & Identitas Brand */
        header {
            background-color: var(--accent-black);
            color: var(--accent-white);
            padding: 3rem 1.5rem;
            text-align: center;
        }

        .logo-container {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 80px;
            height: 80px;
            background-color: var(--accent-white);
            border-radius: 50%;
            margin-bottom: 1rem;
            box-shadow: 0 4px 10px rgba(255, 255, 255, 0.15);
        }

        .logo-paw {
            width: 48px;
            height: 48px;
            fill: var(--accent-black);
        }

        header h1 {
            font-size: 2.2rem;
            letter-spacing: 1px;
            margin-bottom: 0.5rem;
        }

        .badge {
            display: inline-block;
            background-color: var(--accent-white);
            color: var(--accent-black);
            padding: 0.35rem 1rem;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        /* Kontainer Utama */
        main {
            max-width: 900px;
            margin: -1.5rem auto 3rem;
            padding: 0 1.2rem;
        }

        /* Kartu Konten */
        .card {
            background-color: var(--bg-primary);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 2rem;
            margin-bottom: 1.5rem;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
        }

        .card-title {
            font-size: 1.35rem;
            color: var(--accent-black);
            border-bottom: 2px solid var(--accent-black);
            padding-bottom: 0.5rem;
            margin-bottom: 1.25rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .info-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1.2rem;
        }

        .info-item h3 {
            font-size: 1rem;
            color: var(--accent-black);
            margin-bottom: 0.3rem;
        }

        .info-item p {
            color: var(--text-secondary);
            font-size: 0.95rem;
        }

        /* Daftar Fitur & HAKI */
        .haki-section {
            margin-top: 1.2rem;
        }

        .haki-section h3 {
            font-size: 1.1rem;
            background-color: var(--bg-secondary);
            padding: 0.6rem 1rem;
            border-left: 4px solid var(--accent-black);
            margin-bottom: 1rem;
        }

        ul.custom-list {
            list-style: none;
            padding-left: 0.5rem;
        }

        ul.custom-list > li {
            position: relative;
            padding-left: 1.5rem;
            margin-bottom: 0.8rem;
            color: var(--text-secondary);
        }

        ul.custom-list > li::before {
            content: "■";
            position: absolute;
            left: 0;
            color: var(--accent-black);
            font-size: 0.8rem;
            top: 2px;
        }

        ul.sub-list {
            list-style: disc;
            margin-left: 1.5rem;
            margin-top: 0.4rem;
            color: var(--text-secondary);
        }

        .tech-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 0.5rem;
        }

        .tech-tag {
            background-color: var(--accent-black);
            color: var(--accent-white);
            padding: 0.25rem 0.75rem;
            border-radius: 6px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        /* Kotak Pernyataan Hak Cipta */
        .copyright-box {
            background-color: var(--bg-secondary);
            border: 1px dashed var(--accent-black);
            padding: 1rem;
            border-radius: 8px;
            margin-top: 1rem;
            font-weight: 600;
            text-align: center;
            color: var(--accent-black);
        }

        /* Footer */
        footer {
            background-color: var(--accent-black);
            color: var(--accent-white);
            text-align: center;
            padding: 1.5rem;
            font-size: 0.9rem;
        }

        footer p {
            opacity: 0.85;
        }

        /* Responsif untuk layar lebih lebar */
        @media (min-width: 768px) {
            .info-grid {
                grid-template-columns: 1fr 1fr;
            }
            .full-width {
                grid-column: span 2;
            }
        }
    </style>
</head>
<body>

    <!-- Bagian Header & Logo Paw Hitam-Putih -->
    <header>
        <div class="logo-container" title="Logo GnR PetHouse">
            <!-- Ikon SVG Telapak Kaki Kucing (Paw) -->
            <svg class="logo-paw" viewBox="0 0 512 512" xmlns="http://w3.org">
                <path d="M256 224c-79.41 0-192 122.76-192 200.25 0 34.9 26.81 55.75 71.74 55.75 48.84 0 81.09-25.08 120.26-25.08 39.51 0 71.85 25.08 120.26 25.08 44.93 0 71.74-20.85 71.74-55.75C448 346.76 335.41 224 256 224zm-147.28-12.61c-10.4-34.65-42.44-57.09-71.56-50.13-29.12 6.96-44.29 40.69-33.89 75.34 10.4 34.65 42.44 57.09 71.56 50.13 29.12-6.96 44.29-40.69 33.89-75.34zm84.72-20.78c30.94-8.14 46.42-49.94 34.58-93.36s-46.52-72.01-77.46-63.87-46.42 49.94-34.58 93.36c11.84 43.42 46.53 72.02 77.46 63.87zm281.39-29.34c-29.12-6.96-61.15 15.48-71.56 50.13-10.4 34.65 4.77 68.38 33.89 75.34 29.12 6.96 61.15-15.48 71.56-50.13 10.4-34.65-4.77-68.38-33.89-75.34zm-156.27 29.34c30.94 8.14 65.62-20.45 77.46-63.87 11.84-43.42-3.64-85.21-34.58-93.36s-65.62 20.45-77.46 63.87c-11.84 43.42 3.64 85.22 34.58 93.36z"/>
            </svg>
        </div>
        <h1>GnR PetHouse</h1>
        <span class="badge">Aplikasi Kasir & Manajemen Stok Pet Shop</span>
    </header>

    <!-- Konten Utama -->
    <main>
        <!-- Bagian A: Identitas Produk Perangkat Lunak -->
        <section class="card">
            <h2 class="card-title">A. Identitas Produk Perangkat Lunak</h2>
            <div class="info-grid">
                <div class="info-item">
                    <h3>1. Nama Aplikasi / Software</h3>
                    <p><strong>GnR PetHouse</strong></p>
                </div>
                <div class="info-item">
                    <h3>2. Kategori Produk</h3>
                    <p>Aplikasi Kasir dan Manajemen Stok Pet Shop Berbasis Android.</p>
                </div>
                <div class="info-item full-width">
                    <h3>3. Deskripsi Singkat Fungsi Aplikasi</h3>
                    <p>
                        GnR PetHouse adalah aplikasi digital yang dirancang untuk membantu pemilik toko hewan peliharaan dalam pencatatan transaksi penjualan makanan dan perlengkapan hewan, pengelolaan stok barang, serta pencatatan data pelanggan secara praktis.
                    </p>
                </div>
            </div>
        </section>

        <!-- Bagian B: Analisis Perlindungan HAKI Produk -->
        <section class="card">
            <h2 class="card-title">B. Analisis Perlindungan HAKI Produk</h2>

            <!-- 1. Hak Cipta -->
            <div class="haki-section">
                <h3>1. Hak Cipta (Copyright)</h3>
                <ul class="custom-list">
                    <li>
                        <strong>Objek Yang Dilindungi:</strong>
                        <ul class="sub-list">
                            <li>
                                <strong>Kode Sumber (Source Code):</strong> Untuk fitur kasir, pengelolaan stok, dan pencatatan data pelanggan.
                                <div class="tech-tags">
                                    <span class="tech-tag">HTML / CSS</span>
                                    <span class="tech-tag">JavaScript (Frontend)</span>
                                    <span class="tech-tag">Node.js (Backend)</span>
                                    <span class="tech-tag">MySQL (Database)</span>
                                </div>
                            </li>
                            <li style="margin-top: 0.6rem;">
                                <strong>Desain Antarmuka (UI/UX Design):</strong> Termasuk tata letak, skema warna, dan ikon aplikasi.
                            </li>
                            <li>
                                <strong>Dokumen Petunjuk Penggunaan (User Manual):</strong> Untuk aplikasi GnR PetHouse.
                            </li>
                        </ul>
                    </li>
                </ul>
                <div class="copyright-box">
                    Hak Cipta © 2026 oleh Muhamad Vinoe Anjar Ardiansyah. Seluruh hak dilindungi undang-undang.
                </div>
            </div>

            <!-- 2. Merek -->
            <div class="haki-section" style="margin-top: 2rem;">
                <h3>2. Merek (Trademark)</h3>
                <ul class="custom-list">
                    <li>
                    
