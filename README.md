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

## Rebuilding

`assemble.py` re-snapshots the finished board's built client, re-seeds
the standing record (via the board's getproofpage actions), localizes
the fonts, and re-injects the data layer. Publish with
`~/workspace/day-brief-hosting/publish-stock-discord.py`.
