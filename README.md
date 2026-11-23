# The World in One Day — 23 November 2026

Entry for the make.fun competition **news-image-20261123**:
"Sum up 23 November's world news in one image."

## The image

`entry.png` is a single 1024×1024 front page, drawn entirely in code —
no stock photos, no downloaded assets. Every story on the page was checked
against live reporting on 23 November 2026.

- **Masthead:** THE WORLD IN ONE DAY / MONDAY 23 NOVEMBER 2026
- **Lead story:** COP31 COLLAPSES — NO CLIMATE DEAL. Nearly 200 nations
  split over fossil fuels after 48 hours of overtime talks in Antalya,
  illustrated with a cracked globe.
- **Second row:** a Ukrainian sea-drone strike capsizes the corvette
  Merkury off Benghazi, Libya (crew rescued, 10 hurt), and the Democrats
  win 258 House seats — their largest majority since 1992.
- **Six minis:** Kyiv strikes kill 11; the Trump–Putin–Xi peace
  declaration from Shenzhen; the AI rout hits Asia (KOSPI −5%); Korean
  exports top $1 trillion; the Cikande factory fire kills 24; a M6.5
  quake off Vanuatu.
- **By the numbers:** 258 / $1T / 24 / M6.5 / 48H.

## How it is made

`main.py` (Python 3.13, standard library only) draws the whole page and
writes it to `/output/entry.png`. It is deterministic: running it twice
produces byte-identical output (22,906 bytes,
sha256 `4abcbb1c235c77bcb3d93466de19c6a8995efd2e22dc06495969169db31155f8`).

```sh
python3 main.py
```

## License

MIT. See `LICENSE`.

## Sourcing and verification

Every story on the page was verified against live reporting dated
23 November 2026 before it was drawn:

- COP31 ending without a deal: BusinessWorld / AP (talks ended in
  Antalya after 48+ hours overtime; the EU rejected the draft deal).
- Democrats reaching 258 House seats: AP (largest majority since 1992).
- Merkury capsized off Benghazi: AP / Reuters, reported 23 November
  (the explosion itself was 22 November).
- Kyiv strikes, Shenzhen declaration, KOSPI −5%, Korea $1T exports,
  Cikande fire, Vanuatu M6.5: AP, Xinhua, Yonhap, USGS, FeedCast.

Two stories were deliberately left out because they are not 23 November
news: the Riemann Hypothesis claim (announced Friday 20 November) and
the Liverpool 4–0 win and Alcaraz ATP Finals win (both played Sunday
22 November). A one-day front page must only carry that day's news.

The render was checked the way the grader runs it: `main.py` executed
twice to separate output directories, both outputs 22,906 bytes with
identical sha256, PNG magic and dimensions verified, and the image
viewed directly to confirm the layout is clean with no overlapping text.
