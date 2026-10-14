# Fibonacci Circles on a Regression Line (Pine Script v6)

A TradingView indicator that anchors a set of Fibonacci circles to a linear regression line and draws them as smooth line segments on the chart.

## What it does

- Fits a linear regression (`ta.linreg`) over a user-defined lookback window and optionally plots it.
- Chooses an anchor point (window midpoint, latest bar, or a fixed bar offset) and a base radius derived from the price range or set manually.
- Draws circles at the classic Fibonacci ratios (0.236, 0.382, 0.5, 0.618, 0.786, 1.0, 1.618, 2.618), each toggleable.
- Adapts circle smoothness to the horizontal radius and caps the total number of line objects so the script stays under TradingView object limits.

## Inputs

| Group | Input | Purpose |
|---|---|---|
| Regression | Source, Regression Length, Show Regression Line, Regression Color | Lookback and display of the regression line |
| Anchor | Anchor Mode, Bar Offset | Where the circles are centred |
| Radius | Radius Mode, Manual Base Radius, Auto Radius Multiplier | Vertical scale of the circles |
| Shape | Base Circle Smoothness, Horizontal Scale (bars), Horizontal Scale Adjust | Segment count and horizontal stretch |
| Levels | Show 0.236 ... Show 2.618 | Toggle individual Fibonacci levels |
| Style | Circle Color, Line Width | Appearance |

## Usage

1. Open the Pine Editor in TradingView.
2. Paste the contents of `fibonacci_circles_regression.pine`.
3. Click **Add to chart** and tune the inputs. If circles look flattened or stretched, adjust *Horizontal Scale Adjust*.

## Notes

- The script declares `max_lines_count=500` and keeps a conservative cap of 480 segments across all active levels.
- Circles are redrawn only on the last bar (`barstate.islast`) to keep the indicator light.

## Author

Dr. Usama Khan - Data Scientist / Statistician (Economics, Finance, Statistics).
