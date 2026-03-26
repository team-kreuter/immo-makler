# Immobilienmakler Landing Page

Landing-Page-Template für Immobilienmakler im deutschen Markt. Zwei Seiten: Verkauf (Eigentümer ansprechen) und Akquise (Käufer ansprechen). Inhalte werden über ein Admin-Dashboard verwaltet und als JSON in `data/` gespeichert.

## Tech Stack

- Next.js 16+ (App Router), Tailwind CSS v4 (`@tailwindcss/postcss`), Framer Motion, Lucide React, Nodemailer
- Sprache: Deutsch (UI), Englisch (Code)

## Architektur

```
data/verkauf.json        → Inhalte Verkaufs-Landing-Page
data/akquise.json        → Inhalte Akquise-Landing-Page
data/site.json           → Firmen-Metadaten
data/theme.json          → Farb-Tokens
config/                  → Re-Exports aus data/
types/content.ts         → TypeScript-Interfaces
components/sections/     → Section-Komponenten
components/ui/           → UI-Komponenten (IconRenderer, Badge, etc.)
components/admin/        → Admin-Dashboard
app/api/admin/           → Admin-APIs
app/api/contact/         → Kontaktformular-API
```

## Regeln

- Keine neuen Abhängigkeiten ohne Absprache.
- Keine Datenbank. Alles dateibasiert (JSON in `data/`).
- `data/` Dateien nicht manuell editieren — Admin-Dashboard verwaltet sie.
- Icons nur via `IconRenderer` — nie direkt in Section-Komponenten importieren.
- Keine Breaking Changes an der JSON-Struktur. Bestehende Felder nicht umbenennen/entfernen, nur neue optional hinzufügen.
- Keine Environment-Variablen im Client-Code außer `NEXT_PUBLIC_*`.
- TypeScript strict — kein `any` außer wo explizit markiert.
- Tailwind v4 — keine `tailwind.config.ts`.
- Alle Sections müssen immer vorhanden bleiben (Hero, Problem, Solution, Benefits, Testimonials, FAQ, CTA, Contact).
- Mobile-first Layouts.
- Keine externen API-Calls außer SMTP.

## Befehle

```bash
npm run dev      # Entwicklungsserver
npm run build    # Production Build
npm run lint     # ESLint
```
