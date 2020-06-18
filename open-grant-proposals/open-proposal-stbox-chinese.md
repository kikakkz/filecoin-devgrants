# Open Grant Proposal: `StBox - IPFS/FIL上的DropBox`

**Name of Project:** StBox

**Proposal Category:** `app-dev`

**Proposer:** `kikakkz@hotmail.com`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

作为IPFS/FIL项目的技术研究者与社区参与者，我们深感IPFS/FIL发展至今，尽管已经存储了大量数据，并藉由Filecoin主网上线引发
硬件竞赛热潮，却依然止步于具有一定IT技能的小众玩家之间。Filecoin因为确保网络安全而做出的技术选型而导致的硬件与网络条件
的高要求，使得在传统分布式存储战场被寄予厚望的家庭设备，完全失去了参与Filecoin网络的可能性。我们希望能结合过往项目经历
中对于大规模音视频P2P传输、存储网络的开发与实施经验，基于IPFS/FIL开发优质低成本的存储应用StBox。StBox将以便捷的用户界
面，为手机、PC用户提供IPFS上的存储空间。于此同时，StBox允许用户将设备闲置存储空间贡献出来，共同组成能够满足要求的节点，
参与Filecoin网络。最核心处，StBox希望能基于IPFS/FIL提供最便捷的服务，使得普通用户也有机会使用、参与IPFS/FIL网络。

StBox在用户侧将基于IPFS实现两种应用：其一为为用户提供日常数据存储的网盘应用；其二为用户即时拍照上传的存储应用。数据与
照片存储将基于IPFS实现，用户可以使用FIL或法币支付存储空间费用。在网络侧，StBox将设计存储分享界面，用户可以通过该界面，
将本设备的存储资源加入到聚合集群，并从网络获取存储收益。

技术上，StBox将使用喷泉码作为传输信道编码，并在此基础上实现可靠传输协议，该协议使用与喷泉码结合设计的补发BBR拥塞控制算
法。用户上传数据后，在聚合节点将数据做喷泉编码，编码数据将被推送到按照节点质量排序的聚合节点，进行存储。与传统纠删码不
同，喷泉码冗余方式更为高效，每冗余一片数据，都可以为原始数据带来翻倍的数据可靠性提升。由于家庭设备带宽与存储能力有限，
编码数据将被同时推送给多个节点，一方面确保推送效率，另一方面确保数据片更优的区域分布。当设备上的数据需要被使用时，尽管
单台设备能力极其有限，但基于喷泉编码的传输协议，可以支持同时数百条链路的高效传输聚合，喷泉码的块内乱序与冗余传输，可以
保证家庭设备上行带宽充分使用，对于聚合节点，聚合带宽等同于一条数百Ｍ的虚拟链路，可以较好地解决家庭节点网络与存储介质的
不可靠性。

## Value

StBox基于IPFS/FIL提供付费存储服务。如果我们做的事情是对的，并且大部分事情都做对了，StBox能够为IPFS/FIL导入大量有效商业
数据。与此同时，StBox特有的传输协议，将节点能力聚合提供服务，可以帮助IPFS/FIL进入拥有巨大存量的家庭设备。

即使我们做的这件事情没有价值，或者做错了某些事情，由于StBox是一个subnet的方案，其后果只会导致聚合服务节点的抵押被全部
扣除，付费用户因为数据丢失而发生商业纠纷，并不会给IPFS/FIL网络产生任何影响。

StBox及其支撑系统在技术上的难点主要有：
- 我们希望能够同时提供FIL与法币支付渠道，但同时担心FIL价格的波动导致存储成本的波动
- 家庭设备由于上行带宽有限，无法及时为时空证明提供足够的数据，也无法满足检索性能要求
- 家庭网络到聚合节点之间的网络不稳定，导致数据无法及时传输到聚合节点，造成性能瓶颈
- 家庭设备存储介质质量更差，其存储内容也更容易被数据清理软件破坏

## Deliverables

- 一个开源的客户端应用，其中包含
  - iOS，MAC，Windows，Android实现
  - 存储合约生成
  - 数据上传
  - 存储到期监控
  - 账单明细
  - 一键拍照存储
  - 本地存储空间出租
  - 设备登录/登出

- 一个开源的存储节点应用，其中包含
  - Linux，OpenWRT实现
  - 支持节点存储分配
  - 支持节点数据检索

- 一个开源的聚合节点服务，其中包含
  - 节点管理服务
  - 编码服务
  - 推送服务
  - 节点数据检索服务
  - 账单与分成系统
  - 节点聚合传输协议

## Development Roadmap

| Milestone NO. | Milestone Description | People | Roles | Funding | Estimated Timeframe | Output |
|---------------|-----------------------|--------|-------|---------|---------------------|--------|
| 1 | 厘清项目范围，完成业务架构设计 | 2 | Zhao KK: 需求分析与IPFS/FIL在StBox中的应用分析<br>Jin Xuelong: 需求分析与业务架构设计 | $1000 | 2020/8/30 | 需求规格说明书、IPFS/FIL应用白皮书、业务架构设计报告 |
| 2 | 完成未决技术选型与技术架构设计 | 2 | Wang Zhengzhong: 未决技术选型与技术架构设计<br>Zhao KK: 未决技术选型与技术架构设计 | $2000 | 2020/9/20 | 技术调研报告、网络架构设计报告、业务角色交互设计报告 |
| 3 | 完成产品设计 | 2 | Zeng Yuetian: 人机界面原型设计<br>Qiu Junhua: 人机界面原型设计 | $5000 | 2020/9/30 | 产品人机界面原型 |
| 4 | 完成基础喷泉码编解码库Ｃ实现 | 1 | Wang Zhengzhong: 喷泉码编解码库开发与测试 | $8000 | 2020/10/15 | 可供应用开发使用的编解码库、单元测试代码、性能测试代码、应用参考代码、API文档 |
| 5 | 完成喷泉码编解码库在X86和ARM平台的指令集优化 | 1 | Wang Zhengzhong: 喷泉码编解码库指令集优化 | $12000 | 2020/11/15 | 编解码算法在不同体系结构的优化实现、单元测试代码、性能测试代码 |
| 6 | 传输协议设计 | 2 | Zhao KK: 传输协议状态机设计与报文设计<br>Wang Zhengzhong: 传输协议网络模型设计与仿真环境搭建 | $40000 | 2020/11/15 | 网络传输协议研究报告、拥塞算法研究报告、聚合传输协议状态机/报文/拥塞控制/适用场景设计报告 |
| 7 | 传输协议实现 | 5 | Zhao KK: 传输协议库状态机实现<br>Wang Zhengzhong: 传输协议拥塞控制实现<br>Qiu Junhua: 传输协议报文实现<br>Jin Xuelong: 传输协议硬件仿真网络设计与搭建<br>Zhang Tao: 传输协议统计与测试应用实现 | $100000 | 2021/2/15 | 可供应用开发使用的传输协议库、单元测试代码、性能测试代码、参开应用代码、测试报告、API文档 |
| 8 | 应用架构设计与技术选型 | 2 | Wang Zhengzhong: 应用框架技术选型<br>Zhao KK: 应用架构设计 | $1000 | 2021/3/1 | 符合产品设计报告的应用架构设计报告、应用框架分析报告 |
| 9 | 节点存储模型设计 | 1 | Jin Xuelong: 节点存储模型设计 | $2000 | 2021/3/1 | 节点存储模型设计报告 |
| 8 | Linux平台应用实现 | 5 | Zhao KK/Wang Zhengzhong/Qiu Junhua/Zhang Tao: Linux平台应用开发<br>Zeng Yuetian: 测试环境搭建与系统测试 | $50000 | 2021/5/1 | 可以在各种Linux发行版编译运行或安装运行的数据存储/拍照存储/存储出租应用 |
| 9 | Windows平台应用移植 | 2 | Zhang Tao: Windows平台应用移植<br>Zeng Yuetian: 系统测试 | $10000 | 2021/5/20 | 可以在Win 10系统编译运行或安装运行的数据存储/拍照存储/存储出租应用 |
| 10 | Android系统应用实现 | 5 | Zhao KK/Wang Zhengzhong/Qiu Junhua/Zhang Tao: Android系统应用开发<br>Zeng Yuetian: 测试环境搭建与系统测试 | $70000 | 2021/7/1 | 可以在Android 8.0以上版本安装运行的数据存储/拍照存储/存储出租应用 |
| 11 | iOS/Mac系统应用实现 | 5 | Zhao KK/Wang Zhengzhong/Qiu Junhua/Zhang Tao: iOS/Mac系统应用开发<br>Zeng Yuetian: 测试环境搭建与系统测试| $70000 | 2021/10/1 | 可以在iOS/Mac系统安装运行的数据存储/拍照存储/存储出租应用 |
| 12 | Linux/OpenWRT系统聚合存储服务实现 | 4 | Wang Zhengzhong/Zhang Tao: Linux/OpenWRT系统聚合存储服务开发<br>Jin Xuelong: 网络聚合模型验证<br>Zeng Yuetian: 测试环境搭建与系统测试 | $20000 | 2021/11/1 | 可以部署到家用设备节点的聚合存储服务 |

## Total Budget Requested

合计：$391000
| Item | Amount |
|------|--------|
| 开发者工资 |$300000 |
| 调试设备 | $50000 |
| 云服务 | $10000 |
| 应用上线与推广 | $31000 |

## Maintenance and Upgrade Plans

- 2021年7月上线存储服务内测
- 2021年11月上线存储出租服务内测
- 2022年2月正式上线付费存储服务
- 2022年3月正式上线存储出租服务
- StBox将以收费存储服务形式持续维护

# Team

## Team Members

- Zhao KK (Founder / Core Developer)
- Jin Xuelong (Co-Founder / Architect)
- Wang Zhengzhong (Co-Founder / Core Developer)
- Zeng Yuetian (Co-Founder / Test Leader)
- Qiu Junhua (Core Developer)
- Zhang Tao (Core Developer)

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/owen-zhao-489a6815b/
- https://www.linkedin.com/in/%E5%AD%A6%E9%BE%99-%E9%87%91-23b72493/
- https://www.linkedin.com/in/%E6%AD%A3%E4%BB%B2-%E7%8E%8B-47238426/
- https://www.linkedin.com/in/zengyuetian/
-
-

## Team Website

https://stbox.tech

## Relevant Experience

StBox核心团队源于前云熵网络超大规模P2P音视频传输网络研发与实施团队，其工程师都来自于阿里、华为、PPTV、盛大创新院等头部
云计算公司。StBox核心团队在云熵网络研发了基于喷泉码的大规模P2P音视频点播/直播/下载传输架构，在确保视频播放体验的前提下，
帮助视频运营商将分发成本降低到CDN的10%以下。团队基于喷泉码研发的补发BBR可靠传输协议，有效解决不可靠节点之间的存储与传输
可靠性问题，使得使用海量的家庭设备与家庭带宽提供优质可靠的音视频分发能力称为可能。

- Zhao KK：在云熵网络负责P2P音视频网络研发，并与运营商与设备厂商合作将其部署到数以百万记的家用设备
- Jin Xuelong：在云熵网络负责网络架构设计与节点数据分析
- Wang Zhengzhong：前爱立信资深通信工程师，在云熵网络负责可靠协议设计与实现
- Zeng Yuetian：前西门子、Intel资深测试工程师，在云熵网络负责系统与软件测试
- Qiu Junhua：在云熵网络负责可靠协议设计与实现，后在众安科技、同盾人工智能研究院进行AI系统研究
- Zhang Tao：在云熵网络负责系统产品设计与实现，后在NEO进行区块连应用开发、跨链开发

## Team code repositories

Please provide links to your team's prior code repos for similar or related projects.

# Additional Information

N/A
