<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>حسام رمضان - بورتفوليو</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=Cairo:wght@300;400;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --gold: #C9A84C;
    --gold-light: #E8C97A;
    --gold-dim: #8B6914;
    --black: #0A0A0A;
    --dark: #111111;
    --dark2: #1A1A1A;
    --dark3: #242424;
    --text: #E8E0D0;
    --text-muted: #8A8070;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Cairo', sans-serif;
    background: var(--black);
    color: var(--text);
    overflow-x: hidden;
  }

  /* ===== NAVBAR ===== */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.2rem 4rem;
    background: rgba(10,10,10,0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(201,168,76,0.15);
  }

  .logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.6rem;
    font-weight: 900;
    color: var(--gold);
    letter-spacing: 2px;
  }

  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a {
    color: var(--text-muted);
    text-decoration: none;
    font-size: 0.9rem;
    font-weight: 300;
    letter-spacing: 1px;
    transition: color 0.3s;
    position: relative;
  }
  .nav-links a::after {
    content: '';
    position: absolute;
    bottom: -4px; left: 0; right: 0;
    height: 1px;
    background: var(--gold);
    transform: scaleX(0);
    transition: transform 0.3s;
  }
  .nav-links a:hover { color: var(--gold); }
  .nav-links a:hover::after { transform: scaleX(1); }

  /* ===== HERO ===== */
  .hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 0 4rem;
    position: relative;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: -20%; right: -10%;
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(201,168,76,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-grid-line {
    position: absolute;
    top: 0; bottom: 0;
    width: 1px;
    background: rgba(201,168,76,0.06);
  }
  .hero-grid-line:nth-child(1) { left: 25%; }
  .hero-grid-line:nth-child(2) { left: 50%; }
  .hero-grid-line:nth-child(3) { left: 75%; }

  .hero-content { position: relative; z-index: 2; max-width: 700px; }

  .hero-tag {
    display: inline-block;
    font-size: 0.75rem;
    letter-spacing: 4px;
    color: var(--gold);
    text-transform: uppercase;
    margin-bottom: 1.5rem;
    opacity: 0;
    animation: fadeUp 0.8s 0.2s forwards;
  }

  .hero-name {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3rem, 7vw, 6rem);
    font-weight: 900;
    line-height: 1.05;
    margin-bottom: 1rem;
    opacity: 0;
    animation: fadeUp 0.8s 0.4s forwards;
  }

  .hero-name span {
    display: block;
    background: linear-gradient(135deg, var(--gold-light), var(--gold), var(--gold-dim));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-title {
    font-size: 1.1rem;
    color: var(--text-muted);
    font-weight: 300;
    margin-bottom: 2.5rem;
    opacity: 0;
    animation: fadeUp 0.8s 0.6s forwards;
  }

  .hero-btns {
    display: flex;
    gap: 1rem;
    opacity: 0;
    animation: fadeUp 0.8s 0.8s forwards;
  }

  .btn-primary {
    padding: 0.9rem 2.5rem;
    background: var(--gold);
    color: var(--black);
    border: none;
    font-family: 'Cairo', sans-serif;
    font-size: 0.9rem;
    font-weight: 600;
    cursor: pointer;
    letter-spacing: 1px;
    transition: all 0.3s;
    text-decoration: none;
  }
  .btn-primary:hover {
    background: var(--gold-light);
    transform: translateY(-2px);
  }

  .btn-outline {
    padding: 0.9rem 2.5rem;
    background: transparent;
    color: var(--gold);
    border: 1px solid var(--gold);
    font-family: 'Cairo', sans-serif;
    font-size: 0.9rem;
    font-weight: 400;
    cursor: pointer;
    letter-spacing: 1px;
    transition: all 0.3s;
    text-decoration: none;
  }
  .btn-outline:hover {
    background: rgba(201,168,76,0.08);
    transform: translateY(-2px);
  }

  .hero-number {
    position: absolute;
    left: 4rem; bottom: 3rem;
    font-family: 'Playfair Display', serif;
    font-size: 8rem;
    font-weight: 900;
    color: rgba(201,168,76,0.04);
    pointer-events: none;
    z-index: 1;
    line-height: 1;
  }

  /* ===== SECTION BASE ===== */
  section { padding: 7rem 4rem; }
  .section-label {
    font-size: 0.7rem;
    letter-spacing: 5px;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.8rem;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 4vw, 3rem);
    font-weight: 700;
    margin-bottom: 3rem;
    color: var(--text);
  }
  .section-title em {
    font-style: italic;
    color: var(--gold);
  }

  /* ===== DIVIDER ===== */
  .gold-line {
    width: 60px;
    height: 1px;
    background: var(--gold);
    margin-bottom: 1.5rem;
  }

  /* ===== ABOUT ===== */
  .about { background: var(--dark); }
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1.4fr;
    gap: 5rem;
    align-items: center;
  }
  .about-image-wrap {
    position: relative;
  }
  .about-image {
    width: 100%;
    aspect-ratio: 3/4;
    object-fit: cover;
    display: block;
  }
  .about-image-placeholder {
    width: 100%;
    aspect-ratio: 3/4;
    background: var(--dark3);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 5rem;
    position: relative;
  }
  .about-image-border {
    position: absolute;
    top: 16px; left: 16px; right: -16px; bottom: -16px;
    border: 1px solid var(--gold);
    z-index: -1;
  }
  .about-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
    margin-top: 2.5rem;
  }
  .stat-card {
    background: var(--dark2);
    border: 1px solid rgba(201,168,76,0.12);
    padding: 1.5rem;
  }
  .stat-number {
    font-family: 'Playfair Display', serif;
    font-size: 2.5rem;
    font-weight: 900;
    color: var(--gold);
    display: block;
  }
  .stat-label {
    font-size: 0.8rem;
    color: var(--text-muted);
    letter-spacing: 1px;
  }

  /* ===== SKILLS ===== */
  .skills { background: var(--black); }
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
  }
  .skill-card {
    background: var(--dark2);
    border: 1px solid rgba(201,168,76,0.1);
    padding: 2rem;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }
  .skill-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--gold), transparent);
    transform: scaleX(0);
    transform-origin: right;
    transition: transform 0.4s;
  }
  .skill-card:hover::before { transform: scaleX(1); transform-origin: left; }
  .skill-card:hover { border-color: rgba(201,168,76,0.3); transform: translateY(-4px); }

  .skill-icon {
    font-size: 2rem;
    margin-bottom: 1rem;
    display: block;
  }
  .skill-name {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem;
    font-weight: 700;
    margin-bottom: 0.5rem;
    color: var(--text);
  }
  .skill-desc { font-size: 0.85rem; color: var(--text-muted); line-height: 1.7; }
  .skill-bar-wrap { margin-top: 1.2rem; }
  .skill-bar-label {
    display: flex;
    justify-content: space-between;
    font-size: 0.75rem;
    color: var(--text-muted);
    margin-bottom: 0.4rem;
  }
  .skill-bar-bg {
    height: 2px;
    background: rgba(255,255,255,0.05);
    position: relative;
  }
  .skill-bar-fill {
    position: absolute;
    top: 0; left: 0; bottom: 0;
    background: linear-gradient(90deg, var(--gold-dim), var(--gold));
  }

  /* ===== PROJECTS ===== */
  .projects { background: var(--dark); }
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 1.5rem;
  }
  .project-card {
    background: var(--dark2);
    border: 1px solid rgba(201,168,76,0.08);
    overflow: hidden;
    transition: all 0.3s;
    cursor: pointer;
  }
  .project-card:hover { border-color: rgba(201,168,76,0.3); transform: translateY(-6px); }
  .project-img {
    width: 100%;
    height: 200px;
    background: var(--dark3);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 3.5rem;
    position: relative;
    overflow: hidden;
  }
  .project-img::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(to bottom, transparent 60%, var(--dark2));
  }
  .project-body { padding: 1.5rem; }
  .project-tag {
    font-size: 0.65rem;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 0.6rem;
  }
  .project-name {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem;
    font-weight: 700;
    margin-bottom: 0.6rem;
  }
  .project-desc { font-size: 0.85rem; color: var(--text-muted); line-height: 1.7; }
  .project-link {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    margin-top: 1rem;
    font-size: 0.8rem;
    color: var(--gold);
    text-decoration: none;
    letter-spacing: 1px;
    transition: gap 0.3s;
  }
  .project-link:hover { gap: 0.8rem; }

  /* ===== CONTACT ===== */
  .contact { background: var(--black); }
  .contact-inner {
    max-width: 700px;
    margin: 0 auto;
    text-align: center;
  }
  .contact-form {
    margin-top: 3rem;
    display: flex;
    flex-direction: column;
    gap: 1.2rem;
  }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1.2rem; }
  .form-input {
    width: 100%;
    padding: 1rem 1.2rem;
    background: var(--dark2);
    border: 1px solid rgba(201,168,76,0.15);
    color: var(--text);
    font-family: 'Cairo', sans-serif;
    font-size: 0.9rem;
    outline: none;
    transition: border-color 0.3s;
  }
  .form-input:focus { border-color: var(--gold); }
  .form-input::placeholder { color: var(--text-muted); }
  textarea.form-input { resize: vertical; min-height: 140px; }
  .form-submit {
    width: 100%;
    padding: 1.1rem;
    background: var(--gold);
    color: var(--black);
    border: none;
    font-family: 'Cairo', sans-serif;
    font-size: 1rem;
    font-weight: 700;
    cursor: pointer;
    letter-spacing: 2px;
    transition: all 0.3s;
  }
  .form-submit:hover { background: var(--gold-light); transform: translateY(-2px); }

  /* ===== FOOTER ===== */
  footer {
    background: var(--dark);
    border-top: 1px solid rgba(201,168,76,0.1);
    padding: 2.5rem 4rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .footer-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem;
    color: var(--gold);
    font-weight: 700;
  }
  .footer-copy { font-size: 0.8rem; color: var(--text-muted); }
  .social-links { display: flex; gap: 1.2rem; }
  .social-link {
    width: 36px; height: 36px;
    border: 1px solid rgba(201,168,76,0.2);
    display: flex; align-items: center; justify-content: center;
    color: var(--text-muted);
    text-decoration: none;
    font-size: 0.8rem;
    transition: all 0.3s;
  }
  .social-link:hover { border-color: var(--gold); color: var(--gold); }

  /* ===== ANIMATIONS ===== */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.7s, transform 0.7s;
  }
  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* ===== RESPONSIVE ===== */
  @media (max-width: 768px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    section { padding: 5rem 1.5rem; }
    .hero { padding: 0 1.5rem; }
    .hero-number { display: none; }
    .about-grid { grid-template-columns: 1fr; gap: 2.5rem; }
    .form-row { grid-template-columns: 1fr; }
    footer { flex-direction: column; gap: 1rem; text-align: center; }
  }
</style>
</head>
<body>

<!-- NAVBAR -->
<nav>
  <div class="logo">H.R</div>
  <ul class="nav-links">
    <li><a href="#about">من أنا</a></li>
    <li><a href="#skills">مهاراتي</a></li>
    <li><a href="#projects">أعمالي</a></li>
    <li><a href="#contact">تواصل</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-grid-line"></div>
  <div class="hero-grid-line"></div>
  <div class="hero-grid-line"></div>

  <div class="hero-content">
    <span class="hero-tag">✦ مرحباً بكم في بورتفوليو</span>
    <h1 class="hero-name">
      حسام رمضان<br>
      <span>مبدع رقمي</span>
    </h1>
    <p class="hero-title">مصمم واجهات · مطور ويب · صانع تجارب رقمية لا تُنسى</p>
    <div class="hero-btns">
      <a href="#projects" class="btn-primary">اكتشف أعمالي</a>
      <a href="#contact" class="btn-outline">تواصل معي</a>
    </div>
  </div>
  <div class="hero-number">01</div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="about-grid">
    <div class="about-image-wrap reveal">
      <div class="about-image-placeholder">
        👤
        <div class="about-image-border"></div>
      </div>
    </div>
    <div class="reveal">
      <p class="section-label">✦ من أنا</p>
      <div class="gold-line"></div>
      <h2 class="section-title">أبني <em>تجارب</em><br>رقمية متميزة</h2>
      <p style="color: var(--text-muted); line-height: 1.9; margin-bottom: 1.5rem;">
        مصمم ومطور متخصص في صناعة واجهات مستخدم مبهرة ومواقع ويب عالية الأداء.
        أؤمن أن التصميم الجيد يجمع بين الجمال والوظيفة ليخلق تجربة لا تُنسى.
      </p>
      <p style="color: var(--text-muted); line-height: 1.9;">
        مع سنوات من الخبرة في مجال التطوير الرقمي، أسعى دائماً لتقديم أفضل
        الحلول الإبداعية التي تلبي احتياجات العملاء وتتخطى توقعاتهم.
      </p>
      <div class="about-stats">
        <div class="stat-card">
          <span class="stat-number">+50</span>
          <span class="stat-label">مشروع منجز</span>
        </div>
        <div class="stat-card">
          <span class="stat-number">+30</span>
          <span class="stat-label">عميل سعيد</span>
        </div>
        <div class="stat-card">
          <span class="stat-number">5</span>
          <span class="stat-label">سنوات خبرة</span>
        </div>
        <div class="stat-card">
          <span class="stat-number">100%</span>
          <span class="stat-label">التزام بالجودة</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section class="skills" id="skills">
  <p class="section-label reveal">✦ مهاراتي</p>
  <div class="gold-line reveal"></div>
  <h2 class="section-title reveal">ما الذي <em>أتقنه</em></h2>
  <div class="skills-grid">
    <div class="skill-card reveal">
      <span class="skill-icon">🎨</span>
      <p class="skill-name">تصميم UI/UX</p>
      <p class="skill-desc">أصمم واجهات جذابة وسهلة الاستخدام تضع تجربة المستخدم في المقدمة.</p>
      <div class="skill-bar-wrap">
        <div class="skill-bar-label"><span>الإتقان</span><span>95%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:95%"></div></div>
      </div>
    </div>
    <div class="skill-card reveal">
      <span class="skill-icon">💻</span>
      <p class="skill-name">تطوير الواجهة الأمامية</p>
      <p class="skill-desc">HTML, CSS, JavaScript, React — كل ما يلزم لبناء مواقع احترافية.</p>
      <div class="skill-bar-wrap">
        <div class="skill-bar-label"><span>الإتقان</span><span>90%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:90%"></div></div>
      </div>
    </div>
    <div class="skill-card reveal">
      <span class="skill-icon">⚡</span>
      <p class="skill-name">تطوير الواجهة الخلفية</p>
      <p class="skill-desc">Node.js, Python, قواعد بيانات — أبني أنظمة قوية وموثوقة.</p>
      <div class="skill-bar-wrap">
        <div class="skill-bar-label"><span>الإتقان</span><span>80%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar-fill" style="width:80%"></div></div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section class="projects" id="projects">
  <p class="section-label reveal">✦ أعمالي</p>
  <div class="gold-line reveal"></div>
  <h2 class="section-title reveal">أحدث <em>مشاريعي</em></h2>
  <div class="projects-grid">
    <div class="project-card reveal">
      <div class="project-img">🛒</div>
      <div class="project-body">
        <p class="project-tag">تجارة إلكترونية</p>
        <h3 class="project-name">متجر إلكتروني متكامل</h3>
        <p class="project-desc">منصة تسوق متكاملة مع نظام دفع آمن وواجهة مستخدم سلسة وجذابة.</p>
        <a href="#" class="project-link">عرض المشروع →</a>
      </div>
    </div>
    <div class="project-card reveal">
      <div class="project-img">📱</div>
      <div class="project-body">
        <p class="project-tag">تطبيق موبايل</p>
        <h3 class="project-name">تطبيق إدارة المهام</h3>
        <p class="project-desc">تطبيق ذكي لتنظيم المهام اليومية مع إشعارات ذكية وتقارير مفصلة.</p>
        <a href="#" class="project-link">عرض المشروع →</a>
      </div>
    </div>
    <div class="project-card reveal">
      <div class="project-img">🎯</div>
      <div class="project-body">
        <p class="project-tag">لوحة تحكم</p>
        <h3 class="project-name">داشبورد تحليل البيانات</h3>
        <p class="project-desc">لوحة تحكم تفاعلية لعرض وتحليل البيانات بأسلوب بصري احترافي.</p>
        <a href="#" class="project-link">عرض المشروع →</a>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
  <div class="contact-inner">
    <p class="section-label reveal">✦ تواصل معي</p>
    <div class="gold-line reveal" style="margin: 0 auto 1.5rem;"></div>
    <h2 class="section-title reveal">لنبدأ <em>معاً</em></h2>
    <p class="reveal" style="color: var(--text-muted); line-height: 1.8;">
      هل لديك مشروع في ذهنك؟ أنا هنا للاستماع وتحويل أفكارك إلى واقع رقمي مبهر.
    </p>
    <form class="contact-form reveal">
      <div class="form-row">
        <input type="text" class="form-input" placeholder="اسمك الكريم">
        <input type="email" class="form-input" placeholder="بريدك الإلكتروني">
      </div>
      <input type="text" class="form-input" placeholder="موضوع الرسالة">
      <textarea class="form-input" placeholder="اكتب رسالتك هنا..."></textarea>
      <button type="submit" class="form-submit">أرسل الرسالة ✦</button>
    </form>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">H.R</div>
  <p class="footer-copy">© 2026 — جميع الحقوق محفوظة</p>
  <div class="social-links">
    <a href="#" class="social-link">in</a>
    <a href="#" class="social-link">𝕏</a>
    <a href="#" class="social-link">gh</a>
  </div>
</footer>

<script>
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 100);
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

  document.querySelector('.form-submit').addEventListener('click', (e) => {
    e.preventDefault();
    e.target.textContent = 'تم الإرسال بنجاح ✓';
    e.target.style.background = '#4CAF50';
    setTimeout(() => {
      e.target.textContent = 'أرسل الرسالة ✦';
      e.target.style.background = '';
    }, 3000);
  });
</script>
</body>
</html>
