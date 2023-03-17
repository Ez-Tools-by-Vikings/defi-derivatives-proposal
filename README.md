# EzDerivatives (TBD)

EzDerivates is a financial products platform that supports innovative derivative products built on blockchain.

## Options

### eMarkets and eTokens

We propose to build european styled cash settled options market that brings higher captial efficiency to the limited liquidity available in markets.

**What are eMarkets and How they work**

eMarkets are isolated cash settled european markets that allow users to mint eTokens against any given token (as allowed by the protocol).

Let's follow user journey.

Currently ETH price is at 1700$

Bob believe ETH price won't cross 1800$ in this market and he has 1 ETH to invest. He creates a call option with strike price at 1800$ with maturiy in 1 week.

He deposits 1 ETH in the appropriate eMarket contract and receives an eToken Pair, these are long and short eTokens.

He then sells the long eToken pair to Alice for a premium and keeps the short eToken.

If Alice does nothing now (which is usually what happens in these markets) and at the time of expiry price reaches 1900$ they can individually claim:

```
Long eToken - 100/1900 = 0.05263 ETH
Short eToken - 1800/1900 = 0.9473 ETH
```

We would have charged commision at mint and sale of these tokens.

If Bob changed his mind, he can burn his token pairs and retrieve collateral instead of selling. A pair can be burned at any time but individual tokens can be claimed only after maturity.

**What sets us apart**

Let's say Alice was a savvy trader, using our system she could then use the long eToken to collaterize another call option at 1900$ and receive a new eToken pair, she could sell the long tokens now to receive further premium on it thus minimising her premium losses in this exchange.

Let's say primary eTokens were token0 and the ones Alice created were token1 and at maturity ETH price goes to 2000$

```
Short eToken0 - 1800/2000 = 0.9 ETH
Long eToken0 - 200/2000 = 0.1 ETH
```

```
Short eToken1 = (100/200)/2000 = 0.05 ETH
Long eToken1 = (100/200)/2000 = 0.05 ETH
```

Alice had effectively created a call spread for herself without the need to provide excess collateral.

Theoretically our model can provide infinite capital efficiency for users.

## What are we going to build

1. Smart contract system for the markets
2. Order book platform for users to buy/sell options
3. User interface for interaction with our contracts
4. Infrastructure products

Under infrastructure products we plan to build support as well as internal infrastructure for contract automation and DOV (like Ribbon Theta vaults for Opyn).
