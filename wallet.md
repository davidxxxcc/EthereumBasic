[https://dbarobin.com/2018/01/31/blockchain-graphene/](https://dbarobin.com/2018/01/31/blockchain-graphene/)



石墨烯是区块链工具组，由 **Cryptonomex **公司开发，GitHub 项目地址：

[https://github.com/cryptonomex/graphene](https://github.com/cryptonomex/graphene)

，采用 C++ 编写，丹尼尔 • 拉里默（Dan Larimer）是 Cryptonomex 的创始人，而他的父亲斯坦•拉里默（Stan Larimer）是 Cryptonomex 的主席。Cryptonomex 基本上都是在石墨烯区块链库基础上做开发的，石墨烯区块链库已经被多个区块链所采纳，比如 BitShares，Muse，Identabit，Play 等。\[1\] 与大多数数字货币类似，Graphene \(石墨烯\) 使用区块链来记录参与者的转账信息及市场行为。由于每个区块总是指向前一个区块，因此一个区块链条包含了所有在网络上发生的交易信息。区块链是一个公开的、可审计的账簿，每个人都能够查看详细数据，并验证交易、市场订单和买卖盘数据。

第一是**转账速度特别快**。现在的平均确认时间是 1.5 秒，出块时间是 3 秒，在石墨烯进一步进化的 EOS 上可能到了零点几秒，所有的延迟仅仅只是来源于网络，而不是处理本身，所以它的性能是非常强大的。我们对比一下：比特币是 10 分钟出块，以太坊大约是 1 分钟；确认时间上比特币是 1 小时，以太坊是十几分钟，石墨烯只需要秒级的时间。

第二是**吞吐量比较高**。石墨烯的吞吐量现在实测大约是 3300 笔每秒，理论上可以到 10 万次，甚至可以扩展到百万次，比如按照 EOS 的规划就可以达到百万次。对比一下：比特币大约每秒七笔，以太坊每秒三四十笔，这完全不是一个数量级。在真正解决实际问题时，很明显每秒几笔是不符合要求的，那每秒 3000 多笔基本上已经赶上了 VISA 的处理能力，已经算一个工业级的区块链产品。

第三是**石墨烯极其稳定**。石墨烯技术开发运行了这么久，从来没有出过明显的 BUG，也没有资产被盗的情况。

第四是**功能非常强大、完备、容易操作**。如果我们用过一些桌面端的钱包就会发现，比特股钱包的应用性是最强的。以多重签名来举例：比特币也有多重签名，但是比较复杂，而且功能特别简单，只有 M/N 这种模式，就是说如果是 5 个人做多重签名，3 个人同意就可以通过，这是一个很简单的多重签名。石墨烯上的多重签名功能是可以用作公司治理的，它可以设定两个参数：首先它可以设置百分比，每个人占多少百分比，无论多少人都可以随便设。第二个是阈值，就是超过多少个签名就可以生效。假设说现在想做一个 7 个人的理事会管理，有这样一些要求：任何 2 个人出事都不能影响资金的使用；至少 3 个人同意才可以动用资金；非核心成员至少 4 个人同意才能动用资金。这些条件设置好之后，可以很快的算出每个人的占比，这个多签就设置完成了，而且这是在 UI 上直接实现，在操作界面上的，而不是用命令行来实现的。

