# Chart Style

The rules every chart in this portfolio follows. Built from Tableau's visualization best practices, the IDRC "10 Data Visualization Tips", Carnegie Mellon's data visualization guidelines, DBTA's "10 Golden Rules of Data Visualization", and a validated palette.

## Message first

- One message per chart, stated in the headline as a takeaway ("The men's email works for almost everyone"), in sentence case, regular weight
- A short deck under the headline says what is plotted
- Every chart ends with a source line
- Start with the decision the chart supports; if a chart does not change what someone would do, cut it

## Colour

- One highlight colour for the point, grey for context. Colour never carries meaning on its own; direct labels always do too
- Each project has one highlight colour so its charts are recognisable. Colours are never mixed within a chart

| Role | Colour |
|---|---|
| Headlines and values (navy) | #14213d |
| Deck, axes, source (muted) | #5f6470 |
| Context (grey) | #c4c1ba |
| Baselines and reference lines | #dedbd4 |
| Signature accent (orange) | #e0612e |

Project highlights (validated together: lightness band, chroma floor, 3:1 contrast on white, colour-blind separation):

| Project | Highlight |
|---|---|
| City Expansion Scorecard | #2a78d6 |
| Campaign Uplift Targeting | #e0612e |
| SaaS Cross-Sell Playbook | #14946a |
| Business Review Agent | #6250d6 |
| Marketplace Supply Simulation | #2f8a2f |
| Market Entry Investment Case | #c94f86 |
| Funnel Attribution Audit | #b35900 |
| GTM Launch Playbook | #d1495b |
| CRM Data Hygiene Audit | #00819e |
| Marketing Workflows | #8a6a00 |
| Customer Value Emails | #3d5a98 |

## Form

- Pick the simplest chart that shows the message: bars for comparisons (always from zero), lines for change over time (5:8 height to width), a single number when the number is the story
- No pies beyond two or three slices, no 3D, no dual axes
- Sort categories by value unless they have a natural order

## Ink

- No gridlines, borders, backgrounds or legends when direct labels work
- Label values directly, selectively: the highlighted value and the comparisons that matter
- Horizontal text only; commas in large numbers; round sensibly
- Apps: the same palette and rules, with detail in hover rather than on the chart

## Labels

- Category labels are two to four words. Explanations go in the deck, not the label ("Monthly fiber, year 1", not "First-year month-to-month, fiber")
- Value labels are the number and nothing else ("37%", "$611K", "+3.9 pts"). No brackets, no second figure, no "a year"
- At most one annotation inside the plot, in muted grey, under ten words
- Decks are one line. Units and definitions live there

## Layout

Every chart is built with the same functions in `brand_style.py`, so margins, type sizes and spacing match across projects:

| Function | Use |
|---|---|
| `chart()` | Figure with fixed margins in inches, whatever its height |
| `titles()`, `credit()`, `save()` | Headline and deck, source line, export |
| `hbar()` | Ranked categories, with negatives handled |
| `vbar()` | Ordered categories such as time buckets |
| `dotrange()` | An estimate with its interval. Intervals are never drawn over bars |
| `paired_hbar()` | Before and after for the same categories |
| `line_axes()` | Line charts: baseline and light tick labels, no gridlines |
