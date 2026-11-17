# War Cove Battlefield Stock Charts — Discord copy of the Day Brief Stock Board

The Discord-room copy of the Day Brief — Stock Board, built for the
"War Cove Battlefield Stock Charts" room. The board itself (the house
artifact) is the source of truth and is never touched by this copy.

**Address:** https://longshotwolf.github.io/war-cove-stock-board-discord/

## How it reads live inside Discord — the feed door

A page inside a Discord Activity sits in Discord's proxied frame and
cannot fetch outside APIs directly. This copy's data layer answers the
board's own action calls in the browser, off the same public doors the
board uses, in the board's own order — Nasdaq public API first, Yahoo
Finance behind it — and routes them through the app's URL-mapping
prefixes (bare prefix form) when the hostname ends in discordsays.com:

| Prefix | Target |
| --- | --- |
| `/` | longshotwolf.github.io/war-cove-stock-board-discord |
| `/nsd` | api.nasdaq.com |
| `/yho` | query2.finance.yahoo.com |

Outside Discord the same build drinks direct. (Nasdaq and Yahoo send no
CORS headers, so in a plain browser the direct reads are refused and
the board honestly stands on its last saved board / HELD — in the room,
through the door, it reads live.)

The house quote channel (Finnhub) has no browser door: where the board
would fall back to it, this copy falls back to Yahoo, and his crypto
ledger prices read off Yahoo's SYMBOL-USD tape.

## The ledgers in this copy

The proof pages open on the house record as it stood when this copy
was published, then keep recording and grading locally — every board
pass writes its reads and grades open calls when their frame rolls,
under the same rules. Entries written inside this copy live in that
browser's local ledger only; they do not flow back to the house
board's record.

## What this copy carries (refreshed Nov 17, 2026, off the finished board)

Everything the finished board has: the front readings in the pinned
order, the locked seven tickers plus Add Stock, Terra's bottoms and
Vega's tops on MONTH · WEEK · DAY · 4H · 6H, Entries & Exits ranked
MONTH · WEEK · DAY · 6H, the trade alert, the War Cove Newsroom
room, both proof pages and his combined chat ledger — and the
Company Floor whole: **the Owner's office at its head with the
MARKET BELL window** (the bell computer, sound on, rings at the
9:30 AM open and the 4:00 PM close, NYC) and **Calla's room** —
her coin switch (Litecoin · Bitcoin · Ethereum), her board switch
(Day Brief master copy / this stock board), TEST READ, the named
commands (!sable · !sierra · !terra · !vega · !survey — the
one-minute office is refused by name), and her rundowns leading
with the 6H spread relayed out of Sable's room, in Sable's words.
The seed stands at the house record as of this refresh: 80 readers'
entries (42 correct · 32 misses · 6 open), his page empty, waiting
on his real chat calls.

One piece cannot ride into a static copy, stated plainly: **Calla's
voice.** Aria is synthesized line by line through the house TTS
lane on the board's server; a static page has no door to that lane.
In this copy her lines stand as text in her room and no other voice
is substituted — the board itself answers the same way whenever
the lane does not answer.

## Rebuilding

`assemble.py` re-snapshots the finished board's built client, re-seeds
the standing record (via the board's getproofpage actions), localizes
the fonts, and re-injects the data layer. Publish with
`~/workspace/day-brief-hosting/publish-stock-discord.py`.

**Copy-only bell patch (assemble.py step 5):** in the board's own
bundle the bell computer stands in the Owner's Office on the Day Board
screen only — the Owner's Office at the head of the Company Floor
carried just the direction window, and the Warlord found no bell in
his floor office (Nov 17, 2026). Step 5 patches the COPIED bundle so
the same bell computer also stands in the floor Owner's Office, fed
by the same board data. The house board itself is never patched.
