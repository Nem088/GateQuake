# How we keep it fair

Real money is on the line, so "trust us" is not an answer. This page
says, in plain words, what the server decides, what it checks, what it
only watches, and what we cannot promise. The detail lives in
[Match rules](RULES.md) and [Fair play & security](SECURITY.md); where
this page and the game ever disagree, the game is what happened. Tell
us and we will fix the page.

## The short version

- **The server runs the game.** Your browser sends what you press and
  where you look, nothing else. It cannot say where you are, what you
  hit, how much health you have, or what you won.
- **Everyone in a match is under the same code, on the same server
  clock.** There is no rating, no hidden handicap, no premium tier that
  plays by different physics.
- **Nobody picks winners.** The game has no control for moving a
  player, healing one, dropping a tile by hand, or naming a winner. The
  only way a pot is paid is to be the last one standing.
- **The winner takes the whole pot.** The only fee is 3% when you
  withdraw. There is no cut from the pot and no fee on entry beyond the
  posted buy-in.

## What your browser is allowed to say

The list of messages a client can send is short and closed: movement
keys, look angle, "I swung" with the name of the move, "equip this
weapon", "throw", and cosmetics. That is all. There is no message for
"I am here", "I hit them", or "I won", so a modified client has no way
to express a teleport, a speed hack, a fake hit, or a fake payout.

Every swing is checked before it counts:

- the move must exist, and must belong to the weapon you are actually
  holding, so a fist cannot deal a hammer's damage;
- it cannot arrive faster than that move's animation allows;
- reach and arc come from the server's own tables, applied to the
  server's own positions, never to positions a client reports;
- there must be a line of sight. A strike through a wall does not land.

A swing that fails a check is dropped silently. Telling a cheat which
check caught it would only speed up its next attempt.

## What is enforced, and what is only watched

**Enforced by the server, every time:** the checks above, plus a
ceiling on how fast a connection may send. A client hammering the
server is disconnected, and an honest client never gets near that
ceiling.

**Watched, and judged by a person:** signs of automation, such as
turning faster than a hand can or swinging with a machine's regularity.
These are recorded and reviewed by a human before anything happens to
an account. We do this on purpose. Our rule is that **a false positive
that voids an honest player's kill is worse than a cheat we catch a day
later**, because the stake in that match was real. So a machine never
bans anyone on a single signal. Repeated evidence does, and it costs the
account its access and any balance obtained that way.

We do not publish the thresholds or the exact methods. A public list of
what we measure is a checklist for getting around it.

## Hits and lag

Positions and damage are computed on the server for everyone alike.
Your browser predicts your own movement so it feels immediate, and the
server corrects it if they disagree; the server is always right. In the
Practice gate, hits are resolved against where things were on your
screen when you swung, within a strict bound, and that is being tested
there before it comes to paid arenas. In paid arenas, hits resolve
against the server's current positions, the same for every player in
the room.

## The collapsing floor

The quake pattern is chosen by the server, at random, when the tremor
begins, and every player in the room is told at the same moment, five
seconds before the drop. No player and nobody at GateQuake picks tiles,
and nobody sees the pattern early. What we do not offer today is a
published seed you could verify independently; the pattern is fair
because of who chooses it and when, not because of a proof you can
check. If we add a verifiable scheme, it will be announced here.

## Bots

Bots exist only in the Practice gate, where nothing is at stake. A paid
match is between real players' wallets.

## Your money, step by step

1. Your buy-in leaves your balance when you enter the gate and sits in
   that match's pot, recorded in our ledger against that match and your
   wallet.
2. Leave during waiting or countdown and it comes back automatically.
   If the match never starts, or the server tears the room down, every
   buy-in in it is refunded.
3. Once the match is live, leaving is a forfeit. The last one standing
   takes the whole pot, forfeited stakes included.
4. If the last two fall in the same instant, nobody wins, and every
   buy-in is refunded.
5. A paid room holds exactly one round. You cannot be charged twice for
   the same match: if you drop and get back in, the ledger already knows
   you paid.
6. Withdrawals go to any Solana address you choose and must be signed
   by your wallet. While your funds sit as a GQ balance, we are holding
   them. That is a custodial arrangement, and we would rather say so
   plainly; withdraw what you are not playing with. Details in
   [Fair play & security](SECURITY.md#your-money).

## Same rules for everyone

Matches are made by gate, not by rating: whoever walks into a gate is
in that room. Progression toward the tournament and VIP gates only
counts from matches with at least three different paying wallets, which
is the one anti-collusion rule we publish because it changes how you
play. Your pot is never affected by it; see
[Gate progression](RULES.md#gate-progression).

## What we cannot promise

- That nobody will ever cheat. We catch what the server can see, and we
  keep improving it. If a match looked wrong, tell us the gate, the time
  and the name, and we will look at the record.
- That your connection is our problem. Lag on your side is yours, and
  the server does not slow down for it.
- That a lost stake comes back. You can lose. It is a game of skill for
  money against people who also want to win. Read
  [Responsible play](RESPONSIBLE_PLAY.md).

## Found something?

A bug that affects fairness or moves money incorrectly is worth more to
us than the money is. **support@gatequake.com**, subject starting
"FAIRNESS:" or "SECURITY:". Give us a fair chance to fix it before
making it public, and we will not pursue anyone who reports in good
faith. See [Reporting a problem](SECURITY.md#reporting-a-problem).
