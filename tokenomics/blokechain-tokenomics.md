---
description: Uniting the interests of system participants
---

# 🪙 Blokechain Tokenomics

An ideal tokenomics should facilitate the coincidence of the interests of three groups of participants:

* Long-term holders who, having invested once, may not return to the blockchain for years.
* Regular users of the system who constantly use it for a variety of tasks.
* Validators who spend computing resources and time to keep the system running.

The coincidence of interests is not just a theoretical concept. When applied to tokenomics, it means that the growth of some functional parameter of the system must benefit all participants. Since Blokechain is a truly scalable blockchain, we chose network activity, in other words, the number of transactions per unit of time, as such a parameter.

Also, we are pretty sure that it is impossible to create a single-coin tokenomics model in which transaction growth results in gains for all participants, so Blokechain tokenomics uses two coins: BKC and BKG. Their supply is managed by Blokechain Grinder, which is essentially an automated central bank.

#### BKC Coin (Block Coin)

| Parameter          | Value                                              |
| ------------------ | -------------------------------------------------- |
| Maximum Supply     | Unlimited                                          |
| Circulating Supply | Limited by formula                                 |
| Initial Supply     | 1 000 000 000 BKCs during the first 1000 days      |
| Inflation          | 5% yearly after 1000 days                          |
| Utility            | Transaction fees in Blokechain are paid in BKC     |
| Issuance           | Anyone can issue BKC by burning BKG in the Grinder |
| Burning            | All BKCs used to pay commissions are burned        |

What matters most to blockchain users is that transaction fees do not become very expensive. In modern blockchains, the commission amount is determined on an auction basis - the more commission users pay, the faster their transaction will be processed. This leads to two problems: frontrunning and higher fees during activity spikes.

{% hint style="info" %}
Frontrunning is the ability to outrun someone else's massive transaction by increasing the commission paid and earning from the resulting price increase.
{% endhint %}

In Blokechain, the BKC coin will be used to pay commissions. The maximum commission cost will be a fixed amount of 1 BKC, but with the growth of the network activity, the transaction cost will decrease - down to thousandths of a BKC. Moreover, because BKC is an inflationary coin with a 5% supply growth per year, its price will correlate with the real-world inflation rate in the long run.

An activity expansion is usually accompanied by coin price growth. Thus, with the increase in network activity, the relative price of BKC will grow, but the absolute value of the transaction cost expressed in BKC will decrease. This will allow the fees to remain at an acceptable level relative to the real world even at the peak of the bull run.

BKC **Utility**

All transaction fees paid in BKC are immediately burned. The base fee rate per transaction is 1 BKC. But since the volume of transactions can be large, too many BKCs can be burned in a short period. Therefore, as the number of transactions increases, the fee is reduced so that no more than 1% of the total BKC supply is burned daily.

{% tabs %}
{% tab title="Details" %}
The formula defines the target fee cost in BKC depending on the total number of transactions. For the first 1000 days, the formula is:

$$
Fee=\frac{10^7}{10^7+TXN_{daily}}
$$

After 1000 days the formula changes to account for the BKC inflation:

$$
Fee=\frac{0.01\ast BKC_{supply}}{0.01\ast BKC_{supply}+TXN_{daily}}
$$
{% endtab %}
{% endtabs %}

BKC **Issuance**

BKC can only be released into circulation by burning BKG in the Blokechain Grinder. There is a queue of orders arranged by the BKG / BKC rate for this purpose. The more BKGs are offered in exchange for a single BKC, the sooner the Grinder will process that order. The closest analogy to such a queue is exchange limit sell orders, executed by persistent demand from the Grinder.

{% tabs %}
{% tab title="Details" %}
The mathematical formula defines the BKC issuance depending on the day after the launch. For the first 1000 days, the formula is:

$$
BKC_{issuance}=52209083\cdot\frac{e^{-0.00591626\cdot x}}{\left(1+e^{-0.00591626\cdot x}\right)^{9.6}}
$$

After 1000 days the formula changes to keep the constant inflation rate:

$$
BKC_{issuance}=\frac{10^7}{73}\\
$$

These calculations apply only to newly created BKCs. Simultaneously with the issuance, BKCs will be minted through Grinder to replace the burned commission.
{% endtab %}
{% endtabs %}

BKC **Circulating Supply**

The Blokechain Grinder controls the issuance of the BKC coin to reach the target circulating supply determined by a mathematical formula. Since the BKC coin is inflationary and the commissions paid in BKC are burned, there is a constant need to create new BKCs. Blokechain Grinder will print BKCs providing the necessary issuance and replacing burned BKC coins to reach the target BKC circulating supply.

{% tabs %}
{% tab title="Details" %}
The mathematical formula defines the target supply depending on the day after the launch. For the first 1000 days, the formula is:

$$
BKC_{supply}=10^{9.0112}\cdot\left(1+e^{-0.0059162\cdot day}\right)^{-8.6}\;-\frac{10^{9.0112}}{2^{8.6}}
$$

After 1000 days the formula changes to keep the constant inflation rate:

$$
BKC_{supply}=\frac{10^7}{73}\cdot\left(day+6300\right)
$$
{% endtab %}
{% endtabs %}

#### BKG Coin (Block Grinder)

| Parameter      | Value                                     |
| -------------- | ----------------------------------------- |
| Maximum Supply | 100 000 000 BKGs                          |
| Utility        | BKG is used to issue BKC                  |
| Issuance       | Can be minted only as validator's reward  |
| Burning        | A part of BKG while minting BKC is burned |

It is vital for investors and validators that there are explicit mechanics for the growth of the asset in the long run. But in most modern networks, it is not entirely obvious what a coin is secured with, so the main criteria for long-term investments remain the limited supply of the token and the possible popularity of the decentralized system in the future.

In Blokechain, BKG is designed for investment purposes and is directly secured by user activity. BKG is a BKC coin printing certificate. Its main properties are a constant demand from the system and persistent burning. Thus, the more BKC coins are burned as transaction fees, the more must be printed, and the more BKGs will be used for this purpose, part of which will be burned.

Thus, even a constant amount of daily transactions will reduce the overall supply of BKG. Therefore, both investors and validators benefit from the network activity since it directly reduces the BKG coin supply.

BKG **Utility**

BKG is used by Grinder for BKC issuance. Anyone can put BKG coins in the Grinder specifying BKG / BKC rate. The Grinder continuously uses the BKGs offers with the highest bids to issue BKCs. During the order processing, one part of the BKG burns irretrievably, and the other part becomes available for reissue into circulation. It will stop being burned when only 1 000 000 BKGs remain.

{% tabs %}
{% tab title="Details" %}
The percantage of BKG burned depends on the amount of BKGs put in Grinder for BKC issuance. The formula is:

$$
BKC_{\%burned}\;=\;100\cdot\frac{BKG_{grindered}}{BKG_{grindered}+10^7}
$$

When the number of BKGs used for BKC issuance exeeds 990 000 000 there will remain only 1 000 000 of BKG coins and they will stop burning.
{% endtab %}
{% endtabs %}

BKG **Issuance**

Validators' rewards will be calculated in BKC as the sum of burned commissions and inflationary BKC issuance. BKG will be issued corresponding to that amount using a constant product formula as validators' rewards. This means that the reduction of BKG token issuance will not occur in leaps and bounds, as in the case of Bitcoin halvings, but gradually.

Since validator rewards are not directly dependent on the specific transactions they process, the distribution of BKG among validators can be adjusted based on many factors. In addition, this approach prevents front-running.

{% tabs %}
{% tab title="Details" %}
The BKG supply depends on the number of BKCs minted by the Grinder. That includes all newly minted BKCs (issuance and replacement for burned coins). The number of BKGs to mint is defined by the formula:

$$
BKG_{issued}=\frac{10^{16}}{BKC_{minted}+10^8}
$$

The Grinder uses a virtual BKG system pool to issue BKG. The Grinder can only take BKG from there to the extent of the burned commissions and inflation issuance. BKG used but not burned during BKC minting returns to this virtual pool. Thus, over time, fewer and fewer BKG will be issued as a reward.

You can imagine - that there is a virtual AMM in Grinder with a pool of BKC **totally minted** / BKG **for issuance**. But the calculation of the BKG issue is done without having a real AMM - just by the constant product formula.
{% endtab %}
{% endtabs %}

BKG **Circulating Supply**

The amount of BKG circulating supply depends on the ratio of the BKG burning speed to the issuance volume. The BKG burning pace is determined primarily by the BKG market price. The BKG issuance depends on the number of BKCs burned as commissions. Thus, the exact amount of BKG in circulation can only be approximated.

Our simulation shows that though the total supply of BKG is 100 000 000, it is unlikely that there will be more than 20 000 000 BKGs in circulation at any given moment.

{% tabs %}
{% tab title="Details" %}
The circulating supply of BKG is calculated based on a computer model.

It assumes that the number of transactions grows from 0 to a given number within about half a year, and the rate at which Grinder uses BKG is directly proportional to the ratio of BKC and BKG coins in circulation.
{% endtab %}
{% endtabs %}

BKC **/** BKG **Rate**

The BKC / BKG rate depends very much on the initial distribution of coins - therefore, it can even fall during the first few years if the number of transactions is not very high. But in the long term, the amount of BKC in circulation will grow, and the amount of BKG will fall after the peak is passed. So, in the long run, depending on the number of transactions in the blockchain, the amount of BKC given per BKG will steadily grow.

{% tabs %}
{% tab title="Details" %}
The BKC / BKG rate is calculated based on a computer model as a ratio of the BKC circulating supply and the BKG circulating supply.

The model assumes that the number of transactions grows from 0 to a given number within about half a year, and the rate at which Grinder uses BKG is directly proportional to the ratio of BKC and BKG coins in circulation.
{% endtab %}
{% endtabs %}

### FAQ

#### Do you have two tokens? But LUNA also did, and it collapsed!

If some single-token system goes bankrupt, it doesn't mean all single-token mechanics are doomed. We have fundamentally different mechanics from LUNA, self-sufficient and not directly tied to the real world. Thus, it cannot be broken by external manipulation, as it happened with LUNA.

#### How will I be able to deposit or withdraw money from Blokechain?

In the beginning, a bridge with Ethereum will be set up to interact with the outside world, allowing users to use wrapped ETH in Blokechain. It will also be possible to withdraw capital from the Blokechain network using this bridge.

Bridges to other popular blockchains will be created in the future. If necessary, it will be possible to make a bridge with reverse logic, where BKC or BKG is withdrawn from Blokechain, and in another blockchain, the user receives wrapped BKC or BKG tokens.

#### What happens if no one puts BKG in the Grinder?

That won't happen. At least, the Blokechain Team will put a single BKG in the Grinder queue at a price sufficient to issue a billion BKCs. And we have no doubt that there will be many such overpriced orders.

#### BKG will not be burned when trading on the exchanges. Will it break the system?

There will be DEX in Blokechain, so it will be possible to trade BKG for BKC outside the Grinder.

If the price of BKG on DEX drops much relative to prices in the Grinder queue, it will open up an arbitrage opportunity. Anyone can buy a cheap BKG on the exchange and put it into the Grinder at a much higher price.

If the price on the exchange exceeds the price in the Grinder, it would be more profitable to cancel the Grinder's order in the queue and sell the BKG on the market.

Thus, the price on the exchange and in the Grinder queue will strongly correlate. But the burn price in the Grinder will likely be slightly higher than the exchange rate since it will take some time to process the order via the Grinder. In other words, if there is a possibility to swap BKG on the DEX immediately or through Grinder, say, within a week, then, obviously, the long wait must be somehow compensated.

#### What happens if BKG collapses?

As has already been said, the prices in the Grinder queue and on the exchange correlate. If the price of BKG falls (relative to BKC), then the Grinder will start to consume (and burn) significantly more BKG. Therefore, at moments of deep BKG drawdowns, it will be burned at an accelerated pace.

#### Where will the first BKC tokens come from?

The initial BKC tokens must appear somehow to launch the system. Otherwise, it will be impossible to make any transactions. For that, Blokechain will have a rule (both initially and in the future) that each new validator will receive 100 BKC as a gift.

#### Will BKG be distributed evenly?

BKG will be distributed among validators as a reward. Since we plan to launch a network with about a thousand initial validators, and about 10% of the total BKG supply will be distributed among them in the first year, there should be no large BKG holders.

Well, except for the Blokechain Team, which needs a lot of tokens to create bridges, provide liquidity for centralized exchanges, offer grants for developers, etc. The additional reward the Team will receive as Routers' rewards by operating the network layer.
