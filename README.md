<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ortal Bakery | עוגות בוטיק בעבודת יד</title>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400;1,600&family=Heebo:wght@300;400;500;700&display=swap" rel="stylesheet">

    <style>
        :root {
            --cream:      #FAF7F2;
            --parchment:  #F2EDE4;
            --green:      #6B8C5E;
            --dark-green: #3E5432;
            --gold:       #C9A84C;
            --gold-light: #E8C97A;
            --text:       #2A2218;
            --muted:      #7A6E60;
            --white:      #FFFFFF;
            --border:     rgba(107, 140, 94, 0.18);
        }

        *, *::before, *::after {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html { scroll-behavior: smooth; }

        body {
            font-family: 'Heebo', sans-serif;
            background-color: var(--cream);
            color: var(--text);
            line-height: 1.7;
            overflow-x: hidden;
        }

        /* ───── TYPOGRAPHY ───── */
        .serif {
            font-family: 'Cormorant Garamond', serif;
            font-style: italic;
        }

        h2 {
            font-family: 'Cormorant Garamond', serif;
            font-size: clamp(2rem, 5vw, 3rem);
            font-weight: 600;
            text-align: center;
            margin-bottom: 0.4em;
            color: var(--dark-green);
            line-height: 1.2;
        }

        .section-rule {
            display: block;
            width: 48px;
            height: 2px;
            background: var(--gold);
            margin: 0 auto 50px;
        }

        /* ───── NOISE TEXTURE OVERLAY ───── */
        body::before {
            content: '';
            position: fixed;
            inset: 0;
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
            pointer-events: none;
            z-index: 9999;
            opacity: 0.4;
        }

        /* ───── HEADER ───── */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            background: rgba(250, 247, 242, 0.94);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-bottom: 1px solid var(--border);
            padding: 0 5%;
            height: 72px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 16px;
        }

        .logo {
            font-family: 'Cormorant Garamond', serif;
            font-size: 1.75rem;
            font-style: italic;
            font-weight: 600;
            color: var(--dark-green);
            text-decoration: none;
            letter-spacing: 0.5px;
            white-space: nowrap;
            direction: ltr;
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 28px;
            align-items: center;
        }

        nav a {
            text-decoration: none;
            color: var(--muted);
            font-size: 0.9rem;
            font-weight: 500;
            letter-spacing: 0.3px;
            transition: color 0.25s;
            position: relative;
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -3px;
            right: 0;
            width: 0;
            height: 1.5px;
            background: var(--gold);
            transition: width 0.3s;
        }

        nav a:hover { color: var(--dark-green); }
        nav a:hover::after { width: 100%; }

        .btn-whatsapp {
            background: var(--dark-green);
            color: var(--white);
            padding: 10px 22px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 0.88rem;
            display: inline-flex;
            align-items: center;
            gap: 7px;
            transition: background 0.3s, transform 0.2s, box-shadow 0.3s;
            box-shadow: 0 4px 14px rgba(62, 84, 50, 0.25);
            white-space: nowrap;
        }

        .btn-whatsapp:hover {
            background: var(--green);
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(62, 84, 50, 0.35);
        }

        /* ───── HERO ───── */
        .hero {
            min-height: 100vh;
            display: grid;
            place-items: center;
            padding: 100px 5% 60px;
            position: relative;
            overflow: hidden;
        }

        .hero-bg {
            position: absolute;
            inset: 0;
            background:
                linear-gradient(160deg, rgba(250,247,242,0.97) 45%, rgba(107,140,94,0.12) 100%),
                url('https://images.unsplash.com/photo-1578985545062-69928b1d9587?w=1920&q=85&auto=format&fit=crop') center/cover no-repeat;
        }

        .hero-content {
            position: relative;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            max-width: 680px;
        }

        .hero-eyebrow {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            color: var(--green);
            font-size: 0.82rem;
            font-weight: 700;
            letter-spacing: 2.5px;
            text-transform: uppercase;
            margin-bottom: 24px;
        }

        .hero-eyebrow::before,
        .hero-eyebrow::after {
            content: '';
            display: block;
            width: 32px;
            height: 1px;
            background: var(--green);
        }

        .hero h1 {
            font-family: 'Cormorant Garamond', serif;
            font-size: clamp(3rem, 9vw, 6rem);
            font-style: italic;
            font-weight: 600;
            color: var(--dark-green);
            line-height: 1.05;
            margin-bottom: 24px;
            direction: ltr;
        }

        .hero-tagline {
            font-size: clamp(1rem, 2.5vw, 1.15rem);
            color: var(--muted);
            max-width: 480px;
            margin-bottom: 40px;
            font-weight: 300;
        }

        .hero-cta {
            display: flex;
            gap: 14px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .btn-outline {
            padding: 10px 26px;
            border-radius: 50px;
            border: 1.5px solid var(--dark-green);
            color: var(--dark-green);
            font-weight: 600;
            font-size: 0.88rem;
            text-decoration: none;
            transition: all 0.3s;
        }

        .btn-outline:hover {
            background: var(--dark-green);
            color: var(--white);
        }

        /* decorative leaf */
        .hero-decor {
            position: absolute;
            right: -40px;
            top: 10%;
            opacity: 0.07;
            font-size: 18rem;
            line-height: 1;
            color: var(--dark-green);
            pointer-events: none;
            user-select: none;
        }

        /* ───── SECTIONS ───── */
        section {
            padding: clamp(60px, 10vw, 100px) 5%;
            max-width: 1200px;
            margin: 0 auto;
        }

        /* ───── ABOUT ───── */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .about-text p {
            font-size: 1.05rem;
            color: var(--muted);
            margin-bottom: 18px;
            font-weight: 300;
        }

        .about-text p strong {
            color: var(--dark-green);
            font-weight: 600;
        }

        .about-image {
            position: relative;
        }

        .about-image::before {
            content: '';
            position: absolute;
            top: -16px;
            right: -16px;
            width: 100%;
            height: 100%;
            border: 2px solid var(--gold);
            border-radius: 16px;
            z-index: 0;
            opacity: 0.5;
        }

        .about-image img {
            width: 100%;
            border-radius: 14px;
            display: block;
            position: relative;
            z-index: 1;
            box-shadow: 0 20px 50px rgba(0,0,0,0.1);
            object-fit: cover;
            aspect-ratio: 4/3;
        }

        /* ───── MENU ───── */
        .menu-wrapper {
            background: var(--white);
            border-radius: 24px;
            padding: clamp(40px, 6vw, 70px) clamp(24px, 5vw, 60px);
            box-shadow: 0 4px 40px rgba(0,0,0,0.05);
            border: 1px solid var(--border);
            margin: 0 auto;
            max-width: 1100px;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 0;
        }

        .menu-item {
            padding: 28px;
            border-bottom: 1px solid var(--border);
            position: relative;
            transition: background 0.2s;
        }

        .menu-item:hover {
            background: var(--cream);
            border-radius: 12px;
        }

        .menu-item:nth-last-child(-n+2) {
            border-bottom: none;
        }

        .menu-item-header {
            display: flex;
            justify-content: space-between;
            align-items: baseline;
            gap: 12px;
            margin-bottom: 8px;
            flex-wrap: wrap;
        }

        .menu-item h3 {
            font-family: 'Cormorant Garamond', serif;
            font-size: 1.35rem;
            font-weight: 600;
            color: var(--dark-green);
            line-height: 1.3;
        }

        .price {
            font-weight: 700;
            color: var(--gold);
            font-size: 1.15rem;
            white-space: nowrap;
        }

        .menu-item p {
            font-size: 0.9rem;
            color: var(--muted);
            line-height: 1.6;
        }

        .menu-divider {
            width: 1px;
            background: var(--border);
        }

        /* ───── GALLERY ───── */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            grid-template-rows: auto auto;
            gap: 14px;
        }

        .gallery-item {
            overflow: hidden;
            border-radius: 14px;
            position: relative;
            box-shadow: 0 4px 16px rgba(0,0,0,0.07);
        }

        .gallery-item:first-child {
            grid-column: span 2;
            aspect-ratio: 16/9;
        }

        .gallery-item:nth-child(n+2) {
            aspect-ratio: 1;
        }

        .gallery-item:last-child {
            grid-column: span 2;
            aspect-ratio: 16/9;
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s ease;
            display: block;
        }

        .gallery-item:hover img {
            transform: scale(1.07);
        }

        .gallery-item::after {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(to top, rgba(42,34,24,0.3) 0%, transparent 60%);
            opacity: 0;
            transition: opacity 0.3s;
        }

        .gallery-item:hover::after {
            opacity: 1;
        }

        /* ───── FOOTER ───── */
        footer {
            background: var(--dark-green);
            color: rgba(255,255,255,0.85);
            padding: clamp(50px, 8vw, 80px) 5% 36px;
        }

        .footer-inner {
            max-width: 1100px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr auto 1fr;
            gap: 40px;
            align-items: start;
            margin-bottom: 50px;
        }

        .footer-brand .logo {
            color: var(--gold-light);
            font-size: 2.2rem;
            display: block;
            margin-bottom: 12px;
        }

        .footer-brand p {
            font-size: 0.88rem;
            color: rgba(255,255,255,0.5);
            max-width: 220px;
            line-height: 1.6;
        }

        .footer-center {
            text-align: center;
        }

        .footer-center h3 {
            font-family: 'Cormorant Garamond', serif;
            font-size: 1.4rem;
            color: var(--gold-light);
            margin-bottom: 14px;
            font-style: italic;
        }

        .footer-center p {
            font-size: 0.88rem;
            color: rgba(255,255,255,0.6);
            margin-bottom: 8px;
        }

        .payment-badges {
            display: flex;
            gap: 10px;
            justify-content: center;
            margin-top: 16px;
        }

        .badge {
            background: rgba(255,255,255,0.1);
            border: 1px solid rgba(255,255,255,0.15);
            color: var(--white);
            padding: 6px 16px;
            border-radius: 30px;
            font-size: 0.82rem;
            font-weight: 600;
            letter-spacing: 0.5px;
        }

        .footer-social {
            text-align: left;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            gap: 12px;
        }

        .footer-social h4 {
            font-size: 0.8rem;
            font-weight: 700;
            letter-spacing: 2px;
            text-transform: uppercase;
            color: rgba(255,255,255,0.4);
        }

        .share-btn {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: rgba(255,255,255,0.07);
            border: 1.5px solid rgba(255,255,255,0.2);
            color: var(--white);
            padding: 10px 22px;
            border-radius: 50px;
            font-size: 0.88rem;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s;
        }

        .share-btn:hover {
            background: var(--green);
            border-color: var(--green);
        }

        .footer-divider {
            max-width: 1100px;
            margin: 0 auto;
            border: none;
            border-top: 1px solid rgba(255,255,255,0.08);
            margin-bottom: 24px;
        }

        .copyright {
            max-width: 1100px;
            margin: 0 auto;
            text-align: center;
            font-size: 0.82rem;
            color: rgba(255,255,255,0.3);
        }

        .copyright span {
            color: var(--gold-light);
            font-family: 'Cormorant Garamond', serif;
            font-style: italic;
        }

        /* ───── SCROLL ANIMATION ───── */
        .reveal {
            opacity: 0;
            transform: translateY(24px);
            transition: opacity 0.7s ease, transform 0.7s ease;
        }

        .reveal.visible {
            opacity: 1;
            transform: none;
        }

        /* ───── MOBILE ───── */
        @media (max-width: 900px) {
            .footer-inner {
                grid-template-columns: 1fr;
                text-align: center;
            }
            .footer-brand p { max-width: 100%; }
            .footer-social {
                align-items: center;
            }
        }

        @media (max-width: 768px) {
            header {
                height: auto;
                padding: 14px 5%;
                flex-wrap: wrap;
                gap: 10px;
            }

            nav ul {
                gap: 16px;
                flex-wrap: wrap;
                justify-content: center;
                order: 3;
                width: 100%;
                padding: 0 0 4px;
            }

            .btn-whatsapp { order: 2; }

            .about-grid {
                grid-template-columns: 1fr;
                gap: 36px;
            }

            .about-image::before { display: none; }

            .gallery-grid {
                grid-template-columns: 1fr 1fr;
            }

            .gallery-item:first-child,
            .gallery-item:last-child {
                grid-column: span 2;
                aspect-ratio: 16/9;
            }

            .gallery-item:nth-child(n+2):not(:last-child) {
                aspect-ratio: 1;
            }

            .menu-item:nth-last-child(-n+2) {
                border-bottom: 1px solid var(--border);
            }

            .menu-item:last-child {
                border-bottom: none;
            }

            .hero-decor { display: none; }
        }

        @media (max-width: 480px) {
            .gallery-grid {
                grid-template-columns: 1fr;
            }

            .gallery-item,
            .gallery-item:first-child,
            .gallery-item:last-child {
                grid-column: span 1;
                aspect-ratio: 4/3;
            }

            .menu-item-header {
                flex-direction: column;
                gap: 4px;
            }

            .hero-cta { flex-direction: column; align-items: center; }
        }
    </style>
</head>
<body>

    <!-- ═══ HEADER ═══ -->
    <header>
        <a href="#" class="logo">Ortal Bakery</a>
        <nav>
            <ul>
                <li><a href="#about">קצת עליי</a></li>
                <li><a href="#menu">תפריט</a></li>
                <li><a href="#gallery">גלריה</a></li>
            </ul>
        </nav>
        <a href="https://wa.me/972500000000?text=היי, אשמח להזמין עוגה..." class="btn-whatsapp" target="_blank">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
                <path d="M13.601 2.326A7.854 7.854 0 0 0 7.994 0C3.627 0 .068 3.558.064 7.926c0 1.399.366 2.76 1.057 3.965L0 16l4.204-1.102a7.933 7.933 0 0 0 3.79.965h.004c4.368 0 7.926-3.558 7.93-7.93A7.898 7.898 0 0 0 13.6 2.326zM7.994 14.521a6.573 6.573 0 0 1-3.356-.92l-.24-.144-2.494.654.666-2.433-.156-.251a6.56 6.56 0 0 1-1.007-3.505c0-3.626 2.957-6.584 6.591-6.584a6.56 6.56 0 0 1 4.66 1.931 6.557 6.557 0 0 1 1.928 4.66c-.004 3.639-2.961 6.592-6.592 6.592zm3.615-4.934c-.197-.099-1.17-.578-1.353-.646-.182-.065-.315-.099-.445.099-.133.197-.513.646-.627.775-.114.133-.232.148-.43.05-.197-.1-.836-.308-1.592-.985-.59-.525-.985-1.175-1.103-1.372-.114-.198-.011-.304.088-.403.087-.088.197-.232.296-.346.1-.114.133-.198.198-.33.065-.134.034-.248-.015-.347-.05-.099-.445-1.076-.612-1.47-.16-.389-.323-.335-.445-.34-.114-.007-.247-.007-.38-.007a.729.729 0 0 0-.529.247c-.182.198-.691.677-.691 1.654 0 .977.71 1.916.81 2.049.098.133 1.394 2.132 3.383 2.992.47.205.84.326 1.129.418.475.152.904.129 1.246.08.38-.058 1.171-.48 1.338-.943.164-.464.164-.86.114-.943-.049-.084-.182-.133-.38-.232z"/>
            </svg>
            הזמינו עכשיו
        </a>
    </header>

    <!-- ═══ HERO ═══ -->
    <div class="hero">
        <div class="hero-bg"></div>
        <div class="hero-decor">✿</div>
        <div class="hero-content">
            <div class="hero-eyebrow">עוגות בוטיק בעבודת יד</div>
            <h1>Ortal<br>Bakery</h1>
            <p class="hero-tagline">מחומרי הגלם הטובים ביותר, אפויות באהבה, ומוגשות עם תשומת לב לכל פרט.</p>
            <div class="hero-cta">
                <a href="#menu" class="btn-whatsapp">צפו בתפריט</a>
                <a href="#about" class="btn-outline">קצת עליי</a>
            </div>
        </div>
    </div>

    <!-- ═══ ABOUT ═══ -->
    <section id="about">
        <h2>קצת עליי</h2>
        <span class="section-rule"></span>
        <div class="about-grid reveal">
            <div class="about-image">
                <img
                    src="https://images.unsplash.com/photo-1607478900766-efe13248b125?w=800&q=85&auto=format&fit=crop"
                    alt="אופה במטבח"
                    loading="lazy"
                >
            </div>
            <div class="about-text">
                <p>ברוכים הבאים ל-<strong>Ortal Bakery</strong>!</p>
                <p>אני אורטל, ואהבתי הגדולה היא לאפות. כל עוגה שיוצאת מהתנור שלי נאפית עם המון תשומת לב, אהבה והקפדה על הפרטים הקטנים ביותר.</p>
                <p>אני משתמשת בגבינות איכותיות, פירות טריים ווניל אמיתי כדי להבטיח ביס מושלם — כזה שתזכרו עוד הרבה אחרי.</p>
                <p>כל הזמנה היא אירוע מיוחד עבורי, ואני מכינה כל עוגה כאילו היא עבור המשפחה שלי.</p>
            </div>
        </div>
    </section>

    <!-- ═══ MENU ═══ -->
    <section id="menu" style="padding-bottom: 0;">
        <h2>התפריט שלנו</h2>
        <span class="section-rule"></span>
    </section>
    <section style="padding-top: 0; max-width: 1200px; margin: 0 auto; padding-right: 5%; padding-left: 5%; padding-bottom: 80px;">
        <div class="menu-wrapper reveal">
            <div class="menu-grid">
                <div class="menu-item">
                    <div class="menu-item-header">
                        <h3>עוגת גבינה אפויה קלאסית</h3>
                        <span class="price">₪180</span>
                    </div>
                    <p>עוגת גבינה נימוחה וגבוהה, עם תחתית פריכה וציפוי שמנת חמוצה ווניל. (קוטר 24)</p>
                </div>
                <div class="menu-item">
                    <div class="menu-item-header">
                        <h3>טארט פירות יער ומסקרפונה</h3>
                        <span class="price">₪160</span>
                    </div>
                    <p>קלתית שקדים פריכה, קרם מסקרפונה עשיר ושפע פירות יער טריים. מראה חגיגי וטעם מרענן.</p>
                </div>
                <div class="menu-item">
                    <div class="menu-item-header">
                        <h3>קיש פטריות וכמהין</h3>
                        <span class="price">₪140</span>
                    </div>
                    <p>קיש מלוח מושלם לשולחן. שילוב של פטריות יער, מחית כמהין, גבינת גרוייר ופרמז'ן.</p>
                </div>
                <div class="menu-item">
                    <div class="menu-item-header">
                        <h3>פס פחזניות וקרם פטיסייר</h3>
                        <span class="price">₪120</span>
                    </div>
                    <p>פחזניות עננים ממולאות בקרם פטיסייר וניל איכותי, בציפוי קרמל עדין.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- ═══ GALLERY ═══ -->
    <section id="gallery">
        <h2>גלריית העוגות</h2>
        <span class="section-rule"></span>
        <div class="gallery-grid reveal">
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1578985545062-69928b1d9587?w=900&q=85&auto=format&fit=crop" alt="עוגת גבינה" loading="lazy">
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1464349095431-e9a21285b5f3?w=600&q=85&auto=format&fit=crop" alt="טארט פירות" loading="lazy">
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1607478900766-efe13248b125?w=600&q=85&auto=format&fit=crop" alt="אפייה" loading="lazy">
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1519869325930-281384150729?w=600&q=85&auto=format&fit=crop" alt="מאפים" loading="lazy">
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1486427944299-d1955d23e34d?w=900&q=85&auto=format&fit=crop" alt="עוגת שכבות" loading="lazy">
            </div>
        </div>
    </section>

    <!-- ═══ FOOTER ═══ -->
    <footer>
        <div class="footer-inner">
            <div class="footer-brand">
                <a href="#" class="logo">Ortal Bakery</a>
                <p>עוגות ומאפי בוטיק בעבודת יד, מביאים את הקסם והטעם היישר לשולחן שלכם.</p>
            </div>

            <div class="footer-center">
                <h3>אמצעי תשלום</h3>
                <p>ניתן לשלם בנוחות דרך:</p>
                <div class="payment-badges">
                    <span class="badge">Bit</span>
                    <span class="badge">Paybox</span>
                    <span class="badge">מזומן</span>
                </div>
                <p style="margin-top: 14px; font-size: 0.82rem;">ניתן לאסוף את ההזמנה בתיאום מראש</p>
            </div>

            <div class="footer-social">
                <h4>שתפו</h4>
                <a href="whatsapp://send?text=תראו את העוגות המדהימות של Ortal Bakery!" class="share-btn">
                    <svg xmlns="http://www.w3.org/2000/svg" width="15" height="15" fill="currentColor" viewBox="0 0 16 16">
                        <path d="M13.601 2.326A7.854 7.854 0 0 0 7.994 0C3.627 0 .068 3.558.064 7.926c0 1.399.366 2.76 1.057 3.965L0 16l4.204-1.102a7.933 7.933 0 0 0 3.79.965h.004c4.368 0 7.926-3.558 7.93-7.93A7.898 7.898 0 0 0 13.6 2.326z"/>
                    </svg>
                    שתפו בוואטסאפ
                </a>
                <a href="https://wa.me/972500000000" class="btn-whatsapp" target="_blank" style="font-size: 0.85rem;">
                    הזמינו עכשיו
                </a>
            </div>
        </div>

        <hr class="footer-divider">
        <p class="copyright">&copy; 2025 <span>Ortal Bakery</span> — כל הזכויות שמורות</p>
    </footer>

    <script>
        // Reveal on scroll
        const reveals = document.querySelectorAll('.reveal');
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(e => {
                if (e.isIntersecting) {
                    e.target.classList.add('visible');
                    observer.unobserve(e.target);
                }
            });
        }, { threshold: 0.12 });
        reveals.forEach(el => observer.observe(el));
    </script>
</body>
</html>
