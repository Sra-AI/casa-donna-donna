[casa-donna-donna-lookbook.html](https://github.com/user-attachments/files/26861191/casa-donna-donna-lookbook.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Casa Donna Donna | Lookbook</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;1,400&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --color-primary: #1a1a1a;
            --color-secondary: #c9a962;
            --color-cream: #f9f7f2;
            --color-white: #ffffff;
            --font-serif: 'Playfair Display', Georgia, serif;
            --font-sans: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: var(--font-sans);
            color: var(--color-primary);
            background-color: var(--color-cream);
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            padding: 1.5rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: transparent;
            transition: all 0.3s ease;
        }

        nav.scrolled {
            background: rgba(249, 247, 242, 0.98);
            backdrop-filter: blur(10px);
        }

        .logo {
            font-family: var(--font-serif);
            font-size: 1.4rem;
            font-weight: 700;
            letter-spacing: 0.12em;
            text-transform: uppercase;
            color: var(--color-white);
            text-decoration: none;
        }

        nav.scrolled .logo {
            color: var(--color-primary);
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--color-white);
            font-size: 0.8rem;
            font-weight: 500;
            letter-spacing: 0.1em;
            text-transform: uppercase;
            transition: color 0.3s ease;
        }

        nav.scrolled .nav-links a {
            color: var(--color-primary);
        }

        .nav-links a:hover {
            color: var(--color-secondary);
        }

        /* Hero Fullscreen */
        .hero {
            height: 100vh;
            width: 100%;
            position: relative;
            overflow: hidden;
        }

        .hero-slider {
            width: 100%;
            height: 100%;
        }

        .hero-slide {
            position: absolute;
            width: 100%;
            height: 100%;
            opacity: 0;
            transition: opacity 1.5s ease;
        }

        .hero-slide.active {
            opacity: 1;
        }

        .hero-slide img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .hero-overlay {
            position: absolute;
            inset: 0;
            background: rgba(0,0,0,0.3);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--color-white);
        }

        .hero-subtitle {
            font-size: 0.85rem;
            letter-spacing: 0.4em;
            text-transform: uppercase;
            margin-bottom: 1.5rem;
            font-weight: 500;
        }

        .hero-title {
            font-family: var(--font-serif);
            font-size: clamp(3rem, 8vw, 6rem);
            font-weight: 400;
            margin-bottom: 1rem;
        }

        .hero-title em {
            font-style: italic;
            color: var(--color-secondary);
        }

        .scroll-indicator {
            position: absolute;
            bottom: 3rem;
            left: 50%;
            transform: translateX(-50%);
            color: var(--color-white);
            font-size: 0.75rem;
            letter-spacing: 0.2em;
            text-transform: uppercase;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateX(-50%) translateY(0); }
            50% { transform: translateX(-50%) translateY(10px); }
        }

        /* Gallery Section */
        .gallery-section {
            padding: 6rem 5%;
        }

        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }

        .section-label {
            font-size: 0.8rem;
            letter-spacing: 0.25em;
            text-transform: uppercase;
            color: var(--color-secondary);
            margin-bottom: 1rem;
            font-weight: 600;
            display: block;
        }

        .section-title {
            font-family: var(--font-serif);
            font-size: clamp(2.5rem, 5vw, 3.5rem);
            font-weight: 400;
            color: var(--color-primary);
        }

        /* Masonry Grid */
        .masonry-grid {
            column-count: 4;
            column-gap: 1rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .masonry-item {
            break-inside: avoid;
            margin-bottom: 1rem;
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .masonry-item img {
            width: 100%;
            display: block;
            transition: transform 0.6s ease;
        }

        .masonry-item:hover img {
            transform: scale(1.05);
        }

        /* Full Width Images */
        .fullwidth-section {
            width: 100%;
            height: 70vh;
            position: relative;
            overflow: hidden;
            margin: 4rem 0;
        }

        .fullwidth-section img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .fullwidth-overlay {
            position: absolute;
            inset: 0;
            background: rgba(0,0,0,0.4);
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .fullwidth-overlay h2 {
            font-family: var(--font-serif);
            font-size: clamp(2rem, 5vw, 3.5rem);
            font-weight: 400;
            color: var(--color-white);
            text-align: center;
            padding: 2rem;
        }

        /* Featured Models Grid */
        .featured-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1.5rem;
            max-width: 1400px;
            margin: 0 auto;
            padding: 4rem 5%;
        }

        .featured-item {
            position: relative;
            height: 600px;
            overflow: hidden;
            cursor: pointer;
        }

        .featured-item:first-child {
            grid-column: span 2;
        }

        .featured-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.7s ease;
        }

        .featured-item:hover img {
            transform: scale(1.08);
        }

        .featured-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            padding: 3rem 2rem;
            background: linear-gradient(transparent, rgba(0,0,0,0.8));
            color: var(--color-white);
        }

        .featured-overlay h3 {
            font-family: var(--font-serif);
            font-size: 1.8rem;
            font-weight: 400;
            margin-bottom: 0.5rem;
        }

        .featured-overlay p {
            font-size: 0.9rem;
            opacity: 0.9;
        }

        /* Story Section */
        .story-section {
            padding: 6rem 5%;
            background: var(--color-white);
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
            max-width: 1400px;
            margin: 4rem auto;
        }

        .story-content h2 {
            font-family: var(--font-serif);
            font-size: clamp(2rem, 4vw, 3rem);
            font-weight: 400;
            margin-bottom: 1.5rem;
            line-height: 1.3;
        }

        .story-content p {
            color: var(--color-gray);
            font-size: 1.05rem;
            line-height: 1.9;
            margin-bottom: 2rem;
        }

        .story-image {
            height: 600px;
            overflow: hidden;
        }

        .story-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        /* Quote Section */
        /* Atendimento Section */
        .atendimento-section {
            padding: 6rem 5%;
            background: var(--color-white);
        }

        .atendentes-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto 3rem;
        }

        .atendente-card {
            text-align: center;
            padding: 2rem;
            background: var(--color-cream);
            border-radius: 12px;
            transition: all 0.4s ease;
        }

        .atendente-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 50px rgba(0,0,0,0.1);
        }

        .atendente-photo {
            width: 120px;
            height: 120px;
            margin: 0 auto 1.5rem;
            border-radius: 50%;
            overflow: hidden;
            border: 3px solid var(--color-secondary);
        }

        .atendente-photo img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .atendente-card h3 {
            font-family: var(--font-serif);
            font-size: 1.3rem;
            font-weight: 500;
            margin-bottom: 0.5rem;
            color: var(--color-primary);
        }

        .atendente-role {
            font-size: 0.85rem;
            color: var(--color-gray);
            margin-bottom: 1.5rem;
            letter-spacing: 0.05em;
        }

        .btn-whatsapp {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            padding: 0.8rem 1.5rem;
            background: #25D366;
            color: var(--color-white);
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 0.9rem;
            transition: all 0.3s ease;
        }

        .btn-whatsapp:hover {
            background: #128C7E;
            transform: scale(1.05);
        }

        .atendimento-geral {
            text-align: center;
            padding: 2rem;
            background: var(--color-cream);
            border-radius: 12px;
            max-width: 600px;
            margin: 0 auto;
        }

        .atendimento-geral h3 {
            font-family: var(--font-serif);
            font-size: 1.5rem;
            font-weight: 400;
            color: var(--color-primary);
        }

        /* Location Section */
        .location-section {
            padding: 6rem 5%;
            background: var(--color-cream);
        }

        .location-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .location-info h2 {
            font-family: var(--font-serif);
            font-size: clamp(2rem, 4vw, 2.5rem);
            font-weight: 400;
            margin-bottom: 1rem;
        }

        .location-text {
            color: var(--color-gray);
            font-size: 1.05rem;
            line-height: 1.8;
            margin-bottom: 2rem;
        }

        .location-details {
            margin-bottom: 2rem;
        }

        .location-item {
            display: flex;
            gap: 1rem;
            margin-bottom: 1.5rem;
            padding: 1rem;
            background: var(--color-white);
            border-radius: 8px;
        }

        .location-icon {
            font-size: 1.5rem;
            flex-shrink: 0;
        }

        .location-item strong {
            display: block;
            font-size: 0.85rem;
            letter-spacing: 0.05em;
            margin-bottom: 0.3rem;
        }

        .location-item span {
            color: var(--color-gray);
            font-size: 0.95rem;
            line-height: 1.6;
        }

        .location-buttons {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .map-wrapper {
            height: 500px;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 20px 60px rgba(0,0,0,0.1);
        }

        .map-container {
            width: 100%;
            height: 100%;
        }

        .map-container iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        .quote-section {
            padding: 8rem 5%;
            background: var(--color-primary);
            text-align: center;
            color: var(--color-white);
        }

        .quote-section blockquote {
            font-family: var(--font-serif);
            font-size: clamp(1.5rem, 3vw, 2.5rem);
            font-weight: 400;
            font-style: italic;
            max-width: 900px;
            margin: 0 auto;
            line-height: 1.6;
        }

        .quote-section cite {
            display: block;
            margin-top: 2rem;
            font-size: 0.9rem;
            letter-spacing: 0.2em;
            text-transform: uppercase;
            font-style: normal;
            color: var(--color-secondary);
        }

        /* Final CTA */
        .final-cta {
            padding: 6rem 5%;
            text-align: center;
            background: var(--color-cream);
        }

        .final-cta h2 {
            font-family: var(--font-serif);
            font-size: clamp(2rem, 4vw, 3rem);
            font-weight: 400;
            margin-bottom: 1rem;
        }

        .final-cta p {
            color: var(--color-gray);
            margin-bottom: 2rem;
        }

        .btn {
            display: inline-block;
            padding: 1rem 2.5rem;
            font-size: 0.8rem;
            font-weight: 600;
            letter-spacing: 0.15em;
            text-transform: uppercase;
            text-decoration: none;
            transition: all 0.4s ease;
            background: var(--color-primary);
            color: var(--color-white);
        }

        .btn:hover {
            background: var(--color-secondary);
        }

        /* Footer */
        footer {
            background: var(--color-primary);
            color: var(--color-white);
            padding: 3rem 5%;
            text-align: center;
        }

        .footer-logo {
            font-family: var(--font-serif);
            font-size: 1.5rem;
            font-weight: 700;
            letter-spacing: 0.12em;
            text-transform: uppercase;
            margin-bottom: 1.5rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin: 1.5rem 0;
        }

        .social-links a {
            color: var(--color-white);
            text-decoration: none;
            font-size: 0.9rem;
            transition: color 0.3s ease;
        }

        .social-links a:hover {
            color: var(--color-secondary);
        }

        .copyright {
            color: rgba(255,255,255,0.5);
            font-size: 0.85rem;
            margin-top: 1.5rem;
        }

        /* Chat Button */
        .chat-button {
            position: fixed;
            bottom: 30px;
            right: 30px;
            z-index: 999;
        }

        .chat-btn {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            background: linear-gradient(135deg, #25D366 0%, #128C7E 100%);
            border: none;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            box-shadow: 0 8px 25px rgba(37, 211, 102, 0.4);
            transition: all 0.4s ease;
            text-decoration: none;
        }

        .chat-btn:hover {
            transform: scale(1.1);
            box-shadow: 0 12px 35px rgba(37, 211, 102, 0.5);
        }

        .chat-btn::after {
            content: 'Falar com atendente';
            position: absolute;
            right: 80px;
            background: var(--color-primary);
            color: var(--color-white);
            padding: 0.5rem 1rem;
            border-radius: 4px;
            font-size: 0.8rem;
            white-space: nowrap;
            opacity: 0;
            pointer-events: none;
            transition: all 0.3s ease;
        }

        .chat-btn:hover::after {
            opacity: 1;
            right: 75px;
        }

        /* Chat Widget */
        .chat-widget {
            position: fixed;
            bottom: 120px;
            right: 30px;
            width: 380px;
            background: var(--color-white);
            border-radius: 12px;
            box-shadow: 0 10px 50px rgba(0,0,0,0.15);
            z-index: 999;
            transform: scale(0);
            transform-origin: bottom right;
            transition: all 0.3s ease;
            overflow: hidden;
        }

        .chat-widget.active {
            transform: scale(1);
        }

        .chat-header {
            background: linear-gradient(135deg, var(--color-primary) 0%, #2a2a2a 100%);
            color: var(--color-white);
            padding: 1.2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .chat-header-info h4 {
            font-family: var(--font-serif);
            font-size: 1.1rem;
            margin-bottom: 0.2rem;
        }

        .chat-header-info p {
            font-size: 0.8rem;
            opacity: 0.8;
        }

        .chat-close {
            background: transparent;
            border: none;
            color: var(--color-white);
            font-size: 1.5rem;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .chat-close:hover {
            transform: rotate(90deg);
        }

        .chat-body {
            padding: 1.5rem;
        }

        .chat-options {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .chat-option {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem;
            background: var(--color-cream);
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            color: var(--color-primary);
        }

        .chat-option:hover {
            background: var(--color-secondary);
            color: var(--color-white);
            transform: translateX(5px);
        }

        .chat-option-icon {
            width: 45px;
            height: 45px;
            background: var(--color-white);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.3rem;
            flex-shrink: 0;
        }

        .chat-option-text h5 {
            font-size: 0.95rem;
            margin-bottom: 0.2rem;
        }

        .chat-option-text p {
            font-size: 0.8rem;
            opacity: 0.8;
        }

        .chat-status {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-top: 1rem;
            padding-top: 1rem;
            border-top: 1px solid var(--color-light-gray);
            font-size: 0.85rem;
            color: var(--color-gray);
        }

        .status-dot {
            width: 8px;
            height: 8px;
            background: #25D366;
            border-radius: 50%;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }

        /* Mobile */
        @media (max-width: 900px) {
            .masonry-grid {
                column-count: 2;
            }

            .featured-grid {
                grid-template-columns: 1fr;
            }

            .featured-item:first-child {
                grid-column: span 1;
            }

            .story-section {
                grid-template-columns: 1fr;
            }

            .location-container {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .map-wrapper {
                height: 350px;
            }

            .nav-links {
                display: none;
            }
        }

        @media (max-width: 600px) {
            .masonry-grid {
                column-count: 1;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav id="navbar">
        <a href="#" class="logo">Casa Donna Donna</a>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#galeria">Galeria</a></li>
            <li><a href="#colecoes">Coleções</a></li>
            <li><a href="#atendimento">Atendimento</a></li>
            <li><a href="#localizacao">Localização</a></li>
        </ul>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-slider">
            <div class="hero-slide active">
                <img src="https://images.unsplash.com/photo-1469334031218-e382a71b716b?w=1920&q=80" alt="Modelo Donna Donna">
            </div>
            <div class="hero-slide">
                <img src="https://images.unsplash.com/photo-1496747611176-843222e1e57c?w=1920&q=80" alt="Moda Feminina">
            </div>
            <div class="hero-slide">
                <img src="https://images.unsplash.com/photo-1483985988355-763728e1935b?w=1920&q=80" alt="Elegância">
            </div>
        </div>
        <div class="hero-overlay">
            <p class="hero-subtitle">Lookbook 2026</p>
            <h1 class="hero-title">Beleza que <em>inspira</em></h1>
            <p class="scroll-indicator">Role para explorar ↓</p>
        </div>
    </section>

    <!-- Gallery Masonry -->
    <section class="gallery-section" id="galeria">
        <div class="section-header">
            <span class="section-label">Galeria</span>
            <h2 class="section-title">Momentos Donna Donna</h2>
        </div>
        <div class="masonry-grid">
            <div class="masonry-item">
                <img src="https://images.unsplash.com/photo-1509631179647-0177331693ae?w=600&q=80" alt="Modelo">
            </div>
            <div class="masonry-item">
                <img src="https://images.unsplash.com/photo-1539008835657-9e8e9680c956?w=600&q=80" alt="Vestido">
            </div>
            <div class="masonry-item">
                <img src="https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?w=600&q=80" alt="Fashion">
            </div>
            <div class="masonry-item">
                <img src="https://images.unsplash.com/photo-1550614000-4b9519e02d15?w=600&q=80" alt="Alfaiataria">
            </div>
            <div class="masonry-item">
                <img src="https://images.unsplash.com/photo-1552874869-5c39ec9288dc?w=600&q=80" alt="Estilo">
            </div>
            <div class="masonry-item">
                <img src="https://images.unsplash.com/photo-1583496661160-fb5886a0aaaa?w=600&q=80" alt="Look">
            </div>
            <div class="masonry-item">
                <img src="https://images.unsplash.com/photo-1595777457583-95e059d581b8?w=600&q=80" alt="Elegância">
            </div>
            <div class="masonry-item">
                <img src="https://images.unsplash.com/photo-1564257631407-4deb1f99d992?w=600&q=80" alt="Fashion">
            </div>
        </div>
    </section>

    <!-- Full Width Banner -->
    <div class="fullwidth-section">
        <img src="https://images.unsplash.com/photo-1469334031218-e382a71b716b?w=1920&q=80" alt="Banner">
        <div class="fullwidth-overlay">
            <h2>Cada mulher carrega<br>uma história única</h2>
        </div>
    </div>

    <!-- Featured Collections -->
    <section class="featured-grid" id="colecoes">
        <div class="featured-item">
            <img src="https://images.unsplash.com/photo-1558769132-cb1aea458c5e?w=1200&q=80" alt="Coleção Principal">
            <div class="featured-overlay">
                <h3>Coleção Principal</h3>
                <p>Outono/Inverno 2026 • Peças exclusivas</p>
            </div>
        </div>
        <div class="featured-item">
            <img src="https://images.unsplash.com/photo-1539109136881-3be0616acf4b?w=600&q=80" alt="Evening">
            <div class="featured-overlay">
                <h3>Evening</h3>
                <p>Noites memoráveis</p>
            </div>
        </div>
        <div class="featured-item">
            <img src="https://images.unsplash.com/photo-1550614000-4b9519e02d15?w=600&q=80" alt="Alfaiataria">
            <div class="featured-overlay">
                <h3>Alfaiataria</h3>
                <p>Poder e sofisticação</p>
            </div>
        </div>
        <div class="featured-item">
            <img src="https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?w=600&q=80" alt="Casual">
            <div class="featured-overlay">
                <h3>Casual Chic</h3>
                <p>Elegância no dia a dia</p>
            </div>
        </div>
    </section>

    <!-- Story Section -->
    <section class="story-section" id="sobre">
        <div class="story-content">
            <span class="section-label">Nossa Essência</span>
            <h2>Mais que moda,<br>uma expressão de quem você é</h2>
            <p>A Casa Donna Donna nasceu do desejo de celebrar a mulher moderna em toda sua complexidade e beleza. Cada peça é cuidadosamente selecionada para representar diferentes facetas da feminilidade contemporânea.</p>
            <p>Em nossa loja em Florianópolis, criamos uma experiência única onde elegância, conforto e autenticidade se encontram. Venha nos visitar e descubra seu estilo Donna Donna.</p>
            <a href="casa-donna-donna.html" class="btn">Conhecer a Loja</a>
        </div>
        <div class="story-image">
            <img src="https://images.unsplash.com/photo-1441984904996-e0b6ba687e04?w=800&q=80" alt="Loja Donna Donna">
        </div>
    </section>

    <!-- Atendimento Section -->
    <section class="atendimento-section" id="atendimento">
        <div class="section-header">
            <span class="section-label">Fale Conosco</span>
            <h2 class="section-title">Nossas Atendentes</h2>
            <p class="section-subtitle" style="color: var(--color-gray); margin-top: 1rem; font-size: 1.05rem;">Escolha sua atendente de preferência e converse direto pelo WhatsApp</p>
        </div>
        <div class="atendentes-grid">
            <div class="atendente-card">
                <div class="atendente-photo">
                    <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=300&q=80" alt="Ana">
                </div>
                <h3>Ana Carolina</h3>
                <p class="atendente-role">Consultora de Estilo</p>
                <a href="https://wa.me/5548996016330?text=Olá%20Ana,%20gostaria%20de%20atendimento" target="_blank" class="btn-whatsapp">
                    <span>📱</span> (48) 99601-6330
                </a>
            </div>
            <div class="atendente-card">
                <div class="atendente-photo">
                    <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=300&q=80" alt="Beatriz">
                </div>
                <h3>Beatriz Silva</h3>
                <p class="atendente-role">Personal Stylist</p>
                <a href="https://wa.me/5548996016331?text=Olá%20Beatriz,%20gostaria%20de%20atendimento" target="_blank" class="btn-whatsapp">
                    <span>📱</span> (48) 99601-6331
                </a>
            </div>
            <div class="atendente-card">
                <div class="atendente-photo">
                    <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=300&q=80" alt="Camila">
                </div>
                <h3>Camila Costa</h3>
                <p class="atendente-role">Consultora de Vendas</p>
                <a href="https://wa.me/5548996016332?text=Olá%20Camila,%20gostaria%20de%20atendimento" target="_blank" class="btn-whatsapp">
                    <span>📱</span> (48) 99601-6332
                </a>
            </div>
            <div class="atendente-card">
                <div class="atendente-photo">
                    <img src="https://images.unsplash.com/photo-1524504388940-b1c1722653e1?w=300&q=80" alt="Daniela">
                </div>
                <h3>Daniela Oliveira</h3>
                <p class="atendente-role">Gerente de Loja</p>
                <a href="https://wa.me/5548996016333?text=Olá%20Daniela,%20gostaria%20de%20atendimento" target="_blank" class="btn-whatsapp">
                    <span>📱</span> (48) 99601-6333
                </a>
            </div>
            <div class="atendente-card">
                <div class="atendente-photo">
                    <img src="https://images.unsplash.com/photo-1517841905240-472988babdf9?w=300&q=80" alt="Fernanda">
                </div>
                <h3>Fernanda Santos</h3>
                <p class="atendente-role">Consultora de Estilo</p>
                <a href="https://wa.me/5548996016334?text=Olá%20Fernanda,%20gostaria%20de%20atendimento" target="_blank" class="btn-whatsapp">
                    <span>📱</span> (48) 99601-6334
                </a>
            </div>
            <div class="atendente-card">
                <div class="atendente-photo">
                    <img src="https://images.unsplash.com/photo-1529626455594-4ff0802cfb7e?w=300&q=80" alt="Gabriela">
                </div>
                <h3>Gabriela Mendes</h3>
                <p class="atendente-role">Personal Stylist</p>
                <a href="https://wa.me/5548996016335?text=Olá%20Gabriela,%20gostaria%20de%20atendimento" target="_blank" class="btn-whatsapp">
                    <span>📱</span> (48) 99601-6335
                </a>
            </div>
        </div>
        <div class="atendimento-geral">
            <h3>Prefere atendimento geral?</h3>
            <a href="https://wa.me/5548996016330" target="_blank" class="btn btn-gold" style="display: inline-block; margin-top: 1.5rem; padding: 1rem 2.5rem; background: #25D366; color: white; text-decoration: none; border-radius: 50px; font-weight: 600;">
                💬 Falar com qualquer atendente
            </a>
        </div>
    </section>

    <!-- Quote Section -->
    <section class="quote-section">
        <blockquote>
            "A moda é uma forma de arte que você veste todos os dias. É a sua assinatura, a sua maneira de contar ao mundo quem você é."
        </blockquote>
        <cite>— Casa Donna Donna</cite>
    </section>

    <!-- Location Section -->
    <section class="location-section" id="localizacao">
        <div class="location-container">
            <div class="location-info">
                <span class="section-label">Visite-nos</span>
                <h2>Nossa Loja</h2>
                <p class="location-text">Venha viver uma experiência única de compras em nosso ambiente sofisticado, criado especialmente para você.</p>

                <div class="location-details">
                    <div class="location-item">
                        <span class="location-icon">📍</span>
                        <div>
                            <strong>Endereço</strong>
                            <span>Rua do Comércio, 1234 - Centro<br>Ariquemes - RO, 76870-000</span>
                        </div>
                    </div>
                    <div class="location-item">
                        <span class="location-icon">🕐</span>
                        <div>
                            <strong>Horário</strong>
                            <span>Segunda a Sexta: 9h às 19h<br>Sábado: 9h às 13h</span>
                        </div>
                    </div>
                    <div class="location-item">
                        <span class="location-icon">📞</span>
                        <div>
                            <strong>Telefone</strong>
                            <span>(48) 99601-6330</span>
                        </div>
                    </div>
                </div>

                <div class="location-buttons">
                    <a href="https://maps.google.com/?q=Rua+do+Comercio+1234+Ariquemes+RO" target="_blank" class="btn btn-primary">
                        🗺️ Traçar Rota
                    </a>
                    <a href="https://wa.me/5548996016330" target="_blank" class="btn btn-gold">
                        💬 WhatsApp
                    </a>
                </div>
            </div>

            <div class="map-wrapper">
                <div class="map-container">
                    <iframe
                        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3919.5157!2d-63.0456!3d-9.9133!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x9428f12b8a8b8b8b%3A0x1234567890abcdef!2sRua%20do%20Com%C3%A9rcio%2C%201234%20-%20Centro%2C%20Ariquemes%20-%20RO!5e0!3m2!1spt-BR!2sbr!4v1234567890"
                        allowfullscreen=""
                        loading="lazy"
                        referrerpolicy="no-referrer-when-downgrade">
                    </iframe>
                </div>
            </div>
        </div>
    </section>

    <!-- Final CTA -->
    <section class="final-cta">
        <h2>Agende sua visita</h2>
        <p>Receba atendimento personalizado com nossas consultoras de estilo</p>
        <a href="https://wa.me/5548996016330" target="_blank" class="btn">Falar no WhatsApp</a>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-logo">Casa Donna Donna</div>
        <div class="social-links">
            <a href="https://www.instagram.com/casadonnadonna" target="_blank">Instagram</a>
            <a href="https://www.facebook.com/casadonnadonna" target="_blank">Facebook</a>
            <a href="https://linktr.ee/casadonnadonna" target="_blank">Linktree</a>
        </div>
        <p class="copyright">&copy; 2026 Casa Donna Donna. Todos os direitos reservados.</p>
    </footer>

    <!-- Chat Button -->
    <div class="chat-button">
        <button class="chat-btn" id="chatBtn" aria-label="Falar com atendente">💬</button>
    </div>

    <!-- Chat Widget -->
    <div class="chat-widget" id="chatWidget">
        <div class="chat-header">
            <div class="chat-header-info">
                <h4>Atendimento Donna Donna</h4>
                <p>Como podemos ajudar você?</p>
            </div>
            <button class="chat-close" id="chatClose">×</button>
        </div>
        <div class="chat-body">
            <div class="chat-options">
                <a href="https://wa.me/5548996016330" target="_blank" class="chat-option">
                    <div class="chat-option-icon">💬</div>
                    <div class="chat-option-text">
                        <h5>WhatsApp</h5>
                        <p>Resposta em até 5 minutos</p>
                    </div>
                </a>
                <a href="tel:+5548996016330" class="chat-option">
                    <div class="chat-option-icon">📞</div>
                    <div class="chat-option-text">
                        <h5>Ligar Agora</h5>
                        <p>(48) 99601-6330</p>
                    </div>
                </a>
                <a href="mailto:contato@casadonnadonna.com.br" class="chat-option">
                    <div class="chat-option-icon">✉️</div>
                    <div class="chat-option-text">
                        <h5>E-mail</h5>
                        <p>Respondemos em até 24h</p>
                    </div>
                </a>
            </div>
            <div class="chat-status">
                <span class="status-dot"></span>
                <span>Atendimento online • Seg a Sex, 9h às 19h</span>
            </div>
        </div>
    </div>

    <script>
        // Hero Slider
        const slides = document.querySelectorAll('.hero-slide');
        let currentSlide = 0;

        function nextSlide() {
            slides[currentSlide].classList.remove('active');
            currentSlide = (currentSlide + 1) % slides.length;
            slides[currentSlide].classList.add('active');
        }

        setInterval(nextSlide, 5000);

        // Navbar scroll effect
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 100) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });

        // Chat Widget
        const chatBtn = document.getElementById('chatBtn');
        const chatWidget = document.getElementById('chatWidget');
        const chatClose = document.getElementById('chatClose');

        chatBtn.addEventListener('click', function() {
            chatWidget.classList.toggle('active');
        });

        chatClose.addEventListener('click', function() {
            chatWidget.classList.remove('active');
        });

        // Close chat when clicking outside
        document.addEventListener('click', function(e) {
            if (!chatWidget.contains(e.target) && !chatBtn.contains(e.target)) {
                chatWidget.classList.remove('active');
            }
        });
    </script>
</body>
</html>
