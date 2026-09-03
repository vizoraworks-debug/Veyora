# VEYORA — Smart Shopping

A mobile-first e-commerce website inspired by the supplied shopping-app reference. It is designed to be published directly as a GitHub repository and can use Supabase for authentication, products, cart and orders.

## Included

- Home / product catalogue
- Search
- Categories
- Promotional sections
- Product cards
- Cart and quantity controls
- Customer signup/login with Supabase Auth
- Delivery location
- Checkout and Cash on Delivery demo
- Order history and order-status tracking
- Customer profile
- Customer support screen
- Supabase-backed products, cart and orders
- Admin authentication through Supabase Auth
- Admin product add/edit/delete
- Admin order status management
- Row Level Security policies

## Files

- `index.html` — complete VEYORA web app
- `veyora_supabase_setup.sql` — Supabase tables, RLS policies, trigger and starter products

## Supabase setup

1. Create/open your Supabase project.
2. Open **SQL Editor**.
3. Paste and run `veyora_supabase_setup.sql`.
4. In **Authentication → Users**, create the VEYORA administrator account:
   - Email: `mubashir098@gmail.com`
   - Password: use the administrator password you chose in Supabase Auth.
5. The SQL trigger assigns the admin role to that email.
6. `index.html` contains the Supabase project URL and publishable key. Never put a Supabase service-role/secret key in this file.

## GitHub Pages

1. Create a GitHub repository, for example `veyora`.
2. Upload `index.html` and this README.
3. Upload `veyora_supabase_setup.sql` as well if you want the database setup stored with the project.
4. Go to **Settings → Pages**.
5. Select **Deploy from a branch**, choose `main`, folder `/root`, and save.
6. GitHub will provide the public Pages address.

## Security

The browser must only use the Supabase publishable/anon key. Database access is protected by Row Level Security. The administrator password is handled by Supabase Auth rather than being stored in the HTML.

## Important

This version uses client-side checkout and does not process real card/UPI payments. For production payments, connect a payment provider through a secure backend/edge function and verify payment server-side.
