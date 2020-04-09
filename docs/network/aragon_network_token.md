![](../design/artwork/ANT/ANT01.jpg)

# Aragon Network Token

The Aragon Network Token (ticker symbol: ANT) is the native token of the Aragon Network. ANT is primarily used for the governance of the Aragon Network, although additional uses for accessing Aragon Network services have been proposed as well.

## ANT uses

### Governance  

The first use of ANT is as a Sybil-resistant mechanism for governance. In the [Aragon Governance Proposal (AGP) process](https://github.com/aragon/AGPs/blob/master/AGPs/AGP-1.md#aragon-network-votes), which was [first approved by ANT holders](https://blog.aragon.org/final-results-from-the-agp-1-vote/) on November 17, 2018, one ANT equals one vote. This means that anyone can vote on AGPs, even while remaining pseudonymous, by acquiring and holding ANT at the time of the Aragon Network vote they want to participate in. ANT can also be used to vote on proposals in the [Community Funding DAO](https://forum.aragon.org/t/how-to-make-proposals-to-the-community-funding-dao/697), which was first proposed in [AGP-10](https://github.com/aragon/AGPs/blob/master/AGPs/AGP-10.md), approved in [Aragon Network Vote #1](https://blog.aragon.org/final-results-from-aragon-network-vote-1/), and [deployed](https://forum.aragon.org/t/agp-discussion-community-funding-dao/418/36) on March 18, 2019.

On March 13, 2020, ANT holders [voted to sunset the AGP process](https://blog.aragon.org/final-results-from-aragon-network-vote-6/) in preparation for Phase 3 of the [Aragon Network launch](overview/#the-aragon-network-launch).

### Aragon Court
From the [ANJ article](https://help.aragon.org/article/44-how-to-get-anj-and-become-an-aragon-court-juror#bonding-curve) at the Aragon Help Desk:

> ANJ (Aragon Network Juror) is the native token of Aragon Court, which jurors need to activate in the Court to be selected and earn dispute fees. The use of ANJ helps align the incentives of jurors with the long-term health of the Court, ensuring the Court's integrity.

ANJ is minted by depositing ANT using a bonding curve smart contract. The ANJ bonding curve went live with the official launch of Aragon Court on Fight For Freedom Day February 10, 2020.

Continuing from the ANJ Help Desk article:

> ANJ is a continuous token, the supply of which is regulated by a bonding curve. A bonding curve is an automated market maker smart contract that defines a relationship between token price and token supply. 
> 
> ANT is the reserve token used to back the ANJ supply. The more ANT is deposited in the ANJ bonding curve, the more the total supply of ANJ increases; the more ANT is withdrawn from the bonding curve, the more the total supply of ANJ decreases.
> 
> The bonding curve is used to convert ANT into ANJ and back at pre-defined rates. The way the ANJ bonding curve is set up, the more ANT is sent to the bonding curve, the fewer new ANJ will be released back to the sender; the more ANJ is sent to the bonding curve, the fewer ANT will be released back to the sender.
> 
> You can find a technical explanation of bonding curves [here](https://yos.io/2018/11/10/bonding-curves) and find the source code for the specific smart contract used for the ANJ bonding curve [here](https://github.com/AragonBlack/fundraising/blob/next/apps/batched-bancor-market-maker/contracts/BatchedBancorMarketMaker.sol).

More information about the use of ANT and ANJ in Aragon Court can be found in the [Aragon Network whitepaper](https://github.com/aragon/whitepaper).

### Aragon Chain  

In a [blog post announcing Aragon Chain](https://blog.aragon.one/aragon-chain/), a Proof-of-Stake blockchain built for the Aragon community, the Aragon One team has proposed that ANT could be deposited into a bonding curve to mint Aragon Chain (ARA) tokens. These tokens would be required to stake and become a validator for the Aragon Chain. With [AGP-106](https://github.com/aragon/AGPs/blob/master/AGPs/AGP-106.md) approved in Aragon Network Vote #4, the blockchain development company ChainSafe is now the team responsible for putting the Aragon Chain plan into action.

ChainSafe published the first [public specification](https://medium.com/chainsafe-systems/aragon-chain-spec-goes-public-b3b8ff99deb9) of Aragon Chain on January 17, 2020.

## Initial token distribution

ANT was initially created and distributed as a result of a [public token sale](https://blog.aragon.org/announcing-the-aragon-network-token-sale-fe83fe36902c) that took place on [May 17, 2017](https://blog.aragon.org/final-token-sale-recap-1ac64ab7cfcd) - starting at Ethereum block 3,723,000 to be exact. Less than 100 blocks later, 275,000 ETH worth of ANT were sold. Added together with ANT sold in the pre-sale, ANT granted to the Aragon Foundation/Association, and ANT granted to founders and early contributors, the total initial supply of ANT after the token sale is 39,609,523.80952380954 ANT.

**Sources:**

- [Aragon Network token sale terms](https://blog.aragon.org/aragon-network-token-sale-terms-8998f63a3429)
- [Pre-sale transparency report](https://blog.aragon.org/pre-sale-transparency-report-333e310304c)
- [The Aragon token sale: the numbers](https://blog.aragon.org/the-aragon-token-sale-the-numbers-12d03c8b97d3)

### Initial supply breakdown

|  | Amount (ANT)	| % of initial supply |
|:------------- |:-------------:|:-------------:|
| Public sale + Pre-sale grant | 27,726,666.666666666678 ANT | 70% |
| Aragon Foundation grant | 5,941,428.571428571431 ANT | 15% |
| Early contributors and founders grant | 5,941,428.571428571431 ANT | 15% |

Total supply: 39,609,523.80952380954 ANT`*`

> `*` Total supply will be constant only until the AN (Aragon Network) is deployed. From then on, ANT holders will use Aragon Network governance to decide the monetary policy and inflation rate going forward.

**Sources:**

- [Etherscan](https://etherscan.io/token/0x960b236A07cf122663c4303350609A66A7B288C0)
- [Pre-sale script](https://github.com/aragon/aragon-network-token/blob/master/scripts/presale.js#L6-L17)

## Technical details

ANT is an ERC-20 token using the [MiniMe standard](https://github.com/giveth/minime). As Aragon co-founder Jorge Izquierdo [wrote](https://blog.aragon.one/aragon-token-sale-technical-overview-9c2a4b910755) on the Aragon blog:

> We decided to use MiniMe as the base token for ANT because it offers flexibility, security, and a clear upgrade path. The [MiniMe Token](https://github.com/Giveth/minime) is an ERC20 token created by the [Giveth](http://giveth.io/) team that maintains a history of balances and is easily cloned to create independent tokens with unique functionality (shout out to the Giveth team, definitely one of the best Solidity development teams out there).
>
> In addition, MiniMe is a great token standard for governance because it keeps track of balances at the time of starting a proposal vote. This removes the need to lock balances after voting to prevent double voting. With all of its benefits, we’re considering making MiniMe the default token for all Aragon organizations.

**Sources:**

- [Token sale audit results](https://blog.aragon.one/token-sale-audit-results-abea34b61209)

## ANT asset analysis

On October 22, 2019, Aragon One researcher Luke Duncan published an analysis of ANT entitled "[ANT Demand Modeling Framework](https://forum.aragon.org/t/ant-demand-modeling-framework/1389)". Duncan described the document as "a basic framework for thinking about the demand for the Aragon Network Token (ANT) based on its current and potential future utility value".

On March 6, 2020, the venture capital firm Placeholder published an analysis of ANT entitled "[Aragon (ANT) Economics](https://www.placeholder.vc/blog/2020/3/6/aragon-ant-economics)". Placeholder refers to ANT in their analysis as "a governance asset, with planned future economics to reinforce its store-of-value status".

## Store ANT
In addition to self-custody tools available in [hardware and software form](https://wiki.aragon.org/network/governance/how_to_vote/#voting-methods), institutional custodians in the list below have begun offering ANT custody services to qualified clientele.

_Disclaimer: Inclusion of a service does not constitute an endorsement of the service by the Aragon Association or any other member of the Aragon project. Please do your own research before giving custody of your assets to any entity on this page. Keep your funds safe and only do business with people for whom you have a good reason to trust._

- Coinbase Custody - [https://custody.coinbase.com](https://custody.coinbase.com)

## Trade ANT

In addition to buying and selling ANT peer-to-peer, ANT can be bought or sold using the services in the list below.

_Disclaimer: Nothing on this page should be taken as investment advice. Inclusion of a service does not constitute an endorsement of the service by the Aragon Association or any other member of the Aragon project. Please do your own research before trading ANT or using any of the listed services to trade ANT. Keep your funds safe and only do business with people for whom you have a good reason to trust._

**Exchanges:**

- Bancor - [https://www.bancor.network/](https://www.bancor.network/)
- Bitplace - [https://www.bitplace.to](https://www.bitplace.to)
- Bitfinex - [https://bitfinex.com](https://bitfinex.com)
- Bittrex International - [https://international.bittrex.com](https://international.bittrex.com)
- ChangeNOW - [https://changenow.io/](https://changenow.io/)
- EtherDelta - [https://etherdelta.com/](https://etherdelta.com/)
- Ethfinex - [https://www.ethfinex.com](https://www.ethfinex.com)
- HitBTC - [https://hitbtc.com](https://hitbtc.com)
- IDEX - [https://idex.market](https://idex.market)
- KyberSwap - [https://kyberswap.com](https://kyberswap.com/swap/eth-ant)
- Paradex - [https://paradex.io/](https://paradex.io/)
- Radar Relay - [https://radarrelay.com/](https://radarrelay.com/)
- SimpleSwap - [https://simpleswap.io/](https://simpleswap.io/)
- ShapeShift - [https://shapeshift.io](https://shapeshift.io)
- Stealthex - [https://stealthex.io/](https://stealthex.io/)
- Swapzone - [https://swapzone.io/](https://swapzone.io/)
- Switchain - [https://www.switchain.com/](https://www.switchain.com/)
- Uniswap - [https://uniswap.exchange/swap](https://uniswap.exchange/swap)
- UpBit - [https://upbit.com](https://upbit.com)

**OTC Brokers:**

N/A

---
Page owner: John Light (@john-light). Last updated 2020-04-09.