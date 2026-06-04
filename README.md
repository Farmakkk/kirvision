<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover, user-scalable=yes">
  <title>Кирилл · KIRVISION - начинающий full-stack разработчик</title>
  <meta name="description" content="Личный сайт-автобиография Кирилла, 16 лет, начинающий full-stack разработчик из Заринска">
  <meta name="author" content="Кирилл">
  
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;400;500;600;700;800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    /* Variables */
    :root {
      --bg-body: #f9fafb;
      --bg-surface: #ffffff;
      --bg-card: #ffffff;
      --bg-elevated: #f3f4f6;
      --text-primary: #111827;
      --text-secondary: #4b5563;
      --text-muted: #6c757d;
      --border-light: #e5e7eb;
      --accent: #2c5f2d;
      --accent-hover: #1e4620;
      --accent-soft: #e8f0e8;
      --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.05);
      --shadow-md: 0 4px 12px rgba(0, 0, 0, 0.05);
      --shadow-lg: 0 10px 25px -5px rgba(0, 0, 0, 0.08);
      --nav-bg: rgba(255, 255, 255, 0.98);
      --transition: all 0.2s ease;
    }

    body.dark {
      --bg-body: #0f1217;
      --bg-surface: #1a1f2a;
      --bg-card: #1e2432;
      --bg-elevated: #151b26;
      --text-primary: #edf2f7;
      --text-secondary: #cbd5e1;
      --text-muted: #94a3b8;
      --border-light: #2d3748;
      --accent: #6fbf4c;
      --accent-hover: #8bd46c;
      --accent-soft: #1e2a1e;
      --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.3);
      --shadow-md: 0 4px 12px rgba(0, 0, 0, 0.4);
      --shadow-lg: 0 10px 25px -5px rgba(0, 0, 0, 0.5);
      --nav-bg: rgba(18, 22, 32, 0.98);
    }

    body {
      font-family: 'Inter', system-ui, -apple-system, sans-serif;
      background-color: var(--bg-body);
      color: var(--text-primary);
      line-height: 1.5;
      transition: background-color 0.2s ease, color 0.2s ease;
      overflow-x: hidden;
    }

    .container {
      width: 100%;
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 1rem;
    }

    @media (min-width: 768px) {
      .container {
        padding: 0 1.5rem;
      }
    }

    /* Section styles */
    .section {
      margin: 3rem 0;
      scroll-margin-top: 5rem;
    }

    @media (min-width: 768px) {
      .section {
        margin: 4rem 0;
      }
    }

    .section-title {
      font-size: 1.5rem;
      font-weight: 700;
      letter-spacing: -0.02em;
      margin-bottom: 1.25rem;
      border-left: 4px solid var(--accent);
      padding-left: 0.875rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    @media (min-width: 768px) {
      .section-title {
        font-size: 1.85rem;
        margin-bottom: 1.5rem;
        padding-left: 1rem;
      }
    }

    .section-title i {
      color: var(--accent);
      font-size: 1.25rem;
    }

    @media (min-width: 768px) {
      .section-title i {
        font-size: 1.5rem;
      }
    }

    .card {
      background: var(--bg-card);
      border-radius: 1rem;
      padding: 1.25rem;
      box-shadow: var(--shadow-md);
      border: 1px solid var(--border-light);
      transition: transform 0.2s, box-shadow 0.2s;
    }

    @media (min-width: 768px) {
      .card {
        border-radius: 1.25rem;
        padding: 1.75rem;
      }
    }

    .card:hover {
      transform: translateY(-2px);
      box-shadow: var(--shadow-lg);
    }

    .grid-2col {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    @media (min-width: 768px) {
      .grid-2col {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 1.5rem;
      }
    }

    .badge {
      background: var(--accent-soft);
      color: var(--accent);
      padding: 0.25rem 0.75rem;
      border-radius: 100px;
      font-size: 0.75rem;
      font-weight: 600;
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
    }

    @media (min-width: 768px) {
      .badge {
        padding: 0.25rem 0.85rem;
        font-size: 0.8rem;
      }
    }

    /* ===== НАВИГАЦИЯ - ПОЛНОСТЬЮ ПЕРЕДЕЛАНА ===== */
    .navbar {
      position: sticky;
      top: 0;
      left: 0;
      right: 0;
      backdrop-filter: blur(16px);
      background-color: var(--nav-bg);
      border-bottom: 1px solid var(--border-light);
      z-index: 1000;
      width: 100%;
    }

    .nav-container {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 0.5rem;
      width: 100%;
      max-width: 1200px;
      margin: 0 auto;
      padding: 0.6rem 1rem;
    }

    @media (min-width: 768px) {
      .nav-container {
        padding: 0.75rem 1.5rem;
        gap: 1rem;
      }
    }

    .logo {
      font-weight: 800;
      font-size: 1.2rem;
      letter-spacing: -0.02em;
      background: linear-gradient(135deg, var(--accent), #5a9e4b);
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
      flex-shrink: 0;
      white-space: nowrap;
    }

    @media (min-width: 480px) {
      .logo {
        font-size: 1.35rem;
      }
    }

    @media (min-width: 768px) {
      .logo {
        font-size: 1.5rem;
      }
    }

    .logo-sub {
      font-size: 0.55rem;
      font-weight: 400;
      color: var(--text-muted);
    }

    @media (min-width: 768px) {
      .logo-sub {
        font-size: 0.7rem;
      }
    }

    /* Desktop navigation - без точек */
    .nav-links {
      display: none;
      list-style: none;
      margin: 0;
      padding: 0;
      gap: 0.25rem;
    }

    @media (min-width: 992px) {
      .nav-links {
        display: flex;
      }
    }

    .nav-links li {
      list-style: none;
    }

    .nav-links a {
      text-decoration: none;
      font-size: 0.85rem;
      font-weight: 500;
      color: var(--text-secondary);
      padding: 0.4rem 0.8rem;
      border-radius: 0.5rem;
      transition: var(--transition);
      white-space: nowrap;
    }

    @media (min-width: 1200px) {
      .nav-links a {
        font-size: 0.9rem;
        padding: 0.5rem 0.9rem;
      }
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
      padding: 0.35rem 0.8rem;
      cursor: pointer;
      font-size: 0.75rem;
      display: flex;
      align-items: center;
      gap: 0.4rem;
      color: var(--text-primary);
      transition: var(--transition);
      flex-shrink: 0;
    }

    @media (min-width: 768px) {
      .theme-toggle {
        padding: 0.45rem 1rem;
        font-size: 0.85rem;
        gap: 0.5rem;
      }
    }

    .theme-toggle:hover {
      background: var(--accent-soft);
      border-color: var(--accent);
    }

    /* Mobile menu button */
    .mobile-menu-btn {
      display: flex;
      align-items: center;
      justify-content: center;
      background: var(--bg-surface);
      border: 1px solid var(--border-light);
      border-radius: 0.5rem;
      padding: 0.4rem 0.7rem;
      cursor: pointer;
      color: var(--text-primary);
      font-size: 1rem;
      transition: var(--transition);
      flex-shrink: 0;
    }

    @media (min-width: 992px) {
      .mobile-menu-btn {
        display: none;
      }
    }

    .mobile-menu-btn:active {
      background: var(--accent-soft);
    }

    /* Mobile menu overlay */
    .mobile-menu-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      z-index: 998;
      opacity: 0;
      visibility: hidden;
      transition: opacity 0.3s ease, visibility 0.3s ease;
    }

    .mobile-menu-overlay.active {
      opacity: 1;
      visibility: visible;
    }

    /* Mobile navigation panel - без точек */
    .mobile-nav {
      position: fixed;
      top: 0;
      left: -280px;
      width: 280px;
      height: 100%;
      background: var(--bg-surface);
      z-index: 999;
      transition: left 0.3s ease;
      box-shadow: var(--shadow-lg);
      display: flex;
      flex-direction: column;
      overflow-y: auto;
    }

    .mobile-nav.active {
      left: 0;
    }

    .mobile-nav-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 1.25rem;
      border-bottom: 1px solid var(--border-light);
    }

    .mobile-nav-close {
      background: none;
      border: none;
      font-size: 1.3rem;
      cursor: pointer;
      color: var(--text-secondary);
      padding: 0.25rem;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .mobile-nav-links {
      list-style: none;
      padding: 0.5rem 0;
      margin: 0;
    }

    .mobile-nav-links li {
      list-style: none;
      margin: 0;
      padding: 0;
    }

    .mobile-nav-links a {
      display: block;
      text-decoration: none;
      font-size: 1rem;
      font-weight: 500;
      color: var(--text-secondary);
      padding: 0.9rem 1.25rem;
      transition: var(--transition);
      border-bottom: 1px solid var(--border-light);
    }

    .mobile-nav-links a:active {
      color: var(--accent);
      background: var(--accent-soft);
      padding-left: 1.5rem;
    }

    /* Hero */
    .hero {
      text-align: center;
      margin: 1.5rem 0 1.5rem;
    }

    @media (min-width: 768px) {
      .hero {
        margin: 2.5rem 0 2rem;
      }
    }

    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      background: var(--accent-soft);
      padding: 0.3rem 0.8rem;
      border-radius: 2rem;
      font-size: 0.75rem;
      color: var(--accent);
      font-weight: 500;
    }

    @media (min-width: 768px) {
      .hero-badge {
        gap: 0.5rem;
        padding: 0.4rem 1rem;
        font-size: 0.85rem;
      }
    }

    .hero h1 {
      font-size: 1.8rem;
      font-weight: 800;
      letter-spacing: -0.02em;
      margin: 0.75rem 0 0.5rem;
    }

    @media (min-width: 480px) {
      .hero h1 {
        font-size: 2.2rem;
      }
    }

    @media (min-width: 768px) {
      .hero h1 {
        font-size: 3rem;
        margin: 1rem 0 0.5rem;
      }
    }

    .hero p {
      color: var(--text-secondary);
      max-width: 560px;
      margin: 0.5rem auto;
      font-size: 0.9rem;
      padding: 0 0.5rem;
    }

    @media (min-width: 768px) {
      .hero p {
        font-size: 1.1rem;
        margin: 0.75rem auto;
      }
    }

    /* Info list */
    .info-list {
      list-style: none;
    }

    .info-list li {
      margin-bottom: 0.75rem;
      display: flex;
      flex-direction: column;
      gap: 0.25rem;
    }

    @media (min-width: 480px) {
      .info-list li {
        flex-direction: row;
        align-items: baseline;
        gap: 0.75rem;
        flex-wrap: wrap;
      }
    }

    .info-list strong {
      font-weight: 600;
      color: var(--accent);
      min-width: 120px;
    }

    @media (min-width: 768px) {
      .info-list strong {
        min-width: 140px;
      }
    }

    /* Language items */
    .lang-item {
      display: flex;
      flex-direction: column;
      gap: 0.25rem;
      margin: 0.75rem 0;
      border-bottom: 1px dashed var(--border-light);
      padding-bottom: 0.75rem;
    }

    @media (min-width: 480px) {
      .lang-item {
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        gap: 0.5rem;
      }
    }

    .lang-progress {
      background: var(--bg-elevated);
      border-radius: 0.75rem;
      padding: 0.75rem;
      margin-top: 0.75rem;
      font-size: 0.85rem;
    }

    /* Timeline */
    .timeline-step {
      margin-bottom: 1rem;
      display: flex;
      flex-direction: column;
      gap: 0.5rem;
      padding-left: 0;
      border-left: none;
    }

    @media (min-width: 480px) {
      .timeline-step {
        flex-direction: row;
        align-items: flex-start;
        padding-left: 1rem;
        border-left: 2px solid var(--accent);
        gap: 0.75rem;
      }
    }

    /* Tags */
    .tags-cloud {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin: 1rem 0;
    }

    /* Tasks list */
    .tasks-list {
      list-style: none;
    }

    .tasks-list li {
      margin-bottom: 0.7rem;
      display: flex;
      align-items: flex-start;
      gap: 0.5rem;
      font-size: 0.9rem;
    }

    @media (min-width: 768px) {
      .tasks-list li {
        font-size: 1rem;
        gap: 0.6rem;
      }
    }

    .tasks-list li i {
      width: 1.25rem;
      margin-top: 0.125rem;
      color: var(--accent);
      flex-shrink: 0;
    }

    /* Footer */
    footer {
      text-align: center;
      padding: 2rem 1rem 1.5rem;
      border-top: 1px solid var(--border-light);
      margin-top: 2rem;
      color: var(--text-muted);
      font-size: 0.75rem;
    }

    @media (min-width: 768px) {
      footer {
        padding: 2.5rem 0 2rem;
        margin-top: 3rem;
        font-size: 0.85rem;
      }
    }

    /* Animations */
    .section {
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.5s ease, transform 0.5s ease;
    }
    
    .section.visible {
      opacity: 1;
      transform: translateY(0);
    }

    .text-center {
      text-align: center;
    }
  </style>
</head>
<body>

<!-- НАВИГАЦИЯ - УПРОЩЁННАЯ И БЕЗ ТОЧЕК -->
<nav class="navbar">
  <div class="nav-container">
    <div class="logo">
      KIRVISION <span class="logo-sub">· full-stack journey</span>
    </div>
    
    <button class="mobile-menu-btn" id="mobileMenuBtn" aria-label="Меню">
      <i class="fas fa-bars"></i>
    </button>
    
    <!-- Desktop navigation - без точек -->
    <ul class="nav-links">
      <li><a href="#about">О себе</a></li>
      <li><a href="#education">Образование</a></li>
      <li><a href="#languages">Языки</a></li>
      <li><a href="#relocation">Переезд</a></li>
      <li><a href="#finance">Финансы</a></li>
      <li><a href="#traits">Качества</a></li>
      <li><a href="#tasks">Задачи</a></li>
      <li><a href="#mission">Миссия</a></li>
    </ul>
    
    <button class="theme-toggle" id="themeToggle" aria-label="Сменить тему">
      <i class="fas fa-moon"></i>
      <span>Тёмная</span>
    </button>
  </div>
</nav>

<!-- Mobile menu overlay -->
<div class="mobile-menu-overlay" id="mobileOverlay"></div>

<!-- Mobile navigation panel - без точек -->
<div class="mobile-nav" id="mobileNav">
  <div class="mobile-nav-header">
    <span class="logo" style="font-size: 1.2rem;">KIRVISION</span>
    <button class="mobile-nav-close" id="closeMobileMenu">
      <i class="fas fa-times"></i>
    </button>
  </div>
  <ul class="mobile-nav-links">
    <li><a href="#about">О себе</a></li>
    <li><a href="#education">Образование</a></li>
    <li><a href="#languages">Языки</a></li>
    <li><a href="#relocation">Переезд</a></li>
    <li><a href="#finance">Финансы</a></li>
    <li><a href="#traits">Качества</a></li>
    <li><a href="#tasks">Задачи</a></li>
    <li><a href="#mission">Миссия</a></li>
  </ul>
</div>

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
        
        <div style="background: var(--bg-elevated); border-radius: 0.75rem; padding: 1rem; margin: 1rem 0;">
          <p style="font-weight: 700; margin-bottom: 0.75rem;">
            <i class="fas fa-laptop-code"></i> План на 18–22 года:
          </p>
          <ul style="margin-left: 1.25rem; display: flex; flex-direction: column; gap: 0.35rem;">
            <li>Диплом бакалавра в АлтГТУ</li>
            <li>Углублённое изучение JavaScript, React, Node.js, TypeScript</li>
            <li>Участие в open-source и хакатонах</li>
            <li>Работа на фрилансе / стажировки в IT-компании</li>
            <li>Накопление стартового капитала → цель <strong>€5000–7000</strong></li>
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
          <i class="fas fa-check-circle" style="color: var(--accent);"></i> Знаю сербскую кириллицу, базовые фразы. Продолжаю учить самостоятельно.
        </div>
      </div>
    </section>

    <!-- Relocation -->
    <section id="relocation" class="section">
      <h2 class="section-title">
        <i class="fas fa-plane-departure"></i>
        Переезд в Сербию
      </h2>
      <div class="card">
        <p>После получения диплома (ориентировочно <strong id="relocationYearSpan">2032–2034</strong>) переезд → Сербия: <strong>Белград или Нови-Сад</strong> как IT-специалист.</p>
        
        <div style="margin: 1rem 0;">
          <div class="timeline-step">
            <span class="badge">1</span> <span>2–3 месяца по туристическому безвизу — поиск удалённой работы</span>
          </div>
          <div class="timeline-step">
            <span class="badge">2</span> <span>Получение ВНЖ через трудоустройство (Digital nomad / IT)</span>
          </div>
          <div class="timeline-step">
            <span class="badge">3</span> <span>Junior → Middle разработчик. Целевой доход: от €2000–3000+</span>
          </div>
        </div>
      </div>
    </section>

    <!-- Finance -->
    <section id="finance" class="section">
      <h2 class="section-title">
        <i class="fas fa-chart-line"></i>
        Финансы и жильё
      </h2>
      <div class="grid-2col">
        <div class="card">
          <h3 style="margin-bottom: 0.75rem; font-size: 1.1rem;"><i class="fas fa-home"></i> Недвижимость</h3>
          <p>Цель: <strong>3-комнатная квартира в Нови-Саде (€50 000–100 000)</strong>.</p>
          <ul style="margin-top: 0.75rem; margin-left: 1.25rem;">
            <li>Первые 3–5 лет аренда студии</li>
            <li>Накопление взноса 20%</li>
            <li>После гражданства — льготная ипотека</li>
          </ul>
        </div>
        <div class="card">
          <h3 style="margin-bottom: 0.75rem; font-size: 1.1rem;"><i class="fas fa-feather-alt"></i> Вдохновение</h3>
          <p>Часть дохода — в ETF, облигации. Вдохновляюсь <strong>японской литературой</strong>.</p>
          <div class="badge" style="margin: 0.75rem 0 0.5rem;">
            <i class="fas fa-book-open"></i> Мураками, Мисима, Акутагава
          </div>
          <p style="font-size: 0.85rem;">«Норвежский лес», «Исповедь неполноценного человека»</p>
        </div>
      </div>
    </section>

    <!-- Traits -->
    <section id="traits" class="section">
      <h2 class="section-title">
        <i class="fas fa-heart"></i>
        Характер и увлечения
      </h2>
      <div class="card">
        <p><strong>Стратег и планировщик</strong> — веду таблицы расходов, изучаю FIRE, люблю структурировать код.</p>
        
        <div class="tags-cloud">
          <span class="badge"><i class="fab fa-js"></i> Веб-разработка</span>
          <span class="badge"><i class="fas fa-code"></i> Верстка</span>
          <span class="badge"><i class="fas fa-dumbbell"></i> Спорт</span>
          <span class="badge"><i class="fas fa-globe-asia"></i> Японская литература</span>
        </div>
      </div>
    </section>

    <!-- Tasks -->
    <section id="tasks" class="section">
      <h2 class="section-title">
        <i class="fas fa-tasks"></i>
        Ближайшие задачи
      </h2>
      <div class="card">
        <ul class="tasks-list">
          <li><i class="fas fa-check-circle"></i> Сдать ЕГЭ: математика, информатика, русский</li>
          <li><i class="fas fa-check-circle"></i> Поступить в АлтГТУ на бюджет</li>
          <li><i class="fas fa-check-circle"></i> Углубить JavaScript (async/await, fetch, DOM)</li>
          <li><i class="fas fa-check-circle"></i> Сделать 3–5 пет-проектов в портфолио</li>
          <li><i class="fas fa-check-circle"></i> Учить сербский язык (A1→A2)</li>
          <li><i class="fas fa-check-circle"></i> Найти первых заказчиков на фрилансе</li>
        </ul>
        
        <div style="margin-top: 1rem; background: var(--accent-soft); border-radius: 0.75rem; padding: 0.75rem;">
          <i class="fas fa-clock"></i> <strong>До поступления:</strong> 
          <span id="countdownToUni" style="font-weight: 700; color: var(--accent);">-- лет</span>
        </div>
      </div>
    </section>

    <!-- Mission -->
    <section id="mission" class="section">
      <h2 class="section-title">
        <i class="fas fa-rocket"></i>
        Моя миссия
      </h2>
      <div class="card text-center">
        <p style="font-size: 1rem; font-style: italic;">«Стать разработчиком высокого класса, работать удалённо из Европы, создать уютный дом и достичь финансовой независимости»</p>
        <div class="tags-cloud" style="justify-content: center; margin-top: 0.75rem;">
          <span class="badge">FIRE-стратегия</span>
          <span class="badge">Веб-разработка</span>
          <span class="badge">Дисциплина</span>
        </div>
      </div>
    </section>
  </div>
</main>

<footer>
  <p>© 2026 KIRVISION · Кирилл, Заринск → Барнаул → Сербия</p>
  <p style="margin-top: 0.25rem;"><i class="fas fa-map-marker-alt"></i> Алтайский край → мировое IT</p>
</footer>

<script>
  (function() {
    // Theme toggle
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
    }
    
    themeToggle?.addEventListener('click', () => {
      const isDark = document.body.classList.toggle('dark');
      localStorage.setItem('theme', isDark ? 'dark' : 'light');
      updateThemeIcon(isDark);
    });
    
    // Mobile menu
    const mobileBtn = document.getElementById('mobileMenuBtn');
    const mobileNav = document.getElementById('mobileNav');
    const mobileOverlay = document.getElementById('mobileOverlay');
    const closeBtn = document.getElementById('closeMobileMenu');
    
    function openMobileMenu() {
      mobileNav.classList.add('active');
      mobileOverlay.classList.add('active');
      document.body.style.overflow = 'hidden';
    }
    
    function closeMobileMenu() {
      mobileNav.classList.remove('active');
      mobileOverlay.classList.remove('active');
      document.body.style.overflow = '';
    }
    
    mobileBtn?.addEventListener('click', openMobileMenu);
    closeBtn?.addEventListener('click', closeMobileMenu);
    mobileOverlay?.addEventListener('click', closeMobileMenu);
    
    // Close menu on link click
    document.querySelectorAll('.mobile-nav-links a').forEach(link => {
      link.addEventListener('click', (e) => {
        closeMobileMenu();
        const targetId = link.getAttribute('href');
        if (targetId && targetId !== '#') {
          e.preventDefault();
          const targetElement = document.querySelector(targetId);
          if (targetElement) {
            targetElement.scrollIntoView({ behavior: 'smooth' });
          }
        }
      });
    });
    
    // Smooth scroll for desktop links
    document.querySelectorAll('.nav-links a').forEach(link => {
      link.addEventListener('click', (e) => {
        const targetId = link.getAttribute('href');
        if (targetId && targetId !== '#') {
          e.preventDefault();
          const targetElement = document.querySelector(targetId);
          if (targetElement) {
            targetElement.scrollIntoView({ behavior: 'smooth' });
          }
        }
      });
    });
    
    // Dynamic dates
    const now = new Date();
    const currentYear = now.getFullYear();
    const entranceYear = 2028;
    const gradYear = entranceYear + 4;
    
    const badgeSpan = document.getElementById('dynamicYearBadge');
    if (badgeSpan) {
      badgeSpan.innerHTML = `<i class="fas fa-hourglass-half"></i> Поступление в АлтГТУ: ${entranceYear} год`;
    }
    
    const countdownSpan = document.getElementById('countdownToUni');
    if (countdownSpan) {
      let yearsLeft = entranceYear - currentYear;
      if (yearsLeft < 0) yearsLeft = 0;
      const getYearsWord = (n) => {
        if (n === 0) return 'уже в этом году!';
        if (n === 1) return '1 год';
        if (n >= 2 && n <= 4) return `${n} года`;
        return `${n} лет`;
      };
      countdownSpan.textContent = yearsLeft === 0 ? 'уже в этом году!' : getYearsWord(yearsLeft);
    }
    
    const relocationSpan = document.getElementById('relocationYearSpan');
    if (relocationSpan) {
      relocationSpan.textContent = `${gradYear}–${gradYear + 2}`;
    }
    
    // Scroll animations
    const sections = document.querySelectorAll('.section');
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.1 });
    
    sections.forEach(section => observer.observe(section));
  })();
</script>
</body>
</html>
