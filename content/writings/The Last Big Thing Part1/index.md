---
title: "The Last Big Thing - Crypto Payment Part1"
summary: It's not happening until we build it.
date: 2024-10-28T10:30:00+08:00
weight: 1000
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
    alt: "cover" # alt text
    caption: "" # display caption under cover
    relative: true # when using page bundles set this to true
    hidden: false # only hide on current single page
# editPost:
#    URL: "https://github.com/<path_to_repo>/content"
#    Text: "Feedback" # edit text
#    appendFilePath: true # to append file path to Edit link
---

*This article, the first in a three-part series, explores the landscape of traditional payment systems, from their historical origins to modern digital transformations.*

*The <a href="https://larryliu007.github.io/writings/the-last-big-thing-part2/" style="color: #0E97CB;">second part</a> will explore the unique advantages of blockchain technology in payments and assess the current state of crypto payments. The final installment will analyze emerging trends and revolutionary possibilities that could reshape how we transfer value in the future.*

# 1. Introduction

Over time, I came to believe that ***value transfer*** remains the most significant and compelling use case for blockchain technology in the foreseeable future, aligning with its original vision.

As the industry collectively yearns for practical applications rather than further infrastructural developments, I've dedicated the past few months to an intensive exploration of this particular sector. I would like to share these learning notes with the audience, in the hope that they might prove helpful. 

I'm deeply grateful for the invaluable support from: <a href="https://x.com/niarbnotna" style="color: #0E97CB;">@niarbnotna</a>, <a href="https://x.com/YinghuanCui" style="color: #0E97CB;">@YinghuanCui</a>, <a href="https://x.com/gizmothegizzer" style="color: #0E97CB;">@gizmothegizzer</a>, <a href="https://x.com/ryanberckmans" style="color: #0E97CB;">@ryanberckmans</a>, <a href="https://x.com/JimsYoung_" style="color: #0E97CB;">@JimsYoung_</a>, and <a href="https://x.com/sui414" style="color: #0E97CB;">@sui414</a>. 

Special appreciation to all the friends at <a href="https://x.com/holyheld" style="color: #0E97CB;">@holyheld</a>, <a href="https://x.com/Fiat24Official" style="color: #0E97CB;">@Fiat24Official</a>, <a href="https://x.com/WSPNpayment" style="color: #0E97CB;">@WSPNpayment</a>, <a href="https://x.com/kun_sight" style="color: #0E97CB;">@Kun_sight</a>, <a href="https://x.com/Qbit_Neobank" style="color: #0E97CB;">@Qbit_Neobank</a>, <a href="https://x.com/redotpay" style="color: #0E97CB;">@RedotPay</a>, <a href="https://x.com/gnosispay" style="color: #0E97CB;">@gnosispay</a>, and <a href="https://x.com/intent/follow?screen_name=transak" style="color: #0E97CB;">@Transak</a> - your insights have been instrumental!

# 2. Evolution of payment

## 2.1 Card payments

### 2.1.1 The origin of credit card and the enablers

One night in 1949, Frank X. McNamara, a New York City businessman, was dining at a restaurant named Major's Cabin Grill, and soon realized he had forgotten his wallet. As a result, he had to call his wife to bring cash for the bill. This embarrassing incident inspired him to create a single card that could be used to make purchases at various establishments.

In 1950, McNamara founded Diners Club and issued the first credit card to 200 prosperous businessmen and merchants in New York. The cardholders could use the Diners Club card to pay for meals at participating restaurants, and the merchants would then be reimbursed by Diners Club, ***minus a service charge***.

<span style="color: #0E97CB;">*Diners Club Credit Card In The Early Days*</span>

<div align="center">
  <img src="/The_Last_Big_Thing/pic1.png" width = "80%">
</div>

The Diners Club card was an instant success, and the concept quickly spread to other companies and industries:

- In 1958, American Express launched their own credit card product to compete with Diners Club in the travel and entertainment market.
- In 1966, the Interstate Credit Card system, later renamed Master Charge (now Mastercard), was formed by a group of banks to enable a universal credit card that could be used at numerous merchants.
- Also in 1966, Bank of America launched the BankAmericard, which later became Visa, as a licensed franchise issued by various banks.
- In 1969, an association of regional bankcard programs formed the Interbank Card Association, which became Mastercard International in 1979.

The introduction of these bank-issued, all-purpose credit cards expanded the credit card market rapidly in the 1960s and 1970s. Competition grew fierce as these companies and banks engaged in aggressive marketing to sign up merchants and consumers. Rewards programs, annual fees, interest rates and other features were developed over time. Credit cards evolved from a product for travel and entertainment to a widely used payment method for all types of consumer purchases, and gradually became an integral part of the financial system.

<div align="center">
  <img src="/The_Last_Big_Thing/pic2.png" width = "60%">
</div>

***Nevertheless, it is important to note that the widespread adoption is inherently intertwined with the progress of technology.*** The development of computer systems and telecommunications networks in the 1960s and 1970s made all these possble, through enabling the efficient processing and authorization of card transactions on a large scale.

Prior to the advent of computer systems and telecommunications networks, processing card transactions was a manual and cumbersome process. When a customer made a purchase with a card, the merchant had to call the issuing bank to verify the customer's credit limit and obtain authorization for the transaction. This process was time-consuming, inefficient, and limited the scalability of card payments.

The computerization of financial systems and the development of telecommunications networks enabled the automation of card payment processing, including:

1. Electronic data capture at points-of-sale (POS), eliminating manual entry and errors.
2. Efficient transmission of transaction data between merchants, banks, and card issuers through telecommunication networks like leased lines and the internet.
3. Automated, near-real-time authorization of transactions through computerized systems that could quickly access customer data and credit limits.
4. Batch processing and clearing of large transaction volumes between financial institutions.
5. Scalability, speed, and accuracy required to handle widespread card payment adoption across a growing base of merchants and consumers.

These technological advancements laid the foundation for the modern electronic payment infrastructure, transforming card payments from a manual, localized process into a highly efficient, automated, and globally interconnected system, paving the way for their widespread use in retail, online, and various other commerce sectors.

### 2.1.2 How does it work nowadays

Nowadays card payments work through a series of steps involving the customer, the merchant, the merchant's bank (acquiring bank), and the card network and customer's card-issuing bank.

<details>
<summary><i>👈Click to see details on how card payments work</i></summary>

1. Authorization:
   - The customer presents their credit or debit card to the merchant for payment.
   - The merchant sends a request to their payment processor or gateway, including the card details and transaction amount.
   - The payment processor forwards the request to the card network (e.g., Visa, Mastercard).
   - The card network routes the request to the issuing bank (the customer's bank).
   - The issuing bank verifies the card details, checks for sufficient funds or credit, and approves or declines the transaction.
   - The response is sent back through the card network and payment processor to the merchant.
2. Capture:
   - If the transaction is approved, the merchant receives an authorization code.
   - The merchant completes the sale and captures the transaction, typically at the end of the day or in batches.
   - The merchant sends the captured transactions to their payment processor.
3. Clearing and Settlement:
   - The payment processor sends the captured transactions to the card network for clearing.
   - The card network facilitates the exchange of funds and transaction information between the issuing bank and the acquiring bank (the merchant's bank).
   - The issuing bank deducts the transaction amount from the customer's account.
   - The acquiring bank receives the funds and credits the merchant's account, minus any applicable fees.
4. Funding:
   - The merchant receives the funds in their account, typically within 1-3 business days after the settlement.
</details>

During this process, multiple security measures are also implemented to safeguard sensitive card information and prevent unauthorized or illegal transactions. These measures include encryption, compliance checks, and fraud detection, etc.

***It goes without saying that each participant involved in the process takes a small cut of the transaction.*** These fees can vary significantly depending on factors such as the type of card, the industry of the merchant, the transaction volume, and whether the transaction is conducted in person or online, etc. However, when combined, these fees can be surprisingly high. The general process and breakdown is illustrated in the diagram below.

<span style="color: #0E97CB;">*Typical Workflow Of Card Payments*</span>

<div align="center">
  <img src="/The_Last_Big_Thing/pic3.png">
</div>

As a consumer, you likely never notice the many fees involved because payment providers charge merchants rather than customers directly. Over time, these providers have built a powerful network effect, resulting in most customers (particularly in America and Europe) using credit or debit cards as their main form of payment. Despite the high costs, merchants has little choice but to participate in these networks to offer their customers a seamless and convenient payment experience.

## 2.2 From card payment to open banking

### 2.2.1 Digital payments came in

Things have changed since the late 1990s when online payment platforms started to emerge with the widespread use of the internet and the growth of e-commerce. These platforms allow users to make payments quickly and easily from anywhere with an internet connection, eliminating the need for cash or checks. The proliferation of smartphones in the 2000s has further accelerated the adoption of these platforms, as more customers have grown accustomed to the convenience of seamless digital payment experiences.

PayPal was launched in 1998, which soon became the dominant player in the early 2000s, and the introduction of Alipay in China in 2004, which has since become the world's largest mobile and online payment platform. In 2010, Stripe arrived, simplifying payment processing for businesses worldwide. The mobile era ushered in new players, with Apple Pay in 2014 and Google Pay in 2015 turning smartphones into digital wallets, changing how millions pay both online and in stores.

<details>
<summary><i>👈Click to see details on how digital payment works</i></summary>

1. Checkout initiation: When a user is ready to make a purchase, they select their preferred payment method (online or mobile) and initiate the checkout process. If the user is not already logged in, they may be prompted to sign in or create an account.
2. Payment method selection: The user chooses their preferred payment method from the options they have previously set up, such as a credit card, debit card, or mobile wallet.
3. Authentication: The user authenticates the transaction using security measures like passwords, PINs, or biometric data (e.g., fingerprint or facial recognition for mobile payments).
4. Payment processing: The payment service provider securely processes the transaction, either verifying that the user has sufficient funds in their account, or communicating with the user's bank or card issuer to verify and authorize the payment. Fraud detection measures are applied during this step.
5. Confirmation and receipts: Once the payment is processed, both the user and the merchant receive confirmation of the transaction. Digital receipts may be sent via email or stored within the payment platform's interface.
</details>

Digital payments act as a form of disintermediation relative to traditional card payments. ***Money from both users and merchants slowly builds up in the e-wallet, creating a fund pool.*** They rarely interact directly with the traditional payment systems anymore. Instead, transactions are simply internal bookkeeping entries, transferring amounts from one balance to another. This bypasses some of the previous intermediaries, and transactions are now essentially processed in "batches". Moreover, these platforms offer financial products and yield opportunities to their customers, leveraging these funds while taking a commission.

<span style="color: #0E97CB;">*Typical Workflow Of Digital Payments*</span>

<div align="center">
  <img src="/The_Last_Big_Thing/pic4.png">
</div>

More importantly, the move toward digital payments, as the name suggests, is a digitalization process. ***Many of its benefits are (again) made possible by emerging technologies:***

1. Prevailing of mobile devices and internet -> Convenience and Accessibility  
   The ubiquity of smartphones, user-friendly apps, and expansive internet and mobile networks make digital payments convenient and accessible, driving financial inclusion.
2. Adoption of tokenization and biometric authentication -> Enhanced Security  
   Implementing tokenization and biometric authentication significantly improves digital payment security compared to traditional card payments.
3. Utilization of cloud computing and digital infrastructure -> Reduced Costs  
   Leveraging cloud computing and digital infrastructure streamlines transaction processing, minimizing the need for physical infrastructure and reducing fraud-related costs.
4. Advancement in interoperability and integration -> Seamless User Experience  
   APIs, SDKs, and web services, allow digital payment platforms to seamlessly integrate with various digital services, enhancing user experience and encouraging widespread adoption.
5. Harnessing big data analytics and AI -> Expanded Business Opportunities  
   Payment companies employ big data analytics and AI to gain valuable customer insights, develop targeted strategies, and expand their market presence.

### 2.2.2 Cutting-edge technology spreads more quickly in less developed areas

***Interestingly, most advanced payment technologies tend to spread more quickly in relatively less developed countries.***

<span style="color: #0E97CB;">*POS Payment Methods By Volume*</span>

<div align="center">
  <img src="/The_Last_Big_Thing/pic5.jpeg">
</div>

*Data Source: [Global Payments Report 2024, Worldpay](https://worldpay.globalpaymentsreport.com/en)*

Worldpay's report highlights two key trends:

1. More developed regions generally have higher rates of cashless transactions due to better access to advanced technologies and stronger economic foundations, enabling quick adoption of new paradigms for improved convenience and efficiency.
2. Less developed regions are increasingly adopting digital payments. This contrasts with North America and Europe, where payment markets are mature and customers are used to card payments. In these established markets, the convenience of digital payments barely outweighs the costs of switching. Plus, established companies use various tactics to keep their market share, showing how resistant large-scale payment systems can be to change.

This raises an interesting question about crypto payment adoption: Where would it be most effective? In developed countries, and places like China and India, widespread internet access and sophisticated financial systems are already in place. Here, cryptocurrencies offer benefits related to financial independence and privacy, as well as investment opportunities, but these are generally seen as nice-to-have features rather than essentials. On the flip side, in many other parts of Asia, Latin America, and Africa, where inflation is high or large segments of the population lack access to banks and payment platforms, crypto could significantly enhance the convenience and efficiency of financial transactions.

<span style="color: #0E97CB;">*Daily crypto purchasing with ARS (Argentine Peso) vs. ARS value*</span>

<div align="center">
  <img src="/The_Last_Big_Thing/pic6.png">
</div>

*Source: [The 2023 Global Crypto Adoption Index, Chainalysis](https://www.chainalysis.com/blog/2023-global-crypto-adoption-index/)*

Surprisingly, crypto, particularly stablecoins, is already gaining traction in various regions. In Argentina and Turkey, people use cryptocurrencies as a hedge against inflation, with about half of Turkey's youth owning some form of crypto. In the Philippines and Vietnam, cryptocurrencies facilitate remittances, helping workers abroad send money home efficiently. The Philippine central bank even introduced a stablecoin linked to the peso to promote financial inclusion. Across African cities, from Lagos to Nairobi, small and medium-sized businesses are increasingly accepting cryptocurrencies, reducing cross-border transaction fees from as much as 15% to between 1% and 3%.

<span style="color: #0E97CB;">*8 Of The Top 10 Countries Leading In Crypto Adoption Are From Less-developed Regions*</span>

<div align="center">
  <img src="/The_Last_Big_Thing/pic7.png">
</div>

*Source: [The 2023 Global Crypto Adoption Index, Chainalysis](https://www.chainalysis.com/blog/2023-global-crypto-adoption-index/)*

*The <a href="https://larryliu007.github.io/writings/the-last-big-thing-part2/" style="color: #0E97CB;">next article</a> in this series will explore blockchain's unique advantages in payments: how it opens up financial services to a broader audience and creates a transparent environment where different parties can collaborate efficiently. It will also examine the current state of crypto payments, analyzing both the challenges and opportunities in this emerging space.*

---

*Disclaimer: The views, information, and opinions expressed in this article are solely my own and do not reflect the official position of my employer or its affiliates. This post is for informational purposes only and should not be construed as investment, financial, legal, or tax advice. Nothing contained herein constitutes an offer to sell, a solicitation of an offer to buy, or a recommendation for any digital asset or investment. The information presented is subject to change without notice and makes no representation about the accuracy, completeness, or timeliness of the content.*

---