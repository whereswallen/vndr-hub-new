# VNDR Hub Requirements

Working discovery document based on the owner's answers. The earlier prototype and design prompts are reference material, not approved requirements. This document describes the intended product, not functionality that has already been built.

## Product

VNDR Hub is a browser-based platform for stores that rent selling space to independent vendors. Store staff sell products through a shared checkout; the store collects customer payments and later pays vendors outside the platform. Vendors use one account to manage their products and see their activity across participating stores.

Canada is the initial priority. The launch experience supports English and French, desktop and tablet checkout, and desktop and mobile vendor access. Store owners choose their store's language; store-specific vendor views follow that choice. A multi-store vendor overview can show each store's information in that store's language. Each user chooses light or dark mode.

## First Build Priority

- Nail the core online workflow first: vendors add products and maintain stock, store staff find and sell products at checkout, inventory updates accurately, and each affected vendor receives one email per transaction listing only their own items. The combined email reduces message volume.
- The first version built and tested supports cash and manually recorded payments on a separate card terminal. Integrated Stripe and Square payments come afterward.
- Build and validate the online workflow before offline checkout. Offline cash checkout and the other agreed launch features remain part of the broader launch scope; this sequencing does not remove them.

## Businesses and Roles

- A subscribing business may own one or multiple locations. Independently owned businesses have separate accounts and data.
- A VNDR Hub administrator creates live owner accounts, manages subscriptions and demos, provides support, and can access store accounts to investigate issues. Admin access is audited; store owners are not automatically notified. Admin two-factor authentication is required.
- Store owners manage their locations, staff, spaces, vendors, settings, and subscription. Managers have individual accounts with owner-controlled permissions and location access. Only owners manage manager accounts.
- Checkout staff use a shared store login. Owners control permissions and which sensitive actions need a shared manager PIN. Each location has its own PIN, though owners may use the same value at multiple locations. Repeated incorrect PINs do not lock actions.
- Each vendor business has one login and can connect to multiple stores. Store data is isolated: stores see their own activity, and vendors see only their own. Owners and vendors may enable two-factor authentication.
- Login email changes for vendors and owners require a VNDR Hub admin and verification at the new address. The old address is not notified. Owners manage manager profiles and login emails; manager email changes do not require verification. Users can reset passwords by email.
- Owners can remotely revoke checkout devices, reset the shared password and PIN, and configure inactivity timeouts, including no timeout. A password reset signs devices out; offline devices sync completed sales and sign out when they reconnect.

## Subscription and Demo

- The subscription is $100 per month for the first location plus $10 per month for each additional location, with unlimited vendors and the same feature set for all stores. The admin can set custom pricing.
- Owners are billed automatically; the billing provider (Stripe or Square) will be selected later. Owners can update their payment method and view invoices and payment history.
- Owners may add locations themselves after seeing the extra charge; mid-cycle additions are prorated. Location removal and subscription cancellation require contacting VNDR Hub.
- Failed payments flag the account for admin review and the owner is emailed before suspension. Suspension is case by case, not automatic. Suspended stores retain their data, and vendors retain access to past sales and payout statements.
- Prospects contact VNDR Hub for a 14-day demo using sample data. The admin sets up demo access; this is not intended for long-term real vendor operations.
- Owners can download a full export at any time, choosing one location or all locations. The ZIP contains spreadsheets for sales, payouts, rent, products, and vendor details, plus uploaded documents.
- After cancellation, the starting policy is a 90-day export and historical-access period, with reminders before deletion. Owners have read-only access to view and export records, cannot process sales or make changes, and can restore their subscription during that period. Vendor access to the cancelled store is also read-only; vendors can export their own history. Vendors active when the store cancels can view their agreements during the period; former vendors cannot access agreements in the portal and retain their emailed copies. Retention and deletion details require privacy and legal review before launch.

## Store Setup and Spaces

- Initial setup guides the owner through store details, settings, checkout, spaces, and vendors. Business name, location address, and contact details are required. A checkout login is required before the first sale. Fee and tax settings can be configured later; spaces and invitations are optional during setup.
- Each location has its own language, time zone, currency, tax and fee settings, return policy, receipt text, and contact details. Currency defaults to CAD; an admin must handle currency changes after the first sale. Province informs suggested Canadian tax settings; non-Canadian tax settings are entered manually.
- Owners can copy selected settings and optionally a space list from another location, then edit them. They can invite vendors already connected to another location without re-entering contact details; the vendor must accept the new connection.
- Manage spaces in a simple list, not a visual floor plan. A space has a name or number, size, fixed owner-controlled listed rent, status, vendor assignment, availability, and private notes. Statuses include available, occupied, reserved, and unavailable.
- Each space agreement has its own rent amount and billing frequency, monthly by default, and start and end dates. Vendors can rent multiple spaces. Changing a space's listed rent does not automatically change existing agreements.
- Owners can prepare future assignments, receive overlap warnings, and override them. Preserve space occupancy history, including overlapping assignments. Owners may choose whether and when upcoming vacancies appear on the dashboard.
- Owners can maintain a waiting list without creating vendor accounts: contact details, preferred size, notes, date added, reorderable priority, contact date, and declined or no-longer-interested status. Owners contact people individually and can invite them from the list.

## Vendors and Agreements

- Owners invite vendors by email. Invitations expire after seven days, can be resent or revoked, and have visible pending, accepted, expired, revoked, and declined states. Owners are notified of responses and expiry. Vendors accept a store connection as a whole; their invitation shows only their assigned spaces and terms. Owners control space assignments independently of invitation status.
- A vendor's business profile and contact details are shared across their connected stores; changes do not trigger store notifications. The login email is separate from editable contact information.
- Owners assign vendor codes or numbers per location, unique within that store. Related locations may use the same code for a vendor. Codes can change, retaining historical values; old codes no longer work for checkout lookup. Notify the vendor and remind them to update labels.
- Agreements and commission terms support effective dates and preserve the terms applied to past sales. Owners may require signing before a vendor adds products and decide whether a revised agreement requires a new signature. Vendors are notified when terms change.
- Owners upload their own PDF agreements; no templates are supplied. Vendors sign by typing their name and confirming. Signed copies record signing account, date, and time and are emailed to both parties. Preserve prior signed versions; owners can cancel an incorrect request and set deadlines and reminders. Vendors contact the store outside the app if they do not wish to sign.
- Stores can optionally request named documents. Vendors upload PDFs, JPGs, or PNGs, up to 10 MB per document. Owners review, accept, or request replacement with a reason. Documents may have expiry dates and reminders for store and vendor; preserve previous versions and review replacements. Insurance is optional, not assumed.
- Owners can deactivate and later reactivate vendors without losing history. A former vendor retains access to that store's sales, payout statements, and rent history, but not signed agreements in the portal; they keep the emailed agreement. Other store connections remain active.

## Products and Inventory

- Vendors create and maintain products; store staff can correct mistakes. Vendors may create products before assigning them to stores. Store-specific configuration includes price, stock, taxable status, availability, and assigned space. Products may have size, colour, or other variations with their own SKU, barcode, price, and quantity. One-of-a-kind items and multiple units are supported; products are individually priced, not sold by weight.
- When assigning a product to a store, identify the vendor from their account. Automatically select their space if they have only one at that location; if they rent multiple spaces there, let them choose the space for the product.
- No product photos at launch. Optional descriptions and categories are supported. Vendor categories are private to each vendor. Store owners can separately group products across vendors into store-wide checkout categories.
- Vendors provide their own labels outside VNDR Hub. Products can have existing barcodes and vendor SKUs; the app can also assign product codes. Prevent duplicate barcodes and duplicate SKUs within a store; reuse across different stores is allowed. Staff can search by product name, SKU, vendor name, or vendor code.
- Vendors may enter their own SKU or have VNDR Hub generate one when adding a product.
- Product entry accepts a manually entered barcode; scanning a barcode into the form is not required. Vendors may create a product with zero stock and leave it available at checkout; subsequent sales may take stock negative. Setting a low-stock alert threshold is optional.
- A product assigned to a store is available there immediately by default. The vendor may turn availability off for that store.
- When adding a product, a vendor chooses which connected stores receive it. The form accepts one starting price for all selected stores, with per-store price adjustments, and a separate stock quantity for each store.
- Keep variation fields hidden for simple products until the vendor chooses to add variations. Provide a way to save and add another product without returning to the inventory list; the next form is blank, with no category or store selections carried over.
- Vendors can copy products to connected stores, set store-specific values, and choose whether name and description edits affect one or all applicable stores. A per-store toggle controls availability. Archiving removes a product from all checkouts but preserves history and permits restoration.
- Vendors maintain separate stock counts by store. Staff may correct stock. Manual stock adjustments can include an optional reason; history records sales and changes and is visible to the vendor. Store corrections do not trigger a separate vendor email.
- Allow sales into negative stock. Email the vendor every time an item sells while negative. Vendors can set low-stock thresholds; store alerts are optional. Owners can send a combined low-stock email to a vendor with products, quantities, and an optional personal note.
- Vendors and owners can download a product import template, import products and variations, preview changes and errors before applying, and export existing products in the same format for updates. Product lists can also be exported for records.
- Vendors may schedule promotions by location and variation, using fixed sale prices or percentage discounts, individually or in bulk. Dates and times use each store's time zone. Preview calculated prices, block overlapping promotions for the same product and store, permit editing and early ending, and restore regular prices automatically. Percentage promotions follow regular-price changes; fixed sale prices do not. If the regular price falls below an active fixed sale price, use the lower regular price and flag the promotion. Vendors can configure reminders; owners see upcoming and active promotions. Only vendors schedule promotions.

## Checkout and Payments

- Browser checkout supports desktop and tablet, keyboard-style USB and Bluetooth barcode scanners, search, and product tiles browsed by vendor or category. Default maximum is two registered devices per location; a VNDR Hub admin may set a higher limit at no extra device charge. Owners can name and manage devices, view limits, and are warned before removing a device with known unsynced sales.
- Scanning a recognized product barcode adds it to the current sale immediately, without a confirmation prompt. Repeated scans increment the existing line, and the most recently scanned item appears at the top of the sale.
- Successful and unrecognized barcode scans have distinct sounds; an unrecognized scan also displays an error. Owners can turn checkout sounds off. A successfully scanned item's sale line briefly highlights for visual confirmation.
- A product with negative stock is still added immediately and can be sold. Show a warning to checkout staff, but do not show the stock warning on the customer receipt.
- One transaction may contain products from multiple vendors. Show each item's vendor and space, allow repeated scans and quantity changes, and show customer fees and tax before payment. Staff can remove scanned items, cancel unpaid sales without a PIN, and hold unpaid sales. A partially paid sale must be completed or cancelled; a transaction with an uncertain card payment may be held for resolution.
- If a barcode is unrecognized and the product cannot be found, staff select the vendor and space and enter product name, price, quantity, and code. The sale is credited to that vendor and can be paid out before matching. Email the vendor and show the owner an unmatched-sale list. Vendor or owner can match it to an existing or newly created product, deducting sold quantity once. Whether manual entry requires a PIN is owner-controlled.
- The unrecognized-barcode error links directly to manual item entry and pre-fills the scanned barcode. Each entry starts without a remembered vendor. After staff select a vendor, automatically select their only space, or let staff choose when they rent multiple spaces. On completion, add the item to the sale and return to scanning; staff can edit or remove it before payment.
- Staff may override an item's price without changing its listed price. A reason is mandatory; PIN requirements are owner-controlled. Notify the vendor and show original price, override price, and reason in sales history.
- Support item and whole-sale discounts. The store chooses who absorbs each discount; manager approval is configurable. Allocate whole-sale discounts to items. If the store absorbs a discount, the vendor receives their usual share based on the original price; if the vendor absorbs it, calculate their commission on the discounted price. Show the impact before applying and notify affected vendors.
- Payment methods include cash, an integrated Stripe or Square connection, separate card terminals, and owner-defined methods including e-transfer. One integrated provider is connected at a time; each store uses its own provider account. Leave room for other providers later. Provider processing fees are the store's responsibility, not vendor payout deductions.
- Support multiple payment methods in a single split transaction, display the remaining balance, and calculate cash change. Integrated payments require provider confirmation before completion. Failed payments can be retried or switched to another method without rebuilding the sale. Separate terminal payments are manually confirmed and can include an optional transaction reference.
- If a connection fails during an integrated payment, preserve the uncertain sale, alert the owner, and block an automatic retry until the provider status is checked. An owner can record the resolution and its time. Provider transaction references are visible to stores, not vendors.
- Receipts are emailed only, not printed. Customer email is optional and used for receipt delivery, without creating a customer account. Staff can resend receipts and find sales by receipt number, date, or product. Receipts include store branding, contact information, configurable message and return policy, and applicable fee and tax lines.
- No tips at launch. Gift cards, store credit, and an online store are deferred.

## Offline Checkout and Cash Drawers

- Checkout must be configured and signed in online before offline use. Clearly display online, offline, and syncing states. Offline checkout is cash-only, with one cash payment per sale; refunds are online-only. Completed offline sales and drawer closures sync when connectivity returns. Retain unsynced records across browser closure or device restart where browser storage permits, and warn against clearing browser data.
- Show unsynced-sale warnings, retain failed syncs for review, and alert owners until resolved. Allow owners to resolve conflicts and contact support. Keep a history of resolutions. Allow negative stock and flag conflicts. Combine offline sales with vendor stock changes on reconnect; show inventory consequences in vendor history without a separate email.
- Use last-synced product and scheduled promotion data offline. If a sale used an outdated price, keep the amount actually paid and notify both owner and vendor for review. Email the vendor after syncing, showing the actual sale time.
- Each checkout device can have its own cash drawer. Record opening float, cash added or removed with reasons, expected and counted balances, discrepancy, required discrepancy note, and closing reconciliation. PIN requirements for closing are owner-controlled. Alert owners when a discrepancy exceeds their configured tolerance. Reports distinguish devices and drawers for store staff; vendors do not see device details.

## Tax, Fees, and Commission

- Fees and taxes default to zero until configured. The owner controls location settings and reviews suggested provincial rates; multiple tax components are supported and shown separately on customer receipts and store reports. Owners can turn tax collection off. Vendors mark each product taxable or non-taxable per store; products default to non-taxable without a separate prompt. Owners can override that status for their store.
- When enabled, tax is added on top of the vendor's price; it is never included in that price. A vendor agreement specifies whether tax on their products is retained by the store or included in the vendor's payout. Preserve historical treatment and notify vendors of changes. Vendors see the tax treatment and relevant amounts.
- Rent, vendor-paid commission, and customer-facing fees are independently configurable; do not present preset business models. The store sets standard commission and customer fee percentages, with exceptions for vendors or spaces. The customer fee is a percentage of the discounted product price before tax. Calculate it per item and show one combined, owner-labelled line to the customer; the fee belongs to the store and is not shown as vendor earnings.
- Vendor-paid commission is deducted from the vendor's product price. Where the store retains tax, commission is based on product price only. Where the vendor receives tax, the owner can choose a before- or after-tax commission basis. Space-specific terms determine the applicable rate for products assigned to that space; there is no separate additional space commission.
- Stores may enable both tax and the customer-facing fee; warn at settings time. Provide a sample calculation showing customer total, vendor earnings, store retention, and tax where applicable. Fee and tax changes preserve the amounts charged on historical transactions.
- Tax and fee setup is configurable business logic, not a determination of legal tax liability. Canadian federal and provincial requirements, receipt wording, and suggested rates require specialist review.

## Payouts, Rent, and Refunds

- Each location sets one recurring weekly, biweekly, or monthly payout schedule. Monthly dates that do not exist fall on the last day of that month. Remind owners to prepare payouts and notify vendors when schedules change. Owners may also create off-schedule payouts with an end date.
- Owners prepare multiple vendor statements together, preview and adjust each, and finalize them. Statements include eligible sales, commission, tax treatment, optional rent deductions, and other adjustments. Prevent sales from appearing on multiple statements. Finalization emails the vendor; edits before payment send an updated statement and notification. Marking a payout paid is optional; until it is marked paid, the statement remains editable. Marking it paid locks the statement and records any rent deducted from that payout. Later mistakes or refunds are handled as corrections on a later statement. Actual payments occur outside the app.
- Vendors can view and export their own sales and statements for a selected store, including estimates clearly labelled as such. They contact the store outside the app for payout questions. Statements include store contact details. Owners have an overview of ready, finalized, and paid statements.
- Rent is usually paid outside the app. Owners may record full or partial payments per space and rental period, with date and method; custom method labels are supported. Show the current period's remaining balance without automatically carrying unpaid balances forward. Owners may keep private notes. Vendors see their rent records in the portal and can download receipts. Rent deducted from a payout is recorded as a rent payment when that payout is marked paid.
- Owners control rent reminders, recipients, and timing. Rent receipts show store branding and contact information, vendor, space, amount, date, method, and remaining balance. Owners can correct entries with an audit history and export rent reports separately from sales.
- Refunds are disabled by default and configurable by store. When enabled, support individual-item refunds, optional restocking, original or externally handled payment methods, required reason, owner-configured PIN rules, and owner-controlled receipt-free returns. Prefer matching the original sale; permit manual refunds against a vendor and product if necessary. Notify vendors with amount and reason. Reverse the relevant customer fee, tax, and vendor commission; refunds after payout become a later adjustment. Preserve the store's policy on receipts.

## Dashboards, Reports, and Communication

- The vendor's combined dashboard shows sales, estimated earnings, low stock, upcoming payouts, product performance, and slow-moving products, filterable by store and date. It links directly to stock updates. Each vendor sees only their own items and earnings, including original and overridden prices and relevant commission and tax, not other vendors' sales or store-only customer fees.
- Send one email per transaction to each affected vendor, listing only that vendor's items and earnings. Vendors may turn individual-sale emails off and choose daily summaries, weekly summaries, both, or neither. Separate emails cover relevant events such as negative stock, refunds, discounts, and price overrides.
- Owners have a configurable, reorderable dashboard covering sales, spaces, vendor activity, payouts, stock, agreements, and document deadlines. Store reports support daily, weekly, monthly, and custom dates; location and device filtering; vendor comparisons; low-activity vendors; sales, payment methods, discounts, refunds, fees, taxes, commissions, payouts, and rent. Export CSV and PDF, including an accountant-oriented report. No accountant login or scheduled accountant email is required.
- Store owners can enable or disable vendor-to-store messaging. No vendor-to-vendor messaging. Owners can announce to all vendors; email notifications accompany messages and announcements. When messaging is disabled, vendors still see store support contact details.
- Store owners can contact VNDR Hub by email or an in-app support request with attachments. Admins can track and reply to requests; owners see status and can reply in the same thread. Vendors contact their store first.
- Admins see subscribed businesses, locations, demo and subscription status, and support requests. Audit admin access and changes to products, inventory, prices, agreements, and sensitive financial records. Shared checkout actions are attributed to store staff; identifiable owner and vendor actions are attributed to their accounts.

## Open Decisions and Validation

- Confirm the exact contents and format of the all-store export, deletion and backup handling, vendor access during cancellation, and retention exceptions with a Canadian privacy professional.
- Confirm Canadian tax and fee rules, calculation and rounding details, effective-date handling, and receipt wording with a qualified specialist. Defaults and configurable settings do not establish tax compliance.
- Confirm supported payment readers, provider capabilities, partial-payment cancellation and refunds, and integration behaviour before implementation. Payment provider choice for VNDR Hub subscription billing is undecided.
- Validate offline browser storage durability, sign-out and sync behaviour, conflict resolution, and recovery limits through a technical proof of concept. Clearing browser data or losing a device can lose unsynced sales.
- Define how to handle mixed-currency totals if a vendor ever joins stores using different currencies; conversion is not in launch scope.
- Confirm product-code generation rules, vendor/space rate precedence and unusual shared-space terms, plus exact report and notification preferences during detailed design.
- Confirm the product's accessibility, security, backup, deployment, and service-level requirements before launch. The feature list above is intended for launch unless explicitly marked deferred; implementation may need sequencing without dropping agreed functionality.

## Hosting and Backups

- Host the store and vendor app at `app.vndrhub.ca`. Reserve `www.vndrhub.ca` for a future public-facing site. DNS and deployment setup remain to be completed.
- The intended deployment is self-hosted on the owner's existing Proxmox server in a data centre, with VNDR Hub isolated in a VM or container. Confirm capacity, connectivity, security, and recovery arrangements before launch.
- Keep recurring costs minimal. Cloudflare R2 standard storage is a potential off-site backup destination; use its free allowance where practical and monitor usage. The owner accepts a small monthly storage cost if necessary to protect data.
- Aim to minimize lost sales data using frequent database backups and transaction-log backups. The recovery point and schedule must be determined and tested during implementation; do not promise zero data loss. Encrypt off-site backups, protect credentials, alert on failures, and periodically test restores.
- Back up the database, uploaded documents, and essential configuration; determine retention, restore procedures, and safe handling of encryption keys. The scope is VNDR Hub, not other applications on the server.
- Offline sales not yet synced to the server are stored only on the checkout device and cannot be recovered from server backups. Browser storage and device failure risks must be explained to stores.
- Codex can assist the owner with troubleshooting and code fixes, but is not a replacement for monitoring, backup verification, security maintenance, or an incident response plan.

