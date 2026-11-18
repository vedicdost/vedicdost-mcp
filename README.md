# VedicDost MCP Server — Vedic Astrology Tools for AI Apps

**Vedic Astrology That Shows You Why.** Not Guesswork. Shastra. Free kundli, kundli matching, panchang and muhurat in 8 Indian languages, for any MCP client: Claude, ChatGPT, Cursor, VS Code and more.

Every answer is **calculated by VedicDost's own software** (sidereal zodiac, Lahiri ayanamsa, Parashari method, Vimshottari dasha), not guessed by an AI model, and comes with its **classical basis** (shastra reference) and a link to the free page on [vedicdost.com](https://vedicdost.com).

**Accuracy:** VedicDost Engine: Lahiri Ayanamsa (Parashari). Planet Positions Verified Against NASA JPL Horizons and Swiss Ephemeris: 700,000 Positions From 100,000 Charts, All Within 1 Arc-Minute (mean 0.18′, max 0.53′). Proof: [vedicdost/vedicdost tests/nasa](https://github.com/vedicdost/vedicdost) (raw NASA replies saved).

| | |
|---|---|
| **Server URL** | `https://vedicdost.com/mcp` |
| **Transport** | Streamable HTTP (stateless JSON-RPC) |
| **Authentication** | None — free, no login, no API key |
| **Official MCP Registry** | `com.vedicdost/astrology` |
| **Languages** | Hindi, English, Marathi, Gujarati, Bengali, Tamil, Telugu, Kannada (`hi, en, mr, gu, bn, ta, te, kn`) |
| **Details page** | [vedicdost.com/mcp](https://vedicdost.com/mcp) |

## How to Connect

**Claude** (web or desktop): Settings → Connectors → Add custom connector → paste `https://vedicdost.com/mcp`.

**ChatGPT**: turn on Developer mode in ChatGPT settings (Apps), create a new app/connector, paste the URL and choose no authentication.

**Cursor** — add to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "vedicdost": { "url": "https://vedicdost.com/mcp" }
  }
}
```

**VS Code** — add to `.vscode/mcp.json`:

```json
{
  "servers": {
    "vedicdost": { "type": "http", "url": "https://vedicdost.com/mcp" }
  }
}
```

**Any other MCP client**: add a remote HTTP server with the same URL.

Then ask, for example: *"Make my kundli: 10 May 1990, 8:30 am, Bhopal"*, *"Match kundli of …"*, *"Aaj ka panchang Mumbai"*, *"When will I get married?"*

## Tools

| Tool | What It Does |
|---|---|
| `get_kundli` | Vedic birth chart: Lagna, Moon sign, nakshatra and pada, planets with houses, current dasha |
| `match_kundli` | Ashtakoot guna milan (out of 36) with all 8 kootas, plus Manglik check for both |
| `get_panchang` | Panchang for a date and place: tithi, nakshatra, yoga, karana, sunrise/sunset, Rahu kaal, Abhijit muhurat |
| `find_muhurat` | Auspicious dates for marriage, griha pravesh, buying a vehicle or starting a business |
| `check_dosha` | Manglik (from Lagna and Moon), Sade Sati/Dhaiya, Kaal Sarp, Pitra and Gandmool, with classical basis |
| `dasha_timeline` | Vimshottari mahadasha and antardasha timeline |
| `life_event_timing` | Good time windows for marriage, career, wealth, children, property, education or health |
| `numerology` | Indian numerology |
| `shastra_basis` | Classical rules (BPHS, Phaladeepika, Saravali, Jataka Parijata and more, with chapter and verse) that apply to a chart |
| `find_calculator` | Finds the right free VedicDost calculator page for a question |

All tools are read-only. Birth places worldwide are supported (`"City, Country"`), with the correct local time zone.

## Data and Privacy

- Birth details are used only to calculate that answer and are **not stored**; no account is needed.
- **No AI model is called by this server**; it only runs calculations.
- Abuse protection: calls are counted per IP address in memory for one hour (60 calls/hour); this count is not saved.
- Full policy: [vedicdost.com/legal/privacy](https://vedicdost.com/legal/privacy)

## Good to Know

Astrology gives guidance, not certainty; it is not medical, legal or financial advice. Without a birth time, Lagna and houses are skipped.

This repository holds documentation only. The server is hosted by VedicDost at `https://vedicdost.com/mcp`.

**Support:** support@vedicdost.com · **Website:** [vedicdost.com](https://vedicdost.com)

## Credits

Planet positions use [Astronomy Engine](https://github.com/cosinekitty/astronomy) (MIT License, © Don Cross). Swiss Ephemeris is used only for testing, not in the live software.
