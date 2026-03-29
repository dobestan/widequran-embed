# widequran-embed

[![npm](https://img.shields.io/npm/v/widequran-embed)](https://www.npmjs.com/package/widequran-embed)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)](https://www.npmjs.com/package/widequran-embed)
[![Size](https://img.shields.io/badge/size-~5KB-green)](https://bundlephobia.com/package/widequran-embed)

Embed WideQuran scripture widgets on any website. **Zero dependencies**, Shadow DOM style isolation, 3 built-in themes (light, dark, sepia), and automatic daily verse updates. Each widget includes a "Powered by WideQuran" backlink.

> **Try the interactive widget builder at [widget.widequran.com](https://widget.widequran.com)**

## Quick Start

```html
<!-- Place widget div where you want it to appear -->
<div data-widequran="verse" data-ref="2:255" data-theme="light"></div>

<!-- Load the embed script once, anywhere on the page -->
<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1/dist/embed.min.js"></script>
```

That's it. The widget will load, fetch the verse from the WideQuran API, and render it with full style isolation.

## Widget Types

| Type | Usage |
|------|-------|
| Verse Card | `<div data-widequran="verse" data-ref="..." data-theme="light"></div>` |
| Chapter Card | `<div data-widequran="chapter" data-ref="..."></div>` |
| Comparison Card | `<div data-widequran="compare" data-a="..." data-b="..."></div>` |
| Verse of the Day | `<div data-widequran="votd" data-theme="light"></div>` |
| Search Box | `<div data-widequran="search" data-placeholder="..."></div>` |

## Widget Options

| Attribute | Values | Default | Description |
|-----------|--------|---------|-------------|
| `data-widequran` | verse, chapter, person, compare, votd, search | required | Widget type |
| `data-ref` | "2:255" | — | Verse/chapter reference |
| `data-slug` | "moses", "paul" | — | Person slug (person widget only) |
| `data-a` | verse ref | — | First verse for comparison |
| `data-b` | verse ref | — | Second verse for comparison |
| `data-theme` | light, dark, sepia | light | Visual theme |
| `data-size` | default, compact | default | Widget size |
| `data-translation` | sahih, etc. | sahih | Translation code |
| `data-show-original` | true, false | false | Show original language text |
| `data-placeholder` | any string | "Search Quran…" | Search box placeholder |

## Themes

```html
<!-- Light (default) -->
<div data-widequran="votd" data-theme="light"></div>

<!-- Dark -->
<div data-widequran="votd" data-theme="dark"></div>

<!-- Sepia (warm, book-like) -->
<div data-widequran="votd" data-theme="sepia"></div>
```

## CDN Options

### jsDelivr (recommended — global CDN, auto-updates with npm)

```html
<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1/dist/embed.min.js"></script>
```

### R2 CDN (widequran.com hosted)

```html
<script src="https://cdn.widequran.com/embed.min.js"></script>
```

### npm (for bundlers)

```bash
npm install widequran-embed
```

```javascript
import 'widequran-embed';
```

## Examples

### Verse of the Day

```html
<div data-widequran="votd" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1/dist/embed.min.js"></script>
```

### Verse with Original Language

```html
<div data-widequran="verse"
  data-ref="2:255"
  data-show-original="true"
  data-theme="sepia">
</div>
<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1/dist/embed.min.js"></script>
```

### Compact Verse of the Day (sidebar use)

```html
<div data-widequran="votd" data-theme="light" data-size="compact"></div>
<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1/dist/embed.min.js"></script>
```

### Search Box

```html
<div data-widequran="search" data-placeholder="Search Quran…"></div>
<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1/dist/embed.min.js"></script>
```

## Technical Details

- **Shadow DOM**: Complete style isolation — no CSS conflicts with your site
- **Zero dependencies**: No jQuery, React, or any external library
- **System fonts**: No Google Fonts request — loads instantly
- **CORS**: WideQuran API has CORS enabled for all origins
- **Caching**: Verse of the Day cached in localStorage (refreshes daily)
- **MutationObserver**: Works with dynamically added elements (SPAs)
- **Bundle size**: ~5KB gzipped

## Learn More About Quran

Visit [widequran.com](https://widequran.com) — WideQuran is a comprehensive Quran reference with full text, translations, and study tools.

- **API docs**: [widequran.com/developers/](https://widequran.com/developers/)
- **Widget builder**: [widget.widequran.com](https://widget.widequran.com)
- **npm package**: [npmjs.com/package/widequran-embed](https://www.npmjs.com/package/widequran-embed)

## WideHoly Scripture Family

Part of [WideHoly](https://wideholy.com) — Scripture for everyone.

| Site | Domain | Scripture |
|------|--------|-----------|
| **WideBible** | [widebible.com](https://widebible.com) | Bible verses, chapters, people |
| **WideQuran** | [widequran.com](https://widequran.com) | Quran verses, surahs |
| **WideTorah** | [widetorah.com](https://widetorah.com) | Torah verses, portions |
| **WideGita** | [widegita.com](https://widegita.com) | Bhagavad Gita verses |
| **WideSutra** | [widesutra.com](https://widesutra.com) | Buddhist sutras, teachings |
| **WideHoly** | [wideholy.com](https://wideholy.com) | Multi-religion scripture hub |

## Embed Widget

Embed [WideQuran](https://widequran.com) widgets on any website with [widequran-embed](https://widget.widequran.com):

```html
<script src="https://cdn.jsdelivr.net/npm/widequran-embed@1/dist/embed.min.js"></script>
<div data-widequran="entity" data-slug="example"></div>
```

Zero dependencies · Shadow DOM · 4 themes (light/dark/sepia/auto) · [Widget docs](https://widget.widequran.com)

## License

MIT — see [LICENSE](./LICENSE).

Built with ❤️ by [WideHoly](https://wideholy.com).
