# Fair play & security

Real money is involved, so you deserve straight answers about how
results are decided and how funds are handled. This page gives them,
without publishing the kind of detail that would help someone attack
the game. For the plain-words walk through what the server decides,
checks and only watches, start with [How we keep it fair](FAIRNESS.md).

## The server decides everything

GateQuake is **server-authoritative**. Your browser draws the world and
sends your inputs — which way you are moving, where you are looking,
that you swung. It does not decide outcomes.

Every position, every hit, every point of damage, every tile that falls
and every payout is computed on our server, which simulates the whole
match many times a second. The client is a window, not a source of
truth.

The practical consequence: a modified client **cannot** award itself a
kill, teleport, move faster, hit you from across the map, survive a fall
it should not have, or claim a pot it did not win. Those things are not
validated on the client — they are simply not the client's to say.

## Automation and cheating

We actively enforce against automated play, modified clients, and
collusion between accounts. Detected accounts lose access and any
balance obtained that way.

We deliberately do not publish our detection thresholds or methods. A
public list of exactly what we measure is a checklist for evading it.
What we will say is that enforcement runs on the server, on real match
data, and that it improves continuously.

One rule we *do* publish, because it changes how you play: progression
toward the tournament and VIP gates only counts from matches with at
least three different paying wallets. That closes off self-play
farming. See [Match rules](RULES.md#gate-progression).

## Your money

**We never ask for your seed phrase or private key. Nobody at GateQuake
will ever ask you for one. Anybody who does is not us.**

Connecting a wallet lets us read your public address. That is all it
does. It grants no ability to move your funds.

### How balances work — plainly

Deposits are USDC on Solana. When your deposit confirms on-chain, we
credit your GateQuake balance in GQ at 1 USDC = 1,000 GQ.

**Be clear about what that means: while your funds sit as a GQ balance,
GateQuake is holding them.** GQ is a credit in our system redeemable for
USDC, not a token in your wallet and not something you hold on-chain.
This is a custodial arrangement, and you are trusting us with that
balance for as long as you leave it with us. We would rather say so
plainly than dress it up.

If that trust matters to you — and it should — **withdraw what you are
not actively playing with.**

### Withdrawing

- You can withdraw to **any Solana address you control** — your wallet,
  a hardware wallet, an exchange deposit address.
- Every withdrawal must be **signed by your wallet**. Knowing your
  public address is not enough for anyone, including someone who
  compromised our site, to move your balance somewhere you did not
  authorise.
- Your wallet shows you the destination and amount before you sign.
  **Read that prompt every time.** It is the last thing standing between
  you and a mistake, and it is the reason the signature exists.
- Withdrawals are 1,000 GQ = 0.97 USDC. The 3% is the only cut we take.

### What we take, in full

The 3% spread between depositing and withdrawing. That is the whole
business model. There is no rake on pots, no fee on entry beyond the
posted buy-in, no charge to play Practice, and no subscription.

## What GateQuake is not

- **No token.** GQ is not tradeable, not listed, and not an investment.
- **No NFTs.** Nothing to mint, nothing to flip.
- **No presale, no ICO, no airdrop.** Anyone offering you one is running
  a scam using our name.

## Things that are on you

Honesty cuts both ways. These are real, and we cannot fix them for you:

- **Crypto transfers are irreversible.** Send USDC to a wrong address or
  on the wrong network and it is gone. Nobody can claw it back.
- **Only USDC on Solana.** Sending any other asset, or USDC on another
  chain, to a GateQuake deposit address will not credit you and is not
  recoverable.
- **Your wallet is your responsibility.** If someone gets your seed
  phrase, they have your wallet, and no signature check helps.
- **You can lose.** It is a game of skill played for money against other
  people who also want to win. See
  [Responsible play](RESPONSIBLE_PLAY.md).

## Reporting a problem

Found a security issue, a bug that affects fairness, or anything that
moves money incorrectly?

**Contact:** **support@gatequake.com** (subject line starting "SECURITY:")

Tell us what you found and how to reproduce it. Please give us a
reasonable chance to fix it before making it public. We will not
threaten or pursue anyone who reports something in good faith and does
not exploit it or take other people's money with it.

If you find a way to take money that is not yours, reporting it is worth
more to us than the money is. Come talk to us.
