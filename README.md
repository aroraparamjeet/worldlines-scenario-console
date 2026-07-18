# Worldlines — Scenario Console

An interactive geopolitical scenario simulator. Adjust world drivers such as a prolonged Middle East war, US protectionism, dollar collapse, AI labor displacement, climate acceleration, and demographic decline, then watch outcomes recompute for 39 countries in real time.

Two views are included, both self-contained single HTML files:

| File | View |
|---|---|
| `index.html` | **3D globe.** Drag to rotate, scroll to zoom, click a country marker for details. Marker color and height encode the computed score. Built with three.js (loaded from CDN). |
| `tile-map.html` | **2D tile map.** Countries as a geographic tile grid colored red to green, with the same model and controls. |

## How it works

- **Drivers.** Ten preset scenario drivers, each with an intensity slider (0 to 100), an on/off toggle, and a remove button. You can also add custom drivers by naming them, picking which country groups they affect (oil exporters, aging societies, US-aligned, tech leaders, and so on), choosing hurt or help, and setting strength.
- **Country model.** Each country carries an exposure profile: export dependence, dollar exposure, Middle East proximity, climate vulnerability, demographics, alignment, and more. Each driver applies weighted impacts against those exposures.
- **Score.** `score = baseline + sum(active driver effects)`, clamped to 4 to 96, mapped to a continuous red to amber to green scale and a letter grade (A to F).
- **Details.** Clicking a country shows the grade, score versus baseline, a short narrative, a signed contribution bar for every driver, and the exposure profile behind the calculation.
- **World Index.** The header shows the average score across all countries and the delta versus today's baseline, plus counts of stable, strained, and in-crisis countries.

## Running it

No build step. Clone and open either file in a modern browser:

```
git clone https://github.com/aroraparamjeet/worldlines-scenario-console.git
cd worldlines-scenario-console
open index.html
```

The only network calls are Google Fonts and the three.js CDN (globe view). Everything else, including the stylized continent outlines, is generated in code.

## Disclaimer

The weights and baselines are directionally reasoned estimates, not empirical forecasts. This is a thinking tool for exploring how geopolitical and economic pressures interact, not a prediction machine or investment advice.
