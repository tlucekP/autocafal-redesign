# Redesign Spec - autocafal.cz

## Cíl
Moderní, čistý a produkčně připravený statický web v Astro + Tailwind s minimem JS.

## IA a sekce
1. Hero (`#hero`)
2. Služby (`#sluzby`)
3. Ceník (`#cenik`)
4. Galerie (`#galerie`)
5. Kontakt (`#kontakt`)

## Komponenty
- `Header.astro`: sticky hlavička, anchor navigace.
- `Hero.astro`: hlavní claim + blok O nás.
- `ServicesGrid.astro`: služby jako grid karet.
- `Pricing.astro`: ceník ve sloupcích/tabulkách.
- `GalleryGrid.astro`: galerie grid + lightbox (minimum JS).
- `Contact.astro`: kontakt + externí formulář endpoint + UX validace.
- `Footer.astro`: patička.
- `MobileCtaBar.astro`: mobilní sticky CTA lišta.

## Content model (`src/content`)
- `site.json`: základní identita, kontakt, mapy, SEO, hero texty, O nás.
- `services.json`: položky služeb (karty).
- `pricing.json`: sekce ceníku a ceny.
- `gallery.json`: položky galerie.

## Map odkazy
- Google search URL (vyhledat adresu).
- Mapy.cz search URL (vyhledat adresu).

Obě URL jsou uloženy v `site.json` a používají se napříč UI.

## Formulář
- Endpoint je přes env proměnnou `PUBLIC_FORM_ENDPOINT` v `.env`.
- Podporované služby: Formspree/Basin/Getform.

## SEO a a11y
- Meta title/description + OG tagy v layoutu.
- Schema.org JSON-LD (`AutoRepair`) generované z `site.json`.
- Sémantické HTML + focus-visible stavy.

## Performance
- Bez těžkých knihoven.
- Lazy loading obrázků galerie.
- Galerie je připravená na výměnu placeholderů za reálné fotky.

## Spuštění
```bash
npm install
npm run dev
```

## Build
```bash
npm run build
```

## Nasazení
Statický výstup vznikne ve složce `dist/` a lze nasadit na libovolný statický hosting (Netlify, Vercel static, Cloudflare Pages, GitHub Pages).
