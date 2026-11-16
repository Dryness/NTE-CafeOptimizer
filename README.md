# Cafe by Origen — Roster Optimizer

Access the website at https://dryness.github.io/NTE-CafeOptimizer/

A web-based optimizer for Cafe by Origen. Finds the best dish menu and character team to maximize Fons/hr income.

## Credits

This is a fork of [Kuro-121/NTE-CafeOptimizer](https://github.com/Kuro-121/NTE-CafeOptimizer), created by [Kuro-121](https://github.com/Kuro-121), with contributions from [its contributors](https://github.com/Kuro-121/NTE-CafeOptimizer/graphs/contributors). All credit for the original optimizer goes to them. The original site is at https://kuro-121.github.io/NTE-CafeOptimizer/.

This fork adds:
- Akane Rin
- Trend bonus applied after the price multiplier ([Kuro-121#4](https://github.com/Kuro-121/NTE-CafeOptimizer/issues/4))
- Own All / Set All L5 buttons on the Characters tab
- Default Trend Bonus for common trends
- Characters, Character Buffs and Best Menu shown in game order

These changes have been submitted upstream in [Kuro-121#5](https://github.com/Kuro-121/NTE-CafeOptimizer/pull/5).

## Features
- Full optimizer engine (Traffic Flat/Multiply, Price Flat/Multiply)
- Trend bonuses applied automatically
- Manage dishes, characters, ingredients via UI
- Data persists in browser (localStorage)
- English and Simplified Chinese interface
- Default data loaded from `data.json` on first visit

## Skill Format

Each character skill has:
- **Level** — minimum character level to unlock
- **Value** — the buff amount
- **Req** — how many matching menu tags are needed to activate
- **Type** — `Price_Flat`, `Traffic_Flat`, `Price_Multiply`, `Traffic_Multiply`
- **Tag** — which dish type to count (`None`, `Any`, or a specific type like `Beverages`)

## How Multipliers Work

- `Traffic_Multiply` is applied **after** all flat traffic buffs
- `Price_Multiply` multiplies the **final dish price** (base + all flat buffs) by a percentage
- Both multipliers scale with the number of matching menu tags
- How the trend bonus is applied depends on the trend:
  - **Dish-type trends** (e.g. `Main Dishes`) add to the dish's base price, so `Price_Multiply` scales the bonus
  - **Ingredient trends** (e.g. `Coffee Beans`) add a flat amount **after** `Price_Multiply`, so it is not scaled
