# Chipotle Mexican Grill (NYSE: CMG) - DCF Valuation

Driver-based DCF built from Chipotle's FY2025 10-K (filed 4-Feb-2026). Revenue is
forecast from a restaurant unit build (openings, closures, average unit volume), and every input is traced to a primary
filing, an official rate series, or a documented judgement call.

**Valuation date:** 31-Dec-2025 · **Currency:** USD, $ in millions except per-share figures

## Result

| | |
|---|---|
| Enterprise value | $37,871.6mm |
| Equity value | $39,117.9mm |
| Implied share price | **$30.04** |
| Market price (31-Dec-2025) | $37.00 |
| Implied downside | (18.8%) |

At the base-case assumptions below, the model implies the market is pricing in
more than this build supports, for a few reasons - either a faster return to unit growth than 350/yr,
a lower discount rate, or margin recovery beyond what FY2023 levels suggest.
See Sensitivity for how the answer moves with WACC and terminal growth changes.

## Method

**Revenue:** average restaurant count × average unit volume (AUV), then adjusted by
a calibration factor. AUV as disclosed is a trailing-12-month, food-and-beverage-only
figure for restaurants open more or equal to 12 months — a narrower base than total revenue — so
raw unit × AUV overstates FY2025A revenue by ~1.1%. A calibration factor (0.989)
corrects this and is held constant through the forecast.

**Costs:** each restaurant-level and corporate cost line is modeled as % of revenue,
anchored to its FY2025 actual and moved toward a normalized path (e.g. labor and occupancy are trended back down over the 
forecast as comps recover, since FY2025 deterioration tracked falling
AUV rather than rising cost).

**Capital structure:** Chipotle carries no debt (10-K: "we have no outstanding
debt"). WACC therefore equals cost of equity — no relevering, no interest tax
shield, no weighted blend.

**Leases:** treated as an operating expense, not debt. Total FY2025 lease cost
($671.1mm) exceeds the entire Occupancy line ($624.9mm), meaning lease cost is
already embedded across several expense lines with no disclosed split — so the 
lease liability is excluded from net debt rather than estimated back
into EBITDA. Consequence: EBITDA/EV here are not comparable to lease-capitalized
multiples.

**Terminal value:** Gordon growth at 2.5%, chosen because Chipotle's own long-term
target is 7,000 restaurants (a finite ceiling) — so perpetual growth past that
point can only come from pricing, not units. Terminal capex is separately sized
(not just set to D&A) to satisfy g = ROIC × reinvestment rate, using an estimated
~25% incremental ROIC per new restaurant.

## Key assumptions

| | Value | Source |
|---|---|---|
| Risk-free rate | 4.18% | US Treasury, 10-yr CMT, 31-Dec-2025 |
| Equity beta (unlevered, cash-corrected) | 0.783 | Damodaran, Restaurant/Dining, 64 firms (Jan-26) |
| Equity risk premium | 4.46% | Damodaran implied ERP, US (Jan-26) |
| WACC ( = cost of equity, D/E = 0) | 7.67% | — |
| Terminal growth rate | 2.5% | Menu pricing history vs. finite unit ceiling |
| Effective tax rate | 23.6% | FY2025A, 10-K |
| New restaurant openings | 350/yr | FY2026 guidance (350–370 incl. 10–15 partner-operated) |
| Projection period | 5 years | Terminal value equals ~ 83% of enterprise value |

Full rationale for every judgement call — including why the US-specific ERP was
used over the mature-market figure, why beta is cash-corrected, and why change
in NWC is held at zero — is logged in the `Sources` tab with citations to
specific pages and notes of the 10-K and third-party academic sources.

## Limitations encountered

- WACC is tested across 6.67%–8.67% and terminal growth across 1.5%–3.5% 
  in the sensitivity grid in `DCF` tab; the current-year industry beta (0.783) 
  is used in the base case rather than the 5-year sector average (1.03), 
  which trends materially higher.
- Cost-driver recovery paths (labor, occupancy trending back toward FY2023
  margins) are a judgement, not a disclosed target.
- EV/EBITDA here is not comparable to peers reporting under lease-capitalized
  conventions.

## Files

- `DCF.project.CMG.xlsx` — full model (Cover, Assumptions, Historicals, DCF, Sources)
- Historicals transcribed directly from the FY2025 10-K, balance-sheet-ties and
  revenue-bridge checks included on the Historicals tab

## Sources

- Chipotle Mexican Grill, Inc. Form 10-K, FY2025 (filed 4-Feb-2026) — SEC EDGAR
- US Department of the Treasury, Daily Treasury Par Yield Curve Rates
- Aswath Damodaran (NYU Stern) — industry beta and implied ERP datasets
- WSJ Markets Data — historical closing price (comparator only; not a valuation input)
