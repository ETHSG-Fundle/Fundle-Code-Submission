# Fundle

![fundle](https://github.com/ETHSG-Fundle/.github/assets/101350894/c805fd3d-41c6-4efe-b4c6-87f5b0d82942)

Fundle is an interchain Quadratic Funding Platform that is powered by a Lossless Pool generated from DeFi fixed yields. Beyond the traditional direct transfers, donors have the option give without losing anything by simply depositing funds to the protocol for an amount of time. They will get back 100% of their funds risk-free, meanwhile NPOs get to keep the yields (distributed quadratically) to support their causes.

This unique platform solves the problem for many people who are interested to help but come across common hurdles, like:

1. **Donor fatigue from having to evaluate and pick from hundreds of NPOs**: Fundle offers direct deposits to the quadratic pool which automatically allocates to causes that the public care about the most
2. **Needing to do research and verify that the recipient is indeed a legitimate beneficiary**: All the beneficiaries listed on Fundle have been evaluated and accredited by a central authority before they get to be part of the protocol
3. **Transparency of donation distribution**: How the donations will be distributed is already programmed in a smart contract and the status can be monitored in real-time through Fundle
4. **Finding more economically efficient options for donating**: Choosing to spend a budget on even the most deserving charity can be a pain in these challenging times, so Fundle offers a lossless donation option where donors can get back all the money they deposited and still make a huge impact.



## Table of Contents
- [How Fundle Works](#how-fundle-works)
- [Problem Statements Addressed](#problem-statements-addressed)
- [Technologies Used](#technologies-used)
- [Future Developments](#future-developments)
- [How to Run Locally](#how-to-run-locally)
- [Deployed Contract Addresses](#deployed-contract-addresses)
- [Axelar Bounty README](#axelar-bounty-readme)

## A Quadratic Fundraising Platform Powered by Risk Free Yields

Bringing fundraising to the blockchain offers advantages that cannot be found anywhere else. For organizations, fundraising through a completely transparent platform can boost their credibility and streamline the disbursement process for them. And for donors, they can find incredibly efficient systems to maximize the impact of even the smallest contributions. 

![Screenshot (526)](https://github.com/ETHSG-Fundle/.github/assets/101350894/026ad6cf-b207-440e-afd2-706a3507b2a7)


Fundle is taking on the huge challenge of building a credible fundraising platform that opens possibilities for lossless donations. Through fixed yield, people who are economically conscious can contribute by just parking their funds in the platform. **And because it is risk-free, it can radically lower the barrier for anyone who would like to help worthy causes.**

![farm](https://github.com/ETHSG-Fundle/.github/assets/101350894/760e201b-249b-49a6-bcb8-56a5e34aba24)


Aside from that, users can directly donate to the matching pool where their contributions will affect how the quadratic pool from fixed yields is distributed among NPOs.

![Fund](https://github.com/ETHSG-Fundle/.github/assets/101350894/787358b3-261c-458f-b0ac-ebe92c98638b)

Only the accredited beneficiaries can be listed in the donation pool, so while the donation process is convenient, it is also official. The flow of funds is also fully transparent and cannot be tampered with, so it will be open for anyone to monitor. 

## How Fundle Works

**The user journey for NPOs:**

1. A central authority accredits an NPO before getting listed on Fundle
2. Accredited NPO generates a special wallet to be listed and receive funds on Fundle
3. After a funding round, all direct donations as well as the matching funds from the quadratic pool will be distributed to the NPO

**The user journey for Donors:**

1. Donors can donate in three ways. (1) They can park their DAI in the protocol and the yield it generates becomes their donation, (2) They can directly donate their DAI to a project of their choice, and (3) They can send their donation to the quadratic pool and it will match the donations that were directly sent to each NPO.
2. If they choose to park their DAI and generate a lossless donation, they will be prompted to pick which fixed yield strategy to use for their funds
3. They can withdraw their deposits anytime, while the generated yields will go to Fundle's quadratic pool
3. Donations that go to the quadratic pool will be distributed according to how many people directly donated to a project and how much they donated. This ensures that the funds go to organizations that people deem most deserving

## Problem Statements Addressed

**Quadratic Funding Mechanism**

Fundle used a quadratic pool that takes in direct donations and yield-generated donations, and then it distributes them to match the individual donations made to each NPO

-**Charities input programs to attract funding**: Fundle enables accredited charities to list on the protocol, bringing them a secure way to accept donations from a wider audience

-**Ensure credibility of charities**: There will be a centralized authority to see through registration and make sure that only certified beneficiaries can accept donations from Fundle pools

-**Accurate Donor Matching**: The quadratic matching is coded in the Donation Manager smart contract, where the quadratic pool from Farm-to-Fund mechanism and general donations are accurately matched to user's direct NPO donations. 


**One-Stop Cross-Chain Platform**

A centralised, congregated avenue to handle various donation methods for different types of donors and also for fund disbursement.

-**Transparency**: Fund disbursement and handling of donation are all executed via autonomous smart contracts

-**Tracking**: Donors, both big and small are able to track where the donations go in real time through Fundle dApp

-**Engagement**: Seeing how their supported NPOs measure in the quadratic funding pool can encourage greater support from donors

-**Profiling of donors**: There are three different ways to donate for each type of donors

-**Donor payment gateway**: Fundle can accept donations from three chains-- Goerli, Mantle, and Linea

-**Reaching international donors**: Crypto makes cross-border payments incredibly cheap and fast


## Technologies Used

- **Pendle’s PT fUSDC**: Pendle’s fixed yield on fUSDC made the lossless donation pool possible. This is the technology that enables the protocol to generate risk-free yields for the quadratic pool

- **DAI and sDAI**: A live forked version of the ERC4626 Savings DAI contract from SparkProtocol has been launched to integrate with one of our lossless strategy `sDAI ERC4626Strategy` to accrue yield from lossless donors and subsequently matched to donors via our quadratic funding mechanism. This way lossless donor can have the option to generate fixed yield from their funds through MakerDAO and SparkProtocol's DAI and sDAI.

- **Axelar**: Interchain donations were made possible because of Axelar's message and token passing from Mantle and Linea to Goerli. We used a deployed aUSDC (Axelar Wrapped USDC) as the ERC20 token to send through Axelar's interchain communication protocol.

- **Mantle**: We have deployed Donation Relayer contracts on Mantle for user who chose the network's hyperscale performance, data availability, and robust security

- **Linea, Metamask, and Infura**: We also deployed a contract that accepts donations from Linea for users who chose the network for its seamless integration with Metamask. We also use Infura's RPC endpoints for deploying smart contracts in Goerli and Linea. 

- **Nouns Artworks**: We used Nouns’ assets to create a colorful UI theme that fosters optimism

## Future Developments

We are planning to make Fundle a holistic platform for fundraising and we already have a few ideas on how we would like to improve on the MVP. To mention some:

- Fully integrate swap mechanism for deposits in the main donation QF pool to swap into Principal Token fUSDC given that it appreciates over time in terms of the underlying USDC & will generate more USDC for donation disbursement given that funds collected are only distributed upon the end of each `EPOCH`. The protocol will swap back to USDC upon distribution of QF pool donations.
- A gamified way to incentivize users to recurringly donate to their chosen charity
- An AA wallet factory to enable the central authority to generate special purpose-bound wallets for beneficiaries
- A token-gated page where NPOs can communicate to their respective donors and boost engagement and transparency
- Integrating attestations to NPO wallets for donor feedback and suggestions

## How to Run Locally

- navigate to https://github.com/ETHSG-Fundle/fundle-fe
- clone the repository by running `git clone https://github.com/ETHSG-Fundle/fundle-fe.git`
- navigate to your local folder by entering `cd fundle-fe`
- install the project dependencies by running `yarn`
- run `yarn dev`
- open your browser in the indicated localhost port

## Deployed Contract Addresses

**Goerli**

`Beneficiary Certificate`
0x9cC857A6291598D10e9446808d3F0DDd205E0D64

`Donation Manager`
0x32f972DFbFAD84c986Db30681f1177e221ef72dd

`Savings DAI ERC4626 Strategy`
0x10371645FcB4668E04807baB7A34564fd745A111

`GMP Donation Receiver`
0xc027F2D4A76E6e86369aFbA397cfc1a6Fd97D3b5

`DAI (forked)`
0x4023Ec52F26Cb9093D642cd7e40751EeA304eAbe

`sDAI (forked)`
0xaEcB1B62E8C3e6d0DeD2706c0e3A41b29B3Fdb73

`AXLUSDC ERC20 Token`
0x254d06f33bDc5b8ee05b2ea472107E300226659A


**Mantle**

`GMP Donation Relayer`
0x5E04F56F0C5257c398C9A6F7E1e5caa318Eb7398

`AXLUSDC ERC20 Token`
0x254d06f33bDc5b8ee05b2ea472107E300226659A


**Linea**

`GMP Donation Relayer`
0x1FFaa029FD4076c38e75A3dde600dd4A527a3229

`AXLUSDC ERC20 Token`
0x254d06f33bDc5b8ee05b2ea472107E300226659A

## Axelar Bounty README

Fundle offers seamless cross-chain donations to be made to specific beneficiaries or directly to the main quadratic funding pool via the `BeneficiaryDonationManager` that all exists on the main chain (ETH Goerli) from both Linea and Mantle L2 chains that leverages on the following design. This cross-chain experience/capability would be more appealing for donors with liquidity fragmented over different chains.

A `GMPDonationReceiver` is deployed on the main chain that facilitates cross-chain donation function calls of the `BeneficiaryDonationManager` from side chains. Cross-chain calls are executed via `GMPDonationRelayer` that are deployed on both side-chains for donors with liquidity existing on these chains to have their funds bridged and routed to the `GMPDonationReceiver` which will interact directly with the `BeneficiaryDonationManager` in a single transaction call.

**Example Cross-Chain Donation Function Call alongside with sending token i.e. `callContractWithToken`:**
[https://testnet.axelarscan.io/gmp/0x9c2b593cc13756ef2d26cbff2a1faf87a5fb3863d8b3cfb2b6b45af1c0185d91](https://testnet.axelarscan.io/gmp/0x58e154094f1f926a05d346d6e4bd02b9ff2f4e980245b8648b7d5eb12fc3a048) [LINEA GOERLI to ETH GOERLI]

**Experiences:**

1. Learning how to integrate with Axelar Network was relatively smooth and interesting given the detailed documentation, example github repos stated in the documentations.
2. Unlike most SDKs, Axelar Network provides robust support on testnets with almost all chains integrated and D-Apps to support for UI interaction and learning purposes.
3. The Youtube Tutorial videos for devs were extremely helpful as it provided a live working example. The only downside to trying to integrate with Axelar is trying to debug cross-chain integration execution errors as error messages are not that helpful.
