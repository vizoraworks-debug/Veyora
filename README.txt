VEYORA COMPLETE WEBSITE PROJECT

Files
- index.html: single-page VEYORA storefront and admin interface
- veyora-logo.svg: brand logo
- VEYORA_SUPABASE_FIX.sql: SQL setup/fix matching the schema verified in your Supabase project

Current project assumptions verified from your screenshots
- public.products.id is bigint
- public.products includes image_urls (jsonb), video_url, product_type, brand, material, delivery_charge
- public.store_categories is used for category management
- public.store_settings uses setting_key and setting_value
- public.product_reviews uses product_id bigint and customer_name
- public.orders.id and user_id are uuid
- public.payment_proofs uses file_path
- Storage buckets: product-images (public), product-media (public), payment-proofs (private)

Important
1. The website now uses the existing product-images bucket for admin product photo/video uploads because its admin INSERT/UPDATE/DELETE policies were inspected. The product-media bucket may remain unused.
2. payment-proofs must stay private. Never expose its files through public URLs; use signed URLs for authorized admin viewing.
3. The SQL file adds/recreates read/admin policies for store_categories, store_settings, and the admin-review insert policy. Read it before running. It assumes public.profiles(id, role) exists and that role='admin' is the correct admin check.
4. Your existing payment_proofs table was created with file_path; the HTML uses file_path.
5. SQL success does not prove the website is deployed or all features work end-to-end. Test with an admin account and a normal customer account.

Deploy to GitHub Pages
1. Download and extract the ZIP.
2. Open your GitHub repository for the VEYORA site.
3. Replace the repository's index.html with this project's index.html and add/update veyora-logo.svg.
4. Commit the changes to the branch/folder configured for GitHub Pages.
5. Wait for deployment, then hard-refresh the site.

Security
- Never put a Supabase service_role key, secret key, database password, or admin password in index.html.
- Public product images are expected; payment screenshots are sensitive and must remain private.
- Verify UPI payments in your bank/payment app before dispatching; a screenshot alone is not proof of cleared payment.
