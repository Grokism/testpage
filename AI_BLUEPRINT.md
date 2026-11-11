# testpage — Bookins.io AI Application Blueprint

- **Organization:** testpage
- **Live Origin:** `https://testpage.apps.bookins.io`
- **Web Template / Archetype:** `ecommerce` (Online Storefront & Member Catalog (Store Manager + Verified Buyer))
- **Theme Palette:** `emerald_commerce`
- **Generation Engine:** Bookins Role-Aware Archetype Compiler

---

## 1. Configured PermSet Generation Roles (No-Code Bookins Registry)

These roles are automatically registered on your Bookins.io client record (`collections.clients.permsetRoles`) and appear in **Bookins.io -> Add Permset -> Creation Mode** without requiring any code changes:

- **Store Manager** (`roleKey: "store_manager"`, policy: `issuer_only`, scope tag: *Store / Department Tag (optional)*): Create and manage product listings, pricing, inventory, and order fulfillment.
- **Verified Buyer** (`roleKey: "buyer"`, policy: `self_enroll`, scope tag: *Member Tier / Region Tag (optional)*): Browse member catalog, submit orders, and track order fulfillment under an opaque PermSet.

---

## 2. Web Template Questionnaire Answers

- **featuredProducts:** Signature Member Bundle — $39 · Curated weekly artisan essentials · Hand-Thrown Ceramic Mug & Tea Set — $44 · Limited small-batch release · VIP Seasonal Reserve Box — $85 · Priority member allocation
- **productCategories:** Product Listing, Member Exclusive, Buyer Order, Fulfillment Update
- **fulfillmentPolicy:** Order with your Verified Buyer PermSet—choose local pickup by handle code or private fulfillment.
- **memberPerksBanner:** Bot-free member drops · Fair 1-human-1-order limits · Zero personal data stored in the shop

---

## 3. Uploaded Brand & Image Assets (`src/assets/uploads/`)

- No custom image assets uploaded at provisioning time (add images to `src/assets/uploads/`).

---

## 4. Assembled Application Specification Prompt

```text
Build a full-stack MEAN + Nginx web application for "testpage" (Organization: "testpage", Origin: https://testpage.apps.bookins.io).

1. SELECTED WEB TEMPLATE & PURPOSE: Online Storefront & Member Catalog (Store Manager + Verified Buyer)
   - Headline: testpage — Member Storefront & Marketplace
   - Primary Goal: Run a sybil-resistant web commerce store where Store Managers manage product listings and inventory, and amihuman-verified Buyers browse products and place orders keyed by their opaque PermSet handle.
   - Theme Palette: emerald_commerce

2. TEMPLATE QUESTIONNAIRE ANSWERS:
   - 1. Featured Starter Products or Packages (one per line): Signature Member Bundle — $39 · Curated weekly artisan essentials | Hand-Thrown Ceramic Mug & Tea Set — $44 · Limited small-batch release | VIP Seasonal Reserve Box — $85 · Priority member allocation
   - 2. Store Categories / Collections (comma-separated): Product Listing, Member Exclusive, Buyer Order, Fulfillment Update
   - 3. Pickup, Delivery & Ordering Policy: Order with your Verified Buyer PermSet—choose local pickup by handle code or private fulfillment.
   - 4. Verified Member Perks & Guarantee: Bot-free member drops · Fair 1-human-1-order limits · Zero personal data stored in the shop

3. PERMSET PROTOCOL ROLES & ACCESS CONTROL:
   Every user must hold a public amihuman humanity badge plus one of these origin-scoped private PermSets (https://testpage.apps.bookins.io):
  1. Store Manager (roleKey: "store_manager", minting: Issuer-Only in Bookins.io Add Permset, scopeTag: "Store / Department Tag (optional)") — Create and manage product listings, pricing, inventory, and order fulfillment.
  2. Verified Buyer (roleKey: "buyer", minting: Self-Enroll at /join or Admin Minted, scopeTag: "Member Tier / Region Tag (optional)") — Browse member catalog, submit orders, and track order fulfillment under an opaque PermSet.

4. KEY FEATURES & WORKSPACE BEHAVIOR (/home & /api/records):
   - Public catalog showcase with featured collections, member perks, and pickup/shipping info
   - Store Manager PermSet console to add/edit catalog products, pricing, and fulfillment status
   - Verified Buyer PermSet catalog browser, order submission, and order status tracker
   - Bot-free purchasing enforced by public amihuman proof-of-humanity

5. UPLOADED BRAND & IMAGE ASSETS (src/assets/uploads/):
  - None uploaded yet (use clean CSS vector badges and cards)
```
