<!doctype html>
<html lang="ar" dir="rtl">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>كابوس - الموقع الرسمي</title>
<style>
  :root {
    --bg1: #080006;
    --bg2: #120016;
    --purple: #6b21a8;
    --glow: #b84dff;
    --muted: #a98bd6;
    --text-light: #efe7ff;
  }
  * {
    box-sizing: border-box;
  }
  html, body {
    height: 100%;
    margin: 0;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    direction: rtl;
    background: linear-gradient(135deg, var(--bg1), var(--bg2));
    color: var(--text-light);
    overflow-x: hidden;
  }
  .app-shell {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
  }
  .decor {
    position: fixed;
    inset: 0;
    pointer-events: none;
    overflow: hidden;
  }
  .orb {
    position: absolute;
    border-radius: 50%;
    filter: blur(40px);
    opacity: 0.16;
    transform: translate3d(0,0,0);
  }
  .orb.a {
    width: 520px;
    height: 520px;
    left: -120px;
    top: -100px;
    background: radial-gradient(circle at 30% 30%, var(--glow), transparent 40%);
    animation: floatA 14s ease-in-out infinite;
  }
  .orb.b {
    width: 420px;
    height: 420px;
    right: -100px;
    bottom: -60px;
    background: radial-gradient(circle at 70% 70%, var(--purple), transparent 40%);
    animation: floatB 18s ease-in-out infinite;
  }
  @keyframes floatA {
    0% { transform: translateY(0) translateX(0); }
    50% { transform: translateY(-40px) translateX(30px); }
    100% { transform: translateY(0) translateX(0); }
  }
  @keyframes floatB {
    0% { transform: translateY(0) translateX(0); }
    50% { transform: translateY(40px) translateX(-30px); }
    100% { transform: translateY(0) translateX(0); }
  }
  .header {
    position: relative;
    z-index: 10;
    padding: 8px 0;
    background: linear-gradient(180deg, rgba(0,0,0,0.25), transparent);
    backdrop-filter: blur(4px);
    border-bottom: 1px solid rgba(107,33,168,0.12);
  }
  .header-inner {
    max-width: 1100px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 16px;
    padding: 0 16px;
  }
  .brand {
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .logo {
    width: 52px;
    height: 52px;
    border-radius: 10px;
    background: linear-gradient(135deg, var(--purple), #3a0260);
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    color: #fff;
    font-size: 18px;
    user-select: none;
    cursor: pointer;
  }
  .title {
    font-size: 20px;
    font-weight: 700;
    color: var(--glow);
  }
  .nav {
    display: flex;
    gap: 14px;
  }
  .nav a {
    color: var(--muted);
    text-decoration: none;
    padding: 8px 12px;
    border-radius: 8px;
    transition: all 0.18s;
    user-select: none;
  }
  .nav a.active {
    background: rgba(107,33,168,0.12);
    color: var(--glow);
  }
  .container {
    max-width: 1100px;
    margin: 32px auto;
    padding: 0 20px;
    flex: 1;
    z-index: 10;
  }
  .hero {
    min-height: 56vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    flex-direction: column;
    padding: 20px;
  }
  .quote {
    font-size: 28px;
    line-height: 1.4;
    max-width: 900px;
    color: rgba(184, 77, 255, 0.95);
    text-shadow: 0 10px 40px rgba(107,33,168,0.12);
  }
  .cta {
    margin-top: 22px;
  }
  .btn {
    display: inline-block;
    padding: 10px 18px;
    border-radius: 999px;
    background: linear-gradient(90deg, var(--purple), #8b3be6);
    color: #fff;
    font-weight: 700;
    text-decoration: none;
    box-shadow: 0 6px 22px rgba(107,33,168,0.18);
    user-select: none;
    cursor: pointer;
  }
  .section {
    background: linear-gradient(180deg, rgba(0,0,0,0.35), rgba(0,0,0,0.25));
    padding: 28px;
    border-radius: 12px;
    margin-bottom: 24px;
  }
  .grid {
    display: grid;
    gap: 16px;
  }
  @media (min-width: 768px) {
    .grid.cols-3 {
      grid-template-columns: repeat(3, 1fr);
    }
    .hero {
      min-height: 60vh;
    }
    .quote {
      font-size: 40px;
    }
  }
  .card {
    background: rgba(0,0,0,0.45);
    padding: 18px;
    border-radius: 12px;
    border: 1px solid rgba(107,33,168,0.08);
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  .card:hover {
    background: rgba(107,33,168,0.3);
  }
  .form-control {
    width: 100%;
    padding: 10px;
    border-radius: 8px;
    background: #0e0b10;
    border: 1px solid rgba(107,33,168,0.12);
    color: var(--text-light);
    resize: vertical;
    font-family: inherit;
  }
  .footer {
    padding: 20px;
    text-align: center;
    color: #bfa5ed;
    border-top: 1px solid rgba(107,33,168,0.06);
    user-select: none;
  }
  .small {
    font-size: 13px;
    color: rgba(255,255,255,0.65);
  }
  .link {
    color: var(--glow);
    cursor: pointer;
    user-select: none;
  }
  .work-title {
    font-weight: 700;
    color: #fff;
    margin-bottom: 8px;
    font-size: 18px;
  }
  .work-desc {
    color: var(--muted);
    white-space: pre-wrap;
  }
  .icon-btn {
    background: transparent;
    border: 1px solid rgba(255,255,255,0.04);
    padding: 8px;
    border-radius: 8px;
    color: var(--muted);
    cursor: pointer;
    user-select: none;
  }
  .notice {
    padding: 8px 12px;
    border-radius: 8px;
    background: rgba(107,33,168,0.06);
    color: var(--muted);
    display: inline-block;
    user-select: none;
  }
  /* نصوص مختلفة لكل قصيدة */
  .style1 { font-family: 'Cairo', sans-serif; font-size: 18px; line-height: 1.6; }
  .style2 { font-family: 'Amiri', serif; font-size: 20px; font-style: italic; line-height: 1.5; }
  .style3 { font-family: 'Almarai', sans-serif; font-size: 17px; font-weight: 600; line-height: 1.7; }
  /* أزرار لوحة التحكم أسفل الصفحة */
  #admin-buttons {
    position: sticky;
    bottom: 0;
    background: linear-gradient(180deg, rgba(8,0,6,0.95), rgba(18,0,22,0.95));
    padding: 16px 0;
    display: flex;
    justify-content: flex-start;
    gap: 10px;
    border-top: 1px solid rgba(107,33,168,0.15);
    z-index: 20;
  }

  /* زر القائمة (الهاتف) */
  .menu-toggle {
    display: none;
    background: rgba(107,33,168,0.2);
    color: var(--text-light);
    border: none;
    border-radius: 8px;
    padding: 8px 12px;
    font-size: 20px;
    cursor: pointer;
    margin-left: 12px;
  }

  /* تحسين التجاوب للشاشات الصغيرة */
  @media (max-width: 767px) {
    .header-inner {
      flex-wrap: wrap;
      gap: 12px;
      padding: 16px;
    }

    .menu-toggle {
      display: block;
      order: 1;
      margin-right: auto;
    }

    .brand {
      order: 2;
      flex-grow: 1;
    }

    .nav {
      display: none;
      order: 3;
      width: 100%;
      flex-direction: column;
      gap: 8px;
      padding-top: 12px;
      border-top: 1px solid rgba(107,33,168,0.2);
    }

    body.menu-open .nav {
      display: flex;
    }

    .nav a {
      padding: 10px;
      text-align: right;
    }

    .hero {
      min-height: 40vh;
      padding: 20px 12px;
    }

    .quote {
      font-size: 22px;
    }

    .grid.cols-3 {
      grid-template-columns: 1fr;
    }

    .section {
      padding: 18px;
    }

    .logo {
      width: 44px;
      height: 44px;
      font-size: 16px;
      border-radius: 8px;
    }

    .title {
      font-size: 18px;
    }
  }
</style>
</head>
<body>
<div class="app-shell">
  <div class="decor">
    <div class="orb a"></div>
    <div class="orb b"></div>
  </div>
  <header class="header">
    <div class="header-inner">
      <button class="menu-toggle" onclick="document.body.classList.toggle('menu-open')">☰</button>
      <div class="brand">
        <div class="logo" title="لوحة التحكم">ك</div>
        <div>
          <div class="title">كابوس</div>
          <div class="small">شاعر - كاتب</div>
        </div>
      </div>
      <nav class="nav" id="main-nav">
        <a href="#/" data-route="/" class="active">الرئيسية</a>
        <a href="#/about" data-route="/about">عن كابوس</a>
        <a href="#/works" data-route="/works">أعمالي</a>
        <a href="#/contact" data-route="/contact">اتصل بي</a>
        <a href="#/admin" data-route="/admin" style="display:none;">لوحة التحكم</a>
      </nav>
    </div>
  </header>
  <main class="container" id="app"></main>
  <footer class="footer">© <span id="year"></span> كابوس - جميع الحقوق محفوظة</footer>
</div>

<script>
  const STORAGE_KEY = 'kabous_site_data_v2';
  const DEFAULT_DATA = {
    quote: `"نحيا نحن إذا ماتت الحياة فينا\nنحيا لنكتب للأخرى الدواوينَ"`,
    about: 'كابوس هو شاعر وكاتب يعكس الواقع ويتأمل المجتمع من خلال كلمات تنبض بالصدق والإحساس.',
    works: [
      { id: 1, title: 'قصيدة البداية', desc: 'هذه هي قصيدتي الأولى\nأحب أن أكتب الشعر\nوهذا السطر الثالث\nوهذا السطر الرابع', style: 'style1' },
      { id: 2, title: 'قصيدة البنفسج', desc: 'في ظلال البنفسج\nتنساب الكلمات\nهدوء النفس في البوح\nوالشوق للنقاء', style: 'style2' }
    ],
    contact: 'يمكنك التواصل معي عبر البريد الإلكتروني أو الهاتف...'
  };

  function loadData() {
    try {
      const raw = localStorage.getItem(STORAGE_KEY);
      if (!raw) return DEFAULT_DATA;
      const parsed = JSON.parse(raw);
      return Object.assign({}, DEFAULT_DATA, parsed);
    } catch {
      return DEFAULT_DATA;
    }
  }

  function saveData(data) {
    try {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(data));
    } catch {
      alert('فشل الحفظ المحلي');
    }
  }

  function el(sel) { return document.querySelector(sel); }
  function els(sel) { return Array.from(document.querySelectorAll(sel)); }

  function setActiveNav() {
    const route = (location.hash || '#/').slice(1) || '/';
    els('#main-nav a').forEach(a => {
      a.classList.toggle('active', a.getAttribute('data-route') === route);
    });
  }

  function escapeHtml(s) {
    if (!s) return '';
    return String(s)
      .replaceAll('&', '&amp;')
      .replaceAll('<', '&lt;')
      .replaceAll('>', '&gt;')
      .replaceAll('"', '&quot;')
      .replaceAll("'", '&#39;')
      .replaceAll('\n', '<br/>');
  }

  function shortDesc(text) {
    const maxLength = 100;
    if (text.length <= maxLength) return text;
    return text.substring(0, maxLength) + '...';
  }

  function render() {
    setActiveNav();
    const route = (location.hash || '#/').slice(1) || '/';
    if (route.startsWith('/works/')) {
      const id = Number(route.split('/')[2]);
      return renderWorkDetail(id);
    }
    switch (route) {
      case '/admin': return renderAdmin();
      case '/about': return renderAbout();
      case '/works': return renderWorks();
      case '/contact': return renderContact();
      default: return renderHome();
    }
  }

  function renderHome() {
    const data = loadData();
    el('#app').innerHTML = `
      <section class="hero">
        <div class="quote">${escapeHtml(data.quote)}</div>
        <div class="cta"><a class="btn" href="#/works">استكشف أعمالي</a></div>
      </section>
    `;
  }

  function renderAbout() {
    const data = loadData();
    el('#app').innerHTML = `
      <section class="section">
        <h2>عن كابوس</h2>
        <p class="small">${escapeHtml(data.about)}</p>
      </section>
    `;
  }

  function renderWorks() {
    const data = loadData();
    const app = el('#app');
    if (data.works.length === 0) {
      app.innerHTML = `<section class="section"><h2>أعمالي</h2><p class="small">لا توجد قصائد بعد.</p></section>`;
      return;
    }
    let worksHtml = data.works.map(w => `
      <div class="card" onclick="location.hash='#/works/${w.id}'" title="اضغط لقراءة النص الكامل">
        <div class="work-title">${escapeHtml(w.title)}</div>
        <div class="work-desc ${w.style}" style="white-space: pre-wrap;">${escapeHtml(shortDesc(w.desc))}</div>
      </div>
    `).join('');
    app.innerHTML = `
      <section class="section">
        <h2>أعمالي</h2>
        <div class="grid cols-3">${worksHtml}</div>
      </section>
    `;
  }

  function renderWorkDetail(id) {
    const data = loadData();
    const poem = data.works.find(w => w.id === id);
    const app = el('#app');
    if (!poem) {
      app.innerHTML = `<section class="section"><p class="small">القصيدة غير موجودة.</p></section>`;
      return;
    }
    app.innerHTML = `
      <section class="section">
        <h2>${escapeHtml(poem.title)}</h2>
        <div class="${poem.style}" style="white-space: pre-wrap; margin-top: 16px;">${escapeHtml(poem.desc)}</div>
        <div style="margin-top: 20px;">
          <a href="#/works" class="btn">عودة لأعمالي</a>
        </div>
      </section>
    `;
  }

  function renderContact() {
    const data = loadData();
    el('#app').innerHTML = `
      <section class="section">
        <h2>اتصل بي</h2>
        <p class="small">${escapeHtml(data.contact)}</p>
        <form action="https://formspree.io/f/mldladno" method="POST">
          <input class="form-control" name="name" placeholder="الاسم" required />
          <input class="form-control" name="email" placeholder="البريد الإلكتروني" type="email" required style="margin-top:8px" />
          <textarea class="form-control" name="message" rows="4" placeholder="رسالتك" required style="margin-top:8px"></textarea>
          <div style="margin-top:10px"><button class="btn" type="submit">إرسال</button></div>
        </form>
      </section>
    `;
  }

  function renderAdmin() {
    const data = loadData();
    const app = el('#app');
    const logged = sessionStorage.getItem('kabous_admin') === '1';

    if (!logged) {
      app.innerHTML = `
        <section class="section">
          <h2>لوحة التحكم - تسجيل الدخول</h2>
          <form id="login-form" onsubmit="return false;">
            <input id="pw" class="form-control" type="password" placeholder="كلمة المرور" required autocomplete="off" />
            <div style="margin-top:12px;">
              <button class="btn" type="submit">تسجيل الدخول</button>
            </div>
            <div id="login-error" class="small" style="color:#e05555; margin-top: 8px;"></div>
          </form>
        </section>
      `;
      document.getElementById('login-form').onsubmit = () => {
        const pw = el('#pw').value.trim();
        if (pw === 'kabous2025') { // غير كلمة السر هنا حسب رغبتك
          sessionStorage.setItem('kabous_admin', '1');
          renderAdmin();
        } else {
          el('#login-error').textContent = 'كلمة المرور خاطئة!';
        }
        return false;
      };
      return;
    }

    // لوحة التحكم: إضافة، تعديل، حذف أعمال، اقتباس
    let worksHtml = data.works.map(w => `
      <div class="card" style="cursor: default;">
        <input class="form-control" data-id="${w.id}" data-type="title" value="${w.title}" style="margin-bottom: 6px;" />
        <textarea class="form-control" data-id="${w.id}" data-type="desc" rows="5">${w.desc}</textarea>
        <label>نمط النص:
          <select class="form-control" data-id="${w.id}" data-type="style" style="margin-top:6px;">
            <option value="style1" ${w.style==='style1'?'selected':''}>النمط 1 (عادي)</option>
            <option value="style2" ${w.style==='style2'?'selected':''}>النمط 2 (شعري)</option>
            <option value="style3" ${w.style==='style3'?'selected':''}>النمط 3 (ثقيل)</option>
          </select>
        </label>
        <button class="btn" data-action="delete" data-id="${w.id}" style="margin-top:10px; background:#b84141;">حذف القصيدة</button>
      </div>
    `).join('');

    app.innerHTML = `
      <section class="section">
        <h2>لوحة التحكم - إدارة القصائد</h2>
        <div>${worksHtml || '<p>لا توجد قصائد بعد.</p>'}</div>
        <hr style="margin: 24px 0; border-color: rgba(107,33,168,0.15);" />
        <h3>إضافة قصيدة جديدة</h3>
        <form id="add-form" onsubmit="return false;">
          <input class="form-control" id="new-title" placeholder="عنوان القصيدة" required />
          <textarea class="form-control" id="new-desc" rows="6" placeholder="نص القصيدة" required style="margin-top:8px;"></textarea>
          <label>نمط النص:
            <select class="form-control" id="new-style" style="margin-top:6px;">
              <option value="style1">النمط 1 (عادي)</option>
              <option value="style2">النمط 2 (شعري)</option>
              <option value="style3">النمط 3 (ثقيل)</option>
            </select>
          </label>
          <div style="margin-top:10px;">
            <button class="btn" type="submit">إضافة القصيدة</button>
          </div>
        </form>
        <hr style="margin: 24px 0; border-color: rgba(107,33,168,0.15);" />
        <h3>تعديل الاقتباس الرئيسي</h3>
        <textarea class="form-control" id="quote-edit" rows="4">${data.quote}</textarea>
        <button class="btn" id="save-quote" style="margin-top:10px;">حفظ الاقتباس</button>
        <hr style="margin: 24px 0; border-color: rgba(107,33,168,0.15);" />
        <button class="btn" id="logout" style="background:#b84141;">تسجيل الخروج</button>
      </section>
    `;

    // إضافة الحدث لحفظ التعديلات الحية
    els('input[data-type],textarea[data-type],select[data-type]').forEach(elem => {
      elem.addEventListener('input', (e) => {
        const id = Number(e.target.dataset.id);
        const type = e.target.dataset.type;
        let works = data.works.slice();
        const idx = works.findIndex(w => w.id === id);
        if (idx === -1) return;
        if (type === 'title') {
          works[idx].title = e.target.value;
        } else if (type === 'desc') {
          works[idx].desc = e.target.value;
        } else if (type === 'style') {
          works[idx].style = e.target.value;
        }
        data.works = works;
        saveData(data);
      });
    });

    // حذف قصيدة
    els('button[data-action="delete"]').forEach(btn => {
      btn.addEventListener('click', (e) => {
        const id = Number(e.target.dataset.id);
        if (!confirm('هل أنت متأكد من حذف هذه القصيدة؟')) return;
        data.works = data.works.filter(w => w.id !== id);
        saveData(data);
        renderAdmin();
      });
    });

    // إضافة قصيدة جديدة
    el('form#add-form').onsubmit = () => {
      const title = el('#new-title').value.trim();
      const desc = el('#new-desc').value.trim();
      const style = el('#new-style').value;
      if (!title || !desc) {
        alert('يرجى ملء جميع الحقول');
        return false;
      }
      const newId = data.works.length ? Math.max(...data.works.map(w => w.id)) + 1 : 1;
      data.works.push({ id: newId, title, desc, style });
      saveData(data);
      el('#new-title').value = '';
      el('#new-desc').value = '';
      el('#new-style').value = 'style1';
      alert('تمت إضافة القصيدة');
      renderAdmin();
      return false;
    };

    // حفظ الاقتباس
    el('#save-quote').onclick = () => {
      const newQuote = el('#quote-edit').value.trim();
      if (!newQuote) {
        alert('لا يمكن ترك الاقتباس فارغاً');
        return;
      }
      data.quote = newQuote;
      saveData(data);
      alert('تم حفظ الاقتباس');
      renderAdmin();
    };

    // تسجيل الخروج
    el('#logout').onclick = () => {
      sessionStorage.removeItem('kabous_admin');
      render();
    };
  }

  window.addEventListener('hashchange', render);
  window.addEventListener('load', () => {
    document.getElementById('year').textContent = new Date().getFullYear();
    render();
  });
</script>
</body>
</html>
