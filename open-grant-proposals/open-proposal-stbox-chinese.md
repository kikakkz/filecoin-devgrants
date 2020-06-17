# Open Grant Proposal: `StBox - IPFS/FIL上的DropBox`

**Name of Project:** StBox

**Proposal Category:** `app-dev`

**Proposer:** `kikakkz@hotmail.com`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** "Yes"

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

StBox基于IPFS/FIL提供付费存储服务。运行良好的情况下，StBox能够为IPFS/FIL导入大量有效商业数据。与此同时，StBox特有的传输
协议，将节点能力聚合提供服务，可以帮助IPFS/FIL进入拥有巨大存量的家庭设备。最坏的情况下，StBox因为传输协议与冗余机制设计
不完善导致付费用户数据丢失，引发纠纷。

StBox及其支撑系统在技术上的难点主要有：
１　我们希望能够同时提供FIL与法币支付渠道，但同时担心FIL价格的波动导致存储成本的波动
２　家庭设备由于上行带宽有限，无法及时为时空证明提供足够的数据，也无法满足检索性能要求
３　家庭网络到聚合节点之间的网络不稳定，导致数据无法及时传输到聚合节点，造成性能瓶颈
４　家庭设备存储介质质量更差，其存储内容也更容易被数据清理软件破坏

## Deliverables

一个开源的客户端付费应用，其中包含
- iOS，MAC，Windows，Android实现
- 存储合约生成
- 数据上传
- 存储到期监控
- 账单明细
- 一键拍照存储
- 本地存储空间出租
- 设备登录/登出

一个开源的存储节点应用，其中包含
- Linux，OpenWRT实现
- 支持节点存储分配
- 支持节点数据检索

一个开源的聚合节点服务，其中包含
- 节点管理服务
- 编码服务
- 推送服务
- 节点数据检索服务
- 账单与分成系统

## Development Roadmap

Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section).

For each milestone, please describe:
- The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables.
- How many people will be working on each milestone and their roles
- The amount of funding required for each milestone
- How much time this milestone will take to achieve (using real dates)

## Total Budget Requested

Sum up the total requested budget across all milestones, and include that figure here. Also, please include a budget breakdown to specify how you are planning to spend these funds.

## Maintenance and Upgrade Plans

Specify your team's long-term plans to maintain this software and upgrade it over time.

# Team

## Team Members

- Team Member 1
- Team Member 2
- Team Member 3
- ...

## Team Member LinkedIn Profiles

- Team Member 1 LinkedIn profile
- Team Member 2 LinkedIn profile
- Team Member 3 LinkedIn profile
- ...

## Team Website

Please link to your team's website here (make sure it's `https`)

## Relevant Experience

Please describe (in words) your team's relevant experience, and why you think you are the right team to build this project. You can cite your team's prior experience in similar domains, doing similar dev work, individual team members' backgrounds, etc.

## Team code repositories

Please provide links to your team's prior code repos for similar or related projects.

# Additional Information

Please include any additional information that you think would be useful in helping us to evaluate your proposal.
