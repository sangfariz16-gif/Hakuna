# Hakuna Agent — agent-skill.md

Mint Hakuna Agent NFTs on BNB Chain with your Binance Agentic Wallet.

## Project (planned — contract NOT deployed yet)

- **Project:** Hakuna Agent — 5 pig guardians, BEP-721 on BNB Chain (chainId 56)
- **Supply:** 4,444, random token IDs 1–4,444 (swap-and-pop draw)
- **Mint gate:** caller must hold a SPACE ID `.ai` Agent ID. The check happens on-chain. No ID, no mint.
- **Price:** first **mint per wallet FREE** (gas only), then **$0.69 / $0.85 / $1.20 USD in BNB** per mint (by mint count: #2–17 $0.69, #18–32 $0.85, #33–44 $1.20) (Chainlink BNB/USD oracle), max **44 per wallet** total.
- **Bonus token:** 120,000 **HAKU** per PAID mint (proposed economics). Free mints earn 0 HAKU. Claimable after mint.
- **Royalty:** 5%
- **Contract addresses:** NOT deployed yet. This file will be updated with the live NFT + HAKU addresses and BscScan links after deployment. Do not mint against any address not listed here.

## How to mint (once live)

1. Make sure your wallet holds a `.ai` Agent ID (SPACE ID on BNB Chain).
2. Simulate the mint first — call `mint(uint256 quantity)` as a read-only simulation from your own address. If it reverts, do not send.
3. Send `mint(uint256 quantity)` payable:
   - `quantity` 1–44, within your remaining wallet allowance (first mint free, then $0.69 / $0.85 / $1.20 in BNB by mint count).
   - Value: 0 for the free mints; for paid mints, the contract prices $0.69 / $0.85 / $1.20 in BNB (by mint count) via the Chainlink oracle at transaction time. Overpayment is refunded by the contract.
4. Verify on BscScan that the NFT arrived in your wallet.

## Rules

- Never approve a token spend to mint. Minting costs BNB (or nothing for free mints), never an ERC-20 approval.
- Never send BNB to any address claiming to be the Hakuna Agent team. The only mint path is the contract listed here once deployed.
- Rarity is fixed by token ID range: Common 1–2222, Rare 2223–3333, Epic 3334–3999, Legendary 4000–4332, Mythic 4333–4444. The mint is RANDOM — the token id is drawn on-chain (swap-and-pop), not sequential.

## Links

- Mint page: https://hakuna-agent.vercel.app/
- llms.txt: https://hakuna-agent.vercel.app/llms.txt
- Official X: to be announced (do not trust impersonators)
