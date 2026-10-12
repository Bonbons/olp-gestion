# Compétence : Conception de Schéma Cloudflare D1 (SQLite & Drizzle ORM)

## Objectif
Générer le schéma Drizzle ORM et les migrations SQL pour Cloudflare D1 (SQLite) pour l'association sportive.

## Tables Requises (Syntaxe SQLite) :
1. `users` (id TEXT PRIMARY KEY, email TEXT, full_name TEXT, role TEXT CHECK(role IN ('admin', 'coach', 'member')), created_at INTEGER)
2. `teams` (id TEXT PRIMARY KEY, name TEXT, category TEXT, coach_id TEXT REFERENCES users(id))
3. `sessions` (id TEXT PRIMARY KEY, team_id TEXT REFERENCES teams(id), date TEXT, location TEXT, description TEXT)
4. `attendances` (id TEXT PRIMARY KEY, session_id TEXT REFERENCES sessions(id), member_id TEXT REFERENCES users(id), status TEXT CHECK(status IN ('present', 'absent', 'excused')))

## Contraintes D1 :
- Utiliser `TEXT` pour les identifiants UUID (`crypto.randomUUID()`).
- Utiliser `INTEGER` ou `TEXT` ISO-8601 pour les dates.
