# widequran-embed

[![npm](https://img.shields.io/npm/v/widequran-embed)](https://www.npmjs.com/package/widequran-embed)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)](https://www.npmjs.com/package/widequran-embed)
[![Size](https://img.shields.io/badge/size-~5KB-green)](https://bundlephobia.com/package/widequran-embed)

Embed WideQuran scripture widgets on any website. **Zero dependencies**, Shadow DOM style isolation, 3 built-in themes (light, dark, sepia), and automatic daily ayah updates. Each widget includes a "Powered by WideQuran" backlink.

WideQuran covers **114 surahs**, **6,236 ayahs**, Arabic Uthmani script, 5 English translations (Sahih International, Pickthall, Yusuf Ali, Shakir, Hilali-Khan), **7,604 hadith**, and **1,896 tafsir entries** — all accessible via free public API with CORS enabled for any origin.

> **Try the interactive widget builder at [widget.widequran.com](https://widget.widequran.com)**

<p align="center">
  <img src="demo.gif" alt="widequran-embed demo — Quran verse widget with Arabic Uthmani script and English translation, light/dark/sepia themes" width="800">
</p>

## Table of Contents

- [Quick Start](#quick-start)
- [What You Can Do](#what-you-can-do)
  - [Verse Card — Single Ayah Display](#verse-card--single-ayah-display)
  - [Chapter Card — Full Surah with Navigation](#chapter-card--full-surah-with-navigation)
  - [Comparison Card — Side-by-Side Ayah Comparison](#comparison-card--side-by-side-ayah-comparison)
  - [Verse of the Day — Auto-Updating Daily Widget](#verse-of-the-day--auto-updating-daily-widget)
  - [Search Box — Full-Text Quran Search](#search-box--full-text-quran-search)
- [Widget Options](#widget-options)
- [Themes](#themes)
- [CDN Options](#cdn-options)
- [Technical Details](#technical-details)
- [Learn More About the Quran](#learn-more-about-the-quran)
- [WideHoly Scripture Family](#wideholy-scripture-family)
- [License](#license)

## Quick Start

```html
<!-- Place widget div where you want it to appear -->
<div data-widequran="verse" data-ref="2:255" data-theme="light"></div>

<!-- Load the embed script once, anywhere on the page -->
<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1/dist/embed.min.js"></script>
```

That's it. The widget loads, fetches the ayah from the WideQuran API, and renders it with full style isolation. References follow the standard `surah:ayah` format used in Islamic scholarship (e.g., `2:255` = Al-Baqarah ayah 255, Ayat al-Kursi).

## What You Can Do

The Quran was revealed to the Prophet Muhammad (peace be upon him) over 23 years and compiled into its final form during the caliphate of Uthman ibn Affan. The text is divided into 114 surahs (chapters) containing 6,236 ayahs (verses), organized by revelation length — longer surahs first (with the exception of Al-Fatihah). WideQuran presents the complete Arabic Uthmani script alongside scholarly English translations, enabling developers to embed authentic Quranic content on any platform.

### Verse Card — Single Ayah Display

A Verse Card renders a single ayah in Arabic Uthmani script with English translation beneath. Arabic text renders right-to-left with proper ligatures. The default translation is Sahih International (2012), widely regarded for accuracy and modern readability.

| Translation | Code | Scholar/Year |
|-------------|------|--------------|
| Sahih International | `sahih` | Multiple scholars, 2012 |
| Pickthall | `pickthall` | Mohammed Pickthall, 1930 |
| Yusuf Ali | `yusuf` | Abdullah Yusuf Ali, 1934 |
| Shakir | `shakir` | M.H. Shakir, 1999 |
| Hilali-Khan | `hilali` | Khan & Hilali, 1996 |

```html
<!-- Ayat al-Kursi (2:255) — The Throne Verse, most recited single ayah -->
<div data-widequran="verse"
  data-ref="2:255"
  data-theme="light">
</div>

<!-- Al-Fatiha (1:1) with Arabic script visible -->
<div data-widequran="verse"
  data-ref="1:1"
  data-translation="sahih"
  data-show-original="true"
  data-theme="sepia">
</div>

<!-- Al-Ikhlas (112:1) in Pickthall translation, compact -->
<div data-widequran="verse"
  data-ref="112:1"
  data-translation="pickthall"
  data-size="compact"
  data-theme="dark">
</div>

<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1/dist/embed.min.js"></script>
```

**Available options for Verse Card:**

| Attribute | Values | Default |
|-----------|--------|---------|
| `data-ref` | `"surah:ayah"` e.g. `2:255` | required |
| `data-translation` | `sahih`, `pickthall`, `yusuf`, `shakir`, `hilali` | `sahih` |
| `data-show-original` | `true`, `false` | `false` (shows Arabic script) |
| `data-theme` | `light`, `dark`, `sepia` | `light` |
| `data-size` | `default`, `compact` | `default` |

Learn more: [Quran Verse Lookup — widequran.com](https://widequran.com) · [Ayat al-Kursi — The Throne Verse](https://widequran.com) · [Al-Fatiha — The Opening](https://widequran.com)

### Chapter Card — Full Surah with Navigation

A Chapter Card renders all ayahs in a surah with previous/next navigation. The 114 surahs vary dramatically in length — Al-Kawthar (108) has 3 ayahs while Al-Baqarah (2) has 286. Chapter Cards adapt their layout accordingly.

Surahs are classified as Meccan (revealed in Mecca, earlier revelations, mostly shorter — 86 surahs) or Medinan (revealed in Medina, later revelations, often longer — 28 surahs). This classification appears in the Chapter Card header.

```html
<!-- Al-Fatiha (Chapter 1) — The Opening, recited in every prayer -->
<div data-widequran="chapter"
  data-ref="1"
  data-theme="light">
</div>

<!-- Ya-Sin (Chapter 36) — Heart of the Quran, 83 ayahs -->
<div data-widequran="chapter"
  data-ref="36"
  data-translation="sahih"
  data-theme="sepia">
</div>

<!-- Al-Mulk (Chapter 67) — The Sovereignty, 30 ayahs, protection surah -->
<div data-widequran="chapter"
  data-ref="67"
  data-show-original="true"
  data-theme="dark">
</div>

<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1/dist/embed.min.js"></script>
```

Learn more: [Browse All 114 Surahs — widequran.com](https://widequran.com) · [Meccan vs Medinan Surahs](https://widequran.com) · [Short Surahs (Juz Amma)](https://widequran.com)

### Comparison Card — Side-by-Side Ayah Comparison

Compare any two ayahs — useful for showing thematic parallels across surahs, comparing how different translations render a difficult passage, or displaying related concepts across the Quran.

The Quran contains numerous internal cross-references — for example, the story of Moses appears in over 30 surahs with complementary details in each. The Comparison Card makes these parallels visible.

```html
<!-- Compare two descriptions of Paradise: 56:15-16 vs 76:13 -->
<div data-widequran="compare"
  data-a="56:15"
  data-b="76:13"
  data-theme="light">
</div>

<!-- Compare two translations of the Basmala: sahih vs pickthall -->
<div data-widequran="compare"
  data-a="1:1"
  data-b="1:1"
  data-translation="sahih"
  data-theme="sepia">
</div>

<!-- Compare two ayahs on tawakkul (trust in God): 3:159 vs 65:3 -->
<div data-widequran="compare"
  data-a="3:159"
  data-b="65:3"
  data-show-original="true"
  data-theme="dark">
</div>

<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1/dist/embed.min.js"></script>
```

Learn more: [Quran Thematic Index — widequran.com](https://widequran.com) · [Tafsir Entries — 1,896 commentaries](https://widequran.com) · [Cross-References](https://widequran.com)

### Verse of the Day — Auto-Updating Daily Widget

The Verse of the Day widget displays a curated ayah that changes automatically each day. Results are cached in localStorage and refresh at midnight UTC — no server calls on repeat visits within the same day.

The daily ayah selection covers 365 passages from across the Quran — including the 99 Names of Allah, guidance ayahs, mercy and compassion themes, and widely memorized passages from the last 30 juz.

```html
<!-- Verse of the Day — full size, light theme -->
<div data-widequran="votd" data-theme="light"></div>

<!-- Verse of the Day — dark theme for dark websites -->
<div data-widequran="votd" data-theme="dark"></div>

<!-- Verse of the Day — sepia, warm book-like tone -->
<div data-widequran="votd" data-theme="sepia"></div>

<!-- Compact for narrow sidebars (ayah + surah name only) -->
<div data-widequran="votd" data-theme="light" data-size="compact"></div>

<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1/dist/embed.min.js"></script>
```

Learn more: [Daily Quran Verse — widequran.com](https://widequran.com) · [Quran Reading Schedule](https://widequran.com) · [Memorization Guide — Juz Amma](https://widequran.com)

### Search Box — Full-Text Quran Search

Embed a full-text search box that queries all 6,236 ayahs across all 5 translations simultaneously. Results appear in a dropdown as the user types, with surah name, ayah number, and a highlighted snippet. Clicking a result opens the full ayah on widequran.com.

Arabic transliteration search is also supported — searching "bismillah" returns results matching the Basmala even without Arabic keyboard input.

```html
<!-- Default search box -->
<div data-widequran="search"
  data-placeholder="Search Quran verses…"
  data-theme="light">
</div>

<!-- Arabic-friendly placeholder -->
<div data-widequran="search"
  data-placeholder="Search Quran or transliteration…"
  data-theme="sepia">
</div>

<!-- Dark theme search -->
<div data-widequran="search"
  data-placeholder="Find an ayah…"
  data-theme="dark">
</div>

<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1/dist/embed.min.js"></script>
```

Learn more: [Quran Search — widequran.com](https://widequran.com) · [Quran Topics Index](https://widequran.com) · [API Search Endpoint](https://widequran.com/developers/)

## Widget Options

All widget types share these common attributes:

| Attribute | Values | Default | Description |
|-----------|--------|---------|-------------|
| `data-widequran` | `verse`, `chapter`, `compare`, `votd`, `search` | required | Widget type |
| `data-ref` | `"surah:ayah"` e.g. `2:255` | — | Ayah or surah reference |
| `data-a` | ayah reference | — | First ayah for comparison |
| `data-b` | ayah reference | — | Second ayah for comparison |
| `data-theme` | `light`, `dark`, `sepia` | `light` | Visual theme |
| `data-size` | `default`, `compact` | `default` | Compact suits sidebars under 300px |
| `data-translation` | `sahih`, `pickthall`, `yusuf`, `shakir`, `hilali` | `sahih` | English translation |
| `data-show-original` | `true`, `false` | `false` | Show Arabic Uthmani script |
| `data-placeholder` | any string | `"Search Quran…"` | Placeholder for search widget |

## Themes

WideQuran widgets support 3 themes:

```html
<!-- Light — white background, dark text, teal/green accent -->
<div data-widequran="votd" data-theme="light"></div>

<!-- Dark — dark background, light text, teal accent -->
<div data-widequran="votd" data-theme="dark"></div>

<!-- Sepia — warm parchment background — evokes Islamic manuscript tradition -->
<div data-widequran="votd" data-theme="sepia"></div>
```

All themes are self-contained inside Shadow DOM — they never affect or inherit from your site's CSS.

## CDN Options

### jsDelivr (recommended — global CDN, auto-updates with npm)

```html
<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1/dist/embed.min.js"></script>
```

Pin to a specific version for production stability:

```html
<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1.0.1/dist/embed.min.js"></script>
```

### R2 CDN (widequran.com hosted)

```html
<script src="https://cdn.widequran.com/embed.min.js"></script>
```

### npm (for bundlers — Webpack, Vite, Rollup)

```bash
npm install widequran-embed
```

```javascript
import 'widequran-embed';
```

## Technical Details

- **Shadow DOM**: Complete style isolation — no CSS conflicts with your site. Widgets are fully encapsulated.
- **Zero dependencies**: No jQuery, React, Vue, or any external library. Pure browser APIs only.
- **RTL support**: Arabic text renders correctly right-to-left with proper Uthmani script ligatures.
- **System fonts**: No Google Fonts request — widgets use system font stack and load instantly.
- **CORS**: WideQuran API has CORS enabled for all origins — no proxy needed.
- **Caching**: Verse of the Day cached in localStorage, refreshes daily at midnight UTC.
- **MutationObserver**: Works with dynamically added elements (React, Vue, Angular SPAs).
- **Bundle size**: ~5KB gzipped.
- **Accent color**: Teal/green (`#0D9488`) — matches the WideQuran brand.
- **API base**: `https://widequran.com/api/v1/` — free, no authentication required.

## Learn More About the Quran

- **Browse**: [All 114 Surahs — widequran.com](https://widequran.com) · [Juz Amma (30th Part)](https://widequran.com) · [Meccan Surahs](https://widequran.com) · [Medinan Surahs](https://widequran.com)
- **Study**: [Tafsir — 1,896 commentaries](https://widequran.com) · [Hadith — 7,604 narrations](https://widequran.com) · [Quran Topics Index](https://widequran.com)
- **Translations**: [Sahih International](https://widequran.com/translations/) · [Pickthall Translation](https://widequran.com/translations/) · [Yusuf Ali Translation](https://widequran.com/translations/)
- **Tools**: [Ayah Lookup](https://widequran.com) · [Surah Browser](https://widequran.com) · [Widget Builder](https://widget.widequran.com)
- **API**: [REST API Docs](https://widequran.com/developers/) · [OpenAPI Spec](https://widequran.com/api/openapi.json)

## WideHoly Scripture Family

Part of [WideHoly](https://wideholy.com) — Scripture for everyone.

| Site | Domain | Scripture |
|------|--------|-----------|
| WideBible | [widebible.com](https://widebible.com) | 66 books, 31,102 verses, KJV/ASV/BBE/YLT, 1,833 people |
| **WideQuran** | [widequran.com](https://widequran.com) | **114 surahs, 6,236 ayahs, Arabic Uthmani + 5 translations, 7,604 hadith** |
| WideTorah | [widetorah.com](https://widetorah.com) | 24 books, 23,145 verses, Hebrew Masoretic + English, 54 parashot |
| WideGita | [widegita.com](https://widegita.com) | 18 chapters, 700 verses, Sanskrit Devanagari + 9 commentators |
| WideSutra | [widesutra.com](https://widesutra.com) | 5 collections, 5,326 texts, Pali + English |
| WideHoly | [wideholy.com](https://wideholy.com) | 5 religions, 236,000+ scripture records, cross-religion comparison |

## License

MIT — see [LICENSE](./LICENSE).

Built with care by [WideHoly](https://wideholy.com).
