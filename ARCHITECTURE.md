# Modular Architecture
- Next.js App Router + TypeScript + Tailwind (mobile-first, dark/light)
- API: /api/auth, /api/menu/scan (OCR queue), /api/menu/items, /api/intelligence, /api/advisor, /api/crm, /api/reviews, /api/campaigns
- Services: `lib/ocr` (provider-agnostic), `lib/ai` (provider-agnostic), `lib/tenant` (RLS middleware), `lib/rbac`, `lib/queue` (Redis/BullMQ), `lib/storage` (S3), `lib/billing` (Stripe)
- All AI outputs labeled EST. and require human approve/edit.
- Every write creates `audit_logs`; every AI rec creates `ai_recommendations` with source metric.
