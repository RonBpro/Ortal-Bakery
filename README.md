<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ortal Bakery | עוגות בוטיק בעבודת יד</title>
    
    <!-- Google Fonts: Heebo for Hebrew text, Playfair Display for the English brand -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Heebo:wght@300;400;600;800&family=Playfair+Display:ital,wght@0,600;1,600&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary-cream: #FAF9F6;
            --accent-green: #9CAF88;
            --dark-green: #7A8C66;
            --gold: #D4AF37;
            --text-dark: #333333;
            --text-light: #666666;
            --white: #FFFFFF;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Heebo', sans-serif;
            background-color: var(--primary-cream);
            color: var(--text-dark);
            line-height: 1.6;
        }

        /* Typography */
        .brand-name {
            font-family: 'Playfair Display', serif;
            font-weight: 600;
            color: var(--text-dark);
            direction: ltr; /* Keep English LTR */
            display: inline-block;
        }

        h1, h2, h3 {
            margin-bottom: 15px;
            color: var(--text-dark);
        }

        h2 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 40px;
            position: relative;
        }

        h2::after {
            content: '';
            display: block;
            width: 60px;
            height: 3px;
            background-color: var(--accent-green);
            margin: 15px auto 0;
            border-radius: 2px;
        }

        /* Header & Navigation */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(5px);
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            z-index: 1000;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 5%;
        }

        .logo {
            font-size: 1.8rem;
            text-decoration: none;
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 30px;
        }

        nav a {
            text-decoration: none;
            color: var(--text-dark);
            font-weight: 600;
            transition: color 0.3s;
        }

        nav a:hover {
            color: var(--accent-green);
        }

        .btn-whatsapp {
            background-color: #25D366;
            color: var(--white);
            padding: 10px 24px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            transition: transform 0.3s, box-shadow 0.3s;
            box-shadow: 0 4px 6px rgba(37, 211, 102, 0.3);
        }

        .btn-whatsapp:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(37, 211, 102, 0.4);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(250, 249, 246, 0.3), rgba(250, 249, 246, 0.8)), 
                        url('https://images.unsplash.com/photo-1525151498231-0373dfbb99d6?auto=format&fit=crop&w=1920&q=80') center/cover;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 0 20px;
            margin-top: 70px;
        }

        .hero-content {
            background-color: rgba(255, 255, 255, 0.9);
            padding: 50px;
            border-radius: 15px;
            max-width: 600px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            border: 1px solid rgba(156, 175, 136, 0.2);
        }

        .hero-content h1 {
            font-size: 3rem;
            margin-bottom: 10px;
        }

        .hero-content p {
            font-size: 1.2rem;
            color: var(--text-light);
            margin-bottom: 30px;
        }

        .shavuot-badge {
            display: inline-block;
            background-color: var(--accent-green);
            color: var(--white);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 20px;
            letter-spacing: 0.5px;
        }

        /* Sections */
        section {
            padding: 80px 5%;
            max-width: 1200px;
            margin: 0 auto;
        }

        /* About Section */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .about-text p {
            font-size: 1.1rem;
            margin-bottom: 20px;
            color: var(--text-light);
        }

        .about-image img {
            width: 100%;
            border-radius: 15px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.08);
        }

        /* Menu Section */
        .menu-section {
            background-color: var(--white);
            border-radius: 20px;
            padding: 60px 5%;
            box-shadow: 0 5px 20px rgba(0,0,0,0.03);
            margin: 40px auto;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .menu-item {
            border-bottom: 1px dashed #ddd;
            padding-bottom: 20px;
        }

        .menu-item:last-child {
            border-bottom: none;
        }

        .menu-item h3 {
            display: flex;
            justify-content: space-between;
            color: var(--dark-green);
            font-size: 1.4rem;
        }

        .menu-item .price {
            font-weight: 800;
            color: var(--gold);
        }

        /* Gallery */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
        }

        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 12px;
            aspect-ratio: 4/3;
            box-shadow: 0 4px 10px rgba(0,0,0,0.05);
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .gallery-item:hover img {
            transform: scale(1.08);
        }

        /* Payment & Footer */
        footer {
            background-color: #2A3324;
            color: var(--white);
            padding: 60px 5% 30px;
            text-align: center;
        }

        .payment-info {
            background-color: rgba(255, 255, 255, 0.05);
            padding: 30px;
            border-radius: 15px;
            max-width: 600px;
            margin: 0 auto 40px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .payment-info h3 {
            color: var(--gold);
        }

        .payment-icons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 15px;
        }

        .share-btn {
            background-color: transparent;
            color: var(--white);
            border: 2px solid var(--accent-green);
            padding: 10px 25px;
            border-radius: 30px;
            text-decoration: none;
            display: inline-block;
            transition: all 0.3s;
            margin-bottom: 30px;
        }

        .share-btn:hover {
            background-color: var(--accent-green);
        }

        .copyright {
            color: #888;
            font-size: 0.9rem;
            margin-top: 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
            padding-top: 20px;
        }

        /* Responsive */
        @media (max-width: 768px) {
            header {
                flex-direction: column;
                gap: 15px;
                padding: 15px;
            }
            nav ul {
                gap: 15px;
                flex-wrap: wrap;
                justify-content: center;
            }
            .about-grid {
                grid-template-columns: 1fr;
            }
            .hero-content {
                padding: 30px 20px;
            }
            .hero-content h1 {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header>
        <a href="#" class="logo brand-name">Ortal Bakery</a>
        <nav>
            <ul>
                <li><a href="#about">קצת עליי</a></li>
                <li><a href="#menu">תפריט שבועות</a></li>
                <li><a href="#gallery">גלריה</a></li>
            </ul>
        </nav>
        <!-- Replace YOUR_NUMBER with actual number -->
        <a href="https://wa.me/972500000000?text=היי, אשמח להזמין עוגה לחג..." class="btn-whatsapp" target="_blank">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" viewBox="0 0 16 16">
                <path d="M13.601 2.326A7.854 7.854 0 0 0 7.994 0C3.627 0 .068 3.558.064 7.926c0 1.399.366 2.76 1.057 3.965L0 16l4.204-1.102a7.933 7.933 0 0 0 3.79.965h.004c4.368 0 7.926-3.558 7.93-7.93A7.898 7.898 0 0 0 13.6 2.326zM7.994 14.521a6.573 6.573 0 0 1-3.356-.92l-.24-.144-2.494.654.666-2.433-.156-.251a6.56 6.56 0 0 1-1.007-3.505c0-3.626 2.957-6.584 6.591-6.584a6.56 6.56 0 0 1 4.66 1.931 6.557 6.557 0 0 1 1.928 4.66c-.004 3.639-2.961 6.592-6.592 6.592zm3.615-4.934c-.197-.099-1.17-.578-1.353-.646-.182-.065-.315-.099-.445.099-.133.197-.513.646-.627.775-.114.133-.232.148-.43.05-.197-.1-.836-.308-1.592-.985-.59-.525-.985-1.175-1.103-1.372-.114-.198-.011-.304.088-.403.087-.088.197-.232.296-.346.1-.114.133-.198.198-.33.065-.134.034-.248-.015-.347-.05-.099-.445-1.076-.612-1.47-.16-.389-.323-.335-.445-.34-.114-.007-.247-.007-.38-.007a.729.729 0 0 0-.529.247c-.182.198-.691.677-.691 1.654 0 .977.71 1.916.81 2.049.098.133 1.394 2.132 3.383 2.992.47.205.84.326 1.129.418.475.152.904.129 1.246.08.38-.058 1.171-.48 1.338-.943.164-.464.164-.86.114-.943-.049-.084-.182-.133-.38-.232z"/>
            </svg>
            הזמן עכשיו
        </a>
    </header>

    <!-- Hero -->
    <section class="hero">
        <div class="hero-content">
            <h1 class="brand-name">Ortal Bakery</h1>
            <p>עוגות ומאפי בוטיק בעבודת יד, מחומרי הגלם הטובים ביותר. מביאים את הקסם והטעם היישר לשולחן החג שלכם.</p>
            <a href="#menu" class="btn-whatsapp" style="background-color: var(--dark-green); box-shadow: none;">צפו בתפריט</a>
        </div>
    </section>

    <!-- About -->
    <section id="about">
        <h2>קצת עליי</h2>
        <div class="about-grid">
            <div class="about-text">
                <p>ברוכים הבאים ל-<span class="brand-name">Ortal Bakery</span>!</p>
                <p>אני אורטל, והאהבה הגדולה שלי היא לאפות. כל עוגה שיוצאת מהתנור שלי נאפית בהמון תשומת לב, אהבה והקפדה על הפרטים הקטנים ביותר.</p>
                <p>לקראת חג השבועות, רקחתי עבורכם קולקציה חגיגית, עשירה ומפנקת במיוחד, המשלבת טעמים קלאסיים עם טוויסט מודרני. אני משתמשת בגבינות איכותיות, פירות טריים ווניל אמיתי כדי להבטיח ביס מושלם.</p>
            </div>
            <div class="about-image">
                <img src="https://images.unsplash.com/photo-1556910103-1c02745a872f?auto=format&fit=crop&w=800&q=80" alt="אופה במטבח">
            </div>
        </div>
    </section>

    <!-- Menu / Shavuot Specials -->
    <section id="menu" class="menu-section">
        <h2>תפריט שבועות</h2>
        <div class="menu-grid">
            <div class="menu-item">
                <h3>עוגת גבינה אפויה קלאסית <span class="price">₪180</span></h3>
                <p>עוגת גבינה נימוחה וגבוהה, עם תחתית פריכה וציפוי שמנת חמוצה ווניל. (קוטר 24)</p>
            </div>
            <div class="menu-item">
                <h3>טארט פירות יער ומסקרפונה <span class="price">₪160</span></h3>
                <p>קלתית שקדים פריכה, קרם מסקרפונה עשיר ושפע פירות יער טריים. מראה חגיגי וטעם מרענן.</p>
            </div>
            <div class="menu-item">
                <h3>קיש פטריות וכמהין <span class="price">₪140</span></h3>
                <p>קיש מלוח מושלם לשולחן החג. שילוב של פטריות יער, מחית כמהין, גבינת גרוייר ופרמז'ן.</p>
            </div>
            <div class="menu-item">
                <h3>פס פחזניות וקרם פטיסייר <span class="price">₪120</span></h3>
                <p>פחזניות עננים ממולאות בקרם פטיסייר וניל איכותי, בציפוי קרמל עדין.</p>
            </div>
        </div>
    </section>

    <!-- Gallery -->
    <section id="gallery">
        <h2>גלריית העוגות</h2>
        <div class="gallery-grid">
            <!-- Image 1 -->
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1525151498231-0373dfbb99d6?auto=format&fit=crop&w=600&q=80" alt="עוגת גבינה חגיגית">
            </div>
            <!-- Image 2 -->
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1533134242443-d4fd0153c87f?auto=format&fit=crop&w=600&q=80" alt="טארט פירות">
            </div>
            <!-- Image 3 -->
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1464349095431-e9a21285b5f3?auto=format&fit=crop&w=600&q=80" alt="קיש מלוח">
            </div>
            <!-- Image 4 -->
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1621303837174-89787a7d4729?auto=format&fit=crop&w=600&q=80" alt="מאפים מתוקים">
            </div>
            <!-- Image 5 -->
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1602351447937-745cb720612f?auto=format&fit=crop&w=600&q=80" alt="עוגת שכבות">
            </div>
            <!-- Image 6 -->
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1571115177098-24c42d640a92?auto=format&fit=crop&w=600&q=80" alt="פחזניות">
            </div>
        </div>
    </section>

    <!-- Footer & Payments -->
    <footer>
        <div class="payment-info">
            <h3>אמצעי תשלום</h3>
            <p>ההזמנה מתבצעת בנוחות דרך הוואטסאפ.</p>
            <p>ניתן לשלם בקלות באמצעות <strong>Bit</strong> או <strong>Paybox</strong> למספר הטלפון של אורטל, או במזומן בעת איסוף ההזמנה.</p>
        </div>

        <!-- Replace YOUR_URL with the actual published website URL -->
        <a href="whatsapp://send?text=תראו את העוגות המדהימות של Ortal Bakery לקראת שבועות! [הכנס_קישור_לאתר]" class="share-btn">
            שתפו את האתר בוואטסאפ
        </a>

        <div class="copyright">
            &copy; 2024 <span class="brand-name" style="color:#888;">Ortal Bakery</span>. כל הזכויות שמורות.
        </div>
    </footer>

</body>
</html>
