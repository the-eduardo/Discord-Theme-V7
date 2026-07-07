[prettier-badge]: https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square
[prettier-link]: https://github.com/prettier/prettier
[license-badge]: https://img.shields.io/github/license/ClearVision/ClearVision-v7?style=flat-square
[license-link]: https://github.com/ClearVision/ClearVision-v7/blob/master/LICENSE
[sass-badge]: https://img.shields.io/badge/Sass-CC6699.svg?style=flat-square&logo=sass&logoColor=white
[sass-link]: https://sass-lang.com/
[upstream-badge]: https://img.shields.io/badge/upstream-ClearVision--v7-2780e6?style=flat-square
[upstream-link]: https://github.com/ClearVision/ClearVision-v7

<div align="center">

# ClearVision V7 — Edgerunners

[![code style: prettier][prettier-badge]][prettier-link]
[![Language: Sass][sass-badge]][sass-link]
[![License][license-badge]][license-link]
[![Upstream][upstream-badge]][upstream-link]

> A fork of [ClearVision V7](https://github.com/ClearVision/ClearVision-v7) rebuilt with the **Cyberpunk Edgerunners** palette.  
> Night City vibes for your Discord — neon yellow, electric cyan and shock magenta over deep purple.

</div>

---

## What's different from the original

### Color palette

| Role | Original ClearVision | This fork |
|---|---|---|
| Main accent | `#2780e6` Sapphire blue | `#fcee0a` Neon yellow (David's jacket) |
| Hover | `#1e63b3` Dark blue | `#00f0ff` Electric cyan (Lucy) |
| Focus / TAB outline | same as main | `#ff2a6d` Shock magenta |
| Success / online | `#43b581` Discord green | `#00ff9f` Neon green |
| Danger / DND | `#982929` Dark red | `#ff003c` Neon red |
| Streaming | `#593695` Muted purple | `#b026ff` Neon purple |
| Idle | `#faa61a` Amber | `#fcee0a` Neon yellow |
| Offline | `#808080` Grey | `#4a4458` Faded chrome purple |

### Background

The default Sapphire wallpaper is replaced with a **Cyberpunk-style city wallpaper** (`wallhaven-571998`).  
You can swap it back or use any HTTPS image by overriding `--background-image` in Custom CSS.

### Typography

The font stack is prefixed with **Rajdhani** (imported from Google Fonts), a geometric sans-serif with a futuristic / military-HUD look. Falls back to `gg sans` and system fonts as usual.

### Theme shading

All four Discord variants (Light / Ash / Dark / Onyx) use **Night City purple shading** (`#0d0221` family) instead of plain black overlays, so the background always reads as deep-space purple rather than generic dark.

### Readability fixes (not in upstream)

The original theme places light/white text on the neon yellow accent — which is unreadable at high contrast. Every yellow surface in this fork has been corrected:

| Element | Fix |
|---|---|
| Selected channel / DM | Dark text `#0d0221` on yellow bar |
| @user mention chip | Solid yellow pill, dark text; cyan on hover |
| @role / @everyone mention chip | Same — uses a different class from @user, both covered |
| "NEW UNREADS" bar in channel list | Dark text on yellow strip, both new and old bar styles |
| "new messages" bar at top of chat | Dark text |
| APP / bot tags | Dark text on yellow pill |
| Filled primary buttons (Edit Channel, Invite, confirmations, command buttons) | Dark text |
| Settings sidebar — selected item | Dark text |
| Mentioned message row | Subtle 7% yellow tint + red alert bar (no blown-out highlight) |

---

## Installing

**BetterDiscord**  
Download [`ClearVision-v7-BetterDiscord.theme.css`](ClearVision-v7-BetterDiscord.theme.css) and drop it into:
```
%appdata%\betterdiscord\themes
```

**Vencord**  
Download [`ClearVision-v7-Vencord.css`](ClearVision-v7-Vencord.css) and drop it into:
```
%appdata%\vencord\themes
```

**Both (generic)**  
[`ClearVision-v7.theme.css`](ClearVision-v7.theme.css) includes both the BetterDiscord and Vencord import lines.

---

## Customizing

All variables are in the `:root` block at the top of the theme file. Common overrides via Custom CSS:

```css
:root {
  /* swap wallpaper for your own (must be HTTPS) */
  --background-image: url(https://example.com/your-wallpaper.jpg);

  /* change the neon yellow to something else */
  --main-color: #ff2a6d;
  --hover-color: #b026ff;

  /* widen or narrow the channel list */
  --channels-width: 240px;
}
```

The gradient fallback (no image) is:
```css
--background-image: linear-gradient(135deg, #0d0221 0%, #1a0b2e 35%, #240b36 60%, #10021f 100%);
```

---

## Note on class-name hashes

Discord and ClearVision use hashed class names (`lookFilled__201d5`, `active_caf372`, etc.).  
These can change when Discord updates. If a fix regresses after a Discord update, the current class names can be found in [`src/backend/_classes.scss`](src/backend/_classes.scss).

---

## Credits

- **[ClearVision Team](https://github.com/ClearVision/ClearVision-v7)** — original theme architecture and SCSS
- **[the-eduardo](https://github.com/the-eduardo)** — Edgerunners palette, readability overrides, and this fork
- Palette inspired by **Cyberpunk Edgerunners** (Netflix / Studio Trigger / CD Projekt Red)
- Wallpaper: [wallhaven-571998](https://wallhaven.cc/w/571998)

Licensed under the same terms as the upstream project. See [LICENSE](LICENSE).
