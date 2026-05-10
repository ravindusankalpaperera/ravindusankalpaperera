<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GitHub README Preview – Ravindu Sankalpa</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Sora:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0d1117;
    --surface: #161b22;
    --border: #30363d;
    --teal: #2dd4bf;
    --teal-dim: #14b8a6;
    --white: #e6edf3;
    --muted: #8b949e;
    --gold: #f0a500;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--white);
    font-family: 'Sora', sans-serif;
    min-height: 100vh;
    padding: 40px 20px;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
  }

  /* Editor toolbar */
  .toolbar {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px 12px 0 0;
    padding: 12px 20px;
    display: flex;
    align-items: center;
    gap: 12px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--muted);
  }
  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot.red { background: #ff5f57; }
  .dot.yellow { background: #febc2e; }
  .dot.green { background: #28c840; }
  .filename { margin-left: 8px; color: var(--teal); }

  .copy-btn {
    margin-left: auto;
    background: var(--teal);
    color: #0d1117;
    border: none;
    border-radius: 6px;
    padding: 6px 14px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 700;
    cursor: pointer;
    transition: background 0.2s;
  }
  .copy-btn:hover { background: var(--teal-dim); }

  /* README card */
  .readme {
    background: var(--surface);
    border: 1px solid var(--border);
    border-top: none;
    border-radius: 0 0 12px 12px;
    padding: 48px 52px;
    animation: fadeIn 0.6s ease;
  }

  @keyframes fadeIn { from { opacity: 0; transform: translateY(16px); } to { opacity: 1; transform: translateY(0); } }

  /* Header banner */
  .header-banner {
    text-align: center;
    padding-bottom: 32px;
    border-bottom: 1px solid var(--border);
    margin-bottom: 36px;
  }

  .wave { font-size: 42px; display: block; margin-bottom: 12px; animation: wave 2.5s ease-in-out infinite; }
  @keyframes wave {
    0%, 100% { transform: rotate(0deg); }
    25% { transform: rotate(20deg); }
    75% { transform: rotate(-10deg); }
  }

  h1.name {
    font-size: 2.2rem;
    font-weight: 700;
    background: linear-gradient(135deg, var(--teal), #60a5fa);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 6px;
  }

  .subtitle {
    color: var(--muted);
    font-size: 1rem;
    font-weight: 300;
    letter-spacing: 0.04em;
  }

  /* Badges row */
  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
    margin-top: 20px;
  }
  .badge {
    background: rgba(45,212,191,0.1);
    border: 1px solid rgba(45,212,191,0.3);
    border-radius: 20px;
    padding: 5px 14px;
    font-size: 12px;
    font-family: 'JetBrains Mono', monospace;
    color: var(--teal);
    display: flex;
    align-items: center;
    gap: 6px;
  }

  /* Section */
  .section { margin-bottom: 36px; }
  .section-title {
    font-size: 1rem;
    font-weight: 700;
    color: var(--teal);
    font-family: 'JetBrains Mono', monospace;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* About */
  .about-text {
    color: var(--white);
    font-size: 0.95rem;
    line-height: 1.8;
    font-weight: 300;
  }
  .about-text strong { color: var(--teal); font-weight: 600; }

  /* Education cards */
  .edu-grid { display: grid; gap: 14px; }
  .edu-card {
    background: rgba(255,255,255,0.03);
    border: 1px solid var(--border);
    border-left: 3px solid var(--teal);
    border-radius: 8px;
    padding: 14px 18px;
  }
  .edu-card.current { border-left-color: var(--gold); }
  .edu-card h3 { font-size: 0.92rem; font-weight: 600; color: var(--white); margin-bottom: 2px; }
  .edu-card .inst { font-size: 0.82rem; color: var(--muted); margin-bottom: 6px; }
  .edu-card .period { font-size: 0.78rem; font-family: 'JetBrains Mono', monospace; color: var(--teal); }
  .edu-card.current .period { color: var(--gold); }
  .current-tag {
    display: inline-block;
    background: rgba(240,165,0,0.15);
    border: 1px solid rgba(240,165,0,0.4);
    color: var(--gold);
    font-size: 10px;
    font-family: 'JetBrains Mono', monospace;
    border-radius: 4px;
    padding: 1px 7px;
    margin-left: 8px;
    vertical-align: middle;
  }

  /* Skills grid */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
    gap: 10px;
  }
  .skill-pill {
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 14px;
    font-size: 0.83rem;
    display: flex;
    align-items: center;
    gap: 8px;
    transition: border-color 0.2s, background 0.2s;
  }
  .skill-pill:hover { border-color: var(--teal); background: rgba(45,212,191,0.06); }
  .skill-pill .icon { font-size: 16px; }

  /* Achievements */
  .ach-list { list-style: none; display: grid; gap: 10px; }
  .ach-list li {
    background: rgba(255,255,255,0.03);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 12px 16px;
    font-size: 0.87rem;
    display: flex;
    align-items: flex-start;
    gap: 10px;
    line-height: 1.5;
  }
  .ach-list .trophy { font-size: 18px; flex-shrink: 0; }

  /* Contact */
  .contact-row { display: flex; flex-wrap: wrap; gap: 12px; }
  .contact-link {
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 16px;
    font-size: 0.85rem;
    color: var(--white);
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 8px;
    transition: border-color 0.2s;
  }
  .contact-link:hover { border-color: var(--teal); color: var(--teal); }

  /* Footer note */
  .note {
    margin-top: 32px;
    padding: 16px;
    background: rgba(45,212,191,0.05);
    border: 1px dashed rgba(45,212,191,0.3);
    border-radius: 8px;
    font-size: 0.82rem;
    color: var(--muted);
    line-height: 1.6;
  }
  .note strong { color: var(--teal); }

  /* Raw markdown panel */
  .raw-panel {
    margin-top: 24px;
    background: #010409;
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
  }
  .raw-header {
    background: var(--surface);
    padding: 10px 20px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    border-bottom: 1px solid var(--border);
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .raw-code {
    padding: 24px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    line-height: 1.9;
    color: #c9d1d9;
    white-space: pre-wrap;
    word-break: break-word;
    overflow-x: auto;
  }
  .copy-md-btn {
    background: transparent;
    border: 1px solid var(--border);
    color: var(--muted);
    border-radius: 6px;
    padding: 4px 12px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    cursor: pointer;
    transition: all 0.2s;
  }
  .copy-md-btn:hover { border-color: var(--teal); color: var(--teal); }
</style>
</head>
<body>
<div class="container">

  <!-- Toolbar -->
  <div class="toolbar">
    <div class="dot red"></div>
    <div class="dot yellow"></div>
    <div class="dot green"></div>
    <span class="filename">README.md — Preview</span>
    <button class="copy-btn" onclick="copyMarkdown()">📋 Copy Markdown</button>
  </div>

  <!-- README Preview -->
  <div class="readme">

    <div class="header-banner">
      <span class="wave">👋</span>
      <h1 class="name">Ravindu Sankalpa Perera</h1>
      <p class="subtitle">Electrical Engineering Graduate &nbsp;•&nbsp; Software Engineering Student &nbsp;•&nbsp; Sri Lanka 🇱🇰</p>
      <div class="badges">
        <span class="badge">⚡ Electrical Engineering</span>
        <span class="badge">💻 Software Engineering</span>
        <span class="badge">📱 Mobile App Dev</span>
        <span class="badge">🏆 Intel ISEF 2017 Grand Award</span>
        <span class="badge">🇨🇳 Chinese Speaker</span>
      </div>
    </div>

    <div class="section">
      <div class="section-title">About Me</div>
      <p class="about-text">
        I'm a passionate engineer from <strong>Sri Lanka</strong> with a background in <strong>Electrical Engineering & Automation</strong> (Hangzhou Dianzi University, China) and currently pursuing a <strong>Bachelor's in Software Engineering</strong>, focusing on modern programming languages and mobile application development. I thrive in both autonomous and collaborative environments and enjoy bridging the gap between hardware and software.
      </p>
    </div>

    <div class="section">
      <div class="section-title">Education</div>
      <div class="edu-grid">
        <div class="edu-card current">
          <h3>Bachelor's in Software Engineering <span class="current-tag">CURRENT</span></h3>
          <div class="inst">Focused on Modern Programming Languages & Mobile Application Development</div>
          <div class="period">2024 – Present</div>
        </div>
        <div class="edu-card">
          <h3>B.Eng. Electrical Engineering & Automation</h3>
          <div class="inst">Hangzhou Dianzi University, Hangzhou, China</div>
          <div class="period">Sep 2019 – 2023</div>
        </div>
      </div>
    </div>

    <div class="section">
      <div class="section-title">Skills & Technologies</div>
      <div class="skills-grid">
        <div class="skill-pill"><span class="icon">🔌</span> Arduino</div>
        <div class="skill-pill"><span class="icon">⚙️</span> C Programming</div>
        <div class="skill-pill"><span class="icon">🌐</span> Web Design</div>
        <div class="skill-pill"><span class="icon">📱</span> Mobile Dev</div>
        <div class="skill-pill"><span class="icon">🎨</span> Photoshop</div>
        <div class="skill-pill"><span class="icon">👥</span> Leadership</div>
        <div class="skill-pill"><span class="icon">🤝</span> Teamwork</div>
        <div class="skill-pill"><span class="icon">🇨🇳</span> Chinese</div>
      </div>
    </div>

    <div class="section">
      <div class="section-title">Achievements</div>
      <ul class="ach-list">
        <li><span class="trophy">🥇</span> Grand Award — Intel International Science & Engineering Fair 2017, Los Angeles, USA (First Sri Lankan school to win)</li>
        <li><span class="trophy">🏅</span> MAWHIBA Special Award (Water Technology) — Intel ISEF 2017, Los Angeles, USA</li>
        <li><span class="trophy">🥈</span> 2nd Place — Sri Lankan Science & Engineering Fair 2016</li>
        <li><span class="trophy">🏆</span> All Island Best School Inventor of the Year 2017</li>
        <li><span class="trophy">🥇</span> 1st Place — National Science Research Project Competition 2016</li>
        <li><span class="trophy">⭐</span> Student of the Year 2016–2017</li>
        <li><span class="trophy">🎵</span> All Island Best Music Director 2014</li>
      </ul>
    </div>

    <div class="section">
      <div class="section-title">Get In Touch</div>
      <div class="contact-row">
        <a class="contact-link" href="mailto:ravindusankalpaperera@gmail.com">✉️ ravindusankalpaperera@gmail.com</a>
        <a class="contact-link" href="https://linkedin.com/in/sankalpa-perera-938b68170">💼 LinkedIn</a>
        <a class="contact-link" href="tel:+94754067861">📱 +94 75 406 7861</a>
        <a class="contact-link" href="#">⌨️ GitHub (add your URL here)</a>
      </div>
    </div>

    <div class="note">
      <strong>📝 How to use this file:</strong> Click <em>"Copy Markdown"</em> at the top → go to your GitHub profile repository (same name as your username) → open <code>README.md</code> → paste and commit. Remember to replace the GitHub URL placeholder with your actual GitHub link!
    </div>

  </div>

  <!-- Raw Markdown Panel -->
  <div class="raw-panel">
    <div class="raw-header">
      <span>📄 Raw Markdown — paste this into your README.md</span>
      <button class="copy-md-btn" onclick="copyMarkdown()">Copy</button>
    </div>
    <div class="raw-code" id="rawMd">
# 👋 Hi, I'm Ravindu Sankalpa Perera

**Electrical Engineering Graduate • Software Engineering Student • Sri Lanka 🇱🇰**

[![Email](https://img.shields.io/badge/Email-ravindusankalpaperera%40gmail.com-teal?style=flat-square&logo=gmail)](mailto:ravindusankalpaperera@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-sankalpa--perera-blue?style=flat-square&logo=linkedin)](https://linkedin.com/in/sankalpa-perera-938b68170)

---

## 🧑‍💻 About Me

I'm a passionate engineer from **Sri Lanka** with a degree in **Electrical Engineering & Automation** from Hangzhou Dianzi University, China. I'm currently pursuing a **Bachelor's in Software Engineering**, focusing on modern programming languages and mobile application development. I enjoy bridging the gap between hardware and software and thrive in both autonomous and collaborative environments.

---

## 🎓 Education

| Degree | Institution | Period |
|---|---|---|
| 🟡 **B.Sc. Software Engineering** *(Current)* — Modern Programming & Mobile App Dev | *(Your University)* | 2024 – Present |
| ⚡ B.Eng. Electrical Engineering & Automation | Hangzhou Dianzi University, China | 2019 – 2023 |

---

## 🛠️ Skills & Technologies

![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat-square&logo=arduino&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black)
![Web Design](https://img.shields.io/badge/Web%20Design-F7DF1E?style=flat-square&logo=html5&logoColor=black)
![Mobile Dev](https://img.shields.io/badge/Mobile%20Dev-3DDC84?style=flat-square&logo=android&logoColor=white)
![Photoshop](https://img.shields.io/badge/Photoshop-31A8FF?style=flat-square&logo=adobephotoshop&logoColor=white)

- 🔌 Arduino & Embedded Systems
- ⚙️ C Programming
- 🌐 Web Designing
- 📱 Mobile Application Development *(actively learning)*
- 🎨 Adobe Photoshop
- 🇨🇳 Chinese (Conversational)
- 👥 Leadership & Teamwork

---

## 🏆 Achievements & Awards

- 🥇 **Grand Award** — Intel International Science & Engineering Fair 2017, Los Angeles, USA *(First Sri Lankan school in history to win)*
- 🏅 **MAWHIBA Special Award** (Water Technology) — Intel ISEF 2017
- 🥈 **2nd Place** — Sri Lankan Science & Engineering Fair 2016
- 🏆 **All Island Best School Inventor of the Year** 2017
- 🥇 **1st Place** — National Science Research Project Competition 2016
- ⭐ **Student of the Year** 2016–2017
- 🎵 **All Island Best Music Director** 2014
- 🏏 **School Cricket Captain** — U-15 & U-17 Teams | Deputy Head Prefect

---

## 📫 Contact Me

- ✉️ **Email:** ravindusankalpaperera@gmail.com
- 📱 **Phone:** +94 75 406 7861
- 💼 **LinkedIn:** [sankalpa-perera-938b68170](https://linkedin.com/in/sankalpa-perera-938b68170)
- 🏠 **Location:** Boralasgamuwa, Sri Lanka

---

*⚡ Currently learning modern programming languages & mobile app development — open to collaborations!*
    </div>
  </div>

</div>

<script>
function copyMarkdown() {
  const text = document.getElementById('rawMd').innerText;
  navigator.clipboard.writeText(text).then(() => {
    const btn = document.querySelector('.copy-btn');
    const btn2 = document.querySelector('.copy-md-btn');
    btn.textContent = '✅ Copied!';
    btn2.textContent = 'Copied!';
    setTimeout(() => {
      btn.textContent = '📋 Copy Markdown';
      btn2.textContent = 'Copy';
    }, 2000);
  });
}
</script>
</body>
</html>
