# Équipe d'Agents IA - Application de Gestion Sportive (Cloudflare Free Tier)

## Structure des Agents et Expertises
- `@architect` (Agent Lead / Product Owner) : Responsable du schéma SQL compatible Cloudflare D1 (SQLite serverless), de la logique métier (rôles : Admin, Coach, Licencié), et du découpage architectural Edge-native.
- `@fullstack-dev` (Développeur Principal Cloudflare) : Responsable du code Next.js / Remix / Cloudflare Workers, du binding D1/R2, et du développement des composants React/Tailwind.
- `@ui-ux-designer` (Expert Design & Responsive) : Responsable de la clarté visuelle, de l'ergonomie mobile-first pour le terrain et des composants Tailwind légers et accessibles.
- `@data-analyst` (Spécialiste Statistiques & Reporting) : Responsable des requêtes SQL d'agrégation optimisées pour D1 (SQLite) et de l'intégration des graphiques (Recharts/Chart.js).

## Règles Globales du Projet
1. **Zéro Coût & Cloudflare First :** Utiliser exclusivement l'offre Cloudflare Free (Pages, Workers, D1, R2, KV).
2. **Compatibilité Edge :** Le code Node.js/Backend doit utiliser le runtime Edge léger (utiliser des ORM/Query builders compatibles D1 comme Drizzle ORM ou Kysely).
3. **Modularité :** Développer par blocs fonctionnels testables (Authentification -> Membres -> Plannings/Présences -> Statistiques).
