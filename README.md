# EdgeLock

A sports betting arbitrage and middle opportunity calculator for prop bets.

**Live:** [bensteffler.github.io/edgelock](https://bensteffler.github.io/edgelock)

## What It Does

EdgeLock helps you analyze betting opportunities where you can bet on both sides of a prop (e.g., Over 1.5 assists and Under 2.5 assists) to either:

- **Lock in guaranteed profit** (true arbitrage)
- **Find middle opportunities** where both bets can win

## Features

- **Scenario Detection**: Automatically identifies true arbitrage, middle opportunities, gap risks, and negative EV situations
- **Optimal Stake Calculator**: Shows how to distribute your bankroll for equal returns
- **Bet Rating System**: 0-100 score based on safety, middle size, and upside
- **Real-time Calculations**: Updates instantly as you type

## How Scoring Works

| Component | Max | Description |
|-----------|-----|-------------|
| Safety | 35 | Worst-case ROI (positive = high score) |
| Middle | 30 | Number of outcomes where both bets win |
| Upside | 35 | Best-case ROI potential |

**Scoring differences:**
- **Arbitrage**: Linear scaling for upside (finding 10% guaranteed profit is exceptional)
- **Middle**: Square root scaling (hitting middle naturally gives ~100% ROI)

## Scenario Types

| Type | Description | Example |
|------|-------------|---------|
| **True Arbitrage** | Adjacent ranges, guaranteed profit | Over 2.5 @ 2.3 + Under 2.5 @ 2.1 |
| **Middle Opportunity** | Overlapping ranges, both can win | Over 1.5 @ 2.1 + Under 2.5 @ 2.1 |
| **Gap Risk** | Non-adjacent ranges, both can lose | Over 2.5 @ 2.0 + Under 1.5 @ 2.0 |
| **Negative EV** | Combined implied prob > 100% | Over 2.5 @ 1.85 + Under 2.5 @ 1.95 |

## Usage

1. Enter bet type (Over/Under), line, and decimal odds for both bets
2. Enter your total stake
3. View the rating, scenario type, and optimal stake distribution

### Odds Conversion

| American | Decimal |
|----------|---------|
| +110 | 2.10 |
| -110 | 1.91 |
| +200 | 3.00 |
| -150 | 1.67 |

Formula:
- Positive American: `(odds / 100) + 1`
- Negative American: `(100 / |odds|) + 1`

## Local Development

Just open `index.html` in a browser. No build step required.

## License

MIT
