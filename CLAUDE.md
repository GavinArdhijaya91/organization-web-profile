# CLAUDE.md — Organization Web Profile
> Reference for AI Agents (Claude, GPT-5, Copilot, Cursor, etc.)
> Read entirely before writing any code.

---

## 1. PROJECT IDENTITY

```
Assignment    : Single Page Organization Web Profile
Stack         : HTML5 + CSS3 only (no JavaScript, no frameworks)
Output        : One file — index.html (CSS embedded in <style> tag)
Submission    : Screenshot of full page (no source code required)
```

---

## 2. PAGE STRUCTURE (REQUIRED SECTIONS)

Build exactly these sections, top to bottom, in a single HTML file:

```
┌─────────────────────────────┐
│         HERO / HEADER       │  ← Organization name + tagline + logo area
├─────────────────────────────┤
│         ABOUT / DESKRIPSI   │  ← Short description of the organization
├─────────────────────────────┤
│         VISI & MISI         │  ← Vision statement + Mission points
├─────────────────────────────┤
│         FOOTER              │  ← Simple closing / copyright
└─────────────────────────────┘
```

---

## 3. DESIGN REQUIREMENTS

```
Layout        : Single page, full-width sections, centered content
Font          : Google Fonts — use 'Poppins' (import via @import in CSS)
Color scheme  : Choose ONE of the palettes below (do not mix):

  PALETTE A — Professional Blue
    Primary   : #1a1a2e
    Accent    : #16213e / #0f3460
    Highlight : #e94560
    Text      : #ffffff / #cccccc

  PALETTE B — Fresh Green (recommended for student org)
    Primary   : #0d1b2a
    Accent    : #1b4332
    Highlight : #52b788
    Text      : #ffffff / #d8f3dc

  PALETTE C — Warm Academic
    Primary   : #2d2d2d
    Accent    : #8b4513
    Highlight : #f4a261
    Text      : #ffffff / #f0e6d3

Spacing       : Generous padding — min 80px top/bottom per section
Readability   : Font size body min 16px, headings min 32px
```

---

## 4. FULL HTML TEMPLATE

```html
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>VISIONARY</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link
    href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&display=swap"
    rel="stylesheet"
  />
  <style>
    /* ── RESET & BASE ───────────────────────────── */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Poppins', sans-serif;
      background-color: #0d1b2a;
      color: #ffffff;
      line-height: 1.7;
    }

    /* ── HERO SECTION ───────────────────────────── */
    .hero {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 80px 20px;
      background: linear-gradient(135deg, #0d1b2a 0%, #1b4332 100%);
      position: relative;
    }

    .hero::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      height: 4px;
      background: #52b788;
    }

    /* ── DUMMY IMAGE SYSTEM ─────────────────────── */

    /* Option A: CSS Logo (no internet needed) */
    .hero-logo {
      width: 110px;
      height: 110px;
      border-radius: 50%;
      background: linear-gradient(135deg, #52b788, #1b4332);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 2.8rem;
      margin-bottom: 30px;
      box-shadow: 0 0 50px rgba(82, 183, 136, 0.45);
      border: 3px solid rgba(82, 183, 136, 0.4);
    }

    /* Option B: Placeholder image via placehold.co */
    .hero-img {
      width: 120px;
      height: 120px;
      border-radius: 50%;
      object-fit: cover;
      margin-bottom: 30px;
      border: 4px solid #52b788;
      box-shadow: 0 0 40px rgba(82, 183, 136, 0.4);
      display: none; /* ganti ke block kalau pakai Option B */
    }

    /* Decorative about image */
    .about-img-wrap {
      display: flex;
      justify-content: center;
      margin-bottom: 40px;
    }

    .about-img {
      width: 100%;
      max-width: 700px;
      height: 220px;
      object-fit: cover;
      border-radius: 16px;
      border: 2px solid #1b4332;
    }

    /* Member card dummy avatar */
    .avatar {
      width: 72px;
      height: 72px;
      border-radius: 50%;
      object-fit: cover;
      border: 3px solid #52b788;
    }

    .hero h1 {
      font-size: clamp(2rem, 6vw, 4rem);
      font-weight: 800;
      letter-spacing: -1px;
      margin-bottom: 16px;
    }

    .hero h1 span {
      color: #52b788;
    }

    .hero p.tagline {
      font-size: clamp(1rem, 2vw, 1.3rem);
      font-weight: 300;
      color: #d8f3dc;
      max-width: 600px;
    }

    /* ── SECTION BASE ───────────────────────────── */
    section {
      padding: 100px 20px;
    }

    .container {
      max-width: 900px;
      margin: 0 auto;
    }

    .section-label {
      font-size: 0.85rem;
      font-weight: 600;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: #52b788;
      margin-bottom: 12px;
    }

    .section-title {
      font-size: clamp(1.8rem, 4vw, 2.8rem);
      font-weight: 700;
      margin-bottom: 30px;
      line-height: 1.2;
    }

    /* ── ABOUT SECTION ──────────────────────────── */
    .about {
      background-color: #0f2030;
    }

    .about p {
      font-size: 1.1rem;
      color: #d8f3dc;
      max-width: 700px;
    }

    /* ── VISI MISI SECTION ──────────────────────── */
    .visi-misi {
      background-color: #0d1b2a;
    }

    .vm-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 40px;
      margin-top: 20px;
    }

    .vm-card {
      background: #0f2030;
      border: 1px solid #1b4332;
      border-radius: 16px;
      padding: 40px;
      border-top: 4px solid #52b788;
    }

    .vm-card h3 {
      font-size: 1.4rem;
      font-weight: 700;
      margin-bottom: 20px;
      color: #52b788;
    }

    .vm-card p {
      color: #d8f3dc;
      font-size: 1rem;
    }

    .vm-card ul {
      list-style: none;
      padding: 0;
    }

    .vm-card ul li {
      color: #d8f3dc;
      padding: 8px 0;
      padding-left: 20px;
      position: relative;
      font-size: 1rem;
    }

    .vm-card ul li::before {
      content: '▸';
      position: absolute;
      left: 0;
      color: #52b788;
    }

    /* ── FOOTER ─────────────────────────────────── */
    footer {
      background: #060f18;
      text-align: center;
      padding: 40px 20px;
      color: #52b788;
      font-size: 0.9rem;
      border-top: 1px solid #1b4332;
    }

    footer p {
      opacity: 0.7;
    }
  </style>
</head>

<body>

  <!-- ═══════════════ HERO ═══════════════ -->
  <section class="hero">

    <!--
      PILIH SALAH SATU logo di bawah, hapus yang tidak dipakai:

      OPTION A — Emoji logo (no internet, always works)
      OPTION B — Placeholder image dari placehold.co (butuh internet)
                 Ganti teks "ORG" sesuai singkatan organisasimu
                 Ganti warna bg= dan text= sesuai palette-mu
    -->

    <!-- OPTION A: Emoji Logo (DEFAULT, aktif) -->
    <div class="hero-logo">🌿</div>

    <!-- OPTION B: Placeholder image (non-aktif, hapus comment untuk aktifkan) -->
    <!--
    <img
      class="hero-img"
      style="display:block;"
      src="https://placehold.co/120x120/1b4332/52b788?text=ORG&font=poppins"
      alt="Logo Organisasi"
    />
    -->

    <h1>VISIONARY</h1>
    <p class="tagline">Satu Gerakan, Wujudkan Dunia</p>
  </section>

  <!-- ═══════════════ ABOUT ═══════════════ -->
  <section class="about">
    <div class="container">

      <!--
        DUMMY BANNER IMAGE (opsional, hapus seluruh blok ini kalau tidak mau)
        Ganti ukuran 700x220 kalau perlu dimensi berbeda.
        Ganti warna bg= dan text= sesuai palette-mu.
        Kalau sudah punya gambar asli: ganti src= dengan path file-mu.
      -->
      <div class="about-img-wrap">
        <img
          class="about-img"
          src="https://placehold.co/700x220/0f2030/52b788?text=Foto+Kegiatan+Organisasi&font=poppins"
          alt="Kegiatan Organisasi"
        />
      </div>

      <p class="section-label">Tentang Kami</p>
      <h2 class="section-title">Siapa Kami?</h2>
      <p>
        Visionary merupakan sebuah organisasi kemahasiswaan yang berfokus pada pengembangan diri, kepemimpinan, dan kontribusi positif bagi masyarakat.
      </p>
    </div>
  </section>

  <!-- ═══════════════ VISI & MISI ═══════════════ -->
  <section class="visi-misi">
    <div class="container">
      <p class="section-label">Arah & Tujuan</p>
      <h2 class="section-title">Visi & Misi</h2>
      <div class="vm-grid">

        <div class="vm-card">
          <h3>🎯 Visi</h3>
          <p>
            Menjadi organisasi yang visioner, inspiratif, dan transformatif dalam mencetak pemimpin masa depan.
          </p>
        </div>

        <div class="vm-card">
          <h3>🚀 Misi</h3>
          <ul>
            <li>Membentuk karakter pemimpin yang berintegritas, inovatif, dan berwawasan global.</li>
            <li>Mengembangkan potensi mahasiswa melalui program pengembangan diri dan kepemimpinan.</li>
            <li>Menciptakan lingkungan yang kolaboratif dan suportif untuk pertumbuhan anggota.</li>
            <li>Berkontribusi dalam pengembangan masyarakat melalui program pengabdian yang berkelanjutan.</li>
          </ul>
        </div>

      </div>
    </div>
  </section>

  <!-- ═══════════════ FOOTER ═══════════════ -->
  <footer>
    <p>© 2025 VISIONARY — All Rights Reserved</p>
  </footer>

</body>
</html>
```

---

## 5. DUMMY IMAGE REFERENCE CARD

```
Semua dummy image pakai placehold.co — gratis, no signup, no API key.
Format URL: https://placehold.co/{WIDTH}x{HEIGHT}/{BG_COLOR}/{TEXT_COLOR}?text={TEKS}&font=poppins

SIAP PAKAI — copy URL ini langsung ke src="...":

  Logo bulat (120x120)
  → https://placehold.co/120x120/1b4332/52b788?text=ORG&font=poppins

  Banner kegiatan (700x220)
  → https://placehold.co/700x220/0f2030/52b788?text=Foto+Kegiatan&font=poppins

  Avatar anggota (80x80)
  → https://placehold.co/80x80/1b4332/52b788?text=A&font=poppins
  → https://placehold.co/80x80/1b4332/52b788?text=B&font=poppins

  Foto profil persegi (300x300)
  → https://placehold.co/300x300/0f2030/52b788?text=Foto&font=poppins

KUSTOMISASI WARNA (ganti hex di URL):
  Background gelap + teks hijau  : /0f2030/52b788
  Background hijau + teks putih  : /1b4332/ffffff
  Background navy + teks kuning  : /1a1a2e/f4c430
  Background abu + teks putih    : /2d2d2d/ffffff

GANTI KE GAMBAR ASLI:
  Kalau sudah punya foto → taruh di folder yang sama dengan index.html
  Lalu ganti src="https://placehold.co/..." → src="nama-file-foto.jpg"
  Tidak perlu ganti CSS apapun, ukuran dan style otomatis mengikuti.
```

```
Replace every placeholder in square brackets [ ] with real content:

  [NAMA ORGANISASI]     → Nama lengkap organisasi/komunitas kamu
  [Tagline singkat...]  → Slogan atau kalimat moto organisasi
  [Tulis deskripsi...]  → Paragraf about 3-5 kalimat
  [Tulis visi...]       → Kalimat visi (biasanya 1-2 kalimat)
  [Misi pertama...]     → Poin-poin misi (minimal 3, maksimal 6)
  🌿 (emoji logo)       → Ganti dengan emoji yang sesuai karakter organisasimu

Color customization:
  Ganti semua #52b788 (hijau) → warna highlight pilihanmu
  Ganti semua #1b4332 (hijau gelap) → warna accent pilihanmu
  Ganti semua #0d1b2a (navy) → warna background pilihanmu
```

---

## 6. CUSTOMIZATION INSTRUCTIONS

```
Replace every placeholder in square brackets [ ] with real content:

  [NAMA ORGANISASI]     → Nama lengkap organisasi/komunitas kamu
  [Tagline singkat...]  → Slogan atau kalimat moto organisasi
  [Tulis deskripsi...]  → Paragraf about 3-5 kalimat
  [Tulis visi...]       → Kalimat visi (biasanya 1-2 kalimat)
  [Misi pertama...]     → Poin-poin misi (minimal 3, maksimal 6)
  🌿 (emoji logo)       → Ganti dengan emoji yang sesuai karakter organisasimu

Color customization:
  Ganti semua #52b788 (hijau) → warna highlight pilihanmu
  Ganti semua #1b4332 (hijau gelap) → warna accent pilihanmu
  Ganti semua #0d1b2a (navy) → warna background pilihanmu
```

---

## 7. SCREENSHOT TIPS (FOR SUBMISSION)

```
Browser  : Gunakan Chrome atau Edge
Zoom     : Set browser zoom ke 80% agar seluruh halaman muat dalam SS
Method   : Gunakan Full Page Screenshot extension atau:
           Chrome → F12 → Ctrl+Shift+P → "Capture full size screenshot"
Format   : PNG lebih baik dari JPG untuk keterbacaan teks
Checklist sebelum submit:
  ✅ Nama organisasi terlihat jelas
  ✅ Deskripsi terbaca
  ✅ Visi & Misi lengkap terlihat
  ✅ Tidak ada teks [placeholder] yang tersisa
  ✅ Tidak ada bagian yang terpotong
```

---

## 8. AGENT INSTRUCTIONS

```
When asked to generate the web profile:
  1. Ask for: organization name, tagline, description, vision, and mission points
  2. Replace ALL placeholders with the provided content
  3. Output a SINGLE complete index.html file — do not split into separate CSS file
  4. Do not add JavaScript of any kind
  5. Do not add external images (use emoji or CSS shapes instead)
  6. Ensure the vm-grid uses grid-template-columns: 1fr for mobile if needed
  7. Final file must be openable by double-clicking in any browser with no setup
```

---

*CLAUDE.md — Organization Web Profile Assignment · v1.0*

# CLAUDE.md — Cinematic Organization Web Profile (Detective Board Edition)
> Reference for AI Agents (Claude, GPT-5, Copilot, Cursor, etc.)  
> Read entirely before writing any code.

---

# 1. PROJECT IDENTITY

Assignment    : Cinematic Single Page Organization Web Profile  
Theme         : Detective Investigation Board / Strategic Intelligence  
Style         : Modern cinematic + serious + premium academic  
Stack         : HTML5 + CSS3 only (NO JavaScript, NO frameworks)  
Output        : ONE FILE ONLY → index.html  
CSS Rule      : All CSS must be embedded inside <style>  
Submission    : Full page screenshot

---

# 2. DESIGN CONCEPT

The web profile MUST feel like:

✔ Strategic organization headquarters  
✔ Investigation board / detective wall  
✔ Premium modern intelligence room  
✔ Serious and futuristic  
✔ Academic but cinematic  
✔ Minimal yet dramatic  

Visual inspiration:

• Detective red-string investigation board  
• Confidential files & photo pins  
• Glass magnifier aesthetic  
• Strategic command center  
• Noir / intelligence division vibes  

DO NOT create:

✘ Cute student website  
✘ Colorful playful landing page  
✘ Startup gradient style  
✘ Generic portfolio appearance  
✘ Bright neon cyberpunk  

---

# 3. CORE VISUAL ELEMENTS (MANDATORY)

## A. RED INVESTIGATION LINES

Use thin red/maroon connector lines across sections.

Example aesthetics:

```css
background:
linear-gradient(
  120deg,
  transparent 0%,
  rgba(255,70,70,0.08) 45%,
  transparent 50%
);

# CLAUDE.md — CINEMATIC DETECTIVE BOARD ORGANIZATION WEB PROFILE
> Advanced Reference Document for AI Agents (Claude, GPT-5, Cursor, Copilot, Gemini, etc.)
> Read ENTIRELY before generating any code.
> This document defines the artistic direction, layout logic, styling system, UI atmosphere, and generation standards for a premium cinematic organization web profile.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 1 — PROJECT OVERVIEW
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PROJECT NAME:
  Cinematic Strategic Organization Web Profile

PROJECT TYPE:
  Single-page organization landing page

PURPOSE:
  To create a visually striking and professional organization profile website
  with a cinematic detective-board atmosphere that feels strategic,
  serious, intelligent, premium, and modern.

TARGET FEELING:
  The final website should emotionally feel like:

  ✔ an intelligence headquarters
  ✔ a detective investigation room
  ✔ a classified strategic organization
  ✔ a mission planning command center
  ✔ an elite academic division
  ✔ a premium cinematic dossier system

NOTES:
  This is NOT a startup website.
  This is NOT a playful school club website.
  This is NOT a generic landing page.

  The page must feel:
  dark,
  mature,
  confidential,
  tactical,
  dramatic,
  intelligent,
  elite.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 2 — TECHNICAL REQUIREMENTS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

STACK:
  HTML5 + CSS3 ONLY

STRICT RULES:
  ✔ NO JavaScript
  ✔ NO frameworks
  ✔ NO Bootstrap
  ✔ NO Tailwind
  ✔ NO React
  ✔ NO Vue
  ✔ NO CDN libraries except Google Fonts
  ✔ NO external images
  ✔ NO SVG imports
  ✔ NO canvas
  ✔ NO animations requiring JS

FILE STRUCTURE:
  ONLY ONE FILE:
    index.html

CSS RULE:
  All CSS MUST be embedded inside:
    <style> ... </style>

OUTPUT REQUIREMENT:
  The final file must:
  ✔ run instantly by double-clicking index.html
  ✔ require zero setup
  ✔ work offline
  ✔ be responsive
  ✔ look cinematic on desktop
  ✔ remain readable on mobile

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 3 — ART DIRECTION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

CORE AESTHETIC:
  Detective Investigation Board + Strategic Intelligence Division

VISUAL INSPIRATION:
  • detective evidence walls
  • red string conspiracy boards
  • mission dossier archives
  • secret investigation rooms
  • noir tactical headquarters
  • confidential operation center
  • intelligence command dashboard

ATMOSPHERE:
  ✔ cinematic
  ✔ mysterious
  ✔ tactical
  ✔ premium
  ✔ dark-academic
  ✔ elite
  ✔ strategic
  ✔ investigative

THE PAGE MUST FEEL LIKE:
  "A strategic operation room used by an elite organization."

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 4 — COLOR SYSTEM
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

MANDATORY COLOR PALETTE:

PRIMARY BACKGROUND:
  #1a1412

SECONDARY BACKGROUND:
  #241816

CARD SURFACE:
  #2d1f1b

MAROON:
  #7a1f1f

DARK RED:
  #992b2b

CORAL:
  #d97b66

COPPER:
  #8b5e3c

TEXT PRIMARY:
  #f5eee6

TEXT SECONDARY:
  #d8c7b8

TEXT MUTED:
  #9f8b7d

BORDER COLOR:
  rgba(255,255,255,0.08)

GLASS EFFECT:
  rgba(255,255,255,0.04)

OPTIONAL SHADOW:
  rgba(0,0,0,0.45)

DO NOT USE:
  ✘ bright neon blue
  ✘ bright cyan
  ✘ playful green
  ✘ rainbow gradients
  ✘ oversaturated colors
  ✘ childish palette combinations

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 5 — TYPOGRAPHY SYSTEM
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

GOOGLE FONTS:
  Use at least TWO of these:

  • Poppins
  • Inter
  • Space Grotesk

IMPORT RULE:
  Use @import inside CSS.

HEADINGS:
  Must feel:
  ✔ cinematic
  ✔ strategic
  ✔ commanding
  ✔ premium

HEADING STYLE:
  • bold
  • slightly tight letter spacing
  • high contrast
  • large sizing

RECOMMENDED SIZES:

  Hero Title:
    64px–90px desktop

  Section Title:
    38px–54px

  Subtitle:
    18px–24px

  Body Text:
    minimum 16px

TEXT FEEL:
  Professional and intelligent.

DO NOT:
  ✘ use comic-like typography
  ✘ use handwritten fonts
  ✘ use playful fonts

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 6 — PAGE STRUCTURE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

The final layout MUST follow this structure:

┌─────────────────────────────────────┐
│          HERO / COMMAND             │
├─────────────────────────────────────┤
│          ABOUT DOSSIER              │
├─────────────────────────────────────┤
│          STRATEGIC VISI             │
├─────────────────────────────────────┤
│          MISSION BOARD              │
├─────────────────────────────────────┤
│          CORE VALUES                │
├─────────────────────────────────────┤
│          ORGANIZATION INSIGHT       │
├─────────────────────────────────────┤
│          FOOTER                     │
└─────────────────────────────────────┘

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 7 — HERO SECTION DIRECTION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

The HERO section is the MOST IMPORTANT visual section.

REQUIRED ELEMENTS:
  ✔ logo badge
  ✔ cinematic background glow
  ✔ red investigation lines
  ✔ strategic atmosphere
  ✔ subtle glass effects
  ✔ large title
  ✔ tagline
  ✔ small classification label

LAYOUT IDEA:

  [ strategic logo ]

  ORGANIZATION NAME

  "Tagline / Motto"

  Confidential Strategic Organization

VISUAL MOOD:
  The hero should feel like:
  ✔ entering a classified operation center
  ✔ opening an intelligence briefing room
  ✔ accessing an elite organization dashboard

BACKGROUND EFFECTS:
  Use:
  • radial gradients
  • dark overlays
  • subtle red line decorations
  • glass circles
  • cinematic shadows

OPTIONAL LABELS:
  • CLASSIFIED
  • CONFIDENTIAL
  • STRATEGIC DIVISION
  • OPERATIONAL CENTER
  • INTELLIGENCE UNIT

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 8 — RED DETECTIVE THREAD SYSTEM
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

One of the MOST IMPORTANT stylistic elements.

PURPOSE:
  To create the feeling of an investigation wall.

IMPLEMENTATION IDEAS:
  • thin horizontal red lines
  • diagonal connector lines
  • pseudo-element strings
  • glowing maroon separators
  • strategic connection maps

EXAMPLE:

```css
.red-thread {
  position: absolute;
  width: 180px;
  height: 2px;
  background: linear-gradient(
    90deg,
    transparent,
    rgba(217,123,102,0.6),
    transparent
  );
  transform: rotate(-12deg);
}
```

VISUAL FEEL:
  ✔ conspiracy map
  ✔ tactical intelligence linking
  ✔ detective evidence system
  ✔ mission tracking

DO NOT:
  ✘ overuse thick lines
  ✘ create chaotic clutter
  ✘ make lines too bright

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 9 — GLASS MAGNIFIER EFFECT
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

The website SHOULD contain decorative glass circles.

PURPOSE:
  Simulate magnifying lenses and investigation tools.

STYLE:
  ✔ translucent
  ✔ blurred
  ✔ soft border
  ✔ cinematic glow

EXAMPLE:

```css
.glass-orb {
  width: 240px;
  height: 240px;
  border-radius: 50%;
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.08);
  backdrop-filter: blur(14px);
  box-shadow:
    inset 0 0 30px rgba(255,255,255,0.02),
    0 0 50px rgba(217,123,102,0.08);
}
```

PLACEMENT:
  • behind hero content
  • floating beside cards
  • near section edges

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 10 — ABOUT DOSSIER SECTION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

The About section MUST resemble:
  ✔ intelligence report
  ✔ classified document
  ✔ confidential file
  ✔ strategic briefing

STYLE:
  • paper-card appearance
  • layered shadows
  • subtle border accents
  • left maroon line
  • premium spacing

OPTIONAL LABELS:
  • DOSSIER
  • CLASSIFIED REPORT
  • FILE 01
  • INTERNAL DOCUMENT

TEXT STYLE:
  Formal and strategic.

EXAMPLE TONE:
  “Founded to develop strategic collaboration and innovation...”

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 11 — VISI SECTION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

The Vision section should feel:
  ✔ visionary
  ✔ elite
  ✔ future-oriented
  ✔ commanding

STYLE:
  • single cinematic statement
  • centered or offset layout
  • premium typography
  • soft lighting

VISUAL:
  Use:
  • glowing border
  • glass surface
  • subtle spotlight effect

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 12 — MISSION BOARD SECTION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

This section MUST resemble:
  ✔ mission planning board
  ✔ evidence wall
  ✔ operation planning system

CARD STYLE:
  ✔ pinned paper cards
  ✔ investigation notes
  ✔ evidence files
  ✔ dossier fragments

EACH MISSION CARD SHOULD HAVE:
  • number label
  • left accent border
  • subtle hover effect
  • layered shadow
  • cinematic surface

CARD FEEL:
  “Operational directives from a strategic organization.”

OPTIONAL EFFECTS:
  • tape corner
  • paper rotation
  • stacked documents

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 13 — CORE VALUES SECTION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Add a dedicated values section.

TITLE OPTIONS:
  • Core Values
  • Strategic Foundations
  • Operational Principles
  • Foundational Ethics

DISPLAY:
  3–6 cards.

EXAMPLE VALUES:
  • Integrity
  • Discipline
  • Leadership
  • Innovation
  • Collaboration
  • Critical Thinking

STYLE:
  ✔ glassmorphism
  ✔ elegant glow
  ✔ minimal premium layout
  ✔ cinematic lighting

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 14 — ORGANIZATION INSIGHT SECTION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

OPTIONAL but highly recommended.

PURPOSE:
  Showcase:
  • achievements
  • focus areas
  • strategic priorities
  • organizational impact

STYLE:
  ✔ dashboard feel
  ✔ classified metrics
  ✔ cinematic cards
  ✔ intelligence panel aesthetic

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 15 — LAYOUT SYSTEM
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

CONTAINER:
  max-width: 1200px

SECTION SPACING:
  minimum 100px vertical

GRID GAP:
  24px–40px

BORDER RADIUS:
  18px–28px

CARD PADDING:
  28px–42px

USE:
  • CSS Grid
  • Flexbox
  • layered depth

DO NOT:
  ✘ overcrowd sections
  ✘ use tiny spacing
  ✘ create flat layouts

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 16 — RESPONSIVE RULES
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

MOBILE BREAKPOINT:
  @media (max-width: 768px)

MOBILE REQUIREMENTS:
  ✔ stack grids vertically
  ✔ reduce hero size
  ✔ maintain readability
  ✔ preserve cinematic spacing
  ✔ prevent overflow

DO NOT:
  ✘ remove important sections
  ✘ destroy visual hierarchy
  ✘ compress spacing too much

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 17 — ADVANCED EFFECTS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

A. GLOW EFFECTS

```css
box-shadow:
0 0 40px rgba(217,123,102,0.12);
```

B. CINEMATIC GRADIENTS

```css
background:
radial-gradient(
circle at top left,
rgba(217,123,102,0.12),
transparent 40%
);
```

C. NOISE OVERLAY

```css
opacity: 0.03;
mix-blend-mode: soft-light;
```

D. GLASSMORPHISM

```css
backdrop-filter: blur(12px);
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 18 — REQUIRED CSS CLASS SYSTEM
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

The final code SHOULD include classes such as:

```css
.hero
.hero-overlay
.hero-glow
.hero-logo

.board-line
.red-thread

.glass-orb

.about-card
.dossier-label

.vm-grid
.vm-card

.value-grid
.value-card

.insight-grid
.insight-card

.section-title
.section-label

footer
```

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 19 — CONTENT WRITING STYLE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

WRITING STYLE:
  ✔ professional
  ✔ visionary
  ✔ serious
  ✔ strategic
  ✔ intelligent
  ✔ inspiring

AVOID:
  ✘ childish wording
  ✘ slang
  ✘ meme culture
  ✘ startup cliché overload
  ✘ excessive emojis

TEXT SHOULD FEEL LIKE:
  “An elite organization presenting its strategic identity.”

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 20 — SCREENSHOT REQUIREMENTS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Before submission ensure:

✔ no placeholder text remains  
✔ hero fully visible  
✔ detective lines visible  
✔ typography readable  
✔ layout aligned correctly  
✔ mobile responsive works  
✔ footer visible  
✔ cinematic atmosphere preserved  

RECOMMENDED METHOD:

Chrome  
→ F12  
→ Ctrl + Shift + P  
→ “Capture full size screenshot”

USE:
  PNG format preferred.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 21 — AGENT EXECUTION INSTRUCTIONS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

When the user asks to generate the web profile:

STEP 1:
  Ask for:
  • organization name
  • tagline
  • description
  • vision
  • mission points
  • organization values

STEP 2:
  Replace ALL placeholders.

STEP 3:
  Generate ONE COMPLETE index.html.

STEP 4:
  Ensure:
  ✔ cinematic detective-board atmosphere
  ✔ maroon/coral/copper palette
  ✔ red investigation lines
  ✔ glass magnifier effects
  ✔ premium strategic aesthetic
  ✔ responsive layout

STEP 5:
  Return production-ready HTML immediately.

DO NOT:
  ✘ split CSS files
  ✘ explain the code
  ✘ add markdown commentary
  ✘ generate multiple files

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SECTION 22 — FINAL CREATIVE DIRECTION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

The final website should emotionally feel like:

“A classified strategic organization dashboard,
combined with a detective investigation board,
wrapped in a cinematic modern intelligence interface.”

FINAL ATMOSPHERE:
  ✔ mysterious
  ✔ tactical
  ✔ elite
  ✔ strategic
  ✔ intelligent
  ✔ premium
  ✔ dark academic
  ✔ serious
  ✔ futuristic
  ✔ cinematic

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

CLAUDE.md — Cinematic Detective Board Organization Profile
Version 3.0 — Premium Strategic Edition

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━