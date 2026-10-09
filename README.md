# Tugas Rutin 4 — Konversi CSS ke SCSS

Konversi CSS dari Tugas Pertemuan 2 (Portofolio) ke **SCSS** dengan struktur modular **7-1 pattern**.

## Cara menjalankan

```bash
npm install
npm run dev        # server development Vite (SCSS di-compile otomatis)
npm run build      # build production ke folder dist/
npm run sass       # compile manual dengan Dart Sass -> css/style.css
```

## Struktur folder (7-1 pattern)

```
scss/
├── abstracts/      # variables & mixins (tidak menghasilkan CSS)
│   ├── _variables.scss
│   ├── _mixins.scss
│   └── _index.scss
├── vendors/        # CSS pihak ketiga (belum dipakai)
├── base/           # reset & tipografi
├── layout/         # header, navigation, main, aside, footer
├── components/     # eyebrow, figure, form, button
├── pages/          # style khusus halaman utama
├── themes/         # tema gelap + CSS custom properties
└── main.scss       # entry point, memanggil semua folder dengan @use
```

## Checklist requirements

| No | Requirement | Penerapan |
|----|-------------|-----------|
| 1 | Konversi CSS existing ke SCSS | Seluruh isi `style.css` Pertemuan 2 dipindah ke partial di `scss/` |
| 2 | Variables untuk colors & spacing | `abstracts/_variables.scss` (`$accent`, `$ink-900`, `$space-md`, `$space-2xl`, dst.) |
| 3 | Nesting maksimal 3 level | Contoh: `nav → a → &:hover`, `header → > p → &::before` |
| 4 | Minimal 3 mixins reusable | `respond-to`, `mono-text`, `card`, `focus-ring`, `transition`, `container` |
| 5 | Struktur 7-1 pattern (partials) | Lihat struktur folder di atas |
| 6 | Pakai `@use` (bukan `@import`) | Semua partial memakai `@use` / `@forward` |
| 7 | Minimal 1 `@each` / `@for` | `@each` di `themes/_dark.scss`, `base/_typography.scss`, `components/_form.scss`, `abstracts/_mixins.scss` |
| 8 | Compile dengan Vite / Dart Sass | `npm run dev` / `npm run build` (Vite) dan `npm run sass` (Dart Sass) |
