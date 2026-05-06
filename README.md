<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مكتبة الألعاب الإلكترونية | Electronic Games Library</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Poppins:wght@300;400;600;700&family=Cairo:wght@400;700&display=swap');

        :root {
            --primary: #6D28D9;
            --secondary: #EC4899;
            --accent: #00D9FF;
            --dark-bg: #0F172A;
            --card-bg: #1E293B;
            --text-primary: #F1F5F9;
            --text-secondary: #CBD5E1;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #0F172A 0%, #1a0f3f 50%, #0F172A 100%);
            color: var(--text-primary);
            overflow-x: hidden;
            background-attachment: fixed;
        }

        body.ar-lang {
            font-family: 'Cairo', 'Poppins', sans-serif;
            direction: rtl;
        }

        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }

        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: white;
            border-radius: 50%;
            opacity: 0.5;
            animation: twinkle 3s infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 1; }
        }

        /* Header */
        header {
            position: sticky;
            top: 0;
            z-index: 1000;
            background: rgba(15, 23, 42, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 2px solid var(--accent);
            padding: 1rem 0;
        }

        .header-content {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 1rem;
            font-size: 1.8rem;
            font-weight: 900;
            font-family: 'Orbitron', sans-serif;
            color: var(--accent);
            text-shadow: 0 0 20px rgba(0, 217, 255, 0.5);
        }

        .logo-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            box-shadow: 0 0 30px rgba(109, 40, 217, 0.6);
        }

        .nav-center {
            display: flex;
            gap: 2rem;
        }

        .nav-center a {
            color: var(--text-secondary);
            text-decoration: none;
            font-weight: 600;
            position: relative;
            transition: color 0.3s;
            cursor: pointer;
        }

        .nav-center a:hover,
        .nav-center a.active {
            color: var(--accent);
        }

        .nav-center a.active::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 2px;
            background: var(--accent);
        }

        .nav-right {
            display: flex;
            gap: 1.5rem;
            align-items: center;
        }

        .lang-toggle {
            background: var(--primary);
            border: none;
            color: white;
            padding: 0.6rem 1.2rem;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }

        .lang-toggle:hover {
            background: var(--secondary);
            box-shadow: 0 0 20px rgba(236, 72, 153, 0.5);
        }

        .user-menu {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--accent), var(--secondary));
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: transform 0.3s;
        }

        .user-menu:hover {
            transform: scale(1.1);
        }

        /* Main Content */
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 3rem 2rem;
            position: relative;
            z-index: 1;
        }

        /* Hero Section */
        .hero {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
            margin-bottom: 4rem;
            background: linear-gradient(135deg, rgba(109, 40, 217, 0.1), rgba(236, 72, 153, 0.1));
            padding: 3rem;
            border-radius: 20px;
            border: 1px solid rgba(0, 217, 255, 0.3);
            overflow: hidden;
            position: relative;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            font-family: 'Orbitron', sans-serif;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, var(--accent), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            line-height: 1.2;
        }

        .hero-content p {
            font-size: 1.1rem;
            color: var(--text-secondary);
            margin-bottom: 2rem;
            line-height: 1.8;
        }

        .cta-buttons {
            display: flex;
            gap: 1.5rem;
            flex-wrap: wrap;
        }

        .btn {
            padding: 0.9rem 2rem;
            border: none;
            border-radius: 10px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            box-shadow: 0 10px 30px rgba(109, 40, 217, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(109, 40, 217, 0.6);
        }

        .btn-secondary {
            background: transparent;
            border: 2px solid var(--accent);
            color: var(--accent);
            box-shadow: 0 0 20px rgba(0, 217, 255, 0.3);
        }

        .btn-secondary:hover {
            background: rgba(0, 217, 255, 0.1);
            box-shadow: 0 0 30px rgba(0, 217, 255, 0.6);
        }

        .hero-visual {
            position: relative;
            height: 400px;
            perspective: 1000px;
        }

        .game-card-3d {
            width: 100%;
            height: 100%;
            position: relative;
            transform-style: preserve-3d;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotateX(0deg); }
            50% { transform: translateY(-30px) rotateX(5deg); }
        }

        .game-card-front {
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 60px rgba(109, 40, 217, 0.5);
            position: relative;
        }

        .game-card-front::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: moveGrid 20s linear infinite;
        }

        @keyframes moveGrid {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        .game-card-front .content {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            padding: 2rem;
            background: linear-gradient(to top, rgba(0,0,0,0.8), transparent);
            color: white;
        }

        .game-card-front .title {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
        }

        .game-card-front .tag {
            display: inline-block;
            background: rgba(0, 217, 255, 0.2);
            color: var(--accent);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        /* Games Grid */
        .section-title {
            font-size: 2.5rem;
            font-family: 'Orbitron', sans-serif;
            margin-bottom: 2rem;
            color: var(--text-primary);
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .section-title::before {
            content: '';
            width: 5px;
            height: 40px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 3px;
        }

        .games-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }

        .game-card {
            background: var(--card-bg);
            border-radius: 15px;
            overflow: hidden;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 217, 255, 0.2);
            position: relative;
            group: card;
        }

        .game-card:hover {
            transform: translateY(-10px);
            border-color: var(--accent);
            box-shadow: 0 20px 50px rgba(0, 217, 255, 0.3);
        }

        .game-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            position: relative;
            overflow: hidden;
        }

        .game-image::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, rgba(0,217,255,0.1), rgba(236,72,153,0.1));
            opacity: 0;
            transition: opacity 0.3s;
        }

        .game-card:hover .game-image::after {
            opacity: 1;
        }

        .play-btn {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 60px;
            height: 60px;
            background: var(--primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
            opacity: 0;
            transition: all 0.3s;
            box-shadow: 0 0 30px rgba(109, 40, 217, 0.6);
        }

        .game-card:hover .play-btn {
            opacity: 1;
            transform: translate(-50%, -50%) scale(1.1);
        }

        .game-info {
            padding: 1.5rem;
        }

        .game-title {
            font-size: 1.2rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            color: var(--text-primary);
        }

        .game-category {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
            margin-bottom: 1rem;
        }

        .category-tag {
            background: rgba(109, 40, 217, 0.2);
            color: var(--accent);
            padding: 0.3rem 0.8rem;
            border-radius: 5px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .game-rating {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .stars {
            color: var(--secondary);
            font-size: 0.9rem;
        }

        .rating-number {
            background: rgba(0, 217, 255, 0.2);
            padding: 0.3rem 0.8rem;
            border-radius: 5px;
            font-size: 0.9rem;
            font-weight: 600;
            color: var(--accent);
        }

        .game-description {
            color: var(--text-secondary);
            font-size: 0.95rem;
            line-height: 1.6;
            margin-bottom: 1rem;
        }

        .game-stats {
            display: flex;
            justify-content: space-between;
            font-size: 0.85rem;
            color: var(--text-secondary);
            padding-top: 1rem;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        .stat-item {
            text-align: center;
        }

        .stat-label {
            display: block;
            font-size: 0.75rem;
            color: var(--accent);
            font-weight: 600;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            backdrop-filter: blur(5px);
            z-index: 2000;
            align-items: center;
            justify-content: center;
            animation: fadeIn 0.3s;
        }

        .modal.show {
            display: flex;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .modal-content {
            background: var(--card-bg);
            border-radius: 20px;
            width: 90%;
            max-width: 900px;
            max-height: 90vh;
            overflow-y: auto;
            border: 1px solid rgba(0, 217, 255, 0.3);
            box-shadow: 0 0 50px rgba(0, 217, 255, 0.3);
        }

        .modal-header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            padding: 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: white;
        }

        .modal-header h2 {
            font-family: 'Orbitron', sans-serif;
            font-size: 2rem;
        }

        .close-btn {
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .close-btn:hover {
            transform: scale(1.2);
        }

        .modal-body {
            padding: 2rem;
        }

        .modal-video {
            width: 100%;
            height: 400px;
            background: rgba(0,0,0,0.3);
            border-radius: 15px;
            margin-bottom: 2rem;
            border: 1px solid rgba(0, 217, 255, 0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-secondary);
        }

        .modal-info {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .info-block h3 {
            color: var(--accent);
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .info-block p {
            color: var(--text-secondary);
            line-height: 1.6;
        }

        .info-block .rating-display {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-top: 1rem;
        }

        .rating-circle {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, var(--secondary), var(--accent));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: 700;
        }

        /* Filters */
        .filters {
            display: flex;
            gap: 1rem;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }

        .filter-btn {
            padding: 0.7rem 1.5rem;
            background: transparent;
            border: 2px solid rgba(0, 217, 255, 0.3);
            color: var(--text-secondary);
            border-radius: 20px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }

        .filter-btn:hover,
        .filter-btn.active {
            border-color: var(--accent);
            background: rgba(0, 217, 255, 0.1);
            color: var(--accent);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero {
                grid-template-columns: 1fr;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .section-title {
                font-size: 1.8rem;
            }

            .games-grid {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }

            .modal-info {
                grid-template-columns: 1fr;
            }

            .nav-center {
                display: none;
            }
        }

        .scrollbar-hide::-webkit-scrollbar {
            display: none;
        }
    </style>
</head>
<body>
    <!-- Star Background -->
    <div class="stars" id="starsContainer"></div>

    <!-- Header -->
    <header>
        <div class="header-content">
            <div class="logo">
                <div class="logo-icon">🎮</div>
                <div>
                    <div data-en="Game Library" data-ar="مكتبة الألعاب">Game Library</div>
                    <div style="font-size: 0.6em; color: var(--text-secondary);" data-en="Pro Edition" data-ar="الإصدار الاحترافي">Pro Edition</div>
                </div>
            </div>

            <div class="nav-center">
                <a class="active" onclick="navigateTo('home')" data-en="Home" data-ar="الرئيسية">Home</a>
                <a onclick="navigateTo('games')" data-en="Games" data-ar="الألعاب">Games</a>
                <a onclick="navigateTo('categories')" data-en="Categories" data-ar="الفئات">Categories</a>
                <a onclick="navigateTo('trending')" data-en="Trending" data-ar="الشائعة">Trending</a>
            </div>

            <div class="nav-right">
                <button class="lang-toggle" onclick="toggleLanguage()">
                    <span data-en="عربي" data-ar="English">عربي</span>
                </button>
                <div class="user-menu">👤</div>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <div class="container">
        <!-- Hero Section -->
        <section class="hero">
            <div class="hero-content">
                <h1 data-en="Ultimate Gaming Experience" data-ar="أفضل تجربة ألعاب">Ultimate Gaming Experience</h1>
                <p data-en="Discover thousands of games, explore detailed reviews, watch gameplay videos, and join millions of gamers worldwide. Your ultimate destination for everything gaming." data-ar="اكتشف آلاف الألعاب واستكشف التقييمات التفصيلية وشاهد مقاطع اللعب وانضم إلى ملايين لاعبي الفيديو في جميع أنحاء العالم. وجهتك النهائية لكل شيء يتعلق بالألعاب.">
                    Discover thousands of games, explore detailed reviews, watch gameplay videos, and join millions of gamers worldwide.
                </p>
                <div class="cta-buttons">
                    <button class="btn btn-primary" onclick="navigateTo('games')">
                        <i class="fas fa-play"></i>
                        <span data-en="Start Exploring" data-ar="ابدأ الاستكشاف">Start Exploring</span>
                    </button>
                    <button class="btn btn-secondary" onclick="openModal(0)">
                        <i class="fas fa-video"></i>
                        <span data-en="Watch Trailer" data-ar="شاهد الفيديو">Watch Trailer</span>
                    </button>
                </div>
            </div>
            <div class="hero-visual">
                <div class="game-card-3d">
                    <div class="game-card-front">
                        <div style="width: 100%; height: 100%; background: linear-gradient(135deg, #FF6B9D 0%, #C06C84 50%, #6A4C93 100%);"></div>
                        <div class="content">
                            <div class="title">EPIC SAGA 2024</div>
                            <span class="tag">ACTION RPG</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Filters -->
        <div style="margin-bottom: 3rem;">
            <h3 style="margin-bottom: 1rem;" data-en="Filter by Category" data-ar="تصفية حسب الفئة">Filter by Category</h3>
            <div class="filters">
                <button class="filter-btn active" onclick="filterGames('all')" data-en="All" data-ar="الكل">All</button>
                <button class="filter-btn" onclick="filterGames('action')" data-en="Action" data-ar="حركة">Action</button>
                <button class="filter-btn" onclick="filterGames('rpg')" data-en="RPG" data-ar="لعبة دور">RPG</button>
                <button class="filter-btn" onclick="filterGames('sports')" data-en="Sports" data-ar="رياضة">Sports</button>
                <button class="filter-btn" onclick="filterGames('strategy')" data-en="Strategy" data-ar="استراتيجية">Strategy</button>
                <button class="filter-btn" onclick="filterGames('puzzle')" data-en="Puzzle" data-ar="ألغاز">Puzzle</button>
            </div>
        </div>

        <!-- Featured Games -->
        <h2 class="section-title" data-en="Featured Games" data-ar="الألعاب المميزة">Featured Games</h2>
        <div class="games-grid" id="gamesGrid"></div>

        <!-- Trending Games -->
        <h2 class="section-title" data-en="Trending Now" data-ar="الشائعة الآن">Trending Now</h2>
        <div class="games-grid" id="trendingGrid"></div>

        <!-- New Releases -->
        <h2 class="section-title" data-en="New Releases" data-ar="الإصدارات الجديدة">New Releases</h2>
        <div class="games-grid" id="newGrid"></div>
    </div>

    <!-- Modal -->
    <div class="modal" id="gameModal">
        <div class="modal-content">
            <div class="modal-header">
                <h2 id="modalTitle">Game Title</h2>
                <button class="close-btn" onclick="closeModal()">&times;</button>
            </div>
            <div class="modal-body">
                <div class="modal-video">
                    <i class="fas fa-video" style="font-size: 3rem; opacity: 0.5;"></i>
                    <span style="margin-left: 1rem;" data-en="Gameplay Video" data-ar="فيديو اللعب">Gameplay Video</span>
                </div>

                <div class="modal-info">
                    <div>
                        <div class="info-block">
                            <h3 data-en="Description" data-ar="الوصف">Description</h3>
                            <p id="modalDescription">Game description goes here...</p>
                        </div>
                        <div class="info-block">
                            <h3 data-en="Genre" data-ar="النوع">Genre</h3>
                            <p id="modalGenre">Action, Adventure</p>
                        </div>
                    </div>
                    <div>
                        <div class="info-block">
                            <h3 data-en="Rating" data-ar="التقييم">Rating</h3>
                            <div class="rating-display">
                                <div class="rating-circle" id="modalRating">4.8</div>
                                <div>
                                    <div style="color: var(--accent);">★★★★★</div>
                                    <div style="font-size: 0.9rem;">Based on 1000+ reviews</div>
                                </div>
                            </div>
                        </div>
                        <div class="info-block">
                            <h3 data-en="Stats" data-ar="الإحصائيات">Stats</h3>
                            <p>👥 <span id="modalPlayers">2.5M</span> Players | 📥 <span id="modalDownloads">500K</span> Downloads</p>
                        </div>
                    </div>
                </div>

                <button class="btn btn-primary" style="width: 100%;">
                    <i class="fas fa-download"></i>
                    <span data-en="Download Now" data-ar="حمل الآن">Download Now</span>
                </button>
            </div>
        </div>
    </div>

    <script>
        // Game Database
        const games = [
            {
                id: 1,
                titleEn: "God of War Ragnarök",
                titleAr: "إله الحرب رجناروك",
                category: "action",
                genre: "Action, Adventure",
                rating: 4.9,
                reviews: 5200,
                descriptionEn: "Experience the epic conclusion to the God of War saga. Join Kratos and Atreus in an unforgettable journey.",
                descriptionAr: "اختبر الخاتمة الملحمية لملحمة إله الحرب. انضم إلى كراتوس وأترويس في رحلة لا تُنسى.",
                players: "3.2M",
                downloads: "850K",
                image: "#667eea"
            },
            {
                id: 2,
                titleEn: "Elden Ring",
                titleAr: "إلدن رينج",
                category: "rpg",
                genre: "RPG, Adventure",
                rating: 4.8,
                reviews: 4800,
                descriptionEn: "A collaborative masterpiece from FromSoftware and George R.R. Martin. Explore a vast, seamless world.",
                descriptionAr: "تحفة تعاونية من FromSoftware وجورج آر آر مارتن. استكشف عالماً واسعاً وسلساً.",
                players: "2.8M",
                downloads: "720K",
                image: "#764ba2"
            },
            {
                id: 3,
                titleEn: "Forza Horizon 5",
                titleAr: "فورزا هوريزون 5",
                category: "sports",
                genre: "Racing, Open World",
                rating: 4.7,
                reviews: 3900,
                descriptionEn: "Race through Mexico's most beautiful locations in stunning 4K. Experience next-gen racing like never before.",
                descriptionAr: "تسابق عبر أجمل مواقع المكسيك في 4K الخلاب. اختبر السباق من الجيل التالي كما لم يحدث من قبل.",
                players: "1.9M",
                downloads: "640K",
                image: "#ff6b9d"
            },
            {
                id: 4,
                titleEn: "Baldur's Gate 3",
                titleAr: "بالدور ز جيت 3",
                category: "rpg",
                genre: "RPG, Adventure",
                rating: 4.8,
                reviews: 4500,
                descriptionEn: "Shape your own story with incredible freedom. Your choices determine the fate of the world.",
                descriptionAr: "شكّل قصتك الخاصة بحرية مذهلة. اختياراتك تحدد مصير العالم.",
                players: "2.1M",
                downloads: "580K",
                image: "#c06c84"
            },
            {
                id: 5,
                titleEn: "Starfield",
                titleAr: "ستارفيلد",
                category: "rpg",
                genre: "RPG, Space",
                rating: 4.6,
                reviews: 3200,
                descriptionEn: "Explore the universe in this massive space RPG. Create your character and live your space adventure.",
                descriptionAr: "استكشف الكون في لعبة الدور هذه الضخمة. أنشئ شخصيتك واعش مغامرة الفضاء الخاصة بك.",
                players: "2.3M",
                downloads: "690K",
                image: "#6a4c93"
            },
            {
                id: 6,
                titleEn: "Hogwarts Legacy",
                titleAr: "إرث هوجوورتس",
                category: "action",
                genre: "Action, Adventure, Fantasy",
                rating: 4.7,
                reviews: 3800,
                descriptionEn: "Step into the wizarding world and discover your own magical adventure in the 1800s.",
                descriptionAr: "ادخل عالم السحر واكتشف مغامرتك السحرية الخاصة في القرن التاسع عشر.",
                players: "2.6M",
                downloads: "710K",
                image: "#ee5a6f"
            },
            {
                id: 7,
                titleEn: "EA Sports FC 24",
                titleAr: "إي إي سبورتس إف سي 24",
                category: "sports",
                genre: "Sports, Football",
                rating: 4.6,
                reviews: 2900,
                descriptionEn: "Build your ultimate team with the latest football superstars. Compete in thrilling matches worldwide.",
                descriptionAr: "بناء فريقك النهائي مع أفضل نجوم كرة القدم. تنافس في مباريات مشوقة في جميع أنحاء العالم.",
                players: "1.7M",
                downloads: "530K",
                image: "#f77f88"
            },
            {
                id: 8,
                titleEn: "Zelda Tears of the Kingdom",
                titleAr: "زيلدا دموع المملكة",
                category: "action",
                genre: "Action, Adventure, Puzzle",
                rating: 4.9,
                reviews: 4700,
                descriptionEn: "Return to Hyrule in this breathtaking adventure. Solve puzzles and save the kingdom once again.",
                descriptionAr: "عد إلى هايرول في هذه المغامرة المذهلة. حل الألغاز وأنقذ المملكة مرة أخرى.",
                players: "3.4M",
                downloads: "890K",
                image: "#52b788"
            },
            {
                id: 9,
                titleEn: "Civilization VI",
                titleAr: "حضارة 6",
                category: "strategy",
                genre: "Strategy, Turn-based",
                rating: 4.8,
                reviews: 3400,
                descriptionEn: "Build an empire that will stand the test of time. Develop your civilization from ancient times to the future.",
                descriptionAr: "بناء إمبراطورية ستصمد أمام اختبار الزمن. طور حضارتك من العصور القديمة إلى المستقبل.",
                players: "1.5M",
                downloads: "420K",
                image: "#ffd60a"
            },
            {
                id: 10,
                titleEn: "Portal 2",
                titleAr: "بوابة 2",
                category: "puzzle",
                genre: "Puzzle, Science Fiction",
                rating: 4.9,
                reviews: 4200,
                descriptionEn: "Think in portals. Solve intricate puzzles using innovative portal mechanics.",
                descriptionAr: "فكر بالبوابات. حل الألغاز المعقدة باستخدام آليات البوابة المبتكرة.",
                players: "2.2M",
                downloads: "380K",
                image: "#ff9500"
            },
            {
                id: 11,
                titleEn: "Final Fantasy VII Remake",
                titleAr: "فاينل فانتسي 7 ريميك",
                category: "rpg",
                genre: "RPG, Action",
                rating: 4.8,
                reviews: 4100,
                descriptionEn: "Experience the iconic RPG reimagined for modern platforms. The world has never been more beautiful.",
                descriptionAr: "اختبر لعبة الأدوار الأسطورية معاد تخيلها لمنصات حديثة. لم يكن العالم أجمل من أي وقت مضى.",
                players: "2.7M",
                downloads: "630K",
                image: "#00d4ff"
            },
            {
                id: 12,
                titleEn: "Cyberpunk 2077",
                titleAr: "سايبربانك 2077",
                category: "action",
                genre: "Action, RPG, Sci-fi",
                rating: 4.7,
                reviews: 3600,
                descriptionEn: "Immerse yourself in the futuristic world of Night City. Live as you choose in this vast open world.",
                descriptionAr: "انغمس في عالم مدينة الليل المستقبلي. اعش كما تختار في هذا العالم المفتوح الواسع.",
                players: "2.4M",
                downloads: "680K",
                image: "#ffd700"
            }
        ];

        let currentLang = 'en';
        let currentFilter = 'all';

        // Initialize
        function init() {
            createStarBackground();
            renderGames(games.filter(g => g.category.includes('action') || g.category === 'rpg'), 'gamesGrid');
            renderGames(games.filter(g => g.rating >= 4.8), 'trendingGrid');
            renderGames(games.slice(-6), 'newGrid');
            updateLanguage();
        }

        // Create star background
        function createStarBackground() {
            const container = document.getElementById('starsContainer');
            for (let i = 0; i < 50; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.animationDelay = Math.random() * 3 + 's';
                container.appendChild(star);
            }
        }

        // Render games
        function renderGames(gamesToRender, gridId) {
            const grid = document.getElementById(gridId);
            grid.innerHTML = '';
            
            gamesToRender.forEach((game, index) => {
                const card = document.createElement('div');
                card.className = 'game-card';
                card.innerHTML = `
                    <div class="game-image" style="background: linear-gradient(135deg, ${game.image}, ${game.image}dd);">
                        <button class="play-btn" onclick="openModal(${game.id})">
                            <i class="fas fa-play"></i>
                        </button>
                    </div>
                    <div class="game-info">
                        <h3 class="game-title" data-en="${game.titleEn}" data-ar="${game.titleAr}">${currentLang === 'en' ? game.titleEn : game.titleAr}</h3>
                        <div class="game-category">
                            <span class="category-tag" data-en="${game.category}" data-ar="${game.category}">${game.category.toUpperCase()}</span>
                        </div>
                        <div class="game-rating">
                            <span class="stars">★★★★★</span>
                            <span class="rating-number">${game.rating}</span>
                        </div>
                        <p class="game-description" data-en="${game.descriptionEn}" data-ar="${game.descriptionAr}">${currentLang === 'en' ? game.descriptionEn : game.descriptionAr}</p>
                        <div class="game-stats">
                            <div class="stat-item">
                                <span class="stat-label" data-en="Players" data-ar="لاعب">${currentLang === 'en' ? 'Players' : 'لاعب'}</span>
                                <span>${game.players}</span>
                            </div>
                            <div class="stat-item">
                                <span class="stat-label" data-en="Genre" data-ar="النوع">${currentLang === 'en' ? 'Genre' : 'النوع'}</span>
                                <span>${game.genre}</span>
                            </div>
                            <div class="stat-item">
                                <span class="stat-label" data-en="Reviews" data-ar="تقييمات">${currentLang === 'en' ? 'Reviews' : 'تقييمات'}</span>
                                <span>${(game.reviews / 1000).toFixed(1)}K</span>
                            </div>
                        </div>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        // Filter games
        function filterGames(category) {
            currentFilter = category;
            document.querySelectorAll('.filter-btn').forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');
            
            let filtered = games;
            if (category !== 'all') {
                filtered = games.filter(g => g.category === category);
            }
            renderGames(filtered, 'gamesGrid');
        }

        // Modal functions
        function openModal(gameId) {
            const game = games.find(g => g.id === gameId) || games[0];
            document.getElementById('modalTitle').textContent = currentLang === 'en' ? game.titleEn : game.titleAr;
            document.getElementById('modalDescription').textContent = currentLang === 'en' ? game.descriptionEn : game.descriptionAr;
            document.getElementById('modalGenre').textContent = game.genre;
            document.getElementById('modalRating').textContent = game.rating;
            document.getElementById('modalPlayers').textContent = game.players;
            document.getElementById('modalDownloads').textContent = game.downloads;
            document.getElementById('gameModal').classList.add('show');
        }

        function closeModal() {
            document.getElementById('gameModal').classList.remove('show');
        }

        // Language toggle
        function toggleLanguage() {
            currentLang = currentLang === 'en' ? 'ar' : 'en';
            updateLanguage();
        }

        function updateLanguage() {
            const html = document.documentElement;
            if (currentLang === 'ar') {
                html.setAttribute('lang', 'ar');
                html.setAttribute('dir', 'rtl');
                document.body.classList.add('ar-lang');
            } else {
                html.setAttribute('lang', 'en');
                html.setAttribute('dir', 'ltr');
                document.body.classList.remove('ar-lang');
            }

            // Update all translatable elements
            document.querySelectorAll('[data-en]').forEach(el => {
                el.textContent = currentLang === 'en' ? el.dataset.en : el.dataset.ar;
            });

            // Re-render to update game cards
            renderGames(currentFilter === 'all' ? games : games.filter(g => g.category === currentFilter), 'gamesGrid');
            renderGames(games.filter(g => g.rating >= 4.8), 'trendingGrid');
            renderGames(games.slice(-6), 'newGrid');
        }

        function navigateTo(page) {
            console.log('Navigating to:', page);
            // Add navigation logic here
        }

        // Close modal on background click
        document.getElementById('gameModal').addEventListener('click', function(e) {
            if (e.target === this) closeModal();
        });

        // Initialize
        init();
    </script>
</body>
</html>
