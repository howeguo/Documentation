
<h1 align="center">为上亿人构建区块链服务</h1>
<p align="center" class="version">给TTC社区的第一封公开信</p>

分布式账本技术，也被称为区块链技术，是近十年来最具影响力的技术领域，它正以前所未见的方式改变着整个互联网世界。虽然是当下最热门的领域，但由于技术本身尚处于初期阶段，区块链技术仍然需要克服很多障碍，以支持大规模的应用服务。

这封公开信旨在分享我们的目标、战略方法以及未来的项目计划。我们同时欢迎开发者加入我们的社区，共同促进区块链技术的发展，我们将持续在技术社区中公开分享我们的想法和理念。

- [背景](#背景)
- [账户系统](#帐户系统)
- [共识机制 (BFT-DPoS)](#共识机制-bft-dpos)
- [智能合约](#智能合约)
- [跨链](#跨链)
- [多维数据存储](#多维数据存储)
- [预言机](#预言机)
- [生态系统工具包](#生态系统工具包)
- [移动区块链服务](#移动区块链服务)
- [反作弊策略](#反作弊策略)
- [结论](#结论)

## 背景

TTC协议是基于去中心化和代币激励的社交网络及在线社区协议，以加快用户增长为目标，为每个TTC生态系统成员提供高效、透明的社交网络服务。我们正在为大规模社交网络平台构建区块链协议，以提升性能、可扩展性、健壮性，并解决移动适配和延迟问题。由于PoW共识机制在处理大吞吐量交易时存在比较明显的效率问题，TTC协议利用BFT-DPoS共识算法来支持具有大用户群的DAPP。

TTC生态系统的结构包括三个层面：持久层、领域层和服务层。持久层包含账户系统、BFT-DPoS共识机制、智能合约等，领域层由基于智能合约的跨链协议组、预言机协议组、数据映射和存储协议组构成，服务层包含了完整的三方协议、API和SDK，测试沙盒及相关组件。此外，TTC生态为开发人员、广告主和其他成员提供了身份接入，整个生态系统实现了信息产生、消费和转移的完整闭环。

## 帐户系统

区块链技术中有两类主流的账户系统：面向资产（比特币UTXO）和面向用户（以太坊）。TTC协议采用面向用户的账户系统，区分外部所有者账户和智能合约账户。与以太坊将一个私钥与一个地址相匹配的机制不同，TTC协议允许一个私钥对应多个地址，并支持地址所有者的权限转移。

TTC生态系统中的DAPP为每个用户创建并分配一个默认帐户用于数据存储和奖励分配，当用户需要绑定到自己账号时，可以向地址所有者（DAPP）发起申请，原地址拥有者用发起地址权限转移操作，将地址权限归还给用户。

## 共识机制 (BFT-DPoS)

共识算法是区块链技术的核心，经过近十年的发展，共识算法从最初的PoW演变为多种形式，如PoS、DPoS、BFT等。每个共识算法都有其优点和缺点，项目需要根据其理念确定最适合的共识算法。

TTC协议在设计之初考虑的核心诉求是如何能支持每天上亿级用户量的社交应用，这些应用需要更高的事务处理能力和更快速的确认速度。

BFT-DPoS是基于DPoS构建的共识算法，实时选出的多个超级节点生产者可以在公平的前提下保证新块的稳定性和效率，在没有多链并行处理或shading处理机制的情况下，单链处理速度可以达到每秒上千笔交易。BFT机制用于提高每笔交易的确认速度。理想情况下确认时间与新块的生成时间相同，进一步提高了整个区块链的执行效率。

## 智能合约

TTC虚拟机（TTVM）是以太坊虚拟机（EVM）的一个增强版本，具备图灵完整性、安全性和高扩展性，TTVM具有以下特点：

- 编译工具，提供全面的安全检查机制

- 支持Python，JavaScript，Solidity，Go等多种语言，以支持更大规模的开发者社区

- 提供更多标准库，提高开发效率

- 提供开发者友好的IDE及在线调试，编译环境

TTVM上运行的智能合约不仅可以灵活访问区块链上的数据，还可以与外部服务和数据模块相结合，实现预言机的机制，大大扩展了智能合约的功能和使用场景。

## 跨链

跨链是当前区块链开发者社区的热门话题之一，最大限度地提高了区块链的可扩展性和连通性。目前主流的跨链技术包括：公证人机制，侧链/中继，哈希锁定和分布式私钥控制。每个协议在交互操作性、信任模型、实现难度方面有所不同。

TTC协议使用分布式私钥控制的跨链机制，以实现多个链之间数字资产的灵活转移，分布式私钥控制能够支持跨链资产转移和抵押、预言机、多代币智能合约，并且能够抵抗“51％攻击”。

现阶段，TTC协议主要实现同构多链之间的跨链操作。在后期阶段，我们将逐步扩展非同构链跨链操作的兼容性。

在TTC生态系统中，我们扩展了跨链的概念，不仅在区块链上实现跨链操作，还实现了数据交换、共享等服务层跨链需求，其实现方式会基于SSO方案和分布式数据交换。

## 多维数据存储

为了满足不同DAPP的数据要求，TTC协议提供了多种数据存储方式及接口协议，构成了多维数据存储框架和相关服务。

对于数字货币、隐私、版权和其他相关数据，TTC协议提供数据存储及可选择的多种加密方式。对于行为数据，可以根据需求和场景选择不同的存储方法，如分布式存储结构TTFS，同时在TTC协议上创建对应数据的映射关系。

TTC生态系统中所保存的数据具有明确的所有权属性，可以根据特定的业务场景进行共享、转移等操作。例如，广告主可以在TTC生态中构建智能合约，请求获取用户的信息以获取更好的投放策略，如果用户做出响应，存储在区块链中的相关信息将首先解密，然后使用广告主的公钥加密，通过相关合约共享给DAPP。

## 预言机

TTC协议支持区块链预言机机制，DAPP通过智能合约与外部可信接口和数据进行交互。预言机是一种可信的实体，使用签名将不确定的外部世界状态的信息提供给智能合约。智能合约可以访问由预言机签名验证的本地数据，而无需从第三方接口拉取数据，从而确保访问效率和价格一致性。

TTC生态系统支持多节点预言机解决方案，以确保其可靠性、稳定性和去中心化特性。只有当一半的节点数据一致时，才会向区块链发起携带外部数据备注的交易。由于采用BFT-DPoS共识机制，预言机的实际交易确认时长通常等同于一个区块的生成时长。

## 生态系统工具包

TTC生态系统在TTC协议基础上，为不同角色的成员提供了许多特性和工具包。

1) DAPP开发者：可以从开发者社区获取一套完整的TTC测试链和相应的云存储资源，以及详细的文档、用例、多平台跨语言SDK和API。开发者不需要部署服务器，即可直接使用测试链进行开发和调试。接入完成后，只需更换相关地址和应用地址和密钥，即可将DAPP连接到主链。

2) DAPP运营人员：可以通过可视化的图表了解平台用户的统计数据，并实时知晓DAPP用户获取的货币数量。

3) 广告主：不仅可以实时获得广告价值，还可以根据用户授权的行为数据优化投放策略。

4) DAPP用户：通过统一登录权限机制（SSO）可以访问TTC生态系统中的所有DAPP，并通用统一的钱包控制所有的数字资产，进行跨链的资产转移。此外，用户可以使用同一个帐户对不同DAPP之间的信息进行共享、转移等操作，用户可以很容易从多个DAPP获得代币奖励，并无缝地提取这些代币。

## 移动区块链服务

现阶段，大多数主流的服务/平台都是以移动端为中心，但受限于操作性、稳定性、连接性等问题，目前的区块链技术在移动应用程序上的应用十分有限，导致区块链服务尚未被广大互联网用户所接受。TTC协议采用双边授权方案确保移动服务在区块链技术上稳定运行。

## 反作弊策略

TTC生态系统为了给接入的DAPP创造一个公平的环境，搭建并实施了一套多维度反作弊策略。

TTC协议采用多点检测的方式验证DAPP中收益相关行为的真实性，当用户行为被触发时，移动客户端调用SDK通过对应的智能合约记录事件，当服务器获取该操作并录入数据库时，通过相应的API接口，触发对应智能合约进行验证。

同时，TTC协议根据区块链记录的用户行为采用机器学习算法判断行为真实性，通过区块链预言机机制反映到区块链中，影响价值分配计算等业务操作。

## 结论

在我们的理念中，区块链技术有潜力通过明确透明的代币经济，真正实现社区内的社会协作。我们相信每个人的贡献都会让世界变得更美好，这种想法也反映在项目“git.eco”上，这是一个为开发人员提供代币激励的协作社区。参与者通过贡献代码、创建问题、合并代码分支、审查代码等方式获得奖励。

虽然区块链技术在很多方面还需要发展和完善，但我们对区块链世界的未来非常乐观。我们欢迎持有相同想法的开发者共同合作发展区块链技术，创造更美好的未来。

TTC协议

主页：http://www.ttc.eco/

Telegram（英文）：http://t.me/ttc_en

Telegram（韩国）：http://t.me/ttc_kr

邮件：official@ttc.eco
