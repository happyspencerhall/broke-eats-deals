# Broke Eats deals feed

The Broke Eats app downloads `deals.json` from this repo every time it opens or is pulled to refresh.
Edit the file here (on GitHub: open it, click the pencil, commit). Phones pick up changes within a few minutes, without a new app build.

## Format

```json
{
  "updated": "Nov 21, 2026",
  "deals": [
    {
      "id": "unique-id",
      "chain": "mcdonalds",
      "title": "$5 Meal Deal",
      "details": "What you get.",
      "price": "$5",
      "days": [6],
      "appOnly": true,
      "starts": "2026-11-01",
      "ends": "2026-11-30",
      "allergens": ["wheat", "milk"]
    }
  ]
}
```

- `chain`: a chain id from `Chain.all` in the app (e.g. `mcdonalds`, `chipotle`, `pandaexpress`, `cava`). Deals for unknown chains are ignored.
- `allergens` (optional): any of `milk`, `egg`, `wheat`, `soy`, `peanut`, `treenut`, `fish`, `shellfish`, `sesame`. Use `[]` for none. Leave it out if unknown; people with allergies set will not see that deal.
- `days` (optional): weekdays the deal runs, 1 = Sunday … 7 = Saturday. Leave out for every day.
- `price`, `appOnly`, `starts`, `ends`: optional. Dates are `yyyy-MM-dd`.
- If the file has a JSON mistake, the app keeps using the last good copy.
