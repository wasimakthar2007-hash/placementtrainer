# SkillPilot

Placement trainer with hashed-password auth, SQLite (pooled connections), JWT sessions, role-based access, auto-generated aptitude tests, and an admin link hub.

## Run

```bash
npm install
npm start
```

Open http://localhost:3000

| Account | Password | Role |
| --- | --- | --- |
| `admin` | `Admin@123` | Admin |
| `demo` | `Demo@123` | User |

## What is included

- Login / register / forgot & reset password, remember-me JWTs, idle timeout, rate-limited auth
- Tables: users, questions, categories (DSA, Career Resources, Aptitude), user_progress, admin_links, plus test instances, usage tracking, analytics, announcements, settings
- Aptitude never lists the main question bank; `/api/tests/start` builds a temporary instance with opaque item tokens
- Admin link CRUD, clipboard copy, expiration, usage limits, click analytics, `/go/:slug` redirects that work from every page
- Back button on every authenticated page (history API)
- Helmet, parameterized SQL, XSS escaping in the UI, WebSocket + polling for live admin updates

Logs: `logs/info.log`, `logs/security.log`, `logs/audit.log`, `logs/error.log`
Database: `data/skillpilot.db`
