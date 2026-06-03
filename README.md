<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <title>Кирилл · KIRVISION - your example</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;400;500;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
      background-color: var(--bg-body);
      color: var(--text-primary);
      line-height: 1.5;
      scroll-behavior: smooth;
      transition: background-color 0.25s ease, color 0.2s ease;
    }

    :root {
      --bg-body: #f9fafb;
      --bg-surface: #ffffff;
      --bg-card: #ffffff;
      --text-primary: #111827;
      --text-secondary: #4b5563;
      --text-muted: #6c757d;
      --border-light: #e5e7eb;
      --accent: #2c5f2d;
      --accent-soft: #e8f0e8;
      --shadow-sm: 0 8px 20px rgba(0, 0, 0, 0.03), 0 2px 4px rgba(0, 0, 0, 0.05);
      --shadow-md: 0 12px 30px rgba(0, 0, 0, 0.05);
      --nav-bg: rgba(255, 255, 255, 0.85);
      --code-bg: #f3f4f6;
    }

    body.dark {
      --bg-body: #0f1217;
      --bg-surface: #1a1f2a;
      --bg-card: #1e2432;
      --text-primary: #edf2f7;
      --text-secondary: #cbd5e1;
      --text-muted: #94a3b8;
      --border-light: #2d3748;
      --accent: #6fbf4c;
      --accent-soft: #1e2a1e;
      --shadow-sm: 0 8px 20px rgba(0, 0, 0, 0.3);
      --shadow-md: 0 12px 30px rgba(0, 0, 0, 0.4);
      --nav-bg: rgba(18, 22, 32, 0.92);
      --code-bg: #0f1219;
    }

    .container {
      max-width: 1120px;
      margin: 0 auto;
      padding: 0 1.5rem;
    }

    .navbar {
      position: sticky;
      top: 0;
      backdrop-filter: blur(12px);
      background-color: var(--nav-bg);
      border-bottom: 1px solid var(--border-light);
      z-index: 100;
      padding: 0.85rem 0;
    }

    .nav-content {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 1rem;
    }

    .logo {
      font-weight: 700;
      font-size: 1.4rem;
      letter-spacing: -0.3px;
      background: linear-gradient(135deg, var(--accent), #3b8c3a);
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
    }

    .logo-sub {
      font-size: 0.75rem;
      font-weight: 400;
      letter-spacing: normal;
      color: var(--text-muted);
      margin-left: 0.25rem;
    }

    .nav-links {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem 1.2rem;
      list-style: none;
    }

    .nav-links a {
      text-decoration: none;
      font-size: 0.9rem;
      font-weight: 500;
      color: var(--text-secondary);
      transition: color 0.2s;
    }

    .nav-links a:hover {
      color: var(--accent);
    }

    .theme-toggle {
      background: var(--bg-surface);
      border: 1px solid var(--border-light);
      border-radius: 40px;
      padding: 0.45rem 0.9rem;
      cursor: pointer;
      font-size: 0.9rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      color: var(--text-primary);
      transition: all 0.2s;
    }

    .theme-toggle i {
      font-size: 1rem;
    }

    section {
      margin: 3.5rem 0;
      scroll-margin-top: 5rem;
    }

    .section-title {
      font-size: 1.8rem;
      font-weight: 600;
      letter-spacing: -0.02em;
      margin-bottom: 1.5rem;
      border-left: 5px solid var(--accent);
      padding-left: 1rem;
    }

    .card {
      background: var(--bg-card);
      border-radius: 1.25rem;
      padding: 1.8rem;
      box-shadow: var(--shadow-sm);
      border: 1px solid var(--border-light);
      transition: transform 0.2s, box-shadow 0.2s;
    }

    .card:hover {
      box-shadow: var(--shadow-md);
    }

    .grid-2col {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.5rem;
    }

    .info-list {
      list-style: none;
    }

    .info-list li {
      margin-bottom: 0.7rem;
      display: flex;
      align-items: baseline;
      gap: 0.6rem;
      flex-wrap: wrap;
    }

    .info-list strong {
      min-width: 130px;
      font-weight: 600;
      color: var(--accent);
    }

    .badge {
      background: var(--accent-soft);
      color: var(--accent);
      padding: 0.2rem 0.7rem;
      border-radius: 30px;
      font-size: 0.8rem;
      font-weight: 500;
      display: inline-block;
    }

    .lang-progress {
      background: var(--code-bg);
      border-radius: 1rem;
      padding: 1rem;
      margin-top: 0.8rem;
    }

    .lang-item {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      margin: 0.8rem 0;
      border-bottom: 1px dashed var(--border-light);
      padding-bottom: 0.5rem;
    }

    .level {
      font-family: monospace;
      font-weight: 500;
    }

    .timeline-step {
      margin-bottom: 1.2rem;
      padding-left: 1.2rem;
      border-left: 2px solid var(--accent);
    }

    footer {
      text-align: center;
      padding: 2.5rem 0 2rem;
      border-top: 1px solid var(--border-light);
      margin-top: 3rem;
      color: var(--text-muted);
      font-size: 0.85rem;
    }

    @media (max-width: 720px) {
      .container {
        padding: 0 1.2rem;
      }
      .section-title {
        font-size: 1.5rem;
      }
      .card {
        padding: 1.3rem;
      }
      .nav-links {
        gap: 0.8rem;
      }
      .nav-content {
        flex-direction: column;
        align-items: stretch;
      }
      .theme-toggle {
        align-self: flex-end;
      }
    }

    section {
      opacity: 0;
      transform: translateY(14px);
      transition: opacity 0.5s cubic-bezier(0.2, 0.9, 0.4, 1.1), transform 0.5s ease;
    }
    section.visible {
      opacity: 1;
      transform: translateY(0);
    }
  </style>
</head>
<body>

<nav class="navbar">
  <div class="container nav-content">
    <div class="logo">KIRVISION <span class="logo-sub">- your example</span></div>
    <ul class="nav-links">
      <li><a href="#about">О себе</a></li>
      <li><a href="#education">Образование</a></li>
      <li><a href="#languages">Языки</a></li>
      <li><a href="#relocation">Переезд</a></li>
      <li><a href="#finance">Финансы</a></li>
      <li><a href="#traits">Качества</a></li>
      <li><a href="#tasks">Задачи</a></li>
    </ul>
    <button class="theme-toggle" id="themeToggle" aria-label="Сменить тему">
      <i class="fas fa-moon"></i> <span>Тёмная</span>
    </button>
  </div>
</nav>

<main class="container">
  <div style="margin: 2rem 0 1rem 0; text-align: center;">
    <span class="badge"><i class="fas fa-code"></i> начинающий full-stack разработчик · стратег</span>
    <h1 style="font-size: 2.8rem; font-weight: 650; letter-spacing: -1px; margin-top: 1rem;">Кирилл, 16 лет</h1>
    <p style="color: var(--text-secondary); max-width: 560px; margin: 0.75rem auto;">«Пишу код, верстаю интерфейсы, строю будущее через дисциплину и технологии»</p>
  </div>

  <!-- 1. Основные сведения — г. Заринск -->
  <section id="about">
    <h2 class="section-title"><i class="fas fa-user-astronaut"></i> Основные сведения</h2>
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

  <!-- 2. Образование и IT-траектория -->
  <section id="education">
    <h2 class="section-title"><i class="fas fa-graduation-cap"></i> Образование и путь в IT</h2>
    <div class="card">
      <p>Сейчас учусь в <strong>школе №7 г. Заринска</strong>. Уже умею верстать адаптивные сайты (HTML, CSS), есть базовая база JavaScript. После 11 класса планирую поступать в <strong>АлтГТУ им. И.И. Ползунова</strong> (Барнаул) на направление «Программная инженерия» или «Информатика и вычислительная техника». Цель — стать full-stack разработчиком.</p>
      <div style="background: var(--code-bg); border-radius: 1rem; padding: 1rem; margin: 1.2rem 0;">
        <p style="font-weight: 600;"><i class="fas fa-laptop-code"></i> План на 18–22 года:</p>
        <ul style="margin-left: 1.5rem; margin-top: 0.5rem;">
          <li>Диплом бакалавра в АлтГТУ</li>
          <li>Углублённое изучение JavaScript, React, Node.js, TypeScript</li>
          <li>Участие в open-source и хакатонах</li>
          <li>Работа на фрилансе / стажировки в IT-компании для набора опыта</li>
          <li>Накопление стартового капитала (фриланс, пет-проекты) → цель <strong>€5000–7000</strong></li>
        </ul>
      </div>
      <div class="badge" id="dynamicYearBadge"><i class="fas fa-hourglass-half"></i> Поступление в АлтГТУ: 2028 год</div>
    </div>
  </section>

  <!-- 3. Языковые навыки (без французского) -->
  <section id="languages">
    <h2 class="section-title"><i class="fas fa-language"></i> Языковой профиль</h2>
    <div class="card">
      <div class="lang-item"><span><strong>Русский</strong> — родной</span> <span class="level">C2</span></div>
      <div class="lang-item"><span><strong>Английский</strong> (сейчас B2)</span> <span class="level">🎯 C1/C2 к окончанию вуза</span></div>
      <div class="lang-item"><span><strong>Сербский</strong> (изучение с нуля)</span> <span class="level">🎯 A2–B1 к переезду</span></div>
      <div class="lang-progress">✓ Знаю сербскую кириллицу, базовые фразы. Продолжаю учить самостоятельно для комфортной жизни в Сербии.</div>
    </div>
  </section>

  <!-- 4. План переезда в Сербию (IT-специалист) — удалён пункт про воинский учёт -->
  <section id="relocation">
    <h2 class="section-title"><i class="fas fa-plane-departure"></i> Переезд в Сербию (IT-трек)</h2>
    <div class="card">
      <p>После получения диплома (ориентировочно <strong id="relocationYearSpan">2032–2034</strong>) переезд из г. Заринска → Сербия: <strong>Белград или Нови-Сад</strong> как востребованный IT-специалист.</p>
      <div class="timeline-step"><span class="badge">1</span> 2–3 месяца по туристическому безвизу — поиск удалённой работы в европейских компаниях или оффера в местных IT-фирмах, снятие комнаты.</div>
      <div class="timeline-step"><span class="badge">2</span> Получение ВНЖ через трудоустройство (Digital nomad / IT-специалист).</div>
      <div class="timeline-step"><span class="badge">3</span> Карьера: Junior → Middle разработчик (удалёнка или гибрид). Целевой доход: от €2000–3000+ через несколько лет.</div>
      <!-- Пункт про воинский учёт полностью удалён по вашему запросу -->
    </div>
  </section>

  <!-- 5. Финансовая цель и недвижимость + японская литература -->
  <section id="finance">
    <h2 class="section-title"><i class="fas fa-chart-line"></i> Финансовая стратегия & жильё</h2>
    <div class="grid-2col">
      <div class="card">
        <h3><i class="fas fa-home"></i> Недвижимость</h3>
        <p>Цель: <strong>3-комнатная квартира в Нови-Саде или дом в пригороде (€50 000–100 000)</strong>.</p>
        <ul style="margin-top: 0.8rem; margin-left: 1.2rem;">
          <li>Первые 3–5 лет аренда студии, активное накопление взноса (20%)</li>
          <li>После гражданства (8–10 лет) — льготная ипотека или покупка за наличные</li>
          <li>Выход на финансовую независимость к 45 годам: пассивный доход + IT-сбережения</li>
        </ul>
      </div>
      <div class="card">
        <h3><i class="fas fa-feather-alt"></i> Инвестиции & вдохновение</h3>
        <p>Часть дохода — в ETF, облигации. Но главное вдохновение черпаю из <strong>японской литературы</strong>.</p>
        <div class="badge" style="margin-top: 0.8rem; display: inline-block;"><i class="fas fa-book-open"></i> Любимые авторы: Харуки Мураками, Юкио Мисима, Рюноскэ Акутагава</div>
        <p style="margin-top: 0.8rem;">«Норвежский лес», «Исповедь неполноценного человека» — книги, которые меняют взгляд на дисциплину и жизнь.</p>
      </div>
    </div>
  </section>

  <!-- 6. Личные качества и увлечения (программирование + японская литература) -->
  <section id="traits">
    <h2 class="section-title"><i class="fas fa-heart"></i> Характер и увлечения</h2>
    <div class="card">
      <p><strong>Стратег и планировщик</strong> — веду таблицы расходов, изучаю FIRE, люблю структурировать код и жизнь. В общении спокоен, дипломатичен, ценю честность.</p>
      <div style="display: flex; flex-wrap: wrap; gap: 0.6rem; margin: 1.2rem 0;">
        <span class="badge"><i class="fab fa-js"></i> Веб-разработка (JS, React — в процессе)</span>
        <span class="badge"><i class="fas fa-code"></i> Верстка, адаптивный дизайн</span>
        <span class="badge"><i class="fas fa-dumbbell"></i> Спорт: бег, тренажёрный зал</span>
        <span class="badge"><i class="fas fa-globe-asia"></i> Японская литература и культура</span>
        <span class="badge"><i class="fas fa-database"></i> Алгоритмы и структуры данных (осваиваю)</span>
      </div>
      <p>Открыт к коллаборациям, легко нахожу общий язык. Верю: дисциплина и долгосрочное планирование приведут меня к дому у реки, любимой семье и работе-удовольствию.</p>
    </div>
  </section>

  <!-- 7. Ближайшие задачи (16–18 лет) для программиста -->
  <section id="tasks">
    <h2 class="section-title"><i class="fas fa-tasks"></i> Ближайшие задачи (16–18 лет)</h2>
    <div class="card">
      <ul style="margin-left: 1.4rem; display: flex; flex-direction: column; gap: 0.6rem;">
        <li>📚 Сдать ЕГЭ на высокие баллы: профильная математика, информатика, русский язык</li>
        <li>🎓 Поступить в АлтГТУ им. И.И. Ползунова на бюджет</li>
        <li>💻 Углубить знания JavaScript: изучить async/await, fetch, DOM</li>
        <li>🌐 Сверстать 3–5 собственных пет-проектов (портфолио, ToDo-приложение и т.д.)</li>
        <li>🇷🇸 Начать учить сербский язык самостоятельно (разговорный минимум A1→A2)</li>
        <li>📖 Прочитать классику японской литературы (Мураками, Мисима) и технические книги по IT</li>
        <li>🖥️ Найти первых заказчиков на фрилансе (верстка лендингов)</li>
      </ul>
      <div style="margin-top: 1rem; background: var(--accent-soft); border-radius: 1rem; padding: 0.8rem;">
        <i class="fas fa-clock"></i> <strong>Таймер до поступления в АлтГТУ:</strong> 
        <span id="countdownToUni" style="font-weight: 700; color: var(--accent);">-- лет</span>
      </div>
    </div>
  </section>

  <!-- 8. Моя миссия (IT + свобода) -->
  <section>
    <h2 class="section-title"><i class="fas fa-rocket"></i> Моя миссия</h2>
    <div class="card" style="text-align: center;">
      <p style="font-size: 1.2rem; font-style: italic;">«Стать разработчиком высокого класса, работать удалённо из Европы, создать уютный дом и достичь финансовой независимости в 45 лет. Япония в книгах, Сербия как база, а код — мой главный инструмент»</p>
      <div style="margin-top: 1rem;"><i class="fas fa-check-circle" style="color: var(--accent);"></i> FIRE-стратегия · веб-разработка · японская философия</div>
    </div>
  </section>
</main>

<footer>
  <p>© 2026 KIRVISION · Кирилл, г. Заринск — Барнаул — Сербия · Code. Plan. Achieve.</p>
  <p style="margin-top: 0.3rem;"><i class="fas fa-map-marker-alt"></i> Алтайский край → мировое IT-комьюнити</p>
</footer>

<script>
  (function() {
    // Тёмная / светлая тема
    const themeToggleBtn = document.getElementById('themeToggle');
    const currentTheme = localStorage.getItem('theme');
    function updateThemeIcon(isDark) {
      if (themeToggleBtn) {
        const icon = themeToggleBtn.querySelector('i');
        const span = themeToggleBtn.querySelector('span');
        if (isDark) {
          icon.className = 'fas fa-sun';
          span.innerText = 'Светлая';
        } else {
          icon.className = 'fas fa-moon';
          span.innerText = 'Тёмная';
        }
      }
    }
    if (currentTheme === 'dark') {
      document.body.classList.add('dark');
      updateThemeIcon(true);
    } else if (currentTheme === 'light') {
      document.body.classList.remove('dark');
      updateThemeIcon(false);
    } else {
      if (window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
        document.body.classList.add('dark');
        updateThemeIcon(true);
        localStorage.setItem('theme', 'dark');
      } else {
        updateThemeIcon(false);
      }
    }
    if (themeToggleBtn) {
      themeToggleBtn.addEventListener('click', () => {
        const isDark = document.body.classList.toggle('dark');
        localStorage.setItem('theme', isDark ? 'dark' : 'light');
        updateThemeIcon(isDark);
      });
    }

    // Динамические даты (поступление 2028, окончание вуза 2032)
    const now = new Date();
    const currentYear = now.getFullYear();
    const entranceYear = 2028;
    const gradYear = entranceYear + 4;

    const badgeYearSpan = document.getElementById('dynamicYearBadge');
    if (badgeYearSpan) {
      badgeYearSpan.innerHTML = `<i class="fas fa-hourglass-half"></i> Поступление в АлтГТУ: ${entranceYear} год (бюджет, программирование)`;
    }

    const countdownSpan = document.getElementById('countdownToUni');
    if (countdownSpan) {
      let yearsLeft = entranceYear - currentYear;
      if (yearsLeft < 0) yearsLeft = 0;
      const declension = (n) => {
        if (n % 10 === 1 && n % 100 !== 11) return 'год';
        if ([2,3,4].includes(n % 10) && ![12,13,14].includes(n % 100)) return 'года';
        return 'лет';
      };
      countdownSpan.innerText = yearsLeft === 0 ? 'уже в этом году!' : `${yearsLeft} ${declension(yearsLeft)}`;
    }

    const relocationSpan = document.getElementById('relocationYearSpan');
    if (relocationSpan) {
      relocationSpan.innerText = `${gradYear}–${gradYear+2}`;
    }

    // анимация появления секций с intersection observer
    const sections = document.querySelectorAll('section');
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.08, rootMargin: "0px 0px -40px 0px" });
    sections.forEach(section => observer.observe(section));

    // дополнительная заметка о переезде (без воинской темы)
    const makeRelocationNote = () => {
      const targetReloc = 2032;
      let yearsToReloc = targetReloc - currentYear;
      if (yearsToReloc < 0) yearsToReloc = 0;
      const relocateSection = document.querySelector('#relocation .card');
      if (relocateSection && !document.querySelector('#relocation .relo-note')) {
        const note = document.createElement('div');
        note.className = 'relo-note';
        note.style.marginTop = '1rem';
        note.style.fontSize = '0.85rem';
        note.style.padding = '0.5rem';
        note.style.borderRadius = '1rem';
        note.style.backgroundColor = 'var(--accent-soft)';
        const yearsWord = (yearsToReloc === 1 ? 'год' : (yearsToReloc >=2 && yearsToReloc<=4 ? 'года' : 'лет'));
        note.innerHTML = `<i class="fas fa-hourglass-start"></i> До ориентировочного переезда в Сербию ≈ ${yearsToReloc} ${yearsWord}. Время развивать навыки JavaScript и учить сербский!`;
        relocateSection.appendChild(note);
      }
    };
    makeRelocationNote();
  })();
</script>
</body>
</html>
