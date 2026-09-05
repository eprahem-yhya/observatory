# The Trader's Observatory — Control Panel (Preview)

The interface of a private automated trading system, shown as a read-only
preview. Nothing here is connected to a broker and no number is real.

**Live:** https://eprahem-yhya.github.io/observatory/

## What it shows

Four sections of the real panel — overview, positions, the signal pipeline,
and controls. Controls are rendered in their real state and deliberately
inert: the point is to show the interface, not to hand out a remote.

## Notes on the charts

- **Colour carries one meaning: direction.** Up is blue, down is red. The
  green/red pair every trading screen reaches for fails a colourblind
  separation test badly — around ΔE 4 where 8 is the floor — so a
  red/green viewer reads a losing day as a winning one. The blue/red pair
  used here measures ΔE 19. Both are labelled as well, so colour never
  carries the meaning alone.
- **One axis, never two.** Equity and daily result are different scales, so
  they are two charts rather than one chart with two y-axes.
- **Hover is part of the chart**, not an extra: crosshair and tooltip on the
  equity line, per-bar tooltip on daily result.
- The equity series is generated with drift spread across the whole range.
  Pinning the final value alone drew a flat line with a cliff at the right
  edge — a good reminder that a chart can be technically correct and still
  lie about the shape.

## Structure

    index.html    markup, styles, data generation, and both charts

Design and build by **Eprahem Yhya** — eprahemyhya45@gmail.com
