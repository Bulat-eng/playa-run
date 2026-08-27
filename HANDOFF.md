# Playa Run — handoff

**Burning Man 2026 (Axis Mundi), Aug 30 – Sep 7.** Staged out of Las Vegas.
Last updated: Thu Aug 27, 2026 — car day.

- **Live list:** https://bulat-eng.github.io/playa-run/
- **Artifact (syncs checkbox progress):** https://claude.ai/code/artifact/64ea8fa4-8d57-46c5-811e-4dfb82e09cef
- **Repo:** https://github.com/Bulat-eng/playa-run — this folder is the git root

---

## The shape of the trip

Bulat is **hitching a ride in friends' rented RV** and **sleeping in their tent**. He is a
passenger, not a resident: no galley access, **no cooler**, so the whole trip is shelf-stable.
Camp provides **power and shade**, and **water** (he carries two 7-gal containers as his own
supply). Camp does **not** provide meals — hence the REI freeze-dried order.

Ticket and vehicle pass are **purchased**; collected at the Box Office at the front gate, which
runs 24/7 from Aug 24 through Sep 5 noon. Photo ID must match the purchase.

**No gifting** this year — he asked for it to be dropped entirely. Don't reintroduce it.

## Fixed itinerary

| When | What |
|---|---|
| Wed Aug 26, 11:30am | Flight JFK → LAS, lands 2:01pm. Ubers to hotel. |
| Wed 26 – Fri 28 | Boulder Station, 4111 Boulder Hwy. Checkout Fri 11:00am. |
| Thu Aug 27, 10:30am | Rental car, Enterprise 3745 Boulder Hwy. **Needs the Costco card.** |
| Thu Aug 27 | **The only day with a car.** Storage unit + Target (collect + shop) + Costco + REI pickup. Home Depot is now a delivery, so no store stop. He is also working this day. |
| Fri Aug 28, 10:30am | Car back. Then RV pickup 1–4pm, depart. |
| Sun Aug 30, 12:01am | Gate opens. |
| Mon Sep 7 | Exodus. |
| Wed Sep 9, 10:33am | Flight home from **Reno** (RNO → LAX → JFK). |

Two free checked bags, 70 lb each, both directions (Gold Medallion).
Reno car booked Sep 7–9, dropping at RNO. **No Reno hotel** — nothing refundable was available.

Handy coincidence: Enterprise (3745), El Monte RV (3800), and the hotel (4111) are all on the
same half-mile of Boulder Hwy.

## Status

**Done**
- **Target — pickup order placed.** #102003506421687, $278.01, Order Pickup at **Las Vegas
  Flamingo, 4001 S Maryland Pkwy** (702-732-2218, 8am–10pm). Ten lines: kettle, DUDE wipes,
  Boka toothpaste, rodent-repellent trash bags, LED mirror, TENCEL sheet set, chunky knit
  blanket, cooling pillow, 2 gal water, smartwater 6pk. Paid on the Target Mastercard.
- **Home Depot — delivery order placed.** Contents and delivery date not visible (his HD login
  is `156s2ndstreet@gmail.com` and demanded re-auth; the order emails don't land in
  milkypillow@). The section is now a confirm-against-the-email checklist.
- **REI — #A405567097**, ready since Mon Aug 24, held until **Sun Sep 6**. Collect Thursday.
  (The old #A382376840 in earlier versions of this file was wrong.)
- **Amazon — #112-6979851-2410603**, shipped in two boxes. Shower bag delivered Wed Aug 26 and
  is in his hands. Nuun delivered Mon Aug 24 and is **still at the hotel front desk**.

**Open**
- **AC unit — the one real exposure.** Costco order, UPS **1Z824E850314932879**, Ground, last
  scanned Hodgkins IL Wed 5:39pm, estimated **Fri Aug 28 9:30am–12:30pm** into Las Vegas.
  Checkout is 11:00am. Plan on the page: bell desk holds it → late checkout → UPS Access Point
  redirect as fallback → re-check the estimate Thursday night.
- **Costco run, Thursday** — batteries (moved off the Target list) and socks. SW Henderson
  #1320, 3411 St Rose Pkwy, closes 8:30pm. Slots in before the REI pickup.
- **Target in-store list, Thursday** — everything the pickup order doesn't cover: hygiene,
  medical, sleep, shelf-stable food, kit. Same visit as the collection.
- **Goggles and headlamp** — still unbought. Confirm at the storage unit Thursday; Target the
  same afternoon if missing.
- **Home Depot delivery date and address** — unconfirmed.

## Decisions worth not re-litigating

- **Extension cord: 12/3, not 10 AWG.** He'd been looking at a 100 ft 10 AWG at $107.99. At real
  camp draw (2–5 A) the gauge difference is invisible; 12/3 is roughly half the price.
- **Kettle stays, cooking gear went.** No propane stove, no canisters, no insulated bag — he isn't
  cooking. The kettle is the only heat source for the pouches.
- **Nuun over everything.** $0.39/serving vs $1.45 for Target's cheapest.
- **REI pickup in Vegas, not Reno** — it's all his food; don't gamble it on a drive-by during
  store hours.
- **No REI apparel.** He returned $388 of it last year.
- **Cash: $100** is enough. No cooler means no ice runs.
- **Not "Mobile Home Depot"** at 4305 Boulder Hwy — that's a mobile-home parts store. Use
  1401 S Lamb Blvd or 1030 W Sunset Rd, Henderson. Moot unless the delivery comes up short.
- **Batteries moved to Costco**, not Target. Socks added there too — his call.
- **Target store is Las Vegas Flamingo (#265)**, not a Henderson one. The `/sl/<slug>/<number>`
  URL is keyed on the number; the slug is ignored, so a wrong number silently shows another state's store.

## Removed on request — don't re-add

Gifting · the Vegas storage-pull checklist · the Reno section (bike, filling water containers,
ATM, fuel) · rebar, caps, mallet, ground tarp · bucket and lid · bungee cords · broom and dustpan ·
vinegar and spray bottle · moisturizer · sunscreen (he has it) · repair cream · towels · comb,
tweezers, nail clippers · chocolate and almond butter (melted last year) · the "Cut" section itself
(he found it noisy).

## Working on this

Single self-contained `index.html`. Edit it, then:

```bash
cd ~/Documents/Playa/playa-planner/playa-run && git add -A && git commit -m "..." && git push
```

Republish the artifact from the same path with
`url: https://claude.ai/code/artifact/64ea8fa4-8d57-46c5-811e-4dfb82e09cef` to keep the link.

- `private/list-with-bookings.html` is **gitignored** — same page but retaining the hotel and
  rental confirmation numbers. The public copy has them stripped; keep it that way.
- Finished sections become `<details class="fold">` with a `done-tag` and a `.recap` list. Printing
  force-opens them.
- Checkbox state syncs via `artifact.publish({"state.json": ...})`, falling back to `localStorage`
  on GitHub Pages. A **Copy status** button in the footer is the reliable manual path.
- Item keys are `data-list` + position, so **reordering a list shifts its saved state.** The
  Aug 26 rewrite reordered and renamed the lists, so `LOCAL_KEY` moved to `playa-run-v6` — old
  ticks are intentionally dropped rather than landing on the wrong rows.
- **The GitHub push is held.** The page now carries the UPS tracking number and the Target,
  REI and Amazon order numbers; Pages is public. The artifact is private and has them. Ask
  before pushing, or strip the identifiers from the public copy first.

## Style notes

He wants the list, not commentary. He pushed back twice: *"I didn't ask you to question my trip"*
and *"when you remove the cut from the website, it's noise."* State a real concern once, briefly,
then do the thing. Don't re-raise settled points — he told me twice that camp has water before I
stopped flagging it.
