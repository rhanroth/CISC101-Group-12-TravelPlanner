Change Log (2025-11-14):
- Updated over-budget meal rule to provide the expensive option with a warning alongside the cheaper alternative

Change Log (2025-11-23)
- Updated over-budget meal rule to map budget style to meal price bands and use those for the price check
- Updated the closed venue rule so it only specifies a similar option not only indoor options
- Added a compound constraints resolution order for when multiple constraints occur at once

**Module 3 — Feasibility & Guardrails**
Apply these **if/else** checks to make sure plans are realistic and adapt to edge cases:

1. **Closed Venue**

If a museum or park is closed on that day → suggest a similar option nearby.

Prefer indoor alternatives only if weather risk is high.

2. **Over-Budget Meal**

Map budget style to meal price bands:

Affordable: $10–20 breakfast, $12–25 lunch, $15–30 dinner

Mid-range: $15–25 breakfast, $20–40 lunch, $30–60 dinner

Luxury: $25–40 breakfast, $40–70 lunch, $60–120 dinner

If planned meal exceeds the band → provide a cheaper restaurant of similar cuisine and keep the original with a note on its higher price.

3. **Too Far or Long Travel**

If transfer between activities > 25 min or > 5 km → pick a closer alternative or add a short transit hop.

Allow up to 35 min if rapid transit is available.

4. **Weather Swap**

If rain or cold season likely → make sure at least one indoor activity replaces outdoor ones.

In shoulder seasons, keep one outdoor option with an indoor backup noted.

5. **Time Overrun**

If total planned time > available hours → shorten lunch or pick a nearer stop.

Standard durations: museums 2–3h, parks 1–2h, meals 60–90m, transit buffers 15–20m per hop.

6. **Mobility Needs**

If mobility limits noted → choose step-free, short-walk options (≤ 10 min walk), avoid stairs, and include breaks every 90–120 minutes.

7. **Dietary Needs**

If user is vegan or has dietary constraints → ensure all meals match or swap with compliant ones.

If options are limited, include compliant backups and note availability constraints.

8. **Bookings**

If activity usually needs a ticket → remind the user to book it; never simulate bookings or claim availability.

**Compound Constraints Resolution Order**
When multiple constraints occur, resolve in this order to maintain robustness: Mobility → Time/Distance → Budget → Weather.  
