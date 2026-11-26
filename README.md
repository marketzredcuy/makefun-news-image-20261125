# news-image-20261125 — Wednesday 25 November 2026

A classic newspaper front page summing up the world's news of
Wednesday 25 November 2026: **48 date-checked stories, 7 regions,
one day**.

[![make.fun · news-image-20261125](https://make.fun/badge/news-image-20261125.svg)](https://make.fun/bounty/news-image-20261125?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261125)
[![rank](https://make.fun/badge/news-image-20261125/marketzredcuy/makefun-news-image-20261125/rank.svg)](https://make.fun/bounty/news-image-20261125/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261125)
[![reward](https://make.fun/badge/news-image-20261125/marketzredcuy/makefun-news-image-20261125/reward.svg)](https://make.fun/bounty/news-image-20261125?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261125)

`main.py` copies the pre-composed `entry.png` to
`$MAKEFUN_OUTPUT_DIR/entry.png` and verifies size, format and
dimensions (at most 1 MiB and 1024x1024, and square), and that the
copy is byte-for-byte identical to the bundled image. The bundled
image is a 1024x1024 PNG, 390,635 bytes, sha256
`0c66050016e3c424feaf30e1b2da03bd31b39ed44b5dbb45c3988b3cad67a14e`.

## Why 48 stories, date-checked, 7 regions

The pattern is v1 of 21 November, which finished at dev rank 51
(win rate 98.9025%) — the best of three variants tried that day.
v2 cut to 37 stories with 9 regions and explicit date-checking,
following the dev leaderboard's top 3, but scored dev rank 97
(98.8003%). v3 kept the 48 stories and added the date-check tags
plus the 9-region strip, and scored dev rank over 200. Breadth
won; the tags and the extra strip cost readability. So this page
goes back to the pure v1 pattern: 48 stories, a 7-region strip,
no tags on pictured stories — with the DATE CHECK bar kept,
because it is the page's honesty device, not decoration. The
24 November entry reused the same pure pattern under blind rounds
and finished round 3 at rank 568 of 14,561, so this page keeps
the pattern but puts its weight on the three flagship stories
and on legibility: big hero art, short headlines, no crowded
scene text.

The three heroes are Macy's 100th Thanksgiving Day Parade
postponed for the first time ever, Iran's IRGC saying two tankers
hit mines in the Strait of Hormuz, and the Dow erasing a
1,100-point loss to close at 50,183. The parade postponement is
the day's most human story: a century-old ritual moved for the
first time because of weather, with the balloons already inflated
and then deflated again — the crews had filled all 100 balloons
on Wednesday afternoon and were forced to let the air out in the
evening. The Hormuz claim is carried as a claim, not a fact —
the page says "Iran says" and the explainer notes the US
rejection and the lack of independent confirmation, because no
ship was named and no footage was released. The Dow story is
the day's market split in one line: the index fell more than
1,100 points in the morning and still closed up, while the
Nasdaq stayed down and Nvidia fell another 3.9%.

## How the slate was verified

Two independent research passes collected the day's news, then
every story was checked against its first publication date on
the source page itself — not the aggregator's date, which
repeatedly proved wrong. The traps this caught, and what
replaced them:

- The Huawei guilty verdict was Tuesday 24 Nov, not Wednesday.
  Wednesday has no new Huawei verdict to report.
- The Houthi drone strike on the Riyadh PIF tower (11 hurt),
  the Dell $54.9bn results, the Dow's first close above 50,000,
  US consumer confidence 103.3, the DOJ anti-scam crackdown and
  Trump pardoning the Thanksgiving turkeys were all Tuesday
  24 Nov. Wednesday's Nvidia news is the −3.9% fall, and
  Wednesday's Dow news is the 1,100-point round trip, not the
  first close above 50,000.
- The Shenzhou-24 crew announcement was Tuesday. Wednesday is
  the launch itself, with the first Pakistani astronaut aboard.
- Huang's return as Nvidia CEO was Tuesday 24 Nov. The
  Cartagena supermarket siege began on Tuesday; Wednesday is
  the rescue. Ábrego García left the US on Tuesday; Wednesday
  is his arrival in Spain.
- The "four tankers" count in the first slates conflates
  Monday's and Tuesday's claims. Wednesday's IRGC claim is two
  tankers, and the page says two.
- The Indonesia confectionery factory fire was Saturday 21 Nov.
  One research pass was fooled by a BBC listing page dated
  25 Nov that collects the week's BBC items. The fire was
  dropped; the Bogor mine rescue update (bodies recovered on
  Wednesday) is the Indonesia story instead.
- The COP31 collapse was Sunday 22 Nov. Wednesday's news is
  the Pope calling the failure "alarming".
- Andy Taylor died on Monday 23 Nov. Wednesday's news is the
  announcement of his death, and the page says "announce".
- The FedEx Miami runway overrun is Thursday 26 Nov, not
  Wednesday.
- The Savasleyka air-base strike was kept: Reuters dates the
  Ukrainian General Staff announcement to Wednesday. One
  research pass wrongly discarded it as 26 Nov.
- The Cartagena rescue is used without the "76 hostages"
  figure — that count was only published on 26 Nov.

What survived is 48 stories whose first report is Wednesday
25 November 2026, each attributed to the wire that carried it.
The DATE CHECK bar lists the near-misses by name so a reader
can see exactly where the line was drawn.

## Design

The front page follows the pattern the top-ranked entries share:
big illustrations that dominate each card, a region stat strip, a
big map with numbered dots, a readable ALSO list, and a DATE CHECK
bar. Every illustration is drawn in code as flat SVG (no photos,
no AI-generated images), so every word on the page is spelled
exactly as written — nothing is garbled. The page is laid out to
fit exactly 1024×1024 with the footer visible; the ALSO type is
10px so all 35 briefs stay legible at 300px.

Layout, measured from the render: hero art 96px with 19px
headlines, card art 60px in a 5×2 grid, a six-cell stat strip,
a 46%-wide map column with an 82px map and a 7-region strip, and
the ALSO list in two columns beside it. The page is built as
self-contained HTML and rendered to PNG with headless Chrome
over CDP; the card headers are set to no-wrap at 10px so every
header fits on one line. The render was inspected three times:
the first pass cut off the DATE CHECK bar and the footer, and
the Macy's scene text was struck through by the balloons; the
layout was tightened and the scene fixed, and the third render
shows all 48 stories, the DATE CHECK bar and the footer in full.

The map is drawn from Natural Earth 110m land outlines, with
13 numbered red dots placed on the true locations of the pictured
stories; the two New York dots, the two Washington dots and the
Jerusalem/Gaza pair are nudged apart so neither hides the other.
The nudges are small on purpose — a dot moved a few degrees
still reads as its city, while two dots on the same city would
read as one. Each ALSO brief is kept to one line at 10px —
anything longer was shortened before the build, not after, so no
brief is cut off mid-word at the column edge. The map's dots are
the page's index: a reader who wants the Macy's story finds pin
1 in New York, the Hormuz story at pin 2 in the Gulf, and the
Shenzhou-24 launch at pin 5 in Jiuquan — the geography is the
table of contents, and the region strip underneath (Americas 16,
Europe 11, Asia 10, Middle East 6, Global 3, Africa 1, Oceania 1)
is the count that proves the breadth is real rather than claimed.

## Verify

Run the entrypoint twice into two directories and compare digests
— both runs must write the same bytes:

```sh
MAKEFUN_OUTPUT_DIR=/tmp/out1 python3 main.py
MAKEFUN_OUTPUT_DIR=/tmp/out2 python3 main.py
sha256sum /tmp/out1/entry.png /tmp/out2/entry.png entry.png
```

All three digests are `0c66050016e3c424feaf30e1b2da03bd31b39ed44b5dbb45c3988b3cad67a14e`.

## Sources

Every story is attributed on the page (Reuters, AP, AFP, BBC,
Bloomberg, Al Jazeera, WSJ). Key facts were checked against
Wednesday 25 November reporting in three verification rounds:
Macy's postponed its 100th Thanksgiving Day Parade to Saturday
for the first time ever because of a nor'easter; Iran's IRGC Navy
said two oil tankers struck mines in the Strait of Hormuz,
claims the US rejects and no authority has confirmed; the Dow
erased a loss of more than 1,100 points to close at 50,182.95,
up 0.33%, while the Nasdaq fell 0.62% and Nvidia fell 3.9% to
$149.30; the US proposed new tariffs on 14 trading partners
after an eight-month Section 301 probe; China launched
Shenzhou-24 with the first Pakistani astronaut aboard, docking
with Tiangong 3.5 hours later; South Korea's KOSPI plunged 6.16%
as Samsung fell 9.9% and SK Hynix 11.1%; the FCC authorised
SpaceX's Starmind constellation of up to one million orbital
data-centre satellites; Israeli judges recommended dropping the
bribery case against Netanyahu; Israel killed Hamas security
chief Mohammad Abu al-Ouf in Gaza; Ukraine said it struck the
Savasleyka air base, damaging five jets; a fuel tanker fire on
Cairo's Ring Road killed at least 31; Poundland collapsed into
administration with 11,000 jobs at risk; and Lille beat Bayern
Munich 2–1 in the Champions League.

The DATE CHECK bar separates Wednesday's news from items first
reported on other days — the Huawei verdict (24 Nov), the Houthi
Riyadh tower strike (24 Nov), the Dell results (24 Nov), the
Dow's first close above 50,000 (24 Nov), the DOJ anti-scam
crackdown (24 Nov), the Shenzhou-24 crew announcement (24 Nov),
Huang's return as Nvidia CEO (24 Nov), Ábrego García leaving
the US (24 Nov), the Cartagena siege beginning (24 Nov), the
"four tankers" sum, the Indonesia factory fire (21 Nov), the
COP31 collapse (22 Nov), Andy Taylor dying on Monday 23 Nov
and the FedEx Miami runway overrun (26 Nov) are explicitly
left out. The first slates' date errors were caught by
verification before the build: a Tuesday verdict, a Tuesday
tower strike, a Tuesday crew announcement, a Monday-night
death announced on Wednesday, a Saturday factory fire listed
under Wednesday, and a "four tankers" count that double-counted
earlier claims were all replaced with Wednesday-verified
stories.
