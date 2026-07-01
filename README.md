<div align="center">

# $ANSEM Black Bull Charge

### Charge forward. Jump the FUD. Fuel the bull.

[![Play Black Bull Charge](https://img.shields.io/badge/PLAY-NOW-00ff9d?style=for-the-badge&logo=vercel&logoColor=black)](https://theblackbullcharge.vercel.app)
[![Built on Solana](https://img.shields.io/badge/BUILT%20ON-SOLANA-9945FF?style=for-the-badge&logo=solana&logoColor=white)](https://solana.com)
[![Single HTML file](https://img.shields.io/badge/BUILD-SINGLE%20HTML-ffcc00?style=for-the-badge)](index.html)

**[Play the game](https://theblackbullcharge.vercel.app)** &nbsp;·&nbsp;
**[View $ANSEM on Solscan](https://solscan.io/token/9cRCn9rGT8V2imeM2BaKs13yhMEais3ruM3rPvTGpump)**

</div>

![Black Bull Charge main menu](docs/black-bull-charge.png)

## Meet the Black Bull

Black Bull Charge is a fast browser game made for the $ANSEM community. You
play as the Black Bull, charging through a market full of bears, FUD signs,
red candles and rugs. The longer you survive, the faster everything gets.

It begins with a short cinematic about the Black Bull project, then drops you
straight into the run. Space, click or tap to jump. Collect the spinning
$ANSEM coins, watch the market move behind you and try not to get bonked.

This is more than a themed runner. A connected Solana wallet turns the game
into a small $ANSEM utility hub. Players can check real balances, swap through
Jupiter, buy boosts and sign a non-custodial multiplier pledge without leaving
the game.

The whole experience lives inside one `index.html` file. The game, animation,
responsive interface, wallet logic and verified token artwork all travel
together.

## How a run works

Your score grows with distance and collected coins. The pace increases over
time, so a comfortable opening quickly becomes a test of timing. A staking
multiplier can improve the score, while purchased boosts can change how a run
feels or rescue one that should have ended.

| Action | Desktop | Mobile |
|---|---|---|
| Jump | `Space`, `Up Arrow` or `W` | Tap the game |
| Start or retry | Button or `Space` | Tap the button |
| Open the shop | Shop / Pause | Shop / Pause |
| Mute sound | Music button | Music button |

Bears are compact ground blockers. FUD signs and candles demand a committed
jump, while rugs sit low and use a more forgiving collision box. Coins often
appear in arcs that encourage riskier lines through the obstacles.

## Real $ANSEM utility

The power-up shop does not grant a boost merely because a button was pressed.
It builds a real SPL token transaction, asks the connected wallet to approve
it and waits for Solana confirmation. Only then does the game activate the
effect.

| Power-up | Price | What it does |
|---|---:|---|
| Mega Charge | 10 $ANSEM | Adds a 35% speed burst for 7 seconds |
| Moon Jump | 25 $ANSEM | Gives the bull higher jumps for 45 seconds |
| Diamond Shield | 50 $ANSEM | Makes the bull invincible for 8 seconds |
| Full Send Revive | 100 $ANSEM | Survives one collision automatically |

Every purchase is atomic: 70% goes to the community treasury for prizes,
events and development, while 30% is permanently burned. If either part of
the transaction fails, the boost is not granted.

The swap panel supports native SOL or USDC into $ANSEM, as well as $ANSEM back
into either asset. Jupiter finds the route, the wallet signs the final
transaction and the game refreshes the balances after confirmation. Native
SOL remains native in the interface; any wrapping required by the route is
handled inside the transaction.

## Wallets and balances

Phantom, Solflare and Backpack are detected directly in the browser. Once
connected, the account menu shows live SOL, USDC and $ANSEM balances and
provides simple actions for copying the address, opening Solscan, refreshing
or disconnecting.

| Purpose | Address |
|---|---|
| $ANSEM mint | [`9cRC...pump`](https://solscan.io/token/9cRCn9rGT8V2imeM2BaKs13yhMEais3ruM3rPvTGpump) |
| USDC mint | [`EPjF...Dt1v`](https://solscan.io/token/EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v) |
| Community treasury | [`CuVu...SuLB`](https://solscan.io/account/CuVuDcp1iBRggUT3D1ktxFDhZSgJn6ZbfwkfytfsSuLB) |

The configured $ANSEM mint uses Token-2022 with six decimals. Token balances
are read from canonical associated token accounts.

## About the multiplier

The current staking experience is an MVP designed to avoid custody. A player
chooses a pledge amount and signs a clear, human-readable message. The game
verifies that signature locally and stores the resulting multiplier against
that wallet.

No tokens are locked or transferred during this flow. It demonstrates the
experience without pretending to be a production staking protocol. A future
release should move this logic into an audited Anchor program with proper
vaults, withdrawal rules and on-chain accounting.

## Run it locally

You only need a static web server:

```powershell
git clone https://github.com/Datwebguy/theblackbullcharge.git
cd theblackbullcharge
python -m http.server 8000
```

Open [http://localhost:8000](http://localhost:8000). Wallet extensions treat
`localhost` as a secure development context, so avoid opening `index.html`
directly when testing wallet or RPC features.

There is no framework or build step. The application uses HTML5 Canvas,
vanilla JavaScript, Solana Web3.js, SPL Token helpers, TweetNaCl and Jupiter's
Swap API. Vercel serves the file as a static site.

## Deployment

This repository is connected to Vercel. A push to `main` creates a new
production deployment automatically. To deploy manually with the Vercel CLI,
run:

```powershell
vercel --prod
```

The repository stays intentionally small:

```text
.
|-- index.html
|-- docs/
|   `-- black-bull-charge.png
|-- README.md
`-- .vercelignore
```

## What still needs a backend

The current leaderboard, quests and tournament interface are suitable for an
MVP, but real rewards need server authority. A production backend should
replay or validate run events, rate-limit submissions, bind scores to wallet
signatures and reject impossible movement before any payout is considered.

The next meaningful milestones are global validated leaderboards, an audited
Anchor staking vault, treasury-backed claims, on-chain tournament entry and
more maps and seasonal obstacles.

## A note on trust

Wallet private keys never enter the application. Purchases and swaps always
require explicit approval, and boosts wait for confirmed transactions. Swap
responses are checked against the expected mints, amount, payer and signer
layout before the wallet is asked to sign.

This remains an experimental community game, not financial advice. Mainnet
SOL and tokens have real value, so read every wallet prompt before approving
it. The public RPC should also be replaced with a dedicated provider before
high-traffic production use.

The Solana, USDC and wallet marks come from their official sources. The
$ANSEM mark is the verified Black Bull image for the configured mint and is
also used as the site's favicon. The running bull is a project-specific,
four-frame illustrated sprite.

<div align="center">

### Charge forward with $ANSEM power.

</div>
