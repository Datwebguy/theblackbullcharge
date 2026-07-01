# $ANSEM Black Bull Charge

A single-file Solana endless runner for the $ANSEM community.

## Run locally

```powershell
python -m http.server 8000
```

Open `http://localhost:8000`.

## Production

The game is contained in `index.html`. Wallet connection, balances, Jupiter
swaps, power-up purchases, burn/treasury splitting, staking pledges, and local
leaderboards run directly in the browser.

Before production use, replace the shared public Solana RPC with a dedicated
endpoint and add a backend for score validation, global rankings, tournaments,
and reward claims.
