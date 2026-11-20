# VNDR Hub Screen Plan

Working plan based on [requirements.md](requirements.md). These are proposed screens and navigation, not a finished design or implemented functionality. Store-specific settings determine which actions are available; access also depends on role and location permissions.

## Shared Structure

- Sign-in, password reset, invitation acceptance, and email verification are shared entry points. The experience after sign-in depends on the account's role.
- Owners and managers select a location when applicable. A business-wide view is available to authorized owners for cross-location reporting and exports. Managers see only their permitted locations and features.
- Vendors start with a combined overview and can select a connected store to work with that store's products and records. Store-specific content uses the store's chosen language.
- Each user can choose light or dark mode. Layouts adapt to desktop, tablet, and phone; checkout is designed primarily for desktop and tablet.
- Notifications, account controls, and help are accessible throughout the relevant authenticated experience. The store's contact information remains available to vendors even when messaging is disabled.

## Store Owner and Manager

### 1. Dashboard

The owner's starting point shows configurable sections for sales, vendor activity, payouts, low and negative stock, space availability, and agreement or document deadlines. Upcoming vacancies are optional. Owners can rearrange sections, filter by location, and follow an alert to its underlying record. Managers see only authorized information.

### 2. Locations and Setup

Owners can view locations, add one with the subscription charge shown before confirmation, and choose settings or space lists to copy. Each location has its own details, language, time zone, currency, logo, contact information, and settings. Initial setup requires store details and guides the owner through the remaining steps; checkout credentials are required before a first sale. Location removal requires contacting VNDR Hub.

### 3. Spaces

A searchable list shows space number or name, size, listed rent, status, assigned vendor, and availability. A space detail view holds assignments, agreement dates, private notes, and occupancy history. The owner can prepare future assignments, receive an overlap warning, and override it. There is no floor-plan editor.

### 4. Waiting List

Owners manage prospects, contact details, preferred size, notes, priority, contact dates, and status. An owner can reserve a space or invite a person to become a vendor. The store contacts prospects individually.

### 5. Vendors

The vendor directory shows active and former vendors and invitation status. A vendor profile brings together contact details, assigned code and spaces, terms, products, sales, payout statements, rent, documents, and private notes. Owners invite, deactivate, or reactivate vendors and manage location-specific terms. Existing vendors must accept new store connections.

### 6. Inventory and Products

Browse and search products by vendor, category, availability, and stock status. Owners or permitted staff can correct product information or stock, review history, manage store-wide categories, and import or export products. A low-stock view supports combined vendor nudges. An unmatched-sales queue supports matching manually entered sales to products.

### 7. Sales and Cash Drawers

Search sales by date, receipt number, or product; open a sale for items, customer-facing charges, payments, receipt resend, and permitted refunds. Separate views show each device's cash drawer sessions, cash movements, closing counts, discrepancies, and notes. An issues queue surfaces offline sync conflicts and unresolved payments.

### 8. Payouts

An overview shows the location's payout schedule and statements that are ready, finalized, or marked paid. Owners can prepare statements together, preview individual calculations, add adjustments and optional rent deductions, and finalize them for vendor review. Statements remain editable until marked paid. Paid statements lock; later corrections appear on a future statement. Actual money transfers happen outside VNDR Hub.

### 9. Rent

View rent due, partial payments, and paid amounts by vendor, space, and period. Owners record and correct payments, manage private notes and reminders, and issue or download receipts. Current-period balances are visible but do not automatically carry forward. Payout deductions are recorded as rent payments when the payout is marked paid.

### 10. Reports

Provide daily, weekly, monthly, and custom date ranges; filters for authorized locations, vendors, and devices; and CSV/PDF exports. Views cover sales, payment methods, discounts, refunds, tax components, customer fees, vendor commissions, payouts, rent, product performance, and vendor comparisons. An accountant-oriented export separates relevant categories. No separate accountant login is planned.

### 11. Messages and Announcements

If the owner enables messaging, store staff can exchange messages with individual vendors. Owners can send an announcement to all vendors. Vendor-to-vendor messaging is not supported. Email notifications accompany messages and announcements.

### 12. Agreements and Documents

Owners upload PDF agreements, request typed signatures, track status and deadlines, cancel incorrect requests, and preserve signed versions. They can request other documents, review uploads, request replacements, and configure expiry reminders. These records are also accessible from the relevant vendor profile.

### 13. Settings

Location settings cover tax, fees, commission defaults and exceptions, returns, receipt messages, payment provider, custom payment methods, messaging, notifications, payout schedule, cash drawer rules, checkout devices, and PIN requirements. Fee settings include a sample-sale preview. Tax and customer fees can both be enabled, with a settings-time warning. Staff and manager permissions are managed here or through a dedicated team view.

### 14. Subscription, Export, and Support

Owners can view subscription invoices, update payment details, add locations, and download a full ZIP export for one or all locations. Cancellation and location removal are handled by contacting VNDR Hub. An in-app support area lists requests and their status, supports replies and attachments, and displays the support email.

## Checkout

### 15. Register

A focused shared-login screen supports barcode scanning, product and vendor search, and browsing by vendor or category. The current sale shows items, quantities, vendor and space, product prices, discounts, fee, tax, and total. Staff can hold unpaid sales, remove items, enter unrecognized items, or override prices with a reason. Manager-PIN prompts appear only where the owner requires them.

### 16. Payment and Receipt

Staff take cash, an integrated card payment, a manually confirmed separate-terminal payment, or another configured method. Split payments show the remaining balance; cash shows change. Email receipt is optional, and staff can complete a sale without customer email. No printer support is planned. Failed or uncertain provider payments have explicit retry or review states.

### 17. Offline and Sync States

The register clearly indicates online, offline, and syncing status. Offline checkout permits one cash payment per sale and no refunds. Staff see unsynced-sale warnings; owners can review errors and stock or price conflicts after reconnection. Offline data is retained locally where browser storage permits, with warnings about clearing browser data or removing devices.

### 18. Drawer and Sale Lookup

Staff can open and close a device's cash drawer, record cash movements, count cash, and explain discrepancies, subject to owner-configured PIN rules. A sale lookup supports receipts and, when the store enables them, online refunds. Sensitive and management actions remain subject to the owner's permissions.

## Vendor Portal

### 19. Combined Overview

After sign-in, the vendor sees their own sales, estimated earnings, low stock, upcoming payouts, and product performance across connected stores. Filters narrow by store and date; store-specific details follow that store's language. A low-stock item links directly to its quantity.

### 20. Stores

List connected stores and invitations. A selected store shows the vendor's assigned spaces, agreement terms, contact details, and payout schedule. Vendors can accept or decline invitations and view only the spaces and terms assigned to them. Former vendors retain limited historical access.

### 21. Products and Stock

Maintain a reusable product catalogue, variations, barcodes and SKUs, vendor categories, and store-specific price, stock, taxable status, assigned space, and availability. Vendors can copy listings between connected stores, adjust stock with optional reasons, view history, archive products, and use the import template with a preview. Product photos and label generation are not included.

### 22. Promotions

Create and manage upcoming, active, and completed sale prices for selected stores, products, and variations. Support percentage or fixed pricing, date and time windows, bulk selection, preview, editing, and early ending. Store-local time applies; conflicting schedules are blocked.

### 23. Sales and Earnings

Show only the vendor's own items, sale prices, discounts, overrides, commission, tax treatment, and earnings. Filter by store and date and export a selected store's records. The vendor does not see other vendors' items, store-only customer fees, payment provider details, or checkout device details.

### 24. Payouts and Rent

View estimated earnings, finalized statements, and paid status where recorded. Show assigned-space rent, due dates, partial payments, current-period balance, and downloadable rent receipts. Payout questions are handled by contacting the store outside the app.

### 25. Agreements, Documents, and Messages

Review and type-sign agreements; upload requested documents and replacements; see relevant deadlines; and message store staff when the store enables messaging. Store contact information remains accessible when messaging is off. Former vendors do not retain portal access to agreements, though they retain emailed copies.

### 26. Account and Notifications

Edit business and contact details, select a theme, manage optional two-factor authentication, and choose individual-sale, daily, weekly, and promotion reminders as applicable. Login email changes require admin assistance and verification. One login is supported per vendor business.

## VNDR Hub Admin

### 27. Business and Demo Overview

See subscribed businesses, locations, account status, and active demos. Create owner accounts and 14-day sample-data demos. Review failed payments, manage custom subscription pricing, suspend or restore accounts, and handle cancellation or location-removal requests.

### 28. Business Detail and Troubleshooting

View a business's locations, subscription, device limits, support history, and access status. Set an individual location's device limit and assist with login email changes. Admin store access is recorded in an audit log; owners are not automatically notified.

### 29. Support and Audit

Track support requests and attachments, reply to owners, and mark issues open or resolved. Review admin-access and relevant change history. Admin sign-in requires two-factor authentication.

## Key Journeys

1. **New store:** Admin creates owner account → owner completes required store details → owner sets checkout login → owner configures spaces and terms → owner invites vendors.
2. **Vendor joins:** Vendor accepts invitation and creates an account or signs in → reviews assigned terms → signs if required → adds or imports products and store-specific stock.
3. **Customer sale:** Staff scans or searches items → reviews totals → takes payment → optionally emails receipt → vendor receives their own sale details according to notification preferences.
4. **Unknown product:** Staff identifies vendor and space → enters item details → completes sale → vendor is notified → vendor or owner matches the sale to a product and adjusts stock.
5. **Payout:** Owner reviews a period and prepares statements → vendor receives finalized statement → store pays outside the app → owner may mark it paid, locking the statement.
6. **Offline sale:** Configured register loses connectivity → staff completes a cash sale → device retains it locally → sync runs when connected → owner reviews any flagged issues.
7. **Cancellation:** Owner contacts VNDR Hub → admin handles cancellation → owner and vendors get the agreed read-only access during the 90-day period → owner exports data or restores the subscription.

## Design and Validation Notes

- The screen groupings are a proposal; navigation labels and page boundaries can change during design without changing the agreed workflows.
- The launch scope is broad. Sequence implementation and validation, but do not quietly remove agreed features. Online shopping, gift cards, store credit, tips, product photos, and printed receipts are deferred or excluded.
- Resolve the open decisions in the requirements document and validate tax, payments, retention, accessibility, and offline behaviour before treating this plan as an implementation specification.

