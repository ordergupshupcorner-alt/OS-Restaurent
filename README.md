# Restaurant Growth OS — Your AI co-pilot for restaurant growth

**Production-ready multi-tenant SaaS** sitting *above* POS. Focus: menu optimization, pricing, reviews, CRM, WhatsApp marketing, AI advisor.

## Architecture Implemented (First Build)
- **Auth**: Email/pass + Google OAuth, JWT (httpOnly), RBAC (Owner/Admin/Staff), tenant isolation (RLS on `restaurant_id`, `branch_id`)
- **Onboarding**: Restaurant type, branches, staff invites
- **Menu Scanner**: Image/PDF/Excel/CSV → OCR (provider-agnostic) → AI structured extraction (category, name, description, price, variant, portion, dietary, add-ons) → human review
- **Menu Editor**: Full CRUD, branch-scoped, autosave, audit logs
- **Menu Intelligence**: Health Score 0-100, price analysis, category balance, upsell/combo/premium, low-performer detection
- **AI Optimizer**: SEO descriptions (never fabricates ingredients), tags, add-ons, cross-sell
- **Combo Engine**: co-occurrence + margin targets (approve/edit flow)
- **Pricing Intelligence**: food-cost → gross/contribution margin, experiments (not single "correct price")
- **Advisor**: daily recs with reason/metric/impact/confidence/action (Apply/Edit/Dismiss/Schedule/View)
- **Dashboard**: Revenue, Orders, AOV, Growth Score, Top Opportunity/Alert, Today's rec, charts
- **Growth Score**: 7 pillars (Menu, Pricing, Retention, Reviews, Marketing, Upselling, Digital)

## Next Phase Ready
Reviews (sentiment), CRM (consent segments), WhatsApp Business API (templates, opt-in/out, delivery/click/conversion), Campaign Generator, Analytics, Integrations, Billing (Stripe), Notifications, Redis queues, S3 storage, Recharts, GraphQL/REST.

## Stack
Next.js 14 + TypeScript + Tailwind, Node.js, PostgreSQL, Prisma, Redis + BullMQ, S3, provider-agnostic AI/OCR, Recharts

## DB Tables (Prisma schema outline)
users, restaurants, branches, staff, menus, menu_categories, menu_items, menu_variants, addons, combos, orders, order_items, customers, customer_segments, reviews, campaigns, campaign_messages, campaign_events, ai_recommendations, ai_analyses, analytics_snapshots, integrations, subscriptions, notifications, audit_logs

## Security
Tenant isolation, RBAC, encrypted secrets, rate limiting, input validation, audit logs, secure uploads, webhook verification, consent management.

## Run Preview
Single-file demo at /index.html is a high-fidelity, mobile-responsive, interactive prototype of the full product.
