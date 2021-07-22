# 抵押品和储备金
> 使用 SCREAM 贷款平台所需的抵押品和储备金的摘要。

SCREAM 实现了 Compound Protocol 实施的抵押和储备机制。

## 储备系数

储备金是每个 scToken 合约中的一个会计条目，代表了一部分历史利息（作为现金预留），可以通过协议的治理（一旦启用）提取或转移。一小部分借款人的利息应计入协议，由储备系数决定。

储备系数是支付给 SCREAM 协议的利息的百分比。如果储备系数是 10，那么就意味着需要向借款资产支付 10% 的利息。 (原文: The reserve factor is the percentage of interest paid to the SCREAM protocol. If the reserve factor is 10, then that would imply a 10% rate of interest paid on the borrowed asset allocated to SCREAM.)

## 抵押系数

scToken 有一个抵押系数，范围在 0-90% 之间，代表一个账户通过铸造 scToken 获得的流动性（借款限额）的比例增加。

大型或流动性强的资产往往有较高的抵押品系数；而小型或流动性较差的资产则往往有较低的抵押品系数。如果一项资产的抵押系数为 0，它就不能被用作抵押品（或在强制清算事件中被扣押）。然而，该资产仍然可以被借入。

总之，抵押品系数是你能以某一特定资产进行贷款的最大限度。

**例如：** 如果 fUSDT 的抵押系数为 75%，那么你在其他资产中能够借到的最大 fUSDT 金额（假设存款为 fUSDT 1000）将是 $750.

| 代币   | 抵押系数 | 储备系数 |
| ------ | -------- | -------- |
| wFTM   | 75%      | 11%      |
| SCREAM | 0%       | 20%      |
| fUSDT  | 75%      | 15%      |
| fETH   | 75%      | 10%      |
| wBTC   | 75%      | 10%      |
| SNX    | 0%       | 20%      |
| fBTC   | 75%      | 10%      |
| USDC   | 75%      | 10%      |
| YFI    | 0%       | 20%      |
| FRAX   | 0%       | 20%      |
| BAND   | 0%       | 20%      |
| SUSHI  | 0%       | 20%      |
| CRV    | 0%       | 20%      |
| DAI    | 75%      | 10%      |
| wETH   | 75%      | 10%      |

> **❕注意:** 抵押品系数以及储备系数，可能会根据特定资产的流动性等因素不时调整。
