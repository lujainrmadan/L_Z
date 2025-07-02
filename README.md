# L_Z
موقع يضمن علامة تجارية محدد تتبع لادوات التجميل

<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lujain and Zeina</title>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700&family=Playfair+Display:wght@400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">

    <style>
        /* المتغيرات (Variables) لسهولة تخصيص الألوان والظلال */
        :root {
            --primary-color: #8A3D73; /* بنفسجي داكن أساسي (مثل أعلى لون في الصورة) */
            --secondary-color: #C36A9C; /* زهري متوسط للتمييز */
            --accent-color: #E28FB2; /* زهري فاتح للتركيز */
            --text-dark: #333333; /* لون نص داكن */
            --text-light: #555555; /* لون نص فاتح قليلاً */
            --background-light: #FCEFF7; /* خلفية فاتحة جداً (زهري فاتح جداً) */
            --background-dark: #FEC5F6; /* بنفسجي غامق جداً (للتذييل) */
            --white: #ffffff;
            --box-shadow-light: 0 5px 15px rgba(0, 0, 0, 0.08); /* ظل خفيف للعناصر */
            --box-shadow-dark: 0 5px 20px rgba(0, 0, 0, 0.2); /* ظل أغمق للتركيز */
        }

        /* إعادة ضبط المتصفح والخطوط الأساسية */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Cairo', sans-serif;
            line-height: 1.7; /* تباعد أسطر مريح للقراءة */
            color: var(--text-dark);
            background-color: var(--background-light);
            direction: rtl; /* لغة عربية من اليمين لليسار */
            text-align: right;
            overflow-x: hidden; /* منع التمرير الأفقي */
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        a {
            text-decoration: none;
            color: var(--primary-color);
        }

        ul {
            list-style: none;
        }

        h1, h2, h3, h4 {
            font-family: 'Playfair Display', serif; /* خط أنيق للعناوين */
            color: var(--primary-color);
            margin-bottom: 25px;
            text-align: center;
        }

        p {
            margin-bottom: 15px;
            color: var(--text-light);
        }

        /* الأزرار العامة */
        .btn {
            display: inline-block;
            padding: 12px 28px;
            border-radius: 50px; /* حواف مستديرة جداً لزر أنيق */
            font-weight: bold;
            font-size: 1.05em;
            transition: all 0.3s ease;
            margin: 0 10px;
            cursor: pointer;
            text-align: center;
            box-shadow: var(--box-shadow-light);
        }

        .btn-primary {
            background-color: var(--primary-color);
            color: var(--white);
            border: 2px solid var(--primary-color);
        }

        .btn-primary:hover {
            background-color: var(--secondary-color);
            border-color: var(--secondary-color);
            transform: translateY(-3px) scale(1.02);
            box-shadow: var(--box-shadow-dark);
        }

        .btn-secondary {
            background-color: var(--white);
            color: var(--primary-color);
            border: 2px solid var(--primary-color);
        }

        .btn-secondary:hover {
            background-color: var(--primary-color);
            color: var(--white);
            transform: translateY(-3px) scale(1.02);
            box-shadow: var(--box-shadow-dark);
        }

        /* رأس الموقع (Header) */
        .main-header {
            background-color: var(--white);
            padding: 15px 0;
            box-shadow: var(--box-shadow-light);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .main-header .container {
            display: flex;
            justify-content: space-between; /* للحفاظ على المسافة بين اللوجو وزر القائمة */
            align-items: center;
        }

        /* تنسيق اللوجو كصورة */
        .logo-img-link {
            display: flex; /* لجعل الصورة تتصرف كعنصر فليكس */
            align-items: center; /* لمحاذاة الصورة عموديًا إذا كان هناك نص بجانبها */
            margin-bottom: 0; /* تأكدي أن لا يوجد margin إضافي من H1 القديم */
            /* إلغاء margin-bottom للوجو من h1 */
        }

        .logo-img-link img {
            height: 50px; /* اضبطي الارتفاع حسب حجم اللوجو المناسب لشريط التنقل */
            width: auto; /* للحفاظ على نسبة العرض إلى الارتفاع الأصلية للصورة */
            max-width: 100%; /* لضمان أن الصورة لا تتجاوز عرض الحاوية */
            transition: transform 0.3s ease; /* إضافة تأثير عند التحويم */
        }

        .logo-img-link img:hover {
            transform: scale(1.05); /* تكبير بسيط عند التحويم */
        }

        /* تنسيق قائمة التنقل */
        .main-nav {
            display: flex; /* اجعلي الناف نفسها تستخدم فليكس بوكس */
            align-items: center; /* لمحاذاة اللوجو والروابط في المنتصف عموديا */
            gap: 35px; /* مسافة بين اللوجو والروابط */
        }

        .main-nav ul {
            display: flex;
            gap: 35px;
        }

        .main-nav a {
            color: var(--text-dark);
            font-weight: 500;
            font-size: 1.1em;
            transition: color 0.3s ease, transform 0.2s ease;
            position: relative;
            padding-bottom: 5px;
        }

        .main-nav a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background: var(--primary-color);
            bottom: 0;
            right: 0; /* For RTL */
            transition: width 0.3s ease;
        }

        .main-nav a:hover::after {
            width: 100%;
            left: 0; /* Ensure it expands correctly in RTL */
        }

        .main-nav a:hover {
            color: var(--primary-color);
            transform: translateY(-2px);
        }

        .menu-toggle {
            display: none;
            font-size: 2em;
            cursor: pointer;
            color: var(--primary-color);
        }

        /* قسم الأبطال (Hero Section) */
        .hero-section {
            /* استخدم درجات النهدي والزهري من الصورة */
            background: linear-gradient(to top, rgba(252, 239, 247, 0.7), rgba(138, 61, 115, 0.4)),
                        url('https://placehold.co/1500x800/8A3D73/FCEFF7?text=Welcome+ to+ our +small+ store+, +Zeina+ and+ Lujain+.') no-repeat center center/cover;
            color: var(--text-dark);
            text-align: center;
            padding: 120px 0;
            min-height: 600px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            z-index: 1;
            max-width: 900px;
            margin: 0 auto;
        }

        .hero-content h2 {
            font-size: 3.5em;
            color: var(--primary-color);
            margin-bottom: 30px;
            animation: fadeInDown 1s ease-out;
        }

        .hero-content p {
            font-size: 1.3em;
            margin-bottom: 50px;
            color: var(--text-light);
            animation: fadeInUp 1s ease-out 0.3s forwards;
            opacity: 0;
        }

        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* الأقسام العامة */
        section {
            padding: 90px 0;
            text-align: center;
        }

        section:nth-of-type(odd) { /* الأقسام الفردية */
            background-color: var(--white);
        }

        section h3 {
            font-size: 3em;
            margin-bottom: 60px;
            position: relative;
            color: var(--primary-color);
        }

        section h3::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background-color: var(--accent-color);
            border-radius: 2px;
        }

        /* قسم المنتجات المميزة */
        .featured-products .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 40px;
            margin-top: 50px;
        }

        .product-card {
            background-color: var(--white);
            border-radius: 12px;
            box-shadow: var(--box-shadow-light);
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            padding-bottom: 20px;
            text-align: center;
        }

        .product-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: var(--box-shadow-dark);
        }

        .product-card img {
            width: 100%;
            height: 250px;
            object-fit: cover;
            display: block;
            margin-bottom: 15px;
            transition: transform 0.3s ease;
        }

        .product-card:hover img {
            transform: scale(1.05);
        }

        .product-card h4 {
            font-size: 1.6em;
            color: var(--text-dark);
            margin-bottom: 10px;
            padding: 0 15px;
            text-align: center;
        }

        .product-card p {
            font-size: 0.95em;
            color: var(--text-light);
            margin-bottom: 15px;
            padding: 0 15px;
            text-align: center;
        }

        .product-card .price {
            font-size: 1.8em;
            font-weight: 700;
            color: var(--accent-color);
            margin-bottom: 20px;
            display: block; /* لجعل السعر على سطر منفصل */
        }

        .product-card .btn {
            padding: 10px 25px;
            font-size: 0.95em;
        }

        /* قسم الفيديو */
        .video-showcase {
            background-color: var(--background-light);
        }

        .video-wrapper {
            position: relative;
            padding-bottom: 56.25%; /* نسبة عرض إلى ارتفاع 16:9 */
            height: 0;
            overflow: hidden;
            max-width: 900px;
            margin: 50px auto 0 auto;
            border-radius: 12px;
            box-shadow: var(--box-shadow-dark);
        }

        .video-wrapper iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: 0;
        }

        /* قسم قصة العلامة التجارية */
        .brand-story {
            background-color: var(--white);
        }

        .story-content {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 50px;
            text-align: right;
            margin-top: 50px;
        }

        .story-image {
            flex: 1;
            min-width: 300px;
        }

        .story-image img {
            max-width: 100%;
            height: auto;
            border-radius: 12px;
            box-shadow: var(--box-shadow-light);
        }

        .story-text {
            flex: 2;
            min-width: 300px;
        }

        .story-text h4 {
            font-size: 2.2em;
            text-align: right;
            color: var(--text-dark);
        }

        .story-text p {
            margin-bottom: 20px;
            color: var(--text-light);
            font-size: 1.1em;
        }

        /* قسم آراء العملاء */
        .testimonials-section {
            background-color: var(--background-light);
        }

        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .testimonial-card {
            background-color: var(--white);
            padding: 30px;
            border-radius: 12px;
            box-shadow: var(--box-shadow-light);
            text-align: center;
            font-style: italic;
            position: relative;
        }

        .testimonial-card p {
            font-size: 1.05em;
            color: var(--text-dark);
            margin-bottom: 20px;
        }

        .testimonial-card .author {
            font-weight: bold;
            color: var(--primary-color);
            font-style: normal;
            display: block;
            margin-top: 10px;
        }

        .testimonial-card i.fas.fa-quote-right {
            position: absolute;
            bottom: 15px;
            right: 15px;
            font-size: 2.5em;
            color: rgba(138, 61, 115, 0.1); /* لون الأيقونات الخلفية */
            z-index: 0;
        }
        .testimonial-card i.fas.fa-quote-left {
            position: absolute;
            top: 15px;
            left: 15px;
            font-size: 2.5em;
            color: rgba(138, 61, 115, 0.1); /* لون الأيقونات الخلفية */
            z-index: 0;
        }

        /* قسم التواصل (Call to Action / Contact) */
        .contact-section {
            background-color: var(--primary-color);
            color: var(--white);
            padding: 80px 0;
        }

        .contact-section h3 {
            color: var(--white);
            margin-bottom: 30px;
        }

        .contact-section h3::after {
            background-color: var(--accent-color); /* خط تحت العنوان بلون زهري فاتح */
        }

        .contact-section p {
            font-size: 1.2em;
            margin-bottom: 40px;
            color: rgba(255, 255, 255, 0.9);
        }

        .contact-form {
            max-width: 700px;
            margin: 0 auto 50px auto;
            text-align: right;
            background-color: rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 12px;
        }

        .form-group {
            margin-bottom: 25px;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 15px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 8px;
            background-color: rgba(255, 255, 255, 0.1);
            color: var(--white);
            font-family: 'Cairo', sans-serif;
            font-size: 1.1em;
            transition: border-color 0.3s ease;
        }

        .form-group input::placeholder,
        .form-group textarea::placeholder {
            color: rgba(255, 255, 255, 0.7);
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--secondary-color);
            box-shadow: 0 0 8px rgba(255, 255, 255, 0.4);
        }

        .contact-form .btn {
            background-color: var(--secondary-color);
            border-color: var(--secondary-color);
            color: var(--primary-color);
            font-weight: 700;
            padding: 15px 40px;
            border-radius: 8px;
            box-shadow: none; /* إزالة الظل الإضافي للزر */
        }

        .contact-form .btn:hover {
            background-color: var(--white);
            color: var(--primary-color);
            transform: translateY(-2px);
            box-shadow: none;
        }

        .contact-info {
            margin-top: 40px;
            text-align: center;
            color: var(--white);
        }

        .contact-info p {
            font-size: 1.15em;
            margin-bottom: 12px;
            color: rgba(255, 255, 255, 0.9);
        }

        .contact-info p i {
            color: var(--secondary-color);
            margin-left: 12px;
        }

        /* تذييل الموقع (Footer) */
        .main-footer {
            background-color: var(--background-dark); /* بنفسجي غامق جداً */
            color: var(--white);
            padding: 40px 0;
            text-align: center;
            font-size: 0.95em;
        }

        .main-footer .container {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }

        .social-links a {
            color: var(--white);
            font-size: 1.6em;
            margin: 0 12px;
            transition: color 0.3s ease, transform 0.2s ease;
        }

        .social-links a:hover {
            color: var(--secondary-color);
            transform: translateY(-3px) scale(1.1);
        }

        /* التصميم المستجيب (Responsive Design) */
        @media (max-width: 992px) {
            .main-nav ul {
                gap: 20px;
            }
            .hero-content h2 {
                font-size: 3em;
            }
            section h3 {
                font-size: 2.5em;
            }
            .product-card img {
                height: 220px;
            }
            .story-content {
                flex-direction: column;
                text-align: center;
            }
            .story-text h4 {
                text-align: center;
            }

            /* تصغير اللوجو قليلاً على الشاشات الأصغر */
            .logo-img-link img {
                height: 45px;
            }
        }

        @media (max-width: 768px) {
            .main-nav {
                /* خصائص قائمة الموبايل */
                display: none; /* إخفاء الناف بشكل افتراضي */
                flex-direction: column; /* لجعل اللوجو والروابط تظهر فوق بعضها */
                width: 100%;
                position: absolute;
                top: 80px; /* تحت الهيدر */
                left: 0;
                background-color: var(--white);
                box-shadow: var(--box-shadow-light);
                padding: 20px 0;
                border-top: 1px solid #eee;
            }

            .main-nav.active {
                display: flex; /* إظهار الناف عندما يكون كلاس active موجودا */
            }

            .main-nav ul {
                flex-direction: column;
                align-items: center;
                width: 100%;
            }

            .main-nav ul li {
                margin: 10px 0;
                width: 80%; /* لجعل الروابط أكبر للمس */
            }

            .main-nav a {
                padding: 10px 0;
                display: block;
                width: 100%;
                text-align: center;
                border-bottom: 1px solid rgba(0,0,0,0.05); /* فاصل بين الروابط */
            }
            .main-nav a::after {
                display: none; /* إخفاء تأثير الخط السفلي في قائمة الموبايل */
            }
            .main-nav ul li:last-child a {
                border-bottom: none;
            }

            .menu-toggle {
                display: block;
            }

            .hero-content h2 {
                font-size: 2.5em;
            }

            .hero-content p {
                font-size: 1.1em;
            }

            section {
                padding: 60px 0;
            }

            section h3 {
                font-size: 2.2em;
                margin-bottom: 40px;
            }

            .product-card {
                padding-bottom: 15px;
            }
            .product-card img {
                height: 200px;
            }
            .product-card h4 {
                font-size: 1.4em;
            }
            .product-card .price {
                font-size: 1.6em;
            }
            .product-card .btn {
                padding: 8px 20px;
                font-size: 0.9em;
            }

            .video-wrapper {
                margin: 30px auto 0 auto;
                border-radius: 8px;
            }

            .story-content {
                gap: 30px;
            }

            .story-text h4 {
                font-size: 1.8em;
            }

            .story-text p {
                font-size: 1em;
            }

            .testimonial-card {
                padding: 25px;
            }

            /* لضمان ظهور اللوجو بشكل صحيح في قائمة الموبايل */
            .logo-img-link {
                margin-bottom: 20px; /* مسافة تحت اللوجو في قائمة الموبايل */
            }
            .logo-img-link img {
                height: 40px; /* تصغير اللوجو أكثر للموبايل */
            }
        }

        @media (max-width: 480px) {
            .hero-content h2 {
                font-size: 2em;
            }
            .hero-content p {
                font-size: 1em;
            }
            .btn {
                padding: 10px 20px;
                font-size: 0.9em;
            }
            section h3 {
                font-size: 1.8em;
            }
            .product-grid, .testimonial-grid {
                gap: 20px;
            }
            .product-card img {
                height: 180px;
            }
            .contact-form {
                padding: 20px;
            }
            .form-group input,
            .form-group textarea {
                padding: 12px;
                font-size: 1em;
            }
            .contact-form .btn {
                padding: 12px 30px;
            }

            /* أصغر حجم للوجو على أصغر الشاشات */
            .logo-img-link img {
                height: 35px;
            }
        }
    </style>
</head>
<body>

    <header class="main-header">
        <div class="container">
            <nav class="main-nav">
                <a href="#hero" class="logo-img-link">
                    <img src="LOGO.jpg" alt="ZL_Cosmetics Logo">
                </a>
                <ul>
                    <li><a href="#hero">الرئيسية</a></li>
                    <li><a href="#products">منتجاتنا</a></li>
                    <li><a href="#video">شاهدي</a></li>
                    <li><a href="#story">قصتنا</a></li>
                    <li><a href="#testimonials">آراء العملاء</a></li>
                    <li><a href="#contact">تواصل معنا</a></li>
                </ul>
            </nav>
            <div class="menu-toggle" id="menu-toggle">
                <i class="fas fa-bars"></i>
            </div>
        </div>
    </header>

    <section class="hero-section" id="hero">
        <div class="container">
            <div class="hero-content">
                <h2>اكتشفي جمالكِ الطبيعي</h2>
                <p>مجموعتنا الفاخرة من منتجات التجميل المصنوعة بحب وعناية فائقة لتتألقي كل يوم.</p>
                <a href="#products" class="btn btn-primary">منتجاتنا</a>
                <a href="#story" class="btn btn-secondary">اكتشفي قصتنا</a>
            </div>
        </div>
    </section>

    <section class="featured-products" id="products">
        <div class="container">
            <h3>منتجاتنا الأكثر مبيعاً</h3>
            <div class="product-grid">
                <div class="product-card">
                    <img src="1.jpg" alt="كريم الترطيب الفاخر">
                    <h4>كريم الترطيب الفاخر</h4>
                    <p>ترطيب عميق يدوم طوال اليوم، يترك بشرتك ناعمة ومشرقة.</p>
                    <span class="price">2.50jd</span>
                    <a href="https://www.google.com" class="btn btn-primary">تفاصيل اكثر</a>
                </div>
                <div class="product-card">
                    <img src="2.webp" alt="واقي شمس">
                    <h4>  واقي شمس لاروش</h4>
                    <p> مصمم ليمتص بسرعة ويترك البشرة بملمس جاف وغير لامع.</p>
                    <span class="price">5.005jd</span>
                    <a href="https://www.google.com" class="btn btn-primary">تفاصيل اكثر</a>
                </div>
                <div class="product-card">
                    <img src="3.jpg" alt="أحمر الشفاه">
                    <h4>أحمر الشفاه السائل </h4>
                    <p>أحمر شفاه سائل من KIKO MILANO ذو طرفين يوفر لونًا مكثفًا ولامعًا بثبات طويل.</p>
                    <span class="price"> 1.75jd</span>
                    <a href="https://www.google.com" class="btn btn-primary">تفاصيل اكثر</a>
                </div>
                <div class="product-card">
                    <img src="4.png" alt="عطر يارا ">
                    <h4>عطر يارا</h4>
                    <p>عطر "يارا" من لطافة هو عطر نسائي أنيق يأتي في زجاجة وردية جذابة ومزينة، ويشتهر برائحته الزهرية والفواكهية الجذابة.</p>
                    <span class="price">10.0jd</span>
                    <a href="https://www.google.com" class="btn btn-primary">تفاصيل اكثر</a>
                </div>
            </div>
        </div>
    </section>

    <section class="video-showcase" id="video">
        <div class="container">
            <h1><b>شاهدي سحر منتجاتنا</b> </h1>
            <p>تُعرف منتجات Babaria، التي تُصنعها شركة Berioska S.L.، بتقديمها لمجموعة واسعة من مستحضرات العناية بالبشرة والشعر والجسم، والتي غالبًا ما تعتمد على مكونات طبيعية نشطة مثل الألوفيرا وزيت الورد والكولاجين. تسعى Babaria لتوفير حلول فعالة للعناية اليومية، مع التركيز على الجودة والابتكار لتلبية احتياجات المستهلكين المختلفة حول العالم.</p>
            <div class="video-wrapper">
                <iframe width="560" height="415" src="فيديو.mp4" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>
        </div>
    </section>

    <section class="brand-story" id="story">
        <div class="container">
            <h3>قصة Lujain and Zeina</h3>
            <div class="story-content">
                <div class="story-image">
                    <img src="LOGO.jpg" alt="قصتنا">
                </div>
                <div class="story-text">
                    <h4>الجمال يبدأ من الطبيعة</h4>
                    <p>في Lujain and Zeina، نؤمن بأن الجمال الحقيقي ينبع من الطبيعة. لذلك، نلتزم بتقديم منتجات تجميل عضوية وفاخرة، مستوحاة من أنقى المكونات الطبيعية.</p>
                    <p>بدأت رحلتنا بشغف لخلق تجربة عناية بالبشرة تحترم الطبيعة وتعزز جمالكِ الفريد، دون أي تنازلات على الجودة أو الفعالية.</p>
                    <a href="#contact" class="btn btn-primary">اكتشفي شغفنا</a>
                </div>
            </div>
        </div>
    </section>

    <section class="testimonials-section" id="testimonials">
        <div class="container">
            <h3>ماذا يقول عملاؤنا</h3>
            <div class="testimonial-grid">
                <div class="testimonial-card">
                    <i class="fas fa-quote-left"></i>
                    <p>"منتجات Lujain and Zeina غيرت روتين عنايتي بالبشرة تمامًا! بشرتي أصبحت أكثر نضارة وإشراقًا. أوصي بها بشدة!"</p>
                    <span class="author">-marah.</span>
                    <i class="fas fa-quote-right"></i>
                </div>
                <div class="testimonial-card">
                    <i class="fas fa-quote-left"></i>
                    <p>"لم أصدق الفرق الذي أحدثه سيروم الذهب. بشرتي تبدو أصغر سناً وأكثر حيوية. أحب هذه العلامة التجارية!"</p>
                    <span class="author">- raghad .</span>
                    <i class="fas fa-quote-right"></i> </div>
                <div class="testimonial-card">
                    <i class="fas fa-quote-left"></i>
                    <p>"أخيرًا وجدت منتجات طبيعية وفعالة. زيت الشعر رائع، ومعه أصبح شعري أقوى وأكثر لمعاناً."</p>
                    <span class="author"> -reem.</span>
                    <i class="fas fa-quote-right"></i>
                </div>
            </div>
        </div>
    </section>

    <section class="contact-section" id="contact">
        <div class="container">
            <h3>تواصلوا معنا</h3>
            <p>لأي استفسارات أو لتقديم طلبات خاصة، لا تترددوا في التواصل معنا!</p>
            <div class="contact-form">
                <form action="#" method="POST">
                    <div class="form-group">
                        <input type="text" id="name" name="name" placeholder="اسمك الكامل" required>
                    </div>
                    <div class="form-group">
                        <input type="email" id="email" name="email" placeholder="بريدك الإلكتروني" required>
                    </div>
                    <div class="form-group">
                        <textarea id="message" name="message" rows="5" placeholder="رسالتك" required></textarea>
                    </div>
                    <button type="submit" class="btn btn-secondary">إرسال الرسالة</button>
                </form>
            </div>
            <div class="contact-info">
                <p><i class="fas fa-phone"></i> 0792809115</p>
                <p><i class="fas fa-envelope"></i> Laithza_95@yahoo.com</p>
                <p><i class="fas fa-map-marker-alt"></i> الاردن ،عمان، النزهة، مقابل مركز ربوة النزهة الطبي</p>
            </div>
        </div>
    </section>

    <footer class="main-footer">
        <div class="container">
            <p>&copy; 2025 Lujain and Zeina. جميع الحقوق محفوظة.</p>
            <div class="social-links">
                <a href="https://www.facebook.com/share/193zewB5i6/" target="_blank"><i class="fab fa-facebook-f"></i></a> 
                <a href="https://www.instagram.com/zl_cosmeticss?igsh=Ynhmc3U4MmwyM2th" target="_blank"><i class="fab fa-instagram"></i></a>
                <a href="https://www.whatsapp.com/?lang=ar_AR" target="_blank"><i class="fab fa-whatsapp"></i></a>
            </div>
        </div>
    </footer>

    <script>
        // كود JavaScript للتفاعلية
        document.addEventListener('DOMContentLoaded', () => {
            const menuToggle = document.getElementById('menu-toggle'); // زر قائمة التنقل للموبايل
            const mainNav = document.querySelector('.main-nav'); // قائمة التنقل
            const navLinks = document.querySelectorAll('.main-nav ul li a'); // كل روابط التنقل

            // تبديل إظهار/إخفاء قائمة التنقل للموبايل عند النقر على زر القائمة
            if (menuToggle) { // التأكد من وجود العنصر قبل إضافة المستمع
                menuToggle.addEventListener('click', () => {
                    mainNav.classList.toggle('active'); // إضافة/إزالة كلاس 'active'
                });
            }

            // إخفاء القائمة عند النقر على أي رابط داخلها (مفيد لشاشات الموبايل)
            navLinks.forEach(link => {
                link.addEventListener('click', () => {
                    if (mainNav.classList.contains('active')) {
                        mainNav.classList.remove('active');
                    }
                });
            });

            // إضافة تأثير التمرير السلس عند النقر على روابط الأقسام
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault(); // منع السلوك الافتراضي للرابط

                    const targetId = this.getAttribute('href');
                    if (targetId === '#') return; // منع التمرير إذا كان الرابط '#'

                    const targetElement = document.querySelector(targetId);
                    if (targetElement) {
                        targetElement.scrollIntoView({
                            behavior: 'smooth'
                        });
                    }
                });
            });
        });
    </script>
</body>
</html>
