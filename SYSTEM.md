# DIRECTIVES SYSTÈME - PROJET SPORT-ASSIST (Cloudflare Free Tier 0€)

## 1. Contexte & Objectif
Vous développez une application web collaborative de gestion pour une association sportive (licenciés, coachs, bénévoles, plannings d'entraînement, feuilles de présence et statistiques). Le projet ne dispose d'aucun budget financier et est hébergé intégralement sur le plan gratuit de Cloudflare.

## 2. Stack Technique Obligatoire (Cloudflare Ecosystem 0€)
- **Hébergement & Edge API :** Cloudflare Pages / Workers (Next.js avec `@cloudflare/next-on-pages` ou Remix).
- **Base de données SQL :** Cloudflare D1 (SQLite distribué à très faible latence, 5M de requêtes/mois gratuites).
- **ORM / Driver DB :** Drizzle ORM (léger, typé, parfait pour SQLite/Cloudflare D1) ou Kysely.
- **Stockage de Fichiers (Photos/Docs) :** Cloudflare R2 (10 Go gratuits, 0$ de transfert sortant).
- **Auth :** Auth.js (NextAuth) avec adaptateur SQLite/D1, ou Lucia Auth.
- **UI Kit :** Tailwind CSS + composants inspirés de shadcn/ui.
- **Visualisation de données :** Recharts ou Chart.js.

## 3. Comportement des Agents
- Ne proposez **jamais** de services payants ou nécessitant de dépasser les quotas gratuits Cloudflare D1 (5 millions de lectures / 100k écritures par jour).
- Écrivez du code optimisé pour le **Edge Runtime** de Cloudflare (évitez les modules Node.js natifs incompatibles comme `fs` ou `crypto` classique, privilégiez les API Web Standard `fetch`, `Web Crypto`).
- Générez systématiquement les fichiers de configuration nécessaires à Cloudflare (`wrangler.jsonc` / `wrangler.toml`).
