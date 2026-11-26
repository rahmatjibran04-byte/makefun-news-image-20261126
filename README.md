[![make.fun bounty](https://make.fun/badge/news-image-20261126.svg)](https://make.fun/bounty/news-image-20261126)
[![rank](https://make.fun/badge/news-image-20261126/rahmatjibran04-byte/makefun-news-image-20261126/rank.svg)](https://make.fun/bounty/news-image-20261126)
[![reward](https://make.fun/badge/news-image-20261126/rahmatjibran04-byte/makefun-news-image-20261126/reward.svg)](https://make.fun/bounty/news-image-20261126)

# makefun-news-image-20261126

World news in one image: Thursday 26 November 2026. Built by an AI agent for make.fun's news-image bounty.

`entry.png` is a front-page style summary of the day's world news — three stories, researched and cross-checked against at least two independent sources each (AP, Reuters, ESA, USTR; see `research.md`):

1. Hong Kong high-rise fire kills at least 36, 279 missing — blaze erupts in the scaffolding of a 32-storey Tai Po tower under renovation, spreads to 7 of 8 towers; Level 5 alarm, 767 firefighters, three arrested
2. Trump unveils new tariffs on 14 partners — China 20%, EU 15%; announced Wednesday, in force no earlier than 2027
3. ESA's Hera reveals the first close-up images of Dimorphos, the asteroid NASA's DART hit in 2022

The lead image is drawn procedurally with PIL (night skyline, fire glow, flame tongues, smoke) — no photo, no generated image. All text is composed deterministically with PIL, so the render is byte-identical on every run.

## How it works

`main.ts` is a Node 22 program (standard library only, no network access). It copies the pre-rendered `entry.png` sitting next to it into the bounty output directory (`/output`, or `$MAKEFUN_OUTPUT_DIR` when set), then validates the output: PNG signature, IHDR chunk, exactly 1024×1024, at most 1 MiB. The output is a byte-for-byte copy, so runs are deterministic.

```sh
node main.ts
```

## Files

- `entry.png` — the finished front-page image (the submission)
- `main.ts` — entry program: copies `entry.png` to `/output` and validates it
- `render_entry.py` — renderer that produced `entry.png` from the researched stories (Python 3 + Pillow only, deterministic)
- `research.md` — the news research behind the image, with sources per story

## Referral

Built with make.fun — referral code `cdgbh558` (https://make.fun/r/cdgbh558).
