# Website Style, Avatar, Content, and Layout Guide

This document records the final design system, avatar production style, bilingual content structure, and layout rules for the `ydlongtao-personal-site` repository.

Repository: [https://github.com/ydlongtao/ydlongtao-personal-site](https://github.com/ydlongtao/ydlongtao-personal-site)  
Production site: [https://ydlongtao.netlify.app](https://ydlongtao.netlify.app)

## 1. Scope

This repository is a static bilingual academic digital business card website for Longtao Huangfu. It is deployed through Netlify from the `public/` directory.

The site is intentionally lightweight:

- No frontend framework.
- No backend.
- No build step required.
- Plain HTML, CSS, and JavaScript.
- Public assets only in `public/assets/`.

Raw source materials such as the original portrait, PPTX, DOCX CV, QA screenshots, and local Netlify state are excluded from GitHub.

## 2. Design Direction

The final visual direction is:

```text
Academic editorial personal card
Warm paper texture
Biomedical translational research identity
Gastrointestinal oncology visual cue
Calm, rigorous, personal, not corporate-generic
```

Design objectives:

- Present a credible academic identity for oncology pharmacology and translational medicine.
- Keep the page personal rather than institutional or template-like.
- Support Chinese and English readers with equivalent structure.
- Use research and team visuals as part of the story rather than decoration.
- Avoid awkward Chinese line breaks on desktop and mobile.
- Keep the site deployable and maintainable as a static asset.

Avoid:

- Generic blue-purple technology gradients.
- Corporate SaaS landing-page aesthetics.
- Pure white clinical coldness.
- Overly cute cartoon treatment.
- Red or pink anatomical stomach diagrams.
- Text-heavy page sections without visual rhythm.

## 3. Color System

The color system is defined in `public/styles.css`.

| Token | Value | Role |
| --- | --- | --- |
| `--paper` | `#f4f0e7` | Main warm paper background |
| `--paper-deep` | `#ebe3d4` | Contact block and deeper paper panels |
| `--ink` | `#092f3a` | Main typography, dark buttons, brand mark |
| `--ink-soft` | `#32545b` | Secondary body text |
| `--teal` | `#247a7d` | Eyebrows, scientific accents, dots |
| `--teal-pale` | `#a9ccca` | Pale teal labels and soft background accents |
| `--rust` | `#c56a43` | Hero highlight line and warm emphasis |
| `--line` | `rgba(9, 47, 58, 0.18)` | Borders and dividers |

Color usage rules:

- `--ink` is the primary authority color.
- `--rust` is reserved for high-value emphasis, especially the second hero line.
- `--teal` signals biomedical/scientific context.
- `--paper` and `--paper-deep` maintain the editorial paper tone.
- Do not introduce additional saturated accent colors without revisiting the whole palette.

## 4. Typography

The site loads these fonts from Google Fonts:

- Chinese headings: `Noto Serif SC`
- English display headings: `DM Serif Display`
- Body and UI: `Source Sans 3`

CSS variables:

```css
--serif-cn: "Noto Serif SC", serif;
--serif-en: "DM Serif Display", serif;
--sans: "Source Sans 3", sans-serif;
```

Key type rules:

| Element | Rule |
| --- | --- |
| `body` | `17px`, `line-height: 1.65`, `Source Sans 3` |
| `h1` desktop | `clamp(54px, 5vw, 74px)` |
| English `h1` desktop | `clamp(52px, 4.8vw, 74px)` |
| `h1` mobile | `50px` |
| English `h1` mobile | `52px` |
| Default `h2` | `clamp(46px, 5vw, 72px)` |
| Team `h2` | `clamp(40px, 4vw, 58px)` |
| Eyebrow labels | `12px`, uppercase/letter-spaced |
| Buttons | `14px`, bold |

Heading rules:

- Major section headings `01-04` do not use trailing periods.
- Chinese headings use deliberate manual line breaks.
- Desktop hero and team headings are locked with `white-space: nowrap` on each manually broken line.
- Mobile hero Chinese title is tuned so `寻找治疗新路径` stays on one line.

Approved hero title:

```text
从肿瘤演化中，
寻找治疗新路径
```

Approved team heading:

```text
临床问题出发，
跨学科协作推进
```

## 5. Page Structure

The site is a single-page static document:

```text
public/index.html
public/styles.css
public/script.js
```

Main sections:

1. Header and navigation.
2. Hero profile card.
3. Highlight statistics.
4. Research directions.
5. Research model / path-dependent evolution.
6. Team and platform.
7. Selected work.
8. Contact and CV downloads.
9. Footer.

## 6. Header

Header components:

- Brand mark: `LH`
- Chinese name: `皇甫龙韬`
- English name: `LONGTAO HUANGFU`
- Desktop nav:
  - Research / 研究
  - Team / 团队
  - Work / 成果
  - Contact / 联系
- Language toggle: `中 / EN`

Layout:

```css
.site-header {
  width: min(1320px, calc(100% - 48px));
  height: 92px;
}
```

Mobile:

- Hide `.desktop-nav`.
- Keep brand and language toggle visible.

## 7. Hero Section

Desktop layout:

```css
.hero {
  min-height: 720px;
  display: grid;
  grid-template-columns: minmax(0, 1.22fr) minmax(0, .78fr);
  gap: 4vw;
  align-items: center;
}
```

Hero content:

Chinese:

```text
肿瘤药理学 · 转化研究
从肿瘤演化中，
寻找治疗新路径

我是皇甫龙韬，北京大学肿瘤医院助理教授、副研究员、博士生导师。我的研究聚焦胃癌演化、染色体外 DNA 与新型抗肿瘤药物开发。
```

English:

```text
ONCOLOGY PHARMACOLOGY · TRANSLATIONAL RESEARCH
Tracing tumor evolution.
Designing new therapies.

I am Longtao Huangfu, Assistant Professor, Research Associate Fellow and PhD Supervisor at Peking University Cancer Hospital. My work focuses on gastric cancer evolution, extrachromosomal DNA and novel anti-tumor drug development.
```

Actions:

- `了解我的研究` / `Explore my research`
- `发邮件联系` / `Email me`

Meta:

- `PKU Cancer Hospital`
- `Beijing, China`

## 8. Avatar Style

Final file:

```text
public/assets/images/avatar-stomach.jpeg
```

Final style:

- Identity-preserving cartoon avatar based on the professional portrait.
- Polished academic editorial illustration.
- Clean ink-like contour lines.
- Soft gouache/watercolor shading.
- Warm ivory paper background.
- Subtle molecule motifs and faint cell sketches.
- Navy blazer and pale blue shirt preserved.
- Rectangular glasses preserved.
- Calm professional expression preserved.
- Muted pale-blue stomach silhouette behind the subject.
- No text, labels, gore, or bright red anatomy.

The first generated avatar had a muted blue circular background. It was revised because the circular halo was visually generic. The final avatar replaces that shape with a stomach silhouette to align with gastrointestinal oncology while keeping the same muted blue color.

Reusable avatar prompt:

```text
Transform the provided professional portrait into a polished academic editorial cartoon avatar while preserving the person's recognizable identity.

Preserve the subject's facial structure, rectangular glasses, short black hair, calm expression, navy blazer, and pale blue shirt. Use refined hand-drawn digital illustration with clean ink-like contour lines and softly layered gouache/watercolor shading.

Use a warm ivory paper background with subtle biomedical molecule motifs and faint cell sketches near the edges.

Replace the large background halo with a tasteful stylized human stomach silhouette in the same muted pale-blue color and watercolor texture. The stomach should be anatomically recognizable but elegant and abstract, placed behind the subject as a quiet gastrointestinal oncology motif.

No text, no watermark, no extra objects, no bright red or pink anatomy, no gore, no labels, no exaggerated caricature, no change to the person's identity.
```

Avatar asset handling:

- Save final web asset as JPEG to keep the first screen light.
- Use semantic filenames such as `avatar-stomach.jpeg`.
- Update both `<link rel="icon">` and hero `<img src>` when replacing the avatar.
- Use a new filename for major avatar replacements to avoid browser cache ambiguity.

## 9. Highlight Statistics

The highlight strip contains four cards:

| Value | Chinese | English |
| --- | --- | --- |
| `10+` | 近五年代表性 SCI 论文 | RECENT SCI PUBLICATIONS |
| `04` | 获批专利 | APPROVED PATENTS |
| `¥1M+` | 主持科研经费 | PI RESEARCH FUNDING |
| `03` | 核心研究方向 | CORE RESEARCH DIRECTIONS |

Layout:

- Desktop: 4 columns.
- Under 900px: 2 columns.

## 10. Research Directions

Section heading:

```text
01 / 研究方向
用进化视角理解
肿瘤治疗
```

English:

```text
01 / RESEARCH
Understanding therapy
through evolution
```

Intro copy:

```text
围绕胃癌耐药这一临床瓶颈，我关注肿瘤在治疗压力下如何改变、适应与锁定演化路径。
```

```text
To address drug resistance in gastric cancer, I study how tumors change, adapt and lock in evolutionary paths under therapeutic pressure.
```

Three research cards:

1. `ecDNA 与耐药演化` / `ecDNA & drug resistance`
2. `天然分子与小分子药物` / `Natural & small molecules`
3. `药物网络与联合治疗` / `Drug networks & combinations`

Card behavior:

- Border-grid layout.
- Warm paper background.
- Hover uses pale teal background and slight upward movement.
- Card number uses serif display type and rust accent.

## 11. Research Model Section

Asset:

```text
public/assets/images/ecdna-pathways.png
```

Section label:

```text
研究模型 / PATH-DEPENDENT EVOLUTION
```

Heading:

```text
治疗压力下的路径选择
```

English heading:

```text
Path selection under therapeutic pressure
```

Concepts represented:

- ecDNA event.
- Adaptive threshold.
- Low-adaptation route.
- ecDNA amplification path.
- Resistant relapse path.
- Path locking.

## 12. Team and Platform Section

Section heading:

```text
02 / 团队与平台
临床问题出发，
跨学科协作推进
```

English:

```text
02 / TEAM & PLATFORM
Clinical questions
Collaborative answers
```

Copy:

```text
所在团队隶属于恶性肿瘤发病机制及转化研究教育部重点实验室，由季加孚院士领导，并与北京大学药学院紧密合作。
```

```text
Our team is part of the Key Laboratory of Carcinogenesis and Translational Research, led by Academician Jiafu Ji, with close collaboration across Peking University.
```

Assets:

- `public/assets/images/team-group.jpeg`
- `public/assets/images/lab.jpeg`

Platform bullets:

1. 胃肠肿瘤转化研究平台 / Gastrointestinal tumor translational platform
2. 天然药物与仿生药物协作 / Natural and biomimetic drug collaboration
3. 临床 + X 多学科研究支持 / Clinical + X interdisciplinary support

Layout:

```css
.team-grid {
  grid-template-columns: .9fr 1.1fr;
  gap: 56px;
}
```

Visual rhythm:

- Full-width dark section.
- Left side: text and platform bullets.
- Right side: team photo with lab photo overlay.
- Pale teal caption label.

## 13. Selected Work

Section heading:

```text
03 / 代表性成果
从机制发现到
转化策略
```

English:

```text
03 / SELECTED WORK
From mechanism
to translation
```

Current entries:

1. 2026  
   `Cisplatin-Induced ecDNA Enhances Tumor Aggressiveness and Accelerates Chemoresistance Acquisition in Gastric Cancer`  
   `Journal of Advanced Research, 2026 Jul 30:S2090-1232(26)00601-6`  
   Tag: `ecDNA`

2. 2026  
   `TOPK Inhibition Promotes Anti-Tumor Immunity Via eIF4F Complex Mediated STAT1 Translation in Gastric Cancer`  
   `Advanced Science, 13(13):e17380. doi: 10.1002/advs.202517380`  
   Tag: `TOPK`

3. 2025  
   `Exploring the potential of extrachromosomal DNA as a novel oncogenic driver`  
   `Science China Life Sciences, 68(1): 144-157`  
   Tag: `ecDNA`

4. 2024  
   `The deubiquitinase USP15 drives malignant progression of gastric cancer through glucose metabolism remodeling`  
   `Journal of Experimental & Clinical Cancer Research, 43(1):235`  
   Tag: `USP15`

5. 2023  
   `Piceatannol enhances Beclin-1 activity to suppress tumor progression and its combination therapy strategy with everolimus`  
   `Science China Life Sciences, 66(2): 298-312`  
   Tag: `BECLIN-1`

Format rule for future additions:

```text
Year / Article title / Journal citation without author list / Short scientific tag
```

## 14. Contact and CV

Section heading:

```text
04 / 联系方式
期待交流
```

English:

```text
04 / CONTACT
Let’s connect
```

Contact copy:

```text
欢迎围绕肿瘤演化、胃癌耐药与抗肿瘤药物开发开展学术交流。
```

```text
I welcome conversations around tumor evolution, gastric cancer resistance and anti-tumor drug development.
```

Links:

- Email: `ydlongtao@bjmu.edu.cn`
- Profile: `https://teach.bjcancer.org/Html/Teachers/Index/852.html`
- Chinese CV: `public/assets/files/longtao-huangfu-cv-cn.pdf`
- English CV: `public/assets/files/longtao-huangfu-cv-en.pdf` (updated from `CV_20260819.pdf`)

Rule:

- Both downloadable CV files must remain PDF.
- Do not publish DOCX CV files.

## 15. Bilingual Implementation

The static site uses `.zh` and `.en` elements:

```css
.en { display: none; }
body.lang-en .zh { display: none; }
body.lang-en .en { display: inline; }
body.lang-en p.en { display: block; }
```

`public/script.js`:

- Toggles `body.lang-en`.
- Updates `document.documentElement.lang`.
- Updates the language toggle label.
- Stores the preferred language in `localStorage`.

Maintenance rule:

- Any user-facing content update should update both Chinese and English strings.
- Section structure should remain parallel across languages.

## 16. Responsive Layout

Breakpoints:

- `max-width: 900px`: major two-column layouts collapse to one column.
- `max-width: 600px`: mobile-specific header, hero, avatar, statistics, and contact spacing.
- `min-width: 601px`: hero title line fragments are set to `white-space: nowrap`.
- `min-width: 901px`: team heading line fragments are set to `white-space: nowrap`.

Mobile requirements:

- Hide desktop navigation.
- Show avatar before hero text.
- Keep `寻找治疗新路径` on one line.
- Avoid single-character orphan lines.
- Prevent horizontal overflow with `overflow-x: hidden`.
- Keep images at `max-width: 100%`.

## 17. Public Assets

Current public assets:

```text
public/assets/files/longtao-huangfu-cv-cn.pdf
public/assets/files/longtao-huangfu-cv-en.pdf
public/assets/images/avatar-stomach.jpeg
public/assets/images/ecdna-pathways.png
public/assets/images/lab.jpeg
public/assets/images/team-group.jpeg
```

These assets are safe to commit and publish.

## 18. Privacy and Repository Hygiene

Do not commit:

- Original portrait source file.
- Original PPTX file.
- Original Chinese DOCX CV.
- Original English CV source file outside the public PDF.
- Local QA screenshots.
- `.netlify/`.
- `.DS_Store`.
- Build/cache folders.
- Local generated experiments not intended for publication.

Before committing:

```bash
git status --short --branch
git diff --cached --name-status
```

Only commit files explicitly intended for the public repository.

## 19. Deployment

Netlify production deploy:

```bash
npx netlify-cli deploy --prod --dir public
```

Netlify configuration:

```text
netlify.toml
```

The publish directory is:

```text
public
```

Security headers are configured in `netlify.toml`.

## 20. Maintenance Checklist

For visual changes:

- Check desktop and mobile layouts.
- Check Chinese line breaks.
- Check English line breaks.
- Check avatar image load and crop.
- Check all images load.
- Check contact and CV links.

For content changes:

- Update Chinese and English versions.
- Keep section titles clean and without trailing periods.
- Preserve the academic editorial tone.
- Keep CV downloads as PDF.

For GitHub updates:

- Confirm remote is `ydlongtao/ydlongtao-personal-site`.
- Avoid committing raw source materials.
- Push only reviewed files.
