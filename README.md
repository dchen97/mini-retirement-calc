# Mini Retirement Planner

A single-file interactive dashboard for planning mini retirements — extended career breaks taken before full retirement — and visualizing their real impact on your long-term financial trajectory.

**[→ Try it live](https://dchen97.github.io/mini-retirement-calc/)**

![Status](https://img.shields.io/badge/type-single--file%20HTML-blue) ![License](https://img.shields.io/badge/license-MIT-green)

---

## What it does

Most retirement calculators assume you work continuously until you stop forever. This one doesn't. It lets you model one or more "mini retirements" — periods where you pause work, live off your investments, and then return — and shows you in real time whether you'll still hit your FIRE number by the time you fully retire.

The dashboard runs a **year-by-year portfolio simulation** from your current age to 100, across three distinct life phases:

- **Working years** — portfolio grows at 7% annually, plus optional annual savings contributions
- **Mini retirement years** — no contributions; portfolio grows at 7% but you withdraw to cover living expenses
- **Full retirement** — permanent 4% withdrawal rate to fund retirement spending

## Features

- **FIRE number calculation** — derived from your expected retirement spending at a 4% withdrawal rate
- **Live portfolio trajectory chart** — color-coded by phase (working / mini retirement / retired / depleted)
- **FIRE reached indicator** — marks the exact age your portfolio first crosses your FIRE number
- **Mini retirement opportunity cost** — shows how much your retirement balance is reduced vs. no career breaks
- **Surplus / deficit** — how far above or below your FIRE number you'll land at retirement age
- **Status indicator** — ON TRACK / AT RISK / DEPLETED, updates instantly as you adjust inputs
- **Life phase timeline** — a visual bar showing your full working/mini-retirement/retirement schedule
- **Optional annual savings** — toggle on to add yearly contributions during working years
- **Multiple mini retirements** — add as many as you want, each with independent start/end ages and a spending level slider

## Definitions

| Term | Definition |
|---|---|
| **Retirement** | The point after which you plan to have no (or little) outside income beyond the appreciation of your investments. |
| **Mini Retirement** | A defined span of time during which you similarly have no (or little) outside income beyond investment appreciation, before eventually returning to work. |

## Assumptions

| Parameter | Value |
|---|---|
| Investment growth rate | 7% annually |
| Withdrawal rate (retirement) | 4% (the "4% rule") |
| Life expectancy target | Age 100 |
| Mini retirement spend | Drawn from portfolio (no income, no contributions) |

## Usage

No build step. No dependencies to install. Just open the file.

```bash
git clone https://github.com/dchen97/mini-retirement-calc.git
cd mini-retirement-calc
open index.html
```

Or drag `index.html` into any browser window.

### Inputs

| Input | Description |
|---|---|
| Current Age | Your age today |
| Retirement Age | The age you plan to fully retire |
| Current Investments | Total invested assets today |
| Current Annual Spending | What you spend per year right now |
| Retirement Spending | % of current spending you expect in retirement (slider) |
| Annual Savings *(optional)* | Additional amount invested per year during working years |
| Mini Retirements | One or more breaks, each with a start age, end age, and spending % |

## Tech

Pure HTML, CSS, and vanilla JavaScript — no framework, no bundler, no backend. Chart rendered with [Chart.js](https://www.chartjs.org/). Everything runs locally in your browser; no data is sent anywhere.

## Author

Built by [Diana Chen](https://linkedin.com/in/DianaKChen). If you find it useful, [buy me a coffee](https://ko-fi.com/dkitchen) ☕
