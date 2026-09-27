# ArcBounty onboarding report — real first-job flow

Date: 2026-09-27  
Wallet: MetaMask  
Device: MacBook Pro, macOS 27.0 (26A428)  
Browser: Google Chrome 153.0.8010.53  
Arc account: `0x41D926f3853fa2D3bdc9971d105e33210ba21c71`

This report documents my real first ArcBounty job flow. No seed phrase, private key, password, or signing secret is included.

## Steps

1. Opened `https://arcbounty.app/start` and read the Arc mainnet setup: chain ID 5042, RPC `https://rpc.blockdaemon.mainnet.arc.io`, native gas/reward currency USDC.
2. MetaMask was installed, but it opened on **Import wallet / Secret Recovery Phrase** instead of a ready account. I expected the existing wallet to be immediately usable. I restored the wallet manually; the recovery phrase is not shown or stored in this report.
3. Connected MetaMask to ArcBounty. The site detected account `0x41D9…1c71`.
4. First attempt to take a bounty opened MetaMask on **Ethereum**, not Arc. MetaMask showed an Ethereum transaction with an estimated ~$0.12 ETH fee. I cancelled it.
5. Returned to the Start page and used **Add Arc to my wallet**. MetaMask showed an **Update Arc** prompt for `rpc.blockdaemon.mainnet.arc.io`. After Arc was added, the same action correctly showed network **Arc** and gas in USDC.
6. The wallet had 0 USDC on Arc, so the confirmation could not proceed. I funded it with exactly **2 USDC** from **Bybit 2**. Arc Explorer shows the inbound transfer fee as **0.00042 USDC**. Funding transaction: `0x3e3f8a3e14c69fe7995b5faf96fd0ad77a40ea23d2cc73827b7ea725daca03cc`.
7. MetaMask had stale duplicate confirmation prompts from the earlier attempts. One showed **“This transaction is likely to fail”**. I cancelled the stale prompt and retried from a clean state.
8. Took my first ArcBounty job (#15). Transaction: `0xb907c4121272df4c547de4b779204b09b03cd261ce871bad23bb9795c676bf0f`. Fee: **0.00462074 USDC**.
9. Submitted the finished bug report. ArcBounty first requested a message signature with the exact purpose **“ArcBounty IPFS pin”** and then a separate on-chain `submitWork` transaction.
10. `submitWork` transaction: `0xcaafd8df238ff4f290ffc8ec84dfb54424143a52ea063d72d9e5c53e38bc152c`. Fee: **0.00317852 USDC**.
11. The bounty page changed to **Submitted** and displayed the submitted work. Wallet balance after the two ArcBounty transactions: **1.992200746 USDC**.

## Where I got stuck

- **Wallet state:** MetaMask opened on the recovery/import screen rather than a normal account view. This is not ArcBounty's fault, but it was a real first-run blocker.
- **Wrong network on the first take attempt:** after connecting the wallet, the first transaction prompt was Ethereum. I expected the flow to require/switch to Arc before creating a transaction request.
- **Zero-gas state:** the Take transaction could be prepared before the wallet had any Arc USDC, leaving the confirmation unusable. A clearer inline “Fund Arc USDC first” check would reduce confusion.
- **Queued duplicate prompts:** after network/funding retries, MetaMask showed multiple queued requests; one was predicted to fail. Cancelling stale prompts and retrying fixed it.
- **Submit has two confirmations:** first an IPFS-pin signature, then an on-chain transaction. Both are reasonable, but making this two-step sequence explicit before the first prompt would make onboarding easier.

## Screenshots

1. `01_start_page.png` — ArcBounty Start page and Arc network instructions.
2. `02_metamask_arc_network.png` — MetaMask network list with Arc present.
3. `03_funding_and_fees.png` — Arc Explorer showing the 2 USDC inbound funding plus the two ArcBounty transaction fees.
4. `04_first_job_submitted.png` — first ArcBounty job in Submitted state.

## Cost summary

- Funding transfer fee shown by Arc Explorer: **0.00042 USDC**
- Take transaction fee: **0.00462074 USDC**
- Submit transaction fee: **0.00317852 USDC**
- ArcBounty wallet-side total for Take + Submit: **0.00779926 USDC**
