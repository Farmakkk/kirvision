<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <title>Кирилл · KIRVISION - начинающий full-stack разработчик</title>
  <meta name="description" content="Личный сайт-автобиография Кирилла, 16 лет, начинающий full-stack разработчик из Заринска. Планы на переезд в Сербию, IT-карьера и финансовые цели.">
  <meta name="author" content="Кирилл">
  
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;400;500;600;700;800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  
  <style>
    /* ===== RESET & VARIABLES ===== */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      /* Light theme */
      --bg-body: #f9fafb;
      --bg-surface: #ffffff;
      --bg-card: #ffffff;
      --bg-elevated: #f3f4f6;
      --text-primary: #111827;
      --text-secondary: #4b5563;
      --text-muted: #6c757d;
      --text-inverse: #ffffff;
      --border-light: #e5e7eb;
      --accent: #2c5f2d;
      --accent-hover: #1e4620;
      --accent-soft: #e8f0e8;
      --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.05), 0 1px 2px rgba(0, 0, 0, 0.03);
      --shadow-md: 0 4px 12px rgba(0, 0, 0, 0.05), 0 1px 2px rgba(0, 0, 0, 0.03);
      --shadow-lg: 0 10px 25px -5px rgba(0, 0, 0, 0.08);
      --nav-bg: rgba(255, 255, 255, 0.92);
      --transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
    }

    body.dark {
      --bg-body: #0f1217;
      --bg-surface: #1a1f2a;
      --bg-card: #1e2432;
      --bg-elevated: #151b26;
      --text-primary: #edf2f7;
      --text-secondary: #cbd5e1;
      --text-muted: #94a3b8;
      --text-inverse: #111827;
      --border-light: #2d3748;
      --accent: #6fbf4c;
      --accent-hover: #8bd46c;
      --accent-soft: #1e2a1e;
      --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.3);
      --shadow-md: 0 4px 12px rgba(0, 0, 0, 0.4);
      --shadow-lg: 0 10px 25px -5px rgba(0, 0, 0, 0.5);
      --nav-bg: rgba(18, 22, 32, 0.95);
    }

    body {
      font-family: 'Inter', system-ui, -apple-system, sans-serif;
      background-color: var(--bg-body);
      color: var(--text-primary);
      line-height: 1.5;
      transition: background-color 0.2s ease, color 0.2s ease;
    }

    /* ===== TYPOGRAPHY & UTILITIES ===== */
    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 1.5rem;
    }

    .section {
      margin: 4rem 0;
      scroll-margin-top: 5rem;
    }

    .section-title {
      font-size: 1.85rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      margin-bottom: 1.5rem;
      border-left: 4px solid var(--accent);
      padding-left: 1rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .section-title i {
      color: var(--accent);
      font-size: 1.5rem;
    }

    .card {
      background: var(--bg-card);
      border-radius: 1.25rem;
      padding: 1.75rem;
      box-shadow: var(--shadow-md);
      border: 1px solid var(--border-light);
      transition: transform 0.2s, box-shadow 0.2s;
    }

    .card:hover {
      transform: translateY(-2px);
      box-shadow: var(--shadow-lg);
    }

    .grid-2col {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 1.5rem;
    }

    .badge {
      background: var(--accent-soft);
      color: var(--accent);
      padding: 0.25rem 0.85rem;
      border-radius: 100px;
      font-size: 0.8rem;
      font-weight: 600;
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      white-space: nowrap;
    }

    /* ===== NAVIGATION ===== */
    .navbar {
      position: sticky;
      top: 0;
      backdrop-filter: blur(16px);
      background-color: var(--nav-bg);
      border-bottom: 1px solid var(--border-light);
      z-index: 1000;
      padding: 0.75rem 0;
    }

    .nav-content {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 1rem;
    }

    .logo {
      font-weight: 800;
      font-size: 1.5rem;
      letter-spacing: -0.02em;
      background: linear-gradient(135deg, var(--accent), #5a9e4b);
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
      flex-shrink: 0;
    }

    .logo-sub {
      font-size: 0.7rem;
      font-weight: 400;
      color: var(--text-muted);
    }

    /* Desktop navigation */
    .nav-links {
      display: flex;
      gap: 0.25rem;
      list-style: none;
    }

    .nav-links a {
      text-decoration: none;
      font-size: 0.9rem;
      font-weight: 500;
      color: var(--text-secondary);
      padding: 0.5rem 0.9rem;
      border-radius: 0.5rem;
      transition: var(--transition);
    }

    .nav-links a:hover {
      color: var(--accent);
      background: var(--accent-soft);
    }

    /* Theme toggle */
    .theme-toggle {
      background: var(--bg-surface);
      border: 1px solid var(--border-light);
      border-radius: 2rem;
      padding: 0.45rem 1rem;
      cursor: pointer;
      font-size: 0.85rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      color: var(--text-primary);
      transition: var(--transition);
      flex-shrink: 0;
    }

    .theme-toggle:hover {
      background: var(--accent-soft);
      border-color: var(--accent);
    }

    /* Mobile menu button (hidden on desktop) */
    .mobile-menu-btn {
      display: none;
      background: var(--bg-surface);
      border: 1px solid var(--border-light);
      border-radius: 0.5rem;
      padding: 0.5rem 0.75rem;
      cursor: pointer;
      color: var(--text-primary);
      font-size: 1.25rem;
      transition: var(--transition);
    }

    .mobile-menu-btn:hover {
      background: var(--accent-soft);
    }

    /* ===== HERO SECTION ===== */
    .hero {
      text-align: center;
      margin: 2.5rem 0 2rem;
    }

    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      background: var(--accent-soft);
      padding: 0.4rem 1rem;
      border-radius: 2rem;
      font-size: 0.85rem;
      color: var(--accent);
      font-weight: 500;
    }

    .hero h1 {
      font-size: 3rem;
      font-weight: 800;
      letter-spacing: -0.03em;
      margin: 1rem 0 0.5rem;
      background: linear-gradient(135deg, var(--text-primary), var(--accent));
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
    }

    .hero p {
      color: var(--text-secondary);
      max-width: 560px;
      margin: 0.75rem auto;
      font-size: 1.1rem;
    }

    /* ===== INFO LIST ===== */
    .info-list {
      list-style: none;
    }

    .info-list li {
      margin-bottom: 0.85rem;
      display: flex;
      align-items: baseline;
      gap: 0.75rem;
      flex-wrap: wrap;
    }

    .info-list strong {
      min-width: 140px;
      font-weight: 600;
      color: var(--accent);
    }

    /* ===== LANG ITEMS ===== */
    .lang-item {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      margin: 1rem 0;
      border-bottom: 1px dashed var(--border-light);
      padding-bottom: 0.75rem;
    }

    .lang-progress {
      background: var(--bg-elevated);
      border-radius: 1rem;
      padding: 1rem;
      margin-top: 1rem;
    }

    /* ===== TIMELINE ===== */
    .timeline-step {
      margin-bottom: 1.25rem;
      padding-left: 1.25rem;
      border-left: 2px solid var(--accent);
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
    }

    .timeline-step .badge {
      margin-right: 0.75rem;
    }

    /* ===== TAGS CLOUD ===== */
    .tags-cloud {
      display: flex;
      flex-wrap: wrap;
      gap: 0.6rem;
      margin: 1.25rem 0;
    }

    /* ===== TASKS LIST ===== */
    .tasks-list {
      list-style: none;
    }

    .tasks-list li {
      margin-bottom: 0.8rem;
      display: flex;
      align-items: center;
      gap: 0.6rem;
      flex-wrap: wrap;
    }

    .tasks-list li i {
      width: 1.5rem;
      color: var(--accent);
    }

    /* ===== FOOTER ===== */
    footer {
      text-align: center;
      padding: 2.5rem 0 2rem;
      border-top: 1px solid var(--border-light);
      margin-top: 3rem;
      color: var(--text-muted);
      font-size: 0.85rem;
    }

    /* ===== MOBILE STYLES ===== */
    @media (max-width: 768px) {
      .container {
        padding: 0 1rem;
      }
      
      .section-title {
        font-size: 1.5rem;
      }
      
      .hero h1 {
        font-size: 2.2rem;
      }
      
      /* Mobile navigation */
      .mobile-menu-btn {
        display: block;
      }
      
      .nav-links {
        position: fixed;
        top: 60px;
        left: -100%;
        width: 100%;
        max-width: 280px;
        height: calc(100vh - 60px);
        background: var(--bg-surface);
        flex-direction: column;
        padding: 1.5rem;
        gap: 0.5rem;
        border-right: 1px solid var(--border-light);
        transition: left 0.3s ease;
        box-shadow: var(--shadow-lg);
        z-index: 999;
      }
      
      .nav-links.active {
        left: 0;
      }
      
      .nav-links a {
        display: block;
        padding: 0.75rem 1rem;
        font-size: 1rem;
      }
      
      .card {
        padding: 1.25rem;
      }
      
      .info-list strong {
        min-width: 110px;
      }
      
      .badge {
        white-space: normal;
      }
    }

    /* Small phones */
    @media (max-width: 480px) {
      .hero h1 {
        font-size: 1.8rem;
      }
      
      .section {
        margin: 2.5rem 0;
      }
      
      .grid-2col {
        grid-template-columns: 1fr;
      }
      
      .timeline-step {
        flex-direction: column;
        gap: 0.3rem;
      }
    }

    /* ===== ANIMATIONS ===== */
    .section {
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.5s ease, transform 0.5s ease;
    }
    
    .section.visible {
      opacity: 1;
      transform: translateY(0);
    }
  </style>
</head>
<body>

<nav class="navbar">
  <div class="container nav-content">
    <div class="logo">
      KIRVISION <span class="logo-sub">· full-stack journey</span>
    </div>
    
    <button class="mobile-menu-btn" id="mobileMenuBtn" aria-label="Меню">
      <i class="fas fa-bars"></i>
    </button>
    
    <ul class="nav-links" id="navLinks">
      <li><a href="#about" class="nav-link">О себе</a></li>
      <li><a href="#education" class="nav-link">Образование</a></li>
      <li><a href="#languages" class="nav-link">Языки</a></li>
      <li><a href="#relocation" class="nav-link">Переезд</a></li>
      <li><a href="#finance" class="nav-link">Финансы</a></li>
      <li><a href="#traits" class="nav-link">Качества</a></li>
      <li><a href="#tasks" class="nav-link">Задачи</a></li>
      <li><a href="#mission" class="nav-link">Миссия</a></li>
    </ul>
    
    <button class="theme-toggle" id="themeToggle" aria-label="Сменить тему">
      <i class="fas fa-moon"></i>
      <span>Тёмная</span>
    </button>
  </div>
</nav>

<main>
  <div class="container">
    <!-- Hero -->
    <div class="hero">
      <div class="hero-badge">
        <i class="fas fa-code"></i> начинающий full-stack разработчик · стратег
      </div>
      <h1>Кирилл, 16 лет</h1>
      <p>«Пишу код, верстаю интерфейсы, строю будущее через дисциплину и технологии»</p>
    </div>

    <!-- About -->
    <section id="about" class="section">
      <h2 class="section-title">
        <i class="fas fa-user-astronaut"></i>
        Основные сведения
      </h2>
      <div class="card">
        <ul class="info-list">
          <li><strong>Имя:</strong> Кирилл</li>
          <li><strong>Возраст:</strong> 16 лет (родился в 2010)</li>
          <li><strong>Место жительства:</strong> Россия, Алтайский край, г. Заринск</li>
          <li><strong>Школа:</strong> МБОУ СОШ №7, г. Заринск</li>
          <li><strong>Гражданство:</strong> РФ</li>
          <li><strong>Семейное положение:</strong> холост, в планах создать семью</li>
        </ul>
      </div>
    </section>

    <!-- Education -->
    <section id="education" class="section">
      <h2 class="section-title">
        <i class="fas fa-graduation-cap"></i>
        Образование и путь в IT
      </h2>
      <div class="card">
        <p>Сейчас учусь в <strong>школе №7 г. Заринска</strong>. Уже умею верстать адаптивные сайты (HTML, CSS), есть базовая база JavaScript. После 11 класса планирую поступать в <strong>АлтГТУ им. И.И. Ползунова</strong> (Барнаул) на направление «Программная инженерия» или «Информатика и вычислительная техника». Цель — стать full-stack разработчиком.</p>
        
        <div style="background: var(--bg-elevated); border-radius: 1rem; padding: 1.25rem; margin: 1.25rem 0;">
          <p style="font-weight: 700; margin-bottom: 0.75rem;">
            <i class="fas fa-laptop-code"></i> План на 18–22 года:
          </p>
          <ul style="margin-left: 1.25rem; display: flex; flex-direction: column; gap: 0.4rem;">
            <li>Диплом бакалавра в АлтГТУ</li>
            <li>Углублённое изучение JavaScript, React, Node.js, TypeScript</li>
            <li>Участие в open-source и хакатонах</li>
            <li>Работа на фрилансе / стажировки в IT-компании для набора опыта</li>
            <li>Накопление стартового капитала (фриланс, пет-проекты) → цель <strong>€5000–7000</strong></li>
          </ul>
        </div>
        
        <div class="badge" id="dynamicYearBadge">
          <i class="fas fa-hourglass-half"></i> Поступление в АлтГТУ: 2028 год
        </div>
      </div>
    </section>

    <!-- Languages -->
    <section id="languages" class="section">
      <h2 class="section-title">
        <i class="fas fa-language"></i>
        Языковой профиль
      </h2>
      <div class="card">
        <div class="lang-item">
          <span><strong>Русский</strong> — родной</span>
          <span class="badge">C2</span>
        </div>
        <div class="lang-item">
          <span><strong>Английский</strong> (сейчас B2)</span>
          <span class="badge">🎯 C1/C2 к окончанию вуза</span>
        </div>
        <div class="lang-item">
          <span><strong>Сербский</strong> (изучение с нуля)</span>
          <span class="badge">🎯 A2–B1 к переезду</span>
        </div>
        <div class="lang-progress">
          <i class="fas fa-check-circle" style="color: var(--accent);"></i> Знаю сербскую кириллицу, базовые фразы. Продолжаю учить самостоятельно для комфортной жизни в Сербии.
        </div>
      </div>
    </section>

    <!-- Relocation -->
    <section id="relocation" class="section">
      <h2 class="section-title">
        <i class="fas fa-plane-departure"></i>
        Переезд в Сербию (IT-трек)
      </h2>
      <div class="card">
        <p>После получения диплома (ориентировочно <strong id="relocationYearSpan">2032–2034</strong>) переезд из г. Заринска → Сербия: <strong>Белград или Нови-Сад</strong> как востребованный IT-специалист.</p>
        
        <div style="margin: 1.25rem 0;">
          <div class="timeline-step">
            <span class="badge">1</span> 2–3 месяца по туристическому безвизу — поиск удалённой работы в европейских компаниях или оффера в местных IT-фирмах, снятие комнаты.
          </div>
          <div class="timeline-step">
            <span class="badge">2</span> Получение ВНЖ через трудоустройство (Digital nomad / IT-специалист).
          </div>
          <div class="timeline-step">
            <span class="badge">3</span> Карьера: Junior → Middle разработчик (удалёнка или гибрид). Целевой доход: от €2000–3000+ через несколько лет.
          </div>
        </div>
      </div>
    </section>

    <!-- Finance -->
    <section id="finance" class="section">
      <h2 class="section-title">
        <i class="fas fa-chart-line"></i>
        Финансовая стратегия &amp; жильё
      </h2>
      <div class="grid-2col">
        <div class="card">
          <h3 style="margin-bottom: 1rem;"><i class="fas fa-home"></i> Недвижимость</h3>
          <p>Цель: <strong>3-комнатная квартира в Нови-Саде или дом в пригороде (€50 000–100 000)</strong>.</p>
          <ul style="margin-top: 1rem; margin-left: 1.25rem;">
            <li>Первые 3–5 лет аренда студии, активное накопление взноса (20%)</li>
            <li>После гражданства (8–10 лет) — льготная ипотека или покупка за наличные</li>
            <li>Выход на финансовую независимость к 45 годам: пассивный доход + IT-сбережения</li>
          </ul>
        </div>
        <div class="card">
          <h3 style="margin-bottom: 1rem;"><i class="fas fa-feather-alt"></i> Инвестиции &amp; вдохновение</h3>
          <p>Часть дохода — в ETF, облигации. Но главное вдохновение черпаю из <strong>японской литературы</strong>.</p>
          <div class="badge" style="margin: 1rem 0 0.75rem;">
            <i class="fas fa-book-open"></i> Любимые авторы: Харуки Мураками, Юкио Мисима, Рюноскэ Акутагава
          </div>
          <p>«Норвежский лес», «Исповедь неполноценного человека» — книги, которые меняют взгляд на дисциплину и жизнь.</p>
        </div>
      </div>
    </section>

    <!-- Personal traits -->
    <section id="traits" class="section">
      <h2 class="section-title">
        <i class="fas fa-heart"></i>
        Характер и увлечения
      </h2>
      <div class="card">
        <p><strong>Стратег и планировщик</strong> — веду таблицы расходов, изучаю FIRE, люблю структурировать код и жизнь. В общении спокоен, дипломатичен, ценю честность.</p>
        
        <div class="tags-cloud">
          <span class="badge"><i class="fab fa-js"></i> Веб-разработка</span>
          <span class="badge"><i class="fas fa-code"></i> Верстка, адаптив</span>
          <span class="badge"><i class="fas fa-dumbbell"></i> Спорт: бег, зал</span>
          <span class="badge"><i class="fas fa-globe-asia"></i> Японская литература</span>
          <span class="badge"><i class="fas fa-database"></i> Алгоритмы</span>
        </div>
        
        <p>Открыт к коллаборациям, легко нахожу общий язык. Верю: дисциплина и долгосрочное планирование приведут меня к дому у реки, любимой семье и работе-удовольствию.</p>
      </div>
    </section>

    <!-- Tasks -->
    <section id="tasks" class="section">
      <h2 class="section-title">
        <i class="fas fa-tasks"></i>
        Ближайшие задачи (16–18 лет)
      </h2>
      <div class="card">
        <ul class="tasks-list">
          <li><i class="fas fa-check-circle"></i> Сдать ЕГЭ на высокие баллы: профильная математика, информатика, русский язык</li>
          <li><i class="fas fa-check-circle"></i> Поступить в АлтГТУ им. И.И. Ползунова на бюджет</li>
          <li><i class="fas fa-check-circle"></i> Углубить знания JavaScript: async/await, fetch, DOM</li>
          <li><i class="fas fa-check-circle"></i> Сверстать 3–5 собственных пет-проектов (портфолио, ToDo-приложение)</li>
          <li><i class="fas fa-check-circle"></i> Начать учить сербский язык (разговорный минимум A1→A2)</li>
          <li><i class="fas fa-check-circle"></i> Прочитать классику японской литературы и технические книги по IT</li>
          <li><i class="fas fa-check-circle"></i> Найти первых заказчиков на фрилансе (верстка лендингов)</li>
        </ul>
        
        <div style="margin-top: 1.5rem; background: var(--accent-soft); border-radius: 1rem; padding: 1rem;">
          <i class="fas fa-clock"></i> <strong>До поступления в АлтГТУ:</strong> 
          <span id="countdownToUni" style="font-weight: 700; color: var(--accent); margin-left: 0.5rem;">-- лет</span>
        </div>
      </div>
    </section>

    <!-- Mission -->
    <section id="mission" class="section">
      <h2 class="section-title">
        <i class="fas fa-rocket"></i>
        Моя миссия
      </h2>
      <div class="card" style="text-align: center;">
        <p style="font-size: 1.2rem; font-style: italic;">«Стать разработчиком высокого класса, работать удалённо из Европы, создать уютный дом и достичь финансовой независимости в 45 лет. Япония в книгах, Сербия как база, а код — мой главный инструмент»</p>
        <div class="tags-cloud" style="justify-content: center; margin-top: 1rem;">
          <span class="badge">FIRE-стратегия</span>
          <span class="badge">Веб-разработка</span>
          <span class="badge">Японская философия</span>
        </div>
      </div>
    </section>
  </div>
</main>

<footer>
  <p>© 2026 KIRVISION · Кирилл, г. Заринск — Барнаул — Сербия · Code. Plan. Achieve.</p>
  <p style="margin-top: 0.5rem;"><i class="fas fa-map-marker-alt"></i> Алтайский край → мировое IT-комьюнити</p>
</footer>

<script>
  (function() {
    // ===== Theme Toggle =====
    const themeToggle = document.getElementById('themeToggle');
    const updateThemeIcon = (isDark) => {
      const icon = themeToggle?.querySelector('i');
      const span = themeToggle?.querySelector('span');
      if (icon && span) {
        if (isDark) {
          icon.className = 'fas fa-sun';
          span.textContent = 'Светлая';
        } else {
          icon.className = 'fas fa-moon';
          span.textContent = 'Тёмная';
        }
      }
    };
    
    const savedTheme = localStorage.getItem('theme');
    if (savedTheme === 'dark') {
      document.body.classList.add('dark');
      updateThemeIcon(true);
    } else if (savedTheme === 'light') {
      document.body.classList.remove('dark');
      updateThemeIcon(false);
    } else if (window.matchMedia('(prefers-color-scheme: dark)').matches) {
      document.body.classList.add('dark');
      updateThemeIcon(true);
      localStorage.setItem('theme', 'dark');
    } else {
      updateThemeIcon(false);
    }
    
    themeToggle?.addEventListener('click', () => {
      const isDark = document.body.classList.toggle('dark');
      localStorage.setItem('theme', isDark ? 'dark' : 'light');
      updateThemeIcon(isDark);
    });
    
    // ===== Mobile Menu =====
    const mobileBtn = document.getElementById('mobileMenuBtn');
    const navLinks = document.getElementById('navLinks');
    
    if (mobileBtn && navLinks) {
      mobileBtn.addEventListener('click', () => {
        navLinks.classList.toggle('active');
        const icon = mobileBtn.querySelector('i');
        if (icon) {
          icon.className = navLinks.classList.contains('active') ? 'fas fa-times' : 'fas fa-bars';
        }
      });
      
      // Close menu when clicking on a link
      document.querySelectorAll('.nav-link').forEach(link => {
        link.addEventListener('click', () => {
          navLinks.classList.remove('active');
          const icon = mobileBtn.querySelector('i');
          if (icon) icon.className = 'fas fa-bars';
        });
      });
      
      // Close menu when clicking outside
      document.addEventListener('click', (e) => {
        if (!navLinks.contains(e.target) && !mobileBtn.contains(e.target) && navLinks.classList.contains('active')) {
          navLinks.classList.remove('active');
          const icon = mobileBtn.querySelector('i');
          if (icon) icon.className = 'fas fa-bars';
        }
      });
    }
    
    // ===== Dynamic Years =====
    const now = new Date();
    const currentYear = now.getFullYear();
    const entranceYear = 2028;
    const gradYear = entranceYear + 4;
    
    const badgeSpan = document.getElementById('dynamicYearBadge');
    if (badgeSpan) {
      badgeSpan.innerHTML = `<i class="fas fa-hourglass-half"></i> Поступление в АлтГТУ: ${entranceYear} год (бюджет, программирование)`;
    }
    
    const countdownSpan = document.getElementById('countdownToUni');
    if (countdownSpan) {
      let yearsLeft = entranceYear - currentYear;
      if (yearsLeft < 0) yearsLeft = 0;
      const getYearsWord = (n) => {
        if (n === 0) return 'уже в этом году!';
        if (n % 10 === 1 && n % 100 !== 11) return `${n} год`;
        if ([2,3,4].includes(n % 10) && ![12,13,14].includes(n % 100)) return `${n} года`;
        return `${n} лет`;
      };
      countdownSpan.textContent = yearsLeft === 0 ? 'уже в этом году!' : getYearsWord(yearsLeft);
    }
    
    const relocationSpan = document.getElementById('relocationYearSpan');
    if (relocationSpan) {
      relocationSpan.textContent = `${gradYear}–${gradYear + 2}`;
    }
    
    // ===== Scroll Animations =====
    const sections = document.querySelectorAll('.section');
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.1, rootMargin: '0px 0px -20px 0px' });
    
    sections.forEach(section => observer.observe(section));
    
    // ===== Relocation Note (dynamic) =====
    const targetRelocYear = 2032;
    const yearsToReloc = Math.max(0, targetRelocYear - currentYear);
    const relocateCard = document.querySelector('#relocation .card');
    
    if (relocateCard && !document.querySelector('#relocation .relo-note')) {
      const note = document.createElement('div');
      note.className = 'relo-note';
      note.style.marginTop = '1rem';
      note.style.padding = '0.75rem';
      note.style.borderRadius = '0.75rem';
      note.style.backgroundColor = 'var(--accent-soft)';
      note.style.fontSize = '0.85rem';
      
      const getWord = (n) => {
        if (n === 1) return 'год';
        if (n >= 2 && n <= 4) return 'года';
        return 'лет';
      };
      
      note.innerHTML = `<i class="fas fa-hourglass-start"></i> До ориентировочного переезда в Сербию ≈ ${yearsToReloc} ${getWord(yearsToReloc)}. Время развивать навыки JavaScript и учить сербский!`;
      relocateCard.appendChild(note);
    }
  })();
</script>
</body>
</html>
