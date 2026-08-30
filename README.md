# FH Passkey Generator

Generate **default FiberHome WiFi password** from SSID. Clean, fast, glassmorphism UI.

> Input `641b00` → `wlan9be4ff`

## How it works

Default FiberHome password derived from SSID `fh_XXXXXX` (suffix `_5G` ignored).

1. Take 6 hex digits after `fh_`
2. Lowercase
3. Invert each hex digit: `15 - n` (0↔f, 1↔e, 2↔d, 3↔c, 4↔b, 5↔a, 6↔9, 7↔8)
4. Password = `wlan` + inverted result

**Example**

| SSID | Hex | Inverted | Password |
|------|-----|----------|----------|
| `fh_ABC123` | `abc123` | `543edc` | `wlan543edc` |
| `fh_641b00` | `641b00` | `9be4ff` | `wlan9be4ff` |

## Usage

1. Open `index.html` or visit deployed site
2. Enter 6 hex digits (prefix `fh_` auto-displayed, no need to type)
3. Click **Get Passkey** → copy result

## Deploy to Vercel

No build step — static single file.

- **Vercel Dashboard:** Import repo `ahmadghozali-xyz/hack-wifi` → Deploy (no config needed)
- **CLI:** `vercel` inside repo root

## Stack

- Vanilla HTML / CSS / JS
- Glassmorphism + animated ambient orbs
- Zero dependencies

## Disclaimer

For educational & own-device recovery only. Do not use on networks you do not own or have permission to test.

## License

MIT
