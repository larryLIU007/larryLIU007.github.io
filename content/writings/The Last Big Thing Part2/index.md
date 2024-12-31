---
title: "The Last Big Thing - Crypto Payment Part2"
summary: It's not happening until we build it.
date: 2024-10-30T10:30:00+08:00
weight: 999
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
    caption: "gfdsdfdsf" # display caption under cover
    relative: true # when using page bundles set this to true
    hidden: false # only hide on current single page
# editPost:
#    URL: "https://github.com/<path_to_repo>/content"
#    Text: "Feedback" # edit text
#    appendFilePath: true # to append file path to Edit link
---

*Having explored the evolution of payment systems from credit cards to digital payments in <a href="https://larryliu007.github.io/writings/the-last-big-thing-part1/" style="color: #0E97CB;">Part 1</a>, this article examines why blockchain represents the next frontier in payments and assesses the current state of crypto payment solutions.*

# 3. Entering Crypto Payments

## 3.1 Edges And Reasons

So why are crypto and blockchain beneficial?

### 3.1.1 Democratized Access

> <span style="color: #0E97CB;">1️⃣</span> Public blockchains <span style="color: #D73504;">***democratize access to digitalized assets and ownership***</span> through their permissionless and decentralized networks. Node operators benefit from diverse source of revenues, enabling them to serve a broad audience that traditional banking and payment systems fail to reach.
>

Traditional digital payment systems have already driven the marginal cost of serving an additional customer to nearly zero. In contrast, public blockchains usually have extra overhead due to communication costs and redundant work done by multiple nodes. However, node operators largely benefit from token issuance and other diverse revenue sources instead of relying solely on transaction fees.

Taking Ethereum node revenue as an example:

*Currently:*

- Consensus Layer Reward
    - Token issuance - 82.5%
- Execution Layer Reward
    - Priority gas fees (processing fees) - 11.7%
    - Baseline MEV - 5.9%

<span style="color: #0E97CB;">*Ethereum Node Revenue Breakdown*</span>

<div align="center">
  <img src="/The_Last_Big_Thing/pic8.jpeg">
</div>

*Source: [Rated Network](https://explorer.rated.network/network?network=mainnet&timeWindow=30d&rewardsMetric=average&geoDistType=all&hostDistType=all&soloProDist=stake)*

Over the past 30 days, token issuance alone has accounted for 82.5% of a node's revenue, while priority gas fees - similar to payment processing fees in traditional systems - only contribute 11.7%. Although a 3.42% return rate may seem modest, it's denominated in ETH and the risks are fairly low. The scale of funds involved is significant, with around 33 million ETH staked, equating to over $100 billion - about 3.7‰ of the US GDP in 2023 or equivalent to the total US treasury bonds outstanding - all earning a 3%+ yield denominated in ETH annually. Looking ahead, revenue sources are expected to diversify further, with non-issuance rewards comprising a larger share.

These enriched revenue streams and high-value transactions make operating nodes a lucrative business, especially when done professionally. While some argue that L2s may not benefit from PoS staking, launching their own tokens, internalizing gas fees, and potentially earning MEV income could easily offset the disadvantages.

We further delve into the concentration of revenue at the transaction level. The data reveals that the top four transaction types contribute over 60% of the total MEV, yet they occupy only about 22% of the block space, measured by gas spent. These transaction types - Telegram Bot Flow, Sandwich MEV, Bot Swap Flow, and Non-Atomic Arbitrage MEV (essentially CEX-DEX arbitrage) - are primarily associated with trading rather than transfers or other activities. These sophisticated trading operations contribute significant economic rewards to node operators who maintain and secure the network infrastructure. In tandem with technical composability, this has produced a decentralized network serving a much wider audience across borders than ever before.

<span style="color: #0E97CB;">*Order Flow Breakdown*</span>


<div align="center">
  <img src="/The_Last_Big_Thing/pic9.png">
</div>

*Source: [‘Who Wins Ethereum Block Building Auctions and Why?’](https://x.com/boez95/status/1815520545774944466) by Burak Öz, Danning Sui, Thomas Thiery, Florian Matthes*

### 3.1.2 Neutral And Transparent Environment

> <span style="color: #0E97CB;">2️⃣</span> Public blockchains excel at <span style="color: #D73504;">***eliminating the trust assumptions, and thus the frictions of cross-party collaborations.***</span> Essentially, they provide a neutral and transparent environment ensured by trustless data processing and computation.
>

If you have a deposit account with a bank in the US and want to send money to your family in Southeast Asia using a local bank account, you have a few options, but none are ideal. Traditional bank transfers typically take 3-5 days and come with fees ranging from 1-5%. Money transfer services can complete the transfer much faster - often within minutes or hours - but at a higher cost, typically between 5-10%. Even most online services, which are more convenient, usually only manage to transfer funds within 1-2 days, with fees ranging from 0.5-2%. Additionally, FX markups can add another 0.5-5% depending on the provider and other factors.

The primary reason for these lengthy and costly processes is that different banks and countries operate on separate "ledgers". Each bank maintains its own booking system, and even global banks usually keep separate ledgers for different regions or countries. Currently, SWIFT serves as the primary messaging network that banks use to route global remittances. When you initiate a transfer, your bank debits your account and sends a message through SWIFT to the receiving bank. The receiving bank then processes this message and credits the recipient's account. If the two banks don't have a direct relationship, they must rely on one or more intermediary banks to route the messages and funds. These intermediary banks may be in different time zones, have varying levels of digital infrastructure, and follow their own procedures and policies. Some banks prefer to process international transfers in batches rather than in real time. All these factors contribute to significant delays and increased costs.

A similar situation unfolds daily across nearly every industry. Whether it's individuals, companies, organizations, regions, or entire countries, each party operates with its own interests in mind - collaborating when beneficial, but also competing with one another. Economic theories often suggest that this dynamic fosters optimal efficiency and sustains a vibrant society. However, it also undeniably gives rise to countless instances of the prisoner's dilemma, tragedy of the commons, and walled gardens. These dynamics introduce significant frictions in cross-party collaborations, often making such interactions complex, costly, and, in some cases, prohibitively difficult.

Blockchain offers a transformative approach by treating all participants equally and ensuring that every node maintains the exact same ledger, i.e., the canonical chain. Through a rigorous consensus mechanism and a cryptographically secured account system, blockchain guarantees that all applications and accounts operate strictly according to open-source coded rules. This framework allows a user to manage a single account from any location and transfer funds to anyone, anywhere, within seconds.

A bank "on chain" can directly communicate with other banks because they all operate on the same transparent ledger. This ledger is not only universally accessible but also verifiable by any participant, eliminating the need for trust and reducing waiting times. With blockchain, a farmer in rural China can make secure, trustless transactions with a financial service provider in a skyscraper on Wall Street. This is the power of blockchain: it removes barriers, enhances transparency, and democratizes access to financial and other services on a global scale.

## 3.2 Status Check

Despite its promising potential, crypto payments are still in the early stages of development and face significant challenges. These challenges include the rigidity of large-scale payment systems, resistance from established user habits, and the entrenched interests of existing financial giants. While Satoshi envisioned Bitcoin as a widely used form of digital cash, most goods and services in our daily lives are still priced in fiat currency. Therefore, the focus here is primarily on stablecoin payments.

### 3.2.1 Only Adding Extra Steps On Top

***Paradoxically, many current crypto payment solutions introduce additional layers on top of traditional payment methods.*** Take crypto cards, the most common product in this space, as an example.

<span style="color: #0E97CB;">***Typical Workflow Of Current ‘Crypto Payment’***</span>

<div align="center">
  <img src="/The_Last_Big_Thing/pic10.png">
</div>

Although it's often suggested that crypto payments might first gain traction in less developed areas with limited access to traditional banking and cards, I see it as more practical - and symbolically significant - to start with cards, given the current stage of the industry. The key strategy here is to leverage existing Visa and MasterCard networks, which together cover over 150 million merchants in more than 200 countries and territories. Without this approach, we would face the daunting task of convincing individual merchants to adopt a new payment method or persuading existing payment platforms to integrate with crypto systems - neither of which seems practical at this stage.

The early adopters in this space are typically card issuers or entities partnering with card issuers to borrow their issuing capabilities (via BIN sponsorship). ***When issuers promote the ability to spend crypto with their cards, the process typically involves converting crypto to fiat in advance.*** This is often done either through an off-ramp provider or managed by the issuer on the user's behalf. Once this process is complete, you can use the card for payments, which are effectively conducted in fiat currency and have little to do with crypto.

In this context, credit cards are fully backed by assets and are referred to as "secured credit cards." This blurs the line between credit and debit cards, making the distinction between them minimal. While credit cards, debit cards, prepaid cards, and other payment forms do differ in terms of spending limits, use cases, and fee structures - and these differences can vary by country and region - the focus here is on card payments in general, without getting into the specific nuances of each type.

This approach does accommodate native crypto users to some extent, particularly those who hold a significant portion of their assets in crypto but still need to use fiat for everyday expenses. However, it is far from ideal and has several significant flaws:

1. **Custody and Centralization Risks**: During the period between funding the card and making a payment, users' assets are effectively under custody, either with the issuers or specialized custody providers. This introduces potential centralization risks and complicates account management. Users must actively maintain their fiat account balances and are exposed to the risk of something going wrong on the custody side. Additionally, there's an opportunity cost, as users miss out on the potential yield that could have been earned on-chain through staking or other Defi protocols. While some issuers are beginning to offer yields to users, this typically involves lending funds to a portfolio manager, which introduces additional risks and costs.
2. **Increased Complexity and Costs**: Contrary to the original promise of simplifying transactions and reducing intermediaries, this approach actually adds more steps and middlemen to the payment process. Currently, service providers typically charge 1%-3% just for topping up cards, and this cost is directly borne by the cardholders.

### 3.2.2 What Prevents Non-custodial Payments

Given these issues, the question arises: Why can't users simply sign the payment transaction in real time? Why does off-ramping in advance seem necessary so far?

*Provider Side:*

1. **Latency:** When using traditional payment rails, card issuers are required to confirm a payment within approximately 5 seconds to ensure a smooth user experience and mitigate potential security risks. On L1s like Ethereum, this time frame is insufficient even to confirm the transaction's inclusion in a block, let alone achieving finality.
2. **Double Spending:** While real-time authorization is technically feasible on L2s or highly performant L1s, several risks remain. A transaction could be reverted due to various issues such as chain re-orgs or network outages. Transactions that are pre-confirmed by rollup sequencers might be inadvertently or deliberately omitted. Moreover, sophisticated attackers could potentially overwrite their own transactions by bidding higher gas fees, allowing them to move assets to another address before the original transaction is finalized.

The most significant risk faced by payment providers or card issuers in a non-custodial payment system is the possibility of not receiving the tokens as expected, in which case the provider would need to cover the shortfall with their own funds.

<span style="color: #0E97CB;">*Attackers Grief Providers Through Double Spending*</span>

<div align="center">
  <img src="/The_Last_Big_Thing/pic11.png">
</div>

*User Side:*

1. **Gas Fees:** One of the significant challenges for users in a crypto payment system is gas fees. On L1s, the gas fees can be prohibitively expensive, and even on L2s or cheap L1s, where gas fees are considerably lower, the costs can still be unacceptable for high-frequency, low-value transactions like daily payments.
2. **Signing and Managing:** Up to this point, signing transactions with a card swipe has not been supported. Instead, users have had to manually sign each transaction using their phones or hardware wallets, which is far from ideal. Additionally, the process of signing and key management on mobile devices has been neither smooth nor secure. Furthermore, fine-grained access control is often expected, particularly by enterprise clients.

Is it possible to offer solutions that address all these issues? With the introduction of several new primitives, the answer is now yes.

*The <a href="https://larryliu007.github.io/writings/the-last-big-thing-part3/" style="color: #0E97CB;">final</a> article in this series will explore emerging trends that could overcome these challenges and revolutionize crypto payments.*

---

*Disclaimer: The views, information, and opinions expressed in this article are solely my own and do not reflect the official position of my employer or its affiliates. This post is for informational purposes only and should not be construed as investment, financial, legal, or tax advice. Nothing contained herein constitutes an offer to sell, a solicitation of an offer to buy, or a recommendation for any digital asset or investment. The information presented is subject to change without notice and makes no representation about the accuracy, completeness, or timeliness of the content.*

---