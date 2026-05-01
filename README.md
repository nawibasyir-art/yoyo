<!DOCTYPE html>
<html lang="ms" style="scroll-behavior: smooth;">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Yoyo Barbershop | Gunting Rambut Premium</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
    <style>
        /* ==========================================================================
           Pembolehubah CSS (CSS Variables) untuk Tema Konsisten
           ========================================================================== */
        :root {
            --primary-bg: #121212;
            --secondary-bg: #1e1e1e;
            --text-main: #f5f5f5;
            --text-muted: #a0a0a0;
            --accent-color: #D4AF37; /* Warna Emas Premium */
            --accent-hover: #b5952f;
            --border-color: #333333;
            --transition: all 0.3s ease;
        }

        /* ==========================================================================
           Tetapan Asas (Reset & Base Styles)
           ========================================================================== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', sans-serif;
        }

        body {
            background-color: var(--primary-bg);
            color: var(--text-main);
            line-height: 1.6;
            overflow-x: hidden;
        }

        a {
            text-decoration: none;
            color: var(--text-main);
            transition: var(--transition);
        }

        ul {
            list-style: none;
        }

        img {
            max-width: 100%;
            display: block;
        }

        /* ==========================================================================
           Komponen UI Berulang
           ========================================================================== */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
        }

        .btn {
            display: inline-block;
            padding: 14px 28px;
            font-weight: 600;
            border-radius: 4px;
            cursor: pointer;
            text-align: center;
            border: none;
            transition: var(--transition);
        }

        .btn-primary {
            background-color: var(--accent-color);
            color: #000;
        }

        .btn-primary:hover {
            background-color: var(--accent-hover);
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(212, 175, 55, 0.3);
        }

        .btn-outline {
            background-color: transparent;
            color: var(--accent-color);
            border: 2px solid var(--accent-color);
        }

        .btn-outline:hover {
            background-color: var(--accent-color);
            color: #000;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            font-weight: 800;
            margin-bottom: 1rem;
            color: var(--text-main);
        }

        .section-subtitle {
            text-align: center;
            color: var(--text-muted);
            max-width: 600px;
            margin: 0 auto 3rem auto;
            font-size: 1.1rem;
        }

        section {
            padding: 80px 0;
        }

        /* ==========================================================================
           Navigasi (Header)
           ========================================================================== */
        header.navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background-color: rgba(18, 18, 18, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            border-bottom: 1px solid var(--border-color);
            padding: 15px 0;
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 800;
            color: var(--text-main);
            letter-spacing: 1px;
        }

        .logo span {
            color: var(--accent-color);
        }

        .nav-links {
            display: flex;
            gap: 30px;
            align-items: center;
        }

        .nav-links a:hover {
            color: var(--accent-color);
        }

        .hamburger {
            display: none;
            cursor: pointer;
            background: none;
            border: none;
            color: var(--text-main);
        }

        .hamburger svg {
            width: 30px;
            height: 30px;
        }

        /* ==========================================================================
           Seksyen Hero (Pendaratan Utama)
           ========================================================================== */
        .hero {
            height: 100vh;
            min-height: 600px;
            display: flex;
            align-items: center;
            background: linear-gradient(rgba(18, 18, 18, 0.7), rgba(18, 18, 18, 0.9)), 
                        url('https://images.unsplash.com/photo-1585747860715-2ba37e788b70?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80') center/cover;
            padding-top: 80px; /* Offset untuk navbar */
        }

        .hero-content {
            max-width: 650px;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 20px;
        }

        .hero h1 span {
            color: var(--accent-color);
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--text-muted);
            margin-bottom: 30px;
        }

        .hero-btns {
            display: flex;
            gap: 15px;
        }

        /* ==========================================================================
           Seksyen Kelebihan (Features)
           ========================================================================== */
        .features {
            background-color: var(--primary-bg);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
            margin-top: 40px;
        }

        .feature-card {
            background-color: var(--secondary-bg);
            padding: 40px 30px;
            border-radius: 8px;
            text-align: center;
            border: 1px solid var(--border-color);
            transition: var(--transition);
        }

        .feature-card:hover {
            border-color: var(--accent-color);
            transform: translateY(-5px);
        }

        .feature-icon {
            width: 60px;
            height: 60px;
            background-color: rgba(212, 175, 55, 0.1);
            color: var(--accent-color);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px auto;
            font-size: 1.5rem;
        }

        .feature-card h3 {
            margin-bottom: 15px;
            font-size: 1.3rem;
        }

        .feature-card p {
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        /* ==========================================================================
           Seksyen Harga & Perkhidmatan (Services)
           ========================================================================== */
        .services {
            background-color: var(--secondary-bg);
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .service-card {
            background-color: var(--primary-bg);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 30px;
            display: flex;
            flex-direction: column;
            transition: var(--transition);
        }

        .service-card:hover {
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            border-color: var(--accent-color);
        }

        .service-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            border-bottom: 1px dashed var(--border-color);
            padding-bottom: 15px;
        }

        .service-title {
            font-size: 1.2rem;
            font-weight: 600;
        }

        .service-price {
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--accent-color);
        }

        .service-desc {
            color: var(--text-muted);
            font-size: 0.9rem;
            margin-bottom: 25px;
            flex-grow: 1;
        }

        .service-card .btn {
            width: 100%;
        }

        /* Highlight Pakej Premium */
        .service-card.premium {
            border: 2px solid var(--accent-color);
            position: relative;
        }

        .badge {
            position: absolute;
            top: -12px;
            right: 20px;
            background-color: var(--accent-color);
            color: #000;
            font-size: 0.75rem;
            font-weight: 800;
            padding: 4px 12px;
            border-radius: 20px;
            text-transform: uppercase;
        }

        /* ==========================================================================
           Seksyen Testimoni
           ========================================================================== */
        .testimonials {
            background-color: var(--primary-bg);
        }

        .testi-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
        }

        .testi-card {
            background-color: var(--secondary-bg);
            padding: 30px;
            border-radius: 8px;
            position: relative;
        }

        .stars {
            color: var(--accent-color);
            margin-bottom: 15px;
            font-size: 1.2rem;
        }

        .testi-text {
            font-style: italic;
            color: var(--text-muted);
            margin-bottom: 20px;
        }

        .testi-user {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .testi-avatar {
            width: 50px;
            height: 50px;
            background-color: #333;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: var(--accent-color);
        }

        .testi-name {
            font-weight: 600;
        }

        /* ==========================================================================
           Seksyen Lokasi & Waktu Operasi
           ========================================================================== */
        .location {
            background-color: var(--secondary-bg);
        }

        .location-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .info-box {
            background-color: var(--primary-bg);
            padding: 30px;
            border-radius: 8px;
            border-left: 4px solid var(--accent-color);
            margin-bottom: 20px;
        }

        .info-box h3 {
            margin-bottom: 10px;
            color: var(--text-main);
        }

        .info-box p {
            color: var(--text-muted);
        }

        .map-container {
            width: 100%;
            height: 400px;
            background-color: #333;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-muted);
            border: 1px solid var(--border-color);
        }

        /* ==========================================================================
           Footer
           ========================================================================== */
        footer {
            background-color: #0a0a0a;
            padding: 40px 0 20px 0;
            border-top: 1px solid var(--border-color);
            text-align: center;
        }

        .footer-logo {
            font-size: 1.5rem;
            font-weight: 800;
            margin-bottom: 15px;
        }

        .footer-logo span {
            color: var(--accent-color);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 30px;
        }

        .social-links a {
            color: var(--text-muted);
            font-size: 1.5rem;
        }

        .social-links a:hover {
            color: var(--accent-color);
        }

        .copyright {
            color: #666;
            font-size: 0.9rem;
        }

        /* ==========================================================================
           Modal Booking (UI Pengganti Alert)
           ========================================================================== */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            display: none; /* Dikelaskan melalui JS */
            align-items: center;
            justify-content: center;
            z-index: 2000;
            backdrop-filter: blur(5px);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .modal-overlay.active {
            display: flex;
            opacity: 1;
        }

        .modal-content {
            background-color: var(--secondary-bg);
            padding: 40px;
            border-radius: 12px;
            max-width: 450px;
            width: 90%;
            text-align: center;
            border: 1px solid var(--accent-color);
            transform: scale(0.9);
            transition: transform 0.3s ease;
        }

        .modal-overlay.active .modal-content {
            transform: scale(1);
        }

        .modal-content h3 {
            font-size: 1.8rem;
            margin-bottom: 10px;
            color: var(--accent-color);
        }

        .modal-content p {
            color: var(--text-muted);
            margin-bottom: 25px;
        }

        .form-group {
            margin-bottom: 15px;
            text-align: left;
        }

        .form-group input, .form-group select {
            width: 100%;
            padding: 12px;
            background-color: var(--primary-bg);
            border: 1px solid var(--border-color);
            color: var(--text-main);
            border-radius: 4px;
        }

        .form-group input:focus, .form-group select:focus {
            outline: none;
            border-color: var(--accent-color);
        }

        .close-modal {
            background: transparent;
            border: none;
            color: var(--text-muted);
            cursor: pointer;
            margin-top: 15px;
            text-decoration: underline;
        }

        /* ==========================================================================
           Responsif (Media Queries)
           ========================================================================== */
        @media (max-width: 992px) {
            .features-grid, .testi-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            .location-content {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .features-grid, .testi-grid {
                grid-template-columns: 1fr;
            }

            .hamburger {
                display: block;
            }

            .nav-links {
                position: absolute;
                top: 70px;
                left: -100%;
                width: 100%;
                background-color: var(--secondary-bg);
                flex-direction: column;
                padding: 30px 0;
                transition: 0.3s ease;
                border-bottom: 1px solid var(--accent-color);
            }

            .nav-links.active {
                left: 0;
            }

            .nav-links a.btn {
                width: 80%;
                margin: 0 auto;
            }
        }
    </style>
</head>
<body>

    <!-- Navigasi Utama -->
    <header class="navbar">
        <div class="container nav-container">
            <a href="#" class="logo">Yoyo<span>Barbershop</span></a>
            
            <nav class="nav-links" id="navLinks">
                <a href="#hero">Utama</a>
                <a href="#features">Kelebihan</a>
                <a href="#services">Harga</a>
                <a href="#testimonials">Testimoni</a>
                <a href="#location">Lokasi</a>
                <button class="btn btn-primary" onclick="openModal('Umum')">Tempah Slot</button>
            </nav>

            <button class="hamburger" id="hamburgerBtn">
                <svg fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
                </svg>
            </button>
        </div>
    </header>

    <!-- Seksyen Hero -->
    <section id="hero" class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Tampil Yakin Dengan <span>Gaya Rambut Sempurna</span>.</h1>
                <p>Yoyo Barbershop menawarkan potongan klasik, kemasan moden, dan pengalaman dandanan premium. Tukang gunting pakar kami sedia memberikan penampilan terbaik untuk anda.</p>
                <div class="hero-btns">
                    <button class="btn btn-primary" onclick="openModal('Pakej Asas')">Tempah Sekarang</button>
                    <a href="#services" class="btn btn-outline">Lihat Pakej</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Seksyen Kenapa Pilih Kami -->
    <section id="features" class="features">
        <div class="container">
            <h2 class="section-title">Kenapa Pilih Kami?</h2>
            <p class="section-subtitle">Kami bukan sekadar memotong rambut. Kami memberikan keyakinan diri melalui hasil kerja yang teliti dan suasana yang menenangkan.</p>
            
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <!-- Icon Gunting (SVG) -->
                        <svg width="24" height="24" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"></path></svg>
                    </div>
                    <h3>Tukang Gunting Pakar</h3>
                    <p>Barber kami mempunyai pengalaman bertahun-tahun dalam gaya klasik dan trend moden terkini.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <!-- Icon Produk (SVG) -->
                        <svg width="24" height="24" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z"></path></svg>
                    </div>
                    <h3>Produk Premium</h3>
                    <p>Hanya menggunakan pomade, tonik, dan produk penjagaan kualiti tinggi yang mesra pada kulit kepala anda.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <!-- Icon Suasana (SVG) -->
                        <svg width="24" height="24" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20 7l-8-4-8 4m16 0l-8 4m8-4v10l-8 4m0-10L4 7m8 4v10M4 7v10l8 4"></path></svg>
                    </div>
                    <h3>Suasana Eksklusif</h3>
                    <p>Ruang menunggu yang selesa dengan minuman percuma, muzik santai, dan kebersihan tahap maksimum.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Seksyen Harga -->
    <section id="services" class="services">
        <div class="container">
            <h2 class="section-title">Perkhidmatan & Harga</h2>
            <p class="section-subtitle">Pilihan telus tanpa caj tersembunyi. Pilih gaya anda dan biarkan kami uruskan selebihnya.</p>
            
            <div class="services-grid">
                <!-- Kad 1 -->
                <div class="service-card">
                    <div class="service-header">
                        <span class="service-title">Gunting Klasik</span>
                        <span class="service-price">RM35</span>
                    </div>
                    <p class="service-desc">Potongan rambut profesional mengikut kesesuaian bentuk muka, kemasan tepi (fade/taper), dan cucian ringkas.</p>
                    <button class="btn btn-outline" onclick="openModal('Gunting Klasik - RM35')">Pilih Ini</button>
                </div>

                <!-- Kad 2 (Premium) -->
                <div class="service-card premium">
                    <span class="badge">Paling Laris</span>
                    <div class="service-header">
                        <span class="service-title">Pakej Yoyo Lengkap</span>
                        <span class="service-price">RM65</span>
                    </div>
                    <p class="service-desc">Potongan rambut penuh, cuci & urut kepala, kemasan jambang/cukur halus, berserta *hot towel* relaksasi.</p>
                    <button class="btn btn-primary" onclick="openModal('Pakej Yoyo Lengkap - RM65')">Pilih Pakej Laris</button>
                </div>

                <!-- Kad 3 -->
                <div class="service-card">
                    <div class="service-header">
                        <span class="service-title">Kemasan Jambang</span>
                        <span class="service-price">RM25</span>
                    </div>
                    <p class="service-desc">Membentuk, merapikan, dan mencukur jambang atau misai dengan tuala panas & sapuan *aftershave* premium.</p>
                    <button class="btn btn-outline" onclick="openModal('Kemasan Jambang - RM25')">Pilih Ini</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Seksyen Testimoni -->
    <section id="testimonials" class="testimonials">
        <div class="container">
            <h2 class="section-title">Apa Kata Pelanggan Kami</h2>
            <p class="section-subtitle">Lebih 1,000 pelanggan berpuas hati. Lihat pengalaman mereka bersantai di Yoyo Barbershop.</p>
            
            <div class="testi-grid">
                <div class="testi-card">
                    <div class="stars">★★★★★</div>
                    <p class="testi-text">"Sangat teliti! Barber memahami jenis rambut saya yang susah diurus. Suasana kedai juga sangat tenang. Pasti akan datang lagi bulan depan."</p>
                    <div class="testi-user">
                        <div class="testi-avatar">H</div>
                        <div>
                            <div class="testi-name">Hafizuddin Ahmad</div>
                            <small style="color:var(--text-muted)">Pelanggan Tetap</small>
                        </div>
                    </div>
                </div>
                <div class="testi-card">
                    <div class="stars">★★★★★</div>
                    <p class="testi-text">"Pakej Yoyo Lengkap memang berbaloi. Urutan kepala selepas potong rambut sangat melegakan stres kerja. Recommended 100%!"</p>
                    <div class="testi-user">
                        <div class="testi-avatar">S</div>
                        <div>
                            <div class="testi-name">Syed Ali</div>
                            <small style="color:var(--text-muted)">Ahli Perniagaan</small>
                        </div>
                    </div>
                </div>
                <div class="testi-card">
                    <div class="stars">★★★★★</div>
                    <p class="testi-text">"Bawa anak lelaki saya gunting di sini. Barber sangat mesra kanak-kanak dan sabar. Hasil potongan sangat kemas dan bergaya."</p>
                    <div class="testi-user">
                        <div class="testi-avatar">R</div>
                        <div>
                            <div class="testi-name">Razak Majid</div>
                            <small style="color:var(--text-muted)">Bapa</small>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Seksyen Lokasi & Waktu -->
    <section id="location" class="location">
        <div class="container">
            <div class="location-content">
                <div>
                    <h2 class="section-title" style="text-align: left;">Kunjungi Kami</h2>
                    <p style="color: var(--text-muted); margin-bottom: 30px;">Singgah ke cawangan utama kami untuk pengalaman dandanan sejati.</p>
                    
                    <div class="info-box">
                        <h3>Waktu Operasi</h3>
                        <p>Isnin - Jumaat: 10:00 Pagi - 10:00 Malam</p>
                        <p>Sabtu - Ahad: 9:00 Pagi - 11:00 Malam</p>
                        <p style="color: var(--accent-color); margin-top: 5px; font-size: 0.9rem;">*Cuti Umum Buka Seperti Biasa</p>
                    </div>

                    <div class="info-box">
                        <h3>Hubungi Kami</h3>
                        <p>Alamat: No 42, Jalan Utama, Pusat Bandar, 50000 Kuala Lumpur.</p>
                        <p>Telefon: +60 12-345 6789</p>
                        <p>Email: hello@yoyobarbershop.com</p>
                    </div>
                </div>

                <!-- Placeholder Peta -->
                <div class="map-container">
                    [ Gambaran Peta Interaktif / Lokasi Google Maps ]
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-logo">Yoyo<span>Barbershop</span></div>
            <div class="social-links">
                <a href="#">IG</a>
                <a href="#">FB</a>
                <a href="#">TT</a>
            </div>
            <p class="copyright">&copy; 2026 Yoyo Barbershop. Hak Cipta Terpelihara.</p>
        </div>
    </footer>

    <!-- Modal Booking (Custom Alert) -->
    <div class="modal-overlay" id="bookingModal">
        <div class="modal-content">
            <h3>Tempah Slot Anda</h3>
            <p>Sila tinggalkan butiran untuk pengesahan slot.</p>
            
            <form id="bookingForm" onsubmit="submitBooking(event)">
                <div class="form-group">
                    <input type="text" placeholder="Nama Anda" required>
                </div>
                <div class="form-group">
                    <input type="tel" placeholder="Nombor Telefon" required>
                </div>
                <div class="form-group">
                    <select id="serviceSelect">
                        <option value="Gunting Klasik - RM35">Gunting Klasik - RM35</option>
                        <option value="Pakej Yoyo Lengkap - RM65">Pakej Yoyo Lengkap - RM65</option>
                        <option value="Kemasan Jambang - RM25">Kemasan Jambang - RM25</option>
                        <option value="Umum">Lain-lain</option>
                    </select>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">Sahkan Tempahan</button>
            </form>
            
            <button class="close-modal" onclick="closeModal()">Batal</button>
        </div>
    </div>

    <!-- JavaScript Vanilla -->
    <script>
        // Logik Menu Navigasi Mudah Alih (Hamburger Toggle)
        const hamburgerBtn = document.getElementById('hamburgerBtn');
        const navLinks = document.getElementById('navLinks');

        hamburgerBtn.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });

        // Tutup menu bimbit bila klik pautan
        const menuItems = document.querySelectorAll('.nav-links a');
        menuItems.forEach(item => {
            item.addEventListener('click', () => {
                navLinks.classList.remove('active');
            });
        });

        // Logik Modal Custom (Menggantikan alert() biasa)
        const modal = document.getElementById('bookingModal');
        const serviceSelect = document.getElementById('serviceSelect');

        function openModal(serviceName) {
            modal.classList.add('active');
            // Pra-pilih perkhidmatan berdasarkan butang yang ditekan
            if(serviceName) {
                const options = Array.from(serviceSelect.options);
                const exists = options.some(opt => opt.value === serviceName);
                if(exists) {
                    serviceSelect.value = serviceName;
                } else {
                    serviceSelect.value = "Umum";
                }
            }
        }

        function closeModal() {
            modal.classList.remove('active');
            document.getElementById('bookingForm').reset();
        }

        // Tutup modal jika klik di luar kotak (overlay)
        modal.addEventListener('click', function(e) {
            if (e.target === this) {
                closeModal();
            }
        });

        // Simulasi Hantar Borang Tempahan
        function submitBooking(e) {
            e.preventDefault();
            // Menukar kandungan modal untuk menunjukkan kejayaan
            const modalContent = document.querySelector('.modal-content');
            modalContent.innerHTML = `
                <h3 style="color: #4ade80;">Tempahan Berjaya!</h3>
                <p>Terima kasih. Kami akan menghubungi anda melalui WhatsApp sebentar lagi untuk pengesahan masa.</p>
                <button class="btn btn-primary" onclick="resetModalUI()" style="margin-top: 20px;">Tutup</button>
            `;
        }

        // Kembalikan UI asal Modal
        function resetModalUI() {
            closeModal();
            setTimeout(() => {
                const modalContent = document.querySelector('.modal-content');
                modalContent.innerHTML = `
                    <h3>Tempah Slot Anda</h3>
                    <p>Sila tinggalkan butiran untuk pengesahan slot.</p>
                    <form id="bookingForm" onsubmit="submitBooking(event)">
                        <div class="form-group">
                            <input type="text" placeholder="Nama Anda" required>
                        </div>
                        <div class="form-group">
                            <input type="tel" placeholder="Nombor Telefon" required>
                        </div>
                        <div class="form-group">
                            <select id="serviceSelect">
                                <option value="Gunting Klasik - RM35">Gunting Klasik - RM35</option>
                                <option value="Pakej Yoyo Lengkap - RM65">Pakej Yoyo Lengkap - RM65</option>
                                <option value="Kemasan Jambang - RM25">Kemasan Jambang - RM25</option>
                                <option value="Umum">Lain-lain</option>
                            </select>
                        </div>
                        <button type="submit" class="btn btn-primary" style="width: 100%;">Sahkan Tempahan</button>
                    </form>
                    <button class="close-modal" onclick="closeModal()">Batal</button>
                `;
            }, 300); // Tunggu animasi tutup selesai
        }
    </script>
</body>
</html>
