# Playa Run — handoff

**Burning Man 2026 (Axis Mundi), Aug 30 – Sep 7.** Staged out of Las Vegas.
Last updated: Mon Aug 24, 2026.

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
| Thu Aug 27 | **The only day with a car.** Storage unit + Home Depot + Target + REI pickup. He is also working this day. |
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
- REI — 27 food pouches ($285.60) + 2 Aqua-Tainers + 2 water bottles. Paid. **Collect Thursday**
  at Henderson, 2220 Village Walk Dr, closes 9pm weekdays.
- Amazon — Nuun electrolytes + solar shower bag. Arrive Tue Aug 25; must go in a checked bag.

**Open**
- **Home Depot, Thursday** — cord, power strip, GFCI, tapes, zip ties, contractor bags, N95s,
  gloves, paracord, carabiners, LED lantern.
- **Target, Thursday** — the long list: kettle, hygiene, medical, shelf-stable food, kit.
- **AC unit** being delivered to Boulder Station. Hard deadline: **Friday 11am checkout.** Confirm
  the hotel holds packages under his reservation name.
- **Goggles and headlamp** — both priority 1, neither ordered. Confirm at the storage unit
  Thursday; Target the same afternoon if missing.

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
  1401 S Lamb Blvd or 1030 W Sunset Rd, Henderson.

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
- Item keys are `data-list` + position, so **reordering a list shifts its saved state.**

## Style notes

He wants the list, not commentary. He pushed back twice: *"I didn't ask you to question my trip"*
and *"when you remove the cut from the website, it's noise."* State a real concern once, briefly,
then do the thing. Don't re-raise settled points — he told me twice that camp has water before I
stopped flagging it.
