# mountainfyi-embed

[![npm](https://img.shields.io/npm/v/mountainfyi-embed)](https://www.npmjs.com/package/mountainfyi-embed)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.7-blue)](https://www.typescriptlang.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)](https://www.npmjs.com/package/mountainfyi-embed)

Embed **MountainFYI** widgets — mountains, glossary terms, interactive tools, and inline elements — on any website. **6 widget types**, zero dependencies, Shadow DOM style isolation, 4 built-in themes (light, dark, sepia, auto), 2 styles (modern, clean), and live data from the [MountainFYI](https://mountainfyi.com) database.

Every widget includes a "Powered by MountainFYI" backlink directing readers to the full reference.

> **Try the interactive widget builder at [widget.mountainfyi.com](https://widget.mountainfyi.com)**

## Quick Start

```html
<!-- Place widget div where you want it to appear -->
<div data-mountainfyi="entity" data-slug="mountains" data-theme="light"></div>

<!-- Load the embed script once, anywhere on the page -->
<script src="https://cdn.jsdelivr.net/npm/mountainfyi-embed@1/dist/embed.min.js"></script>
```

That's it. The widget fetches data from the MountainFYI API and renders with full style isolation.

## Widget Types

| Type | Usage | Description |
|------|-------|-------------|
| `entity` | `<div data-mountainfyi="entity" data-slug="..."></div>` | Entity detail card — city, mountain, earthquake, or postal code |
| `glossary` | `<div data-mountainfyi="glossary" data-slug="..."></div>` | Glossary term definition with cross-references |
| `faq` | `<div data-mountainfyi="faq" data-slug="..."></div>` | FAQ accordion with expand/collapse |
| `search` | `<div data-mountainfyi="search" data-slug="..."></div>` | Search box linking to the full database |
| `elevation-badge` | `<div data-mountainfyi="elevation-badge" data-slug="..."></div>` | Inline elevation badge with altitude display |
| `difficulty-badge` | `<div data-mountainfyi="difficulty-badge" data-slug="..."></div>` | Inline climbing difficulty grade badge |

## Widget Options

| Attribute | Values | Default | Description |
|-----------|--------|---------|-------------|
| `data-mountainfyi` | entity, glossary, faq, search, [tools] | required | Widget type |
| `data-slug` | e.g. "mountains" | — | Entity slug from the MountainFYI database |
| `data-theme` | light, dark, sepia, auto | light | Visual theme (`auto` follows OS preference) |
| `data-style` | modern, clean | modern | Widget design style |
| `data-size` | default, compact, large | default | Widget size |
| `data-placeholder` | any string | "Search Mountains..." | Search box placeholder |

## Themes

```html
<!-- Light (default) -->
<div data-mountainfyi="entity" data-slug="mountains" data-theme="light"></div>

<!-- Dark -->
<div data-mountainfyi="entity" data-slug="mountains" data-theme="dark"></div>

<!-- Sepia -->
<div data-mountainfyi="entity" data-slug="mountains" data-theme="sepia"></div>

<!-- Auto — follows OS dark/light preference -->
<div data-mountainfyi="entity" data-slug="mountains" data-theme="auto"></div>
```

## Styles

```html
<!-- Modern (default) — clean lines, rounded corners, accent gradients -->
<div data-mountainfyi="entity" data-slug="mountains" data-style="modern"></div>

<!-- Clean — minimal borders, utility-focused, data-first aesthetic -->
<div data-mountainfyi="entity" data-slug="mountains" data-style="clean"></div>
```

## Web Components (Custom Elements)

As an alternative to `data-*` attributes, you can use native HTML custom elements:

```html
<!-- Custom element form -->
<mountainfyi-entity slug="mountains" theme="light"></mountainfyi-entity>
<mountainfyi-search placeholder="Search Mountains..."></mountainfyi-search>

<script src="https://cdn.jsdelivr.net/npm/mountainfyi-embed@1/dist/embed.min.js"></script>
```

Use `style-variant` (not `style`) to avoid conflicts with the HTML reserved `style` attribute.

## Examples

### Entity Card

```html
<div data-mountainfyi="entity" data-slug="mountains" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/mountainfyi-embed@1/dist/embed.min.js"></script>
```

### Search Box

```html
<div data-mountainfyi="search" data-placeholder="Search Mountains..."></div>
<script src="https://cdn.jsdelivr.net/npm/mountainfyi-embed@1/dist/embed.min.js"></script>
```

### Glossary Term

```html
<div data-mountainfyi="glossary" data-slug="example-term" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/mountainfyi-embed@1/dist/embed.min.js"></script>
```

## CDN Options

### jsDelivr (recommended — global CDN, auto-updates with npm)

```html
<script src="https://cdn.jsdelivr.net/npm/mountainfyi-embed@1/dist/embed.min.js"></script>
```

### Specific version (production stability)

```html
<script src="https://cdn.jsdelivr.net/npm/mountainfyi-embed@1.0.0/dist/embed.min.js"></script>
```

### npm (for bundlers)

```bash
npm install mountainfyi-embed
```

```javascript
import 'mountainfyi-embed';
```

## Technical Details

- **Shadow DOM**: Complete style isolation — no CSS conflicts with your site
- **Zero dependencies**: No jQuery, React, or any external library
- **2 styles**: Modern (accent gradients) and Clean (minimal, data-first)
- **4 themes**: Light, Dark, Sepia, Auto (OS preference detection)
- **CORS**: MountainFYI API has CORS enabled for all origins
- **MutationObserver**: Works with dynamically added elements (SPAs)
- **IntersectionObserver**: Lazy loading — widgets only fetch when entering viewport (200px margin)
- **Rich Snippets**: DefinedTerm JSON-LD injected for glossary widgets
- **Bundle size**: Tree-shaken per site — only includes tools available on MountainFYI

## Learn More About Mountains

Visit [mountainfyi.com](https://mountainfyi.com) — MountainFYI is a comprehensive mountains reference with interactive tools, guides, and developer resources.

- **API docs**: [mountainfyi.com/developers/](https://mountainfyi.com/developers/)
- **Widget builder**: [widget.mountainfyi.com](https://widget.mountainfyi.com)
- **npm package**: [npmjs.com/package/mountainfyi-embed](https://www.npmjs.com/package/mountainfyi-embed)
- **GitHub**: [github.com/fyipedia/mountainfyi-embed](https://github.com/fyipedia/mountainfyi-embed)

## Geo FYI Family

Part of [FYIPedia](https://fyipedia.com) — open-source developer tools ecosystem. Geo FYI covers distance, mountains, earthquakes, and postal codes. Hub: [earthfyi.com](https://earthfyi.com).

| Site | Domain | Focus | Package |
|------|--------|-------|---------|
| DistanceFYI | [distancefyi.com](https://distancefyi.com) | 33,336 cities, Haversine distance, travel times | [npm](https://www.npmjs.com/package/distancefyi-embed) |
| **MountainFYI** | [mountainfyi.com](https://mountainfyi.com) | 2,000 mountains, elevation, difficulty grades | **[npm](https://www.npmjs.com/package/mountainfyi-embed)** |
| QuakeFYI | [quakefyi.com](https://quakefyi.com) | 20,702 earthquakes, magnitude scale, USGS alerts | [npm](https://www.npmjs.com/package/quakefyi-embed) |
| ZipFYI | [zipfyi.com](https://zipfyi.com) | 41,488 postal codes, demographics, median income | [npm](https://www.npmjs.com/package/zipfyi-embed) |

## FYIPedia Developer Tools

| Package | PyPI | npm | Description |
|---------|------|-----|-------------|
| colorfyi | [PyPI](https://pypi.org/project/colorfyi/) | [npm](https://www.npmjs.com/package/@fyipedia/colorfyi) | Color conversion, WCAG contrast, harmonies — [colorfyi.com](https://colorfyi.com) |
| emojifyi | [PyPI](https://pypi.org/project/emojifyi/) | [npm](https://www.npmjs.com/package/emojifyi) | Emoji encoding & metadata for 3,953 emojis — [emojifyi.com](https://emojifyi.com) |
| unitfyi | [PyPI](https://pypi.org/project/unitfyi/) | [npm](https://www.npmjs.com/package/unitfyi) | Unit conversion, 220 units — [unitfyi.com](https://unitfyi.com) |
| timefyi | [PyPI](https://pypi.org/project/timefyi/) | [npm](https://www.npmjs.com/package/timefyi) | Timezone ops & business hours — [timefyi.com](https://timefyi.com) |
| holidayfyi | [PyPI](https://pypi.org/project/holidayfyi/) | [npm](https://www.npmjs.com/package/holidayfyi) | Holiday dates & Easter calculation — [holidayfyi.com](https://holidayfyi.com) |
| namefyi | [PyPI](https://pypi.org/project/namefyi/) | [npm](https://www.npmjs.com/package/namefyi) | Korean romanization & Five Elements — [namefyi.com](https://namefyi.com) |
| distancefyi | [PyPI](https://pypi.org/project/distancefyi/) | [npm](https://www.npmjs.com/package/distancefyi) | Haversine distance & travel times — [distancefyi.com](https://distancefyi.com) |
| fyipedia | [PyPI](https://pypi.org/project/fyipedia/) | — | Unified CLI for all FYI tools — [fyipedia.com](https://fyipedia.com) |

## License

MIT — see [LICENSE](./LICENSE).

Built with care by [FYIPedia](https://fyipedia.com).
