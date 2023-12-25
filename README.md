# osmanozdemir1's Audit Portfolio

Some of my findings in public contests can be found in this repository.

## About

I'm an independent security researcher who has an interest in smart contract audits. 

I have been participating in public audit contests on [Code4rena](https://code4rena.com/) and [Sherlock](https://audits.sherlock.xyz/contests) since June 2023. 

Over the past six months (at the time of creating this repository), I achieved numerous top 3, top 5, and top 10 results, with several of my submissions being selected for inclusion in the final report.

You can find my Code4rena profile [here](https://code4rena.com/@osmanozdemir1).



## Audit Contests

| Contest | Findings | Ranking | Platform |
|--|:--:|--|:--:|
| [Dodo V3](https://audits.sherlock.xyz/contests/89) | 2 H | #5 | Sherlock |
| [Chainlink Cross-Chain Contract Administration: Multi-signature Contract, Timelock and Call Proxies Contest](https://code4rena.com/audits/2023-07-chainlink-cross-chain-contract-administration-multi-signature-contract-timelock-and-call-proxies#top) | Non-public | #3 (_sharing 2_) | Code4rena |
| [Arcade](https://code4rena.com/audits/2023-07-arcadexyz#top) | 1 M | #6 (_sharing 5_) | Code4rena |
| [Good Entry](https://code4rena.com/audits/2023-07-arcadexyz#top) | 1 H, 2 L | #14 | Code4rena |
| [Allo V2](https://audits.sherlock.xyz/contests/109) | 1 H, 6 M | #21 | Sherlock | 
| [Wildcat Protocol](https://code4rena.com/audits/2023-10-the-wildcat-protocol#top) | 2 H, 1 M, 2L | #11 | Code4rena | 
| [Kelp DAO / rsETH ](https://code4rena.com/audits/2023-11-kelp-dao-rseth#top) | 2 H, 1 M, 5L | #38 | Code4rena | 
| [Canto Application Specific Dollars and Bonding Curves for 1155s](https://code4rena.com/audits/2023-11-canto-application-specific-dollars-and-bonding-curves-for-1155s#top) | 1 H, 1 M, 4L | #11 (_sharing 9 & 10_) | Code4rena | 


## Findings
### Dodo V3 Contest (June 2023)

| Vulnerability | Severity | Vulnerability Type | Protocol Type | Platform |
| - | :-: | - | - | - |
| [Anyone can sell other users' tokens as `fromToken`, and get the `toToken`'s themselves due to `decodeData.payer` is never checked](/sherlock/dodoV3/001-H.md).| High | Input validation | Leveraged Market Making | Sherlock |
| [`_poolRepayAll()` function updates the state incorrectly, which might cause the vault to be exploited](/sherlock/dodoV3/002-H.md). | High | Incorrect state handling | Leveraged Market Making | Sherlock |


### Arcade.xyz Contest (July 2023)

| Vulnerability | Severity | Vulnerability Type | Protocol Type | Platform |
| - | :-: | - | - | - |
| [Users who claimed an airdrop with a previous Merkle root won't be able to claim again even if they have more `totalGrant` in the new Merkle root](/code4rena/arcade/001-M.md).| Medium | Incorrect state handling | NFT Lending Market | Code4rena |


### GoodEntry Contest (August 2023)

| Vulnerability | Severity | Vulnerability Type | Protocol Type | Platform |
| - | :-: | - | - | - |
|[All withdrawals after the first one will burn users' liquidity for nothing when the pool is not enabled in `GeVault::withdraw()`](/code4rena/goodEntry/001-H.md).| High | Loss of Funds | Perpetual Trading | Code4rena |
|[`GeVault::modifyTick()` doesn't check if the new ticks array is properly ordered](/code4rena/goodEntry/001-L.md). | Low | Input validation | Perpetual Trading | Code4rena |
|[`GeVault::pushTick()` and `GeVault::shiftTick()` doesn't check if the `tokenisableRange` instance is ticker or ranger](/code4rena/goodEntry/002-L.md). | Low | Input validation | Perpetual Trading | Code4rena |


### Allo V2 Contest (September 2023)
| Vulnerability | Severity | Vulnerability Type | Protocol Type | Platform |
| - | :-: | - | - | - |
|[Allocators can allocate as much as they want in `QVSimpleStrategy`](/sherlock/AlloV2/001-H.md).| High | Voting Manipulation | Governance | Sherlock |
|[`QVBaseStrategy::reviewRecipients()` doesn't check if the recipient is already accepted or rejected, and overwrites the current status](/sherlock/AlloV2/001-M.md).| Medium | Incorrect state handling | Governance | Sherlock |
|[`RFPSimpleStrategy::setMilestones()` doesn't revert even if the milestones are already set](/sherlock/AlloV2/002-M.md).| Medium | Incorrect state handling | Governance | Sherlock |
|[`RFPSimpleStrategy::_distribute()` might revert even though it has enough funds to distribute](/sherlock/AlloV2/003-M.md).| Medium | Locked funds | Governance | Sherlock |
|[`RFPSimpleStrategy::_registerRecipient()` will always revert if `useRegistryAnchor` is "true"](/sherlock/AlloV2/004-M.md).| Medium | Incorrect state handling | Governance | Sherlock |
|[`QVBaseStrategy::_qv_allocate()` updates the `allocator.voiceCreditsCastToRecipient` incorrectly, which results in more votes for the recipient](/sherlock/AlloV2/005-M.md).| Medium | Voting manipulation | Governance | Sherlock |
|[The protocol doesn't work as expected with fee-on-transfer tokens](/sherlock/AlloV2/001-M.md).| Medium | Weird ERC20 tokens | Governance | Sherlock |


### Wildcat Protocol Contest (October 2023)

**Note:** Findings H-01 and M-01 below are selected for the final report.

| Vulnerability | Severity | Vulnerability Type | Protocol Type | Platform |
| - | :-: | - | - | - |
|[Borrowers can escape from paying half of the penalty fees by closing the market, and those remaining penalty fees will be covered by the lender who withdraws last](/code4rena/Wildcat/001-H.md).| High | Loss of funds | Lending | Code4rena |
|[`WildcatMarket::closeMarket()` can never be called](/code4rena/Wildcat/002-H.md).| High | Incorrect state handling | Lending | Code4rena |
|[Blocked accounts keep earning interest contrary to the WhitePaper](/code4rena/Wildcat/001-M.md).| Medium | Unfair yield distribution | Lending | Code4rena |
|[Tokens may still be stuck in the escrow contract even if the borrower overrides the sanction](/code4rena/Wildcat/001-L.md).| Low | Locked tokens | Lending | Code4rena |
|[The total supply of the market tokens does not decrease after transfer to zero address](/code4rena/Wildcat/002-L.md).| Low | ERC20 | Lending | Code4rena |



### Kelp DAO Contest (November 2023)
This contest had 3 High and 2 Medium findings. I found 2 of the 3 Highs and 1 of the 2 mediums.

| Vulnerability | Severity | Vulnerability Type | Protocol Type | Platform |
| - | :-: | - | - | - |
|[`rsETH` amount to mint calculation when depositing an asset in the `LRTDepositPool::depositAsset()` is incorrect, leading to an immediate loss of value](/code4rena/KelpDao/001-H.md).| High | Loss of Funds | DAO | Code4rena |
|[`rsETH` price can be manipulated by directly transferring funds to the pool, and the first depositor can use it to steal from everyone](/code4rena/KelpDao/002-H.md).| High | Price Manipulation | DAO | Code4rena |
|[Deposited amounts in the `EigenLayer` strategy should be checked before updating the strategy for the asset](/code4rena/KelpDao/001-M.md).| Medium | Incorrect state handling | DAO | Code4rena |
|[Contextual error when checking the balance deposited to EigenLayer may result in an incorrect deposit limit](/code4rena/KelpDao/001-L.md).| Low | Context | DAO | Code4rena |
|`LRTConfig::updateAssetDepositLimit()` function doesn't check if the current deposits are greater than the new limit. | Low | Context | DAO | Code4rena |
|`LRTDepositPool::addNodeDelegatorContractToQueue()` function should check if the inputted array includes the same addresses.| Low | Input validation | DAO | Code4rena |
|`LRTDepositPool::updateMaxNodeDelegatorCount` should check the new count is not below the current delegator count.| Low | Input validation | DAO | Code4rena |
|`ChainlinkPriceOracle::getAssetPrice()` function should check the stale price. | Low | Oracle | DAO | Code4rena |

QA Report with Low and NC findings can be found [here](/code4rena/KelpDao/QAreport.md).


### Canto Application Specific Dollar contest (November 2023)
This contest 1 High and 2 Medium severity findings. I found 1/1 High and 1/2 Mediums.

| Vulnerability | Severity | Vulnerability Type | Protocol Type | Platform |
| - | :-: | - | - | - |
|[`asD` contract owner can not withdraw interests due to incorrect scaling factor](/code4rena/Canto/001-H.md).| High | Locked Funds | Stable Coin | Code4rena |
|[Buying and selling shares in the Market.sol is vulnerable to sandwich attacks](/code4rena/Canto/001-M.md).| Medium | Sandwich Attack | Stable Coin | Code4rena |
|[`asD` instances are vulnerable to reorg attack](/code4rena/Canto/001-L.md).| Low | Reorg | Stable Coin | Code4rena |
|`Market::createNewShare()` function should update the shareBondingCurves mapping.| Low | Redundant state variable | Stable Coin | Code4rena |
|`Market::_splitFess()` should split the shareholder fee to the protocol and creator when there are no tokens in circulation.| Low | Context | Stable Coin | Code4rena |
|`Market::changeShareCreatorWhitelist` should emit an event.| Low | Event | Stable Coin | Code4rena |

QA Report with Low findings can be found [here](/code4rena/Canto/QAreport.md).


### Chainlink Cross-Chain Contract Administration: Multi-signature Contract, Timelock and Call Proxies Contest (July 2023)

This contest didn't have any valid high or medium findings. The result of the contest was determined by the overall quality and the number of the downgraded submissions of the participants. 

I was able to get a place in top 3 in this contest. The official contest page and the leaderboard can be found [here](https://code4rena.com/audits/2023-07-chainlink-cross-chain-contract-administration-multi-signature-contract-timelock-and-call-proxies#top).

**Note:** Findings of this contest are private and can not be shared.

