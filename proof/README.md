# Accuracy Proof — VedicDost Engine (18 Nov 2026)

VedicDost Engine: Lahiri Ayanamsa (Parashari). Planet Positions Verified Against NASA JPL Horizons and Swiss Ephemeris: 700,000 Positions From 100,000 Charts, All Within 1 Arc-Minute.

| Reference | Positions | Mean difference | Max difference | Above 1′ |
|---|---|---|---|---|
| NASA JPL Horizons (DE441) | 700,000 | 0.182′ | 0.529′ | 0 |
| Swiss Ephemeris (test only) | 700,000 | 0.182′ | 0.538′ | 0 |

- 100,000 random birth charts (1930–2025, India), 7 planets each (Sun to Saturn), geocentric apparent ecliptic longitude.
- `nasa-jpl-100000/nasa_raw_replies/`: the 700 original replies from the NASA JPL Horizons API, saved unchanged (gzip), each with NASA's own timestamp and "source: DE441".
- `nasa-jpl-100000/RESULT_*.txt`: per-planet results.
- Swiss Ephemeris was used only to check results; it is not part of the live software.
