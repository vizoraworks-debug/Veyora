VEYORA requested feature expansion

Files: index.html, veyora-logo.svg, VEYORA_FEATURES_MIGRATION.sql.

Before launch: back up Supabase, verify products.id and orders.id types match UUID assumptions in the migration, review/run SQL, and configure Storage buckets and policies.

Features: admin category manager; editable homepage offer banner; UPI ID/payee settings; payment screenshot submission; up to 7 product images; product video; product description/type/brand/material; per-item delivery charge; 3–5 star admin and customer reviews.

Security: payment proofs use a separate private `payment-proofs` bucket and metadata table. Configure owner/admin-only Storage read policies. Admin writes depend on profiles.role='admin'; adjust if your schema differs. Verify payments manually before dispatch. Do not expose service-role keys or secrets in frontend code.
