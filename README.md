# Observatory — Trading Bot Control Panel (Preview)

The actual interface of a private automated trading system, published as a
public preview. Same React application, same components, same Arabic RTL
layout — running on generated data with nothing behind it.

**Live:** https://eprahem-yhya.github.io/observatory/

## What is real and what is not

Real: every screen, panel, chart and interaction. This is the application
itself, built from its own source.

Not real: all of the data. Account, tickets, prices, signals, log lines and
channel names are generated in the browser. No broker, no server, no database.
Writes are accepted and discarded, so buttons respond and change nothing.

## How it was made into a demo

The live application funnels every call through a single `request()` in
`src/api/client.ts` and a single WebSocket client in `src/api/ws.ts`. Replacing
those two files was enough to put the entire interface on generated data —
no page, hook or component was touched. That is the payoff of routing all
network access through one place.

- `client.ts` becomes a path router over an in-memory dataset, with a small
  artificial latency so the loading states stay visible.
- `ws.ts` becomes a scripted event emitter, so the live feed and the
  connection badge behave as they do in the running system.
- `BrowserRouter` becomes `HashRouter`, because a static host cannot rewrite
  an inner route back to `index.html`.
- A fixed notice states on every screen that this is a preview.

The source of the trading system itself stays private.

Design and build by **Eprahem Yhya** — eprahemyhya45@gmail.com
