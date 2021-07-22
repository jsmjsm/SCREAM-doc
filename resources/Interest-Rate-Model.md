# 利率模型
> SCREAM 上的 APY 是如何计算的

## 借贷 APY
借款资产的利率模型可以用以下公式来计算：

```
= Base + Multiplier * min(UtilizationRate, Kink) + max(JumpMultiplier * UtilizationRate - Kink, 0)
```


## 供应资金 APY

供应资产的利率模型可以用以下公式来计算：

```
= Distribute (Interest Paid by Borrowers Per Block - Reserve) to all suppliers, and convert it into APY

= Distribute [(1 + Borrow APY) ^ (1 / BlocksPerYear) - 1] * Total Borrow * (1 - Reserve Factor) to all suppliers, and convert it into APY

= {[(1 + Borrow APY) ^ (1 / BlocksPerYear) - 1] * Total Borrow * (1 - Reserve Factor) / Total Supply}, and convert it into APY

= {1 + [(1 + Borrow APY) ^ (1/BlocksPerYear) - 1] * Total Borrow * (1 - Reserve Factor) / Total Supply} ^ BlocksPerYear - 1
```
