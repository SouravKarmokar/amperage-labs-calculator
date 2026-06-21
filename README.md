# Amperage Labs

Off-grid solar, battery, and MPPT sizing calculator. Built to answer one question properly: *how big does my battery bank and solar array actually need to be?*

Live at: [amperage-labs-calculator.vercel.app](https://amperage-labs-calculator.vercel.app/)

## What it does

Most sizing calculators give you a number with no explanation. This one shows the formula behind every result, lets you tweak Depth of Discharge per battery chemistry, and includes a recharge-time estimate so you know how long your system takes to recover after running on battery for a few days.

- Battery bank sizing (Wh and Ah) based on daily load, autonomy days, and DoD
- Solar array wattage with a 30% real-world loss margin
- MPPT controller current rating
- Recharge time estimate, with a sulfation warning for Lead-Acid setups
- Regional Peak Sun Hours presets (Bangladesh, Europe, USA) plus a quick-reference table
- Dark mode
- Shareable config via URL params
- Full methodology page with derivations and assumptions

## Stack

- [Astro](https://astro.build) — static site framework
- [Tailwind CSS](https://tailwindcss.com) — styling
- Vanilla TypeScript for the calculator logic (no framework overhead for a single interactive page)
- Deployed on [Vercel](https://vercel.com)

## Project structure

```text
/
├── public/
│   └── favicon.svg
├── src/
│   ├── layouts/
│   │   └── Layout.astro
│   └── pages/
│       ├── index.astro          # the calculator
│       └── methodology.astro    # formula breakdown & assumptions
└── package.json
```

## Running it locally

```sh
git clone https://github.com/yourusername/amperage-labs-calculator.git
cd amperage-labs-calculator
npm install
npm run dev
```

Then open `localhost:4321`.

## Commands

| Command             | What it does                              |
| -------------------- | ------------------------------------------ |
| `npm install`         | installs dependencies                      |
| `npm run dev`          | starts the dev server                      |
| `npm run build`         | builds for production into `./dist/`       |
| `npm run preview`        | previews the production build locally      |

## Notes on the calculations

The sizing formulas follow standard off-grid design practice — battery bank sized for autonomy and DoD, solar array sized for daily replenishment with a loss margin, charge controller derived from array output. Full derivations, worked examples, and what the tool deliberately doesn't account for (panel string config, shading, inverter VA sizing, grid-tied setups) are documented on the [methodology page](https://amperage-labs-calculator.vercel.app/methodology).

## License

Source is public for portfolio and transparency purposes. All rights reserved — please don't redistribute or deploy this as your own without permission.
