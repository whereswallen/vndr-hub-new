# VNDR Hub Design Prompt Playbook

Foolproof, copy-paste prompts for designing every page with Claude Design at [claude.ai](https://claude.ai).

The boxes below use plain code fences. The rule is always the same: **copy the ENTIRE box, from the very first word to the very last word.** Nothing outside the box is ever copied.

---

## How this works

You will do **8 rounds**, one per screen. Each round is the same 3 moves:

1. **Open a NEW chat** at claude.ai. New chat each time means no leftover confusion.
2. **Copy one box** from this file and **paste it into the chat message box**, then press Enter.
3. Claude replies with a live design in an "Artifact" panel on the right. If you like it, save it. If not, type what to change in plain English, such as "make the buttons bigger" or "the green is too bright", and press Enter again.

**The only thing you ever fill in yourself** is your DESIGN TOKENS, and Round 0 hands them to you ready to paste. That's it.

**Do Round 0 first and do not skip it.** It creates the look every other screen copies. Skipping it means every page looks different, which makes the app look amateur.

---

## ROUND 0 - Create your look

Do this first, one time.

**Move 1:** Open a new chat at claude.ai.

**Move 2:** Copy the WHOLE box below and paste it in:

```text
You're helping me build the visual design system for VNDR Hub, a modern multi-vendor Point-of-Sale SaaS for Canadian antique malls and consignment shops. The feeling should be clean, professional, and engineered - the opposite of the dated beige software our competitors use.

Design a one-page component style guide that shows, in BOTH light and dark themes, all of the following:
- A color palette: one primary accent color, neutral greys, and success / warning / error colors. Label every color with its hex code.
- A typography scale: headings, body text, and a monospace font used for money and barcodes.
- Buttons: primary, secondary, and destructive (delete) styles.
- Form inputs: a text field, a dropdown, a focused field, and a field showing an error.
- One data-table row.
- Status badges: Active, Pending, Paid, Void.
- One card.

Rules: money always renders in the monospace font with the decimals lined up. Build it as a single self-contained HTML artifact with inline CSS, and put a light/dark toggle button at the top so I can flip between themes.

At the very end of your reply, OUTSIDE the artifact, print a plain-text block titled "DESIGN TOKENS" that lists the exact font names and the exact hex codes you chose, formatted so I can copy-paste it into future prompts.
```

**Move 3:** Claude builds the style guide and, at the bottom of its text reply, prints a block that starts with **DESIGN TOKENS**.

**SAVE THIS:** Select that DESIGN TOKENS block, copy it, and paste it into a notes file or keep the tab open. You will paste it into every round below. From here on, wherever a box says `[PASTE YOUR DESIGN TOKENS HERE]`, you replace those words with that block.

**Example** of what a finished paste looks like. Yours will have different values:

```text
Screen: Vendor list
Use this exact design system:
DESIGN TOKENS
Fonts: Headings = Space Grotesk, Body = Inter, Money = JetBrains Mono
Primary accent: #2563EB
Neutrals: #0F172A / #334155 / #94A3B8 / #F1F5F9
Success #16A34A, Warning #D97706, Error #DC2626
...rest of screen prompt...
```

That's the only editing you ever do: swap `[PASTE YOUR DESIGN TOKENS HERE]` for your real block.

---

## ROUNDS 1-7 - One box per screen

For every round: **new chat -> paste the whole box -> press Enter.** Before pasting, replace the line `[PASTE YOUR DESIGN TOKENS HERE]` with your saved DESIGN TOKENS block.

### ROUND 1 - Vendors & Booths

```text
You're designing ONE screen for VNDR Hub, a multi-vendor POS for Canadian antique malls.

Use this exact design system:
[PASTE YOUR DESIGN TOKENS HERE]

Screen: Vendor list with a vendor-detail side panel.
What the user does here: the mall operator browses their dealers, sees who's active, and clicks one to see details and which booth they rent.
Data to show (use these real example values, not lorem ipsum):
- A table of vendors with columns: Vendor Code (V-014, monospace), Display Name (Prairie Relics), Booth (B-22), Commission (10%), Status badge (Active / Inactive), This Month's Sales ($1,240.00). Show 4 example rows with varied values.
- A detail panel for one selected vendor: contact email, phone, payment method, monthly booth rent ($85.00), commission rate (10%).
Must include these four states: loading, empty (no vendors yet), error, and the normal full state.
Rules: desktop-first (operators use a laptop), works in light AND dark theme, all money in the monospace font.

Build it as a single self-contained HTML artifact with inline CSS and a light/dark toggle.
```

### ROUND 2 - Inventory & Label Printing

```text
You're designing ONE screen for VNDR Hub, a multi-vendor POS for Canadian antique malls.

Use this exact design system:
[PASTE YOUR DESIGN TOKENS HERE]

Screen: A vendor's inventory list, PLUS a print-preview sheet of barcode price tags.
What the user does here: a vendor manages their items, then prints barcode tags at home to stick on their products.
Data to show (real example values):
- Inventory table columns: SKU (PR-0142, monospace), Item Name (Vintage Brass Lamp), Price ($45.00), Qty (3), Category (Lighting). Show 4 rows.
- A print sheet: a grid of price tags, each tag showing the shop name, the item name, the price, and a Code128-style barcode.
Must include these four states for the inventory list: loading, empty, error, normal.
Rules: the inventory screen works in light AND dark theme; the print sheet is white-background only because it goes on paper. All money in the monospace font.

Build it as a single self-contained HTML artifact with inline CSS and a light/dark toggle.
```

### ROUND 3 - POS Terminal

```text
You're designing ONE screen for VNDR Hub, a multi-vendor POS for Canadian antique malls.

Use this exact design system:
[PASTE YOUR DESIGN TOKENS HERE]

Screen: The full-screen POS checkout terminal - this is the most important screen in the app, make it excellent.
What the user does here: a cashier scans items into a cart, sees Canadian sales tax break down automatically, and takes payment.
Layout: left side = a large search / scan bar and a grid of tappable products; right side = the cart and the totals.
Data to show (real example values):
- Cart items GROUPED BY VENDOR (each vendor name is a small subheading), each line showing item name, quantity, and price.
- A totals block that breaks tax out SEPARATELY (this is critical for Canada): Subtotal $120.00, GST (5%) $6.00, PST (7%) $8.40, Total $134.40.
- Three large payment buttons: Cash, Card / Interac, Split.
Also design the printed receipt: it shows the shop's GST/HST number, the tax broken out separately, and the itemized list.
Must include these states: empty cart, a cart with items, and a payment-processing state.
Rules: touchscreen-friendly with big tap targets, works in light AND dark theme, all money in the monospace font.

Build it as a single self-contained HTML artifact with inline CSS and a light/dark toggle.
```

### ROUND 4 - Vendor Portal Mobile

```text
You're designing ONE screen for VNDR Hub, a multi-vendor POS for Canadian antique malls.

Use this exact design system:
[PASTE YOUR DESIGN TOKENS HERE]

Screen: The vendor portal home screen, designed for a PHONE (mobile width).
What the user does here: a dealer opens their phone to watch their sales happen in real time.
Data to show (real example values):
- A big hero number = today's net earnings, shown very large in the monospace font: $318.40.
- A live sales feed below it: each recent sale is a card showing item name, time (2:14 PM), and amount ($45.00), newest on top. Show 5 cards.
- A small stat row: Today / This Week / This Month totals.
Must include these four states: loading, empty (no sales yet today), error, and the normal full state.
Rules: mobile-first - design it at phone width. Works in light AND dark theme. Should feel alive and modern. All money in the monospace font.

Build it as a single self-contained HTML artifact with inline CSS and a light/dark toggle.
```

### ROUND 5 - Settlements & Payouts

```text
You're designing ONE screen for VNDR Hub, a multi-vendor POS for Canadian antique malls.

Use this exact design system:
[PASTE YOUR DESIGN TOKENS HERE]

Screen: A vendor's monthly statement / payout summary.
What the user does here: the operator and the vendor both review the math of what the vendor gets paid this period.
Data to show (real example values), as a clean financial document:
- Gross Sales $2,400.00, minus Commission -$240.00, minus Booth Rent -$85.00, minus Processing Fees -$62.00, equals Net Payout $2,013.00 (make the net payout the visual hero).
- Below that, a line-item list of the individual sales that made up the gross.
- A payout status badge (Pending / Paid) and the payout method (Interac e-Transfer / EFT).
Must include these four states: loading, empty (no sales this period), error, normal.
Rules: looks like a clean, trustworthy financial statement. Works in light AND dark theme. All money in the monospace font and right-aligned so decimals line up.

Build it as a single self-contained HTML artifact with inline CSS and a light/dark toggle.
```

### ROUND 6 - Onboarding Wizard

```text
You're designing ONE screen for VNDR Hub, a multi-vendor POS for Canadian antique malls.

Use this exact design system:
[PASTE YOUR DESIGN TOKENS HERE]

Screen: A multi-step setup wizard for a brand-new shop signing up.
What the user does here: a mall owner sets up their account in guided steps, feeling reassured.
Data to show:
- A progress bar with 5 steps: 1) Shop info, 2) Province & tax, 3) Connect payments, 4) Add vendors, 5) First product.
- Design step 2 in detail: a dropdown to pick the province, which then auto-fills the correct tax rates (show an example: choosing Ontario fills in "HST 13%").
- Design step 3 in detail: a big primary button "Connect your Square account", with a smaller secondary option "Use Stripe instead".
Rules: friendly and reassuring tone (this user is nervous and new). Works in light AND dark theme.

Build it as a single self-contained HTML artifact with inline CSS and a light/dark toggle.
```

### ROUND 7 - Operator Dashboard

```text
You're designing ONE screen for VNDR Hub, a multi-vendor POS for Canadian antique malls.

Use this exact design system:
[PASTE YOUR DESIGN TOKENS HERE]

Screen: The main operator dashboard - the home screen the mall owner sees after logging in.
What the user does here: sees how the whole business is doing at a glance.
Data to show (real example values):
- Four KPI cards across the top: Today's Sales $3,240.00, Active Vendors 42, Commission Owed $1,180.00, Tax Collected $421.00.
- A sales-over-time line chart.
- A "Top Vendors" list and a "Low Stock Alerts" list.
Must include these four states: loading, empty (brand-new shop with no data), error, and the normal full state.
Rules: desktop-first, works in light AND dark theme, all money in the monospace font, charts clean and easy to read.

Build it as a single self-contained HTML artifact with inline CSS and a light/dark toggle.
```

---

## When a design isn't right

Don't start over. In the SAME chat, type the change in plain English and press Enter. Examples that work:

- "The accent color is too bright - make it calmer."
- "Make the cart text bigger and the buttons taller."
- "Move the totals to the top."
- "This looks cramped - add more spacing."

Claude updates the same design. Repeat until happy.

---

## Saving each finished design

When you like a screen, you have two easy options:

1. In the Artifact panel, use its menu to **Copy** the code, and paste it into a file named after the screen, such as `design-pos.html`, in a folder like `designs/`.
2. Or just keep the chat. You can return to it anytime.

You are NOT wiring these into the real app yet. These are visual mockups that tell you, and later the coding step, exactly what each page should look like. When you build each phase from the VNDR Hub build plan, you hand the matching mockup to the coding tool as the visual target.

---

## The order to do everything

Do them interleaved, screen by screen: design a screen, then build it, then move on. This keeps the design matched to real data.

0. **Round 0 (design system)** - do this first, before anything.
1. Build **Phase 0** (foundation/login) - no fancy design needed yet.
2. **Round 3 (POS design)** early, even before you build it - it's your differentiator; seeing it guides everything.
3. Then for each remaining phase: **design the screen (its Round) -> build that phase (its Phase prompt from the build plan) -> check it -> next.**

Phase 1 build <-> Round 1 design  
Phase 2 build <-> Round 2 design  
Phase 3 build <-> Round 3 design  
Phase 4 build <-> Round 4 design  
Phase 5 build <-> Round 5 design  
Phase 6 build <-> Round 6 design  
Phase 7 build <-> Round 7 design

Rule of thumb: **never build a page you haven't designed, and never design a page more than one step ahead of building it**, except the POS, which you design early on purpose.

