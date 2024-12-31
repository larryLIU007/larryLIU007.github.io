---
title: "The Last Big Thing - Crypto Payment Part3"
summary: It's not happening until we build it.
date: 2024-11-05T10:30:00+08:00
weight: 998
# aliases: ["/first"]
tags: ["Sector"]
authors:
  - name: "Larry007"
    link: "https://x.com/Larry_007__"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: true
draft: false
hidemeta: false
comments: false
description: "—— It's not happening until we build it."
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: true
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: false
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: false
ShowRssButtonInSectionTermList: false
UseHugoToc: false
cover:
    image: "cover.jpg" # image path/url
    alt: "" # alt text
    caption: "" # display caption under cover
    relative: true # when using page bundles set this to true
    hidden: false # only hide on current single page
# editPost:
#    URL: "https://github.com/<path_to_repo>/content"
#    Text: "Feedback" # edit text
#    appendFilePath: true # to append file path to Edit link
---

*The <a href="https://larryliu007.github.io/writings/the-last-big-thing-part2/" style="color: #0E97CB;">previous</a> articles explored traditional payment systems and blockchain's unique advantages, along with current challenges in crypto payments. This final installment analyzes emerging trends and innovations that could overcome these obstacles. From non-custodial solutions to DeFi integration, these developments could fundamentally reshape value transfer in the crypto age.*

# 4. Trends

## 4.1 The Rise of Non-custodial Solutions

In the past two years, numerous innovative ***account designs*** have emerged, gradually dismantling previous barriers. Soon, users will no longer need to convert their crypto into fiat currency in advance.


<span style="color: #12B886;">*Resource Lock - Instruments to prevent double spending*</span>  
<span style="color: #0E97CB;">*Implementations: MPC, TEE, Smart Contract, etc.*</span>  
<span style="color: #D73504;">*Issues solved: Double Spending, Latency*</span>


A resource lock is an instrument designed to help users make credible commitments regarding their account activities. It allows users to ensure that their account will or will not engage in specific behaviors, potentially based on certain conditions. One of the most common applications is preventing double spending, where users can credibly ensure they won't spend the same assets in their account more than once. This assurance allows service providers to proceed with the next steps even before the transaction is fully settled or finalized.


<span style="color: #0E97CB;">*Resource Lock Can Improve UX By Large*</span>

<div align="center">
  <img src="/The_Last_Big_Thing/pic12.png">
</div>

I borrowed the term from Frontier's research article, but these implementations have been widely used in the industry long before One Balance was introduced.

***Case1 - StablesMoney***

For example, Stables Money, an Australian-based card issuer, keeps users' funds on-chain until payments are made. Stables utilizes MPC wallets, where private keys are split into three shards managed separately by the users, Stables, and Fireblocks, one of the largest custody providers. When a payment is initiated, Stables facilitates co-signing, initiates the transaction, and confirms it with the card network instantly. Meanwhile, they update the user's balance in their own database even before the transaction is finalized on-chain. When the user initiates a subsequent transaction, Stables checks the user's balance against their internal records, rejecting any double spending attempts. Under this setup, the only way for users to double spend is by bypassing Stables and colluding with Fireblocks within a short window, which is highly unlikely. However, this approach is still centralized, and theoretically, Stables and Fireblocks could collude to steal users' funds.

***Case2 - Gnosis Pay***

Gnosis Pay takes a different approach, prioritizing decentralization over efficiency. In Gnosis Pay's system, transactions are categorized into card transactions and non-card transactions, with the latter typically initiated directly through wallets by users. Card transactions are confirmed instantly, while non-card ones are subject to a delay - a three-minute waiting period, during which time any previously initiated card transaction is usually settled and notified to the providers already. This design choice also helps mitigate the risk of a malicious double spending effectively.

Gnosis Pay implemented this method by adding a "[delay module](https://github.com/gnosisguild/zodiac-modifier-delay?tab=readme-ov-file)" developed by Zodiac on top of a standard SAFE account. This solution is subtle and elegant but also very specific, which results in limited efficiency and flexibility. For example, if a user needs to quickly reallocate funds to prevent a liquidation, a three-minute waiting period could be fatal. It’s also worth mentioning that this type of transaction processing doesn’t support all card transactions, such as complex reversals or delayed refunds.

A resource lock can also be programmed to operate under specific conditions. For instance, in the cross-chain NFT purchasing scenario mentioned by Frontier, the locked funds could either be claimed by any solver who presents a valid fulfillment proof or be returned to the user after a set expiration period. Nowadays the cross-chain transaction experience has improved significantly between L2s and fast chains, but with a resource lock, waiting times can be minimized, even when bridging from the mainnet.

```rust
resource_lock: {
	lock: 1500 USDC,
	fulfill: DeGods #12345,
	expiry: Solana block 245547084
}
```
*Source: [Frontier Tech](https://ethresear.ch/t/introducing-onebalance/19557)*

This example demonstrates that a resource lock has versatile applications and should not limited to payments or cross-chain transactions alone.

Another implementation method that is certainly worth exploring involves leveraging TEEs. Within TEE, a resource lock would be fully programmable and highly efficient. By incorporating a decentralized network and robust attestation mechanisms, many of the concerns related to centralization and collusion could be alleviated. If implemented correctly, this approach could also achieve a high degree of security.

Resource locks may introduce additional trust assumptions, but when properly implemented, they have the potential to unlock a myriad of use cases that are currently infeasible and significantly enhance the user experience. The greatest advantage of this concept lies in its ability to allow the next action to proceed as if the previous one has already been completed, thereby eliminating many of the frictions that typically hinder user experience. Essentially, "it decouples fulfillment from settlement", said Frontier.

A card issuer could confirm a transaction as though it has already been settled. A solver could advance funds to the user on the destination chain as if the assets were already locked on the source chain.

Imagine a future where not only users but also solvers, market makers, and other providers adopt resource locks with a uniform, interoperable standard. In such a scenario, the entire process - from initiating a transaction to routing, fulfilling, and confirming it - could occur in an instant. This would finally bring instant, low-cost, and enriched crypto usage experience on par with that of Web2.

<span style="color: #12B886;">*Fast confirmation - Near-Instant Transaction Confirmations*</span>  
<span style="color: #0E97CB;">*Implementations: High-performance chains, Pre-confirmation, etc.*</span>  
<span style="color: #D73504;">*Issues solved: Double spending, Latency*</span>

Another approach to addressing finality and latency is to enable fast confirmations. One viable method is to develop high-performance, stable chains where even large volumes of transactions can be settled in real-time. When a transaction is settled within milliseconds, providers and merchants receive a definitive outcome instantly, making it extremely difficult for even sophisticated attackers to double spend or exploit the system. Teams like MegaETH and others are actively working on this front.

Alternatively, on mainnet or based rollups, pre-confirmations could achieve similar results if implemented effectively. Pre-confirmation allows L1 proposers to opt into a new supply branch, allocating part of the block space and committing to include certain transactions in advance, before the entire block is constructed and broadcast across the network. Projects like Commit Boost, Luban, and Chainbound are among those undertaking the comprehensive design and engineering required to make this a reality.

<span style="color: #12B886;">*Smart Contract Accounts - Customized logic and enriched function defined by smart contracts*</span>  
<span style="color: #0E97CB;">*Implementations: Zerodev, Particle, etc.*</span>  
<span style="color: #D73504;">*Issues solved: Signing & Managing*</span>

The signing experience is generally straightforward when using crypto-native apps for payments, as a wallet is embedded, and transactions are signed when users select "pay now" or "transfer." However, this becomes a challenge for non-custodial card designers, who must ask users to swipe their cards and approve transactions separately. Tangem is developing a product that combines a hardware wallet and a payment card, but this approach requires customized manufacturing, which increases costs.

Furthermore, the signature curve used by most mainstream blockchains today, Secp256k1, is not integrated or supported by most mobile manufacturers. As a result, private keys for EOAs are typically managed at the software level rather than leveraging the secure enclaves used in modern mobile key management, which introduces additional risks for payment app users.

There is also a growing demand for fine-grained payment access controls. For example, enterprises may want to grant access to employees only during business trips, with specific spending limits. Parents might want to allow their children to use a card for specific purposes under certain limits.

To address these needs, smart contract accounts are being actively developed by various startups. These accounts enable users to delegate balance deductions to others on their behalf, with the ability to specify spending limits, time constraints, and other granular details.

<span style="color: #12B886;">*Pay Master - Enabling gas payment for others or in alternative tokens*</span>  
<span style="color: #0E97CB;">*Implementations: Biconomy Paymaster, Pimlico Paymaster, etc.*</span>  
<span style="color: #D73504;">*Issues solved: Gas Fees*</span>

Abstracting gas fees away from the user experience is crucial for making blockchain technology more accessible and user-friendly.

Summarizing above into one chart:  
<span style="color: #0E97CB;">*Hurdles For Non-custodial Crypto Payment And Primitives That Help*</span>

<div align="center">
  <img src="/The_Last_Big_Thing/pic13.jpeg">
</div>

## **4.2 Integration with Defi Protocols**

Users are increasingly seeking payment products that seamlessly integrate with Defi protocols, offering yield opportunities and sophisticated asset management in a trustless manner.

The traditional payment system, despite its complexity, essentially only revolves around two basic instructions: debit and credit. As Holyheld describes in their whitepaper:

"…In-between consumer and product there are numerous intermediaries each one of them executing, transmitting, or relaying a simple instruction. At each step, there is a reconciliation of debit and credit instructions. It is not possible to program or enrich such instructions…"

To access additional asset management tools and opportunities, users are forced to turn to separate institutions and third parties. This reliance on siloed, independently maintained ledgers introduces significant costs and frictions.

Defi was created to address these issues. While still in its early stages, Defi has already introduced a variety of on-chain yield opportunities, including:

- Staking and restaking - Earning yield by helping to operate a blockchain or protocol.
- LP fees - Generating revenue by providing liquidity where depth or immediacy matters
- RWA - yield from redirecting on-chain funds to off-chain assets
- CeDefi - revenue from redirecting on-chain funds to off-chain strategies

Moreover, we're witnessing the development of numerous automation tools, combinations, derivatives, and strategies built on top of these protocols. The logical next step is to close the last mile by integrating payment applications with Defi protocols. This would allow users to store, manage, and spend their assets seamlessly and trustlessly within one single account.

***Case1 - Etherfi***

Partnering with Scroll, Etherfi recently launched [a "real" credit card](https://x.com/ether_fi/status/1833132921143906398), which aligns perfectly with this mission. Currently, Etherfi is best known as an LRT protocol built on top of EigenLayer. However, with the introduction of Cash, users will gain the ability to borrow and spend stablecoins against their staking positions using Visa credit cards issued through the platform. The outstanding balances on these cards can be automatically paid off with the interest generated from their staking. Etherfi also offers Liquid, which provides vaults with automated Defi strategies. Users simply deposit their tokens, and behind the scenes, the vault allocates funds across various Defi positions.

***Case2 - RoboSaver***
In contrast, Onchainification Labs advocates for a non-custodial approach. They have released an alpha version of [RoboSaver](https://github.com/onchainification/robosaver), a smart contract module designed for installation on the Safe smart account that underpins every Gnosis Pay card. This module allows users to deposit the idle balance into Defi protocols like Balancer or Aura, where it earns yield and collects swapping fees. When the card balance falls below a certain threshold, RoboSaver automatically withdraws assets from the pool to top up the card. The contracts have already been deployed, and a withdrawal was successfully [triggered](https://gnosisscan.io/tx/0x155499dd64a0340129144ce0e47e2549817ad72e95d5d2836bbbf7acbb0750dc) during an experiment where they purchased a coffee.

Here are two products or features that I think hold the most immense potential:

1. ***Allowing users to borrow and pay with stablecoins against their staking/restaking positions** (just as Etherfi Cash is doing):*

   Staking is a cornerstone in the crypto world, often viewed as the equivalent of a risk-free rate. It offers simplicity and predictable yields, attracting a significant number of participants and substantial assets. Many stakers, especially large investors (whales), might appreciate having a card for everyday use.

   It might sound like a credit card, but can be uniquely structured by incorporating a liquidity pool model between users and issuers. This way, issuers wouldn't need to use their own funds for transactions, allowing assets to be settled promptly.

   Alternatively, we could leverage existing lending protocols like AAVE or Compound. The Holyheld team has conducted internal tests for credit lines using wstETH (Lido) and AAVE's V3 delegation module. While the system functions as intended, there's a significant limitation: AAVE's credit delegation only supports an "all or nothing" approach. This means it's impossible to delegate just a portion of the position or a specific amount. Compound faces the same issue.

2. ***Allowing users to hold and pay with (risk-free) yield-bearing assets:***

   It's ironic that most crypto users - from retail investors to most professional institutions - continue to lend funds to Tether and Circle without receiving any yield in return. In a highly digitalized world, users should be experiencing more transparency and fairness, not continued exploitation by centralized entities. RWAs, particularly yield-bearing stablecoins, are poised to iterate on the current ones. The importance of a risk-free, yield-bearing stablecoin cannot be overstated, as bonds and treasuries have long been the go-to investment vehicles in many parts of the world. These are highly standardized, easy to understand, and backed by sovereign nations. Many people hold USDT or USDC as a digital alternative to the dollar, primarily because it offers better protection against inflation than the fiat currency of their own country. Naturally, these users would also want to earn a risk-free interest rate on their holdings. However, adoption remains low, and this can be attributed to two main factors:

    - **On-chain challenges:** The current standards for yield-bearing tokens are not easily integrated into existing systems, creating friction.

      For a token to be considered a stablecoin, its value must remain stable, but the assets backing these RWA protocols, like treasuries and bonds, appreciate over time. To pass this value back to users while keeping the token price stable, many yield-bearing stablecoins, such as USDM by Mountain and STBT by Matrixport, use a rebase token model. This model adjusts all holders' balances proportionally using a <span style="color: #D73504;">`rebaseFactor`</span> to reflect the accrued value. Although it's a neat design, it has yet to gain widespread support from Defi protocols, wallets, and centralized exchanges, where the simpler ERC-20 standard still dominates. Additionally, these protocols typically trigger the rebase process once a day, which can create arbitrage opportunities for traders and lead to price fluctuations that many users find undesirable. One possible solution is to stream rewards on a block-by-block basis, which could help smooth out price fluctuations. However, this approach would incur significant gas costs, and the potential for arbitrage would still remain.

    - **Off-chain Challenges:** Issuing these types of assets could potentially expose projects to significant legal risks, particularly from the SEC, as they may be deemed "unregistered securities."

      This is why many of these projects explicitly exclude U.S. residents or citizens from their services. These protocols often invest considerable time and resources in developing legal frameworks to ensure that users can retrieve their assets even if the protocol itself fails (bankruptcy remote). However, until new legislation is passed or any precedent-setting case is decided, the legal outlook for these projects remains uncertain.

    Another key factor in establishing a widely adopted stablecoin is building a comprehensive, globally distributed banking support network. While on-ramping is important, ensuring a smooth off-ramp process for merchants or institutions is even more critical. Tether achieves this through a network of distributors, while Circle leverages its compliance and strong relationships with various banks. New entrants into the market will need to determine their own strategies. For RWAs, gaining access to deep liquidity, such as that offered by firms like BlackRock, could be crucial.


In the near future, payment systems will become seamlessly integrated into the entire Defi ecosystem. Individuals will have access to a wide range of investment vehicles, management tools, and strategies, all from a unified account.

Moreover, cryptocurrency payments will be increasingly integrated into traditional financial systems. Currently, issuing banks are the first to adopt cryptocurrency because they manage the initial stages of fund flow and are most downstream in the information flow. Once these issuers handle the conversion between crypto and fiat, other participants, such as card networks and acquiring banks, can operate without needing to be aware of the cryptocurrency involved.

However, in the long term, we can expect cryptocurrency to be integrated further downstream in the fund flow - or, conversely, further upstream in the information flow - due to its efficiency and cost-effectiveness, with fewer conversions required. We've already seen Visa and MasterCard actively exploring the integration of crypto into their networks and traditional payment rails, signaling a definitive shift in the industry. Similarly, Stripe's [recent move](https://x.com/jeff_weinstein/status/1844080628427620642) to enable stablecoin payments further underscores this trend.

As cryptocurrency adoption grows, more funds will remain on-chain for secure and convenient management, as well as to take advantage of better yield opportunities, with conversions to fiat occurring only when necessary.

# 5. Closing Thoughts

## 5.1 How should crypto payments ideally work?

While the exact future remains uncertain, we can envision an ideal scenario based on current knowledge and trends.

In the future, the process of making crypto payments should be as seamless and quick as today's digital payments. Customers would only need to engage in a brief interaction with the merchant, similar to how we currently use QR codes, NFC, or biometric authentication. This simple interaction would allow the merchant to identify the user's abstracted or smart account, powered by the primitives discussed in section 3.2.1.

A payment processor, serving as one of the few intermediaries in this streamlined system, would handle a range of security checks on behalf of the merchant and the user. These checks might include identity verification, balance confirmation, AML compliance, fraud detection, and access control, among others. Once these checks are successfully completed, the payment request would be routed to the user's smart account.

This smart account could be used to hold a variety of assets, such as those related to staking, liquidity provision, RWA, CeDefi products, or other yield-generating opportunities and their combinations. Importantly, these assets would remain non-custodial, fully controlled by the user. Pre-authorization and access control would be defined and granted through smart contracts, with gas fees often being covered by the app or service provider.

To ensure speed and security, the system could leverage resource locks, fast confirmations, or high-performance chains. This would enable payment processors or other service providers to confirm transactions almost instantly, minimizing the risk of malicious activity. The merchant would receive immediate notification of the transaction's completion status, while the actual settlement of funds could occur either instantly or at a later time. Ultimately, the corresponding assets would be transferred to the merchant's account, closing the transaction.

<span style="color: #0E97CB;">*(Ideal) Crypto Payment Flowchart*</span>

<div align="center">
  <img src="/The_Last_Big_Thing/pic14.png">
</div>

As you may have noticed, in addition to the payment processor, another third party that users and merchants will likely need to rely on is the account service provider or manager. This necessity arises because basic native accounts, such as EVM EOAs, are insufficient for delivering the smooth experience and complex management. Moreover, a purely open-source solution may struggle to keep pace with the rapid evolution of blockchain technology and the changing needs of users.
A key advantage of crypto payments, which helps minimize the number of intermediaries and thus reduces costs, is that ***blockchain unifies the flow of funds and information within a single ledger***.

## 5.2 Unification, Democratization, and Disintermediation


<span style="color: #0E97CB;">***Payment Eras***</span>

<div align="center">
  <img src="/The_Last_Big_Thing/pic15.png">
</div>

To summarize the entire article:

Card payments marked the beginning of the digitalization of financial transactions, leveraging computers and the internet for bookkeeping and information transmission. As the payment industry grew and technology advanced, the process involved an increasing number of specialized intermediaries. Digital payments furthered this digitalization by utilizing emerging technologies as consumer internet usage became widespread. It also disintermediated the traditional process by abstracting away customers' direct interactions with banks.

Blockchain and crypto payments take this disintermediation a step further, offering a system where users retain control of their assets while gaining access to a wide array of composable yield opportunities and asset management tools. This technology provides a decentralized and permissionless network, making digital assets and ownership accessible to nearly everyone on the planet. It fosters a transparent and neutral environment where all parties can collaborate without needing to establish trust beforehand.

---

*Disclaimer: The views, information, and opinions expressed in this article are solely my own and do not reflect the official position of my employer or its affiliates. This post is for informational purposes only and should not be construed as investment, financial, legal, or tax advice. Nothing contained herein constitutes an offer to sell, a solicitation of an offer to buy, or a recommendation for any digital asset or investment. The information presented is subject to change without notice and makes no representation about the accuracy, completeness, or timeliness of the content.*

---