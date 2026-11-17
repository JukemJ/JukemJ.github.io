# dixn.dev

Source for [dixn.dev](https://dixn.dev), the portfolio site of Chris Dixon: CAN and J1939 networks, embedded vehicle firmware, and high-voltage EV integration on heavy trucks.

## What's on the page

- **Live J1939 bus trace** in the hero. A simulated `can0` at 250 kbit/s scrolls frames (EEC1, ET1, CCVS1, DM1, and a Proprietary B message). Click any frame to decode it: the 29-bit ID is split into priority, PGN, and source address, and the payload is decoded into engineering values. The default view shows the active DM1 fault.
- **Work**: the triple-CAN vehicle gateway, the hybrid-electric truck program, and J1939 diagnostics and data tooling.
- **Experience**, **Tools and skills**, **Earlier web projects** (Wordle clone, rodeo schedule tool), and **Contact**.

## How it's built

Everything lives in one file, `index.html`. There's no build step, no framework, and no dependencies.

- **Styles**: inline `<style>` block. The colors are CSS custom properties on `:root`. The accent colors come from CAN wiring: `--canh` is yellow (CAN_H) and `--canl` is green (CAN_L).
- **Script**: an inline IIFE of about 160 lines in plain JavaScript. It has three parts: frame builders, a J1939 decoder, and the trace renderer.
- **Fonts**: Barlow, Barlow Semi Condensed, and IBM Plex Mono from Google Fonts. These are the only external requests.
- **Hosting**: GitHub Pages. `CNAME` points the site at `dixn.dev`.

### Trace behavior

- A new frame arrives every 240 ms, and the list keeps the last 12.
- The trace pauses while the pointer is over the frame list, while a frame has keyboard focus, when the trace is scrolled out of view, and when the tab is hidden.
- When `prefers-reduced-motion` is set, the trace starts paused. The **Pause / Resume trace** button toggles it by hand.
- Frames are buttons with `aria-pressed`, and the decode panel is an `aria-live` region.

## Running locally

Open `index.html` in a browser, or serve the folder:

```bash
python -m http.server 8000
# then visit http://localhost:8000
```

## Editing

| To change | Edit in `index.html` |
| --- | --- |
| Projects | the `<article class="project">` blocks under `#work` |
| Roles and credentials | the `<ol class="timeline">` under `#experience` |
| Skills | the `.skills` grid under `#skills` |
| Colors and fonts | the `:root` variables at the top of `<style>` |
| Trace frames | `builders` and `schedule` in the script |
| Decoded signals | the `PGN`, `SA`, `SPN`, and `FMI` lookup tables and the `switch` in `decode()` |

To add a message to the trace, write a builder that returns `{ id, d }` (a 29-bit ID and 8 data bytes), add its key to `schedule`, and add a `case` for its PGN in `decode()`.

## Repository layout

```
├── index.html   # The whole site: markup, styles, and script
├── CNAME        # Custom domain for GitHub Pages
├── assets/      # Legacy: from the earlier Strata-based version
├── images/      # Legacy: from the earlier Strata-based version
├── LICENSE.txt
└── README.md
```

The current page doesn't reference `assets/` or `images/`. They're kept from the previous HTML5 UP Strata version of the site.

## Browser support

Current versions of Chrome, Edge, Firefox, and Safari. The page uses modern CSS (`min()`, `clamp()`, `:focus-visible`) and ES2015+ JavaScript, so Internet Explorer is not supported.

## Contact

- **Website**: [dixn.dev](https://dixn.dev)
- **Email**: chris@dixn.dev
- **GitHub**: [JukemJ](https://github.com/JukemJ)
- **LinkedIn**: [chris-dixn](https://www.linkedin.com/in/chris-dixn)
