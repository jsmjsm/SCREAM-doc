# ScLoans
> 面向 Screamers 的闪电贷

SCREAM 已经将 **ScLoans** 纳入其 Fantom 货币市场。

ScLoans 是开发人员的工具，提供了获得低抵押贷款的机会，待借款金额（和费用）在网络上一个交易区块内返回。

ScLoans 将提供广泛的使用案例，包括套利和抵押品互换机会，以及利率互换。

ScLoans 源于 Aave Flash Loans，只不过 ScLoans 是在Scream 的借贷代币 scToken 上实现的。

1. 开发人员可以直接与 scToken 互动，而不是与贷款池互动。为了执行 ScLoan，用户必须知道 scToken 的具体资产地址。
2. 当回调函数 `executeOperation` 被调用时，有一个额外的参数 `initiator` 。发起者是调用 ScLoan 数的 `msg.sender` 。
3. 费用为 0.02%。

## 可用资产列表
| NO  | ASSET CONFIRM | CONFIRM ADDRESS |
| --- | ------------- | --------------- |
| No  | TBC           | TBC             |

[合约地址](/resources/Contract-Address.md)

**❕提醒：** 可用的资产清单和相关合同地址将在推出后在此更新。
