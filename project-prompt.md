You are a senior full-stack engineer.

I want you to build a complete production-grade clone of NameMC (Minecraft username and skin search website).

The goal is to recreate NameMC as closely as possible while remaining fully legal, fully open-source, and 100% free to host and operate.

IMPORTANT CONSTRAINTS:

- Entire project must be deployable on Netlify
- Must use only free services
- No paid APIs
- No monthly hosting cost
- No proprietary paid infrastructure
- Must be scalable to 50,000+ daily users
- Code must be production quality
- SEO optimized
- Mobile responsive
- Fast loading
- Use modern architecture

TECH STACK REQUIREMENTS:

Frontend:
- Next.js 15
- React 19
- TypeScript
- TailwindCSS
- App Router
- Server Components

Backend:
- Netlify Functions
- TypeScript
- Prisma ORM

Database:
- Supabase PostgreSQL free tier

Caching:
- Upstash Redis free tier

3D Rendering:
- Three.js
- react-three-fiber

Infrastructure:
- Netlify deployment
- GitHub Actions cron jobs
- Edge functions where useful

NO Docker.

NO paid services.

NO AWS.

NO Google Cloud.

NO Vercel paid features.

NO Firebase.

NO Elasticsearch.

SYSTEM ARCHITECTURE:

Build the following architecture.

========================================
FEATURE 1 — PLAYER SEARCH
========================================

Implement search for Minecraft usernames.

Requirements:

- Search by username
- Search by UUID
- Search by partial username
- Fast autocomplete
- Search results under 100ms if cached

Create endpoint:

/api/search?query=username

Use PostgreSQL full text search.

Implement ranking algorithm.

========================================
FEATURE 2 — MOJANG API INTEGRATION
========================================

Integrate Mojang API.

Endpoints:

- Username → UUID
- UUID → profile
- UUID → skin texture
- Profile metadata

Create wrapper service:

lib/mojang.ts

Requirements:

- Retry logic
- Rate limiting
- Response validation
- Automatic cache

Cache all API responses for 24 hours.

========================================
FEATURE 3 — USERNAME HISTORY TRACKING
========================================

Track username changes.

Store:

- UUID
- Old username
- New username
- Changed date

Database schema:

players
username_history

Create polling system.

GitHub Actions runs every 6 hours.

Detect username changes.

Insert history records.

Create page:

/profile/[username]/history

========================================
FEATURE 4 — PLAYER PROFILE PAGE
========================================

Page example:

/profile/notch

Display:

- Current username
- UUID
- Skin preview
- Cape preview
- Username history
- First seen date
- Last updated date

SEO:

Generate dynamic metadata.

Use static rendering when possible.

========================================
FEATURE 5 — SKIN RENDERING ENGINE
========================================

Build Minecraft skin viewer.

Requirements:

- 3D model viewer
- Rotate camera
- Cape support
- Slim model support
- Download skin PNG
- Real-time preview

Use:

Three.js
react-three-fiber

Create component:

components/SkinViewer.tsx

========================================
FEATURE 6 — SKIN DATABASE
========================================

Store skins.

Schema:

skins
skin_hash
texture_url
created_at
player_uuid

Allow:

- Browse skins
- Trending skins
- Recently uploaded skins

Pages:

/skins
/skins/trending
/skins/recent

========================================
FEATURE 7 — SERVERLESS API
========================================

Create Netlify Functions.

Functions:

- search.ts
- profile.ts
- mojang.ts
- skin.ts
- history.ts

Requirements:

- Zero Express
- Native Netlify functions

========================================
FEATURE 8 — DATABASE SCHEMA
========================================

Create Prisma schema.

Tables:

players
skins
capes
username_history
search_logs
favorites
cached_profiles

Use indexes aggressively.

========================================
FEATURE 9 — SEO
========================================

Extremely important.

Implement:

- Dynamic metadata
- OpenGraph tags
- Twitter cards
- Sitemap generation
- robots.txt
- Structured JSON-LD
- Canonical URLs
- Server rendering

All profile pages indexable.

========================================
FEATURE 10 — SEARCH ENGINE
========================================

Implement autocomplete.

As user types:

Show username suggestions.

Must be instant.

Debounce input.

Search ranking:

- Exact match highest
- Prefix match second
- Similarity match third

========================================
FEATURE 11 — ADMIN CRON SYSTEM
========================================

GitHub Actions cron.

Runs:

Every 6 hours.

Tasks:

- Refresh Mojang data
- Detect username changes
- Update trending usernames
- Cache hot pages
- Purge stale cache

========================================
FEATURE 12 — CACHING
========================================

Implement multi-layer cache.

Layer 1:
Browser cache

Layer 2:
Redis cache

Layer 3:
Database cache

Layer 4:
Netlify edge cache

TTL:

Profile pages = 6 hours

Search = 1 hour

Skin textures = 7 days

========================================
FEATURE 13 — UI DESIGN
========================================

Match NameMC closely.

Design requirements:

- Dark theme
- Minecraft-inspired aesthetic
- Green accents
- Fast loading
- Minimal animations
- Card-based layout

Pages:

Homepage
Profile page
Search page
Skin gallery
Trending usernames
Server lookup page

========================================
FEATURE 14 — PERFORMANCE
========================================

Target:

Lighthouse 95+

Metrics:

TTFB under 200ms

Largest Contentful Paint under 2 seconds

Use:

- image optimization
- lazy loading
- route splitting
- server components

========================================
FEATURE 15 — SECURITY
========================================

Implement:

- Rate limiting
- Input validation
- SQL injection prevention
- Bot protection
- API abuse prevention
- XSS prevention

========================================
PROJECT STRUCTURE
========================================

Use this structure:

/app
/components
/lib
/hooks
/services
/prisma
/public
/netlify/functions
/scripts
/types

========================================
DELIVERY REQUIREMENTS
========================================

Generate complete codebase.

Do NOT skip implementation details.

Do NOT write pseudocode.

Generate actual working code.

Every file must be production ready.

Build incrementally.

Start with architecture plan.

Then create database schema.

Then backend.

Then frontend.

Then deployment.

Then optimization.

After each phase continue automatically.

Never stop early.

Never summarize.

Keep coding until full project is complete.

Treat this as a real startup product.
