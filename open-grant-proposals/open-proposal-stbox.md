# Open Grant Proposal: `StBox - Storage application based on IPFS/FIL`

**Name of Project:** StBox

**Proposal Category:** `app-dev`

**Proposer:** `kikakkz@hotmail.com`

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

As Filecoin mainnet is coming soon, a lot of developers are focusing on mining optimization and involving in continuous hardware upgrading competition. The miner entry threshold is very high, home devices cannot provide large latent storage space or high speed bandwidth to join IPFS/Filecoin network. Therefore, Filecoin community is exclusive to IT developers and big data storage providers at this moment. But the key of adding value of a network and bringing greater benefit of the whole community is to achieve mass adoption and to expand IPFS/FIL ecosystem. StBox is committed to improve the infrastructure of IPFS/FIL network by providing convenient and user-friendly application to include home devices joining IPFS/Filecoin network and to encourage more people to use IPFS/FIL network on a daily basis.

Our team is experience in the development and implementation of large-scale audio and video Peer-to-Peer network. After conducting deep research on IPFS & Filecoin network, we plan to build StBox, a user-friendly application to help IPFS & Filecoin network to achieve massive adoption quickly. Stbox is a cross-platform Dropbox alternative application, which enables everyone store his data on IPFS network easily. Moreover, Stbox makes every home device be able to provide its latent storage space to IPFS network and earn Filecoin block rewards accordingly. StBox is a Dropbox alternative on IPFS network, it allows users to upload their photos and data to IPFS network instantly. Users can pay FIL token or fiat currency for using IPFS storage space. Moverover, StBox will build an aggregate cluster and develop a storage space sharing interface in this application. Users can join the aggregate cluster and contribute latent storage space of their home devices to IPFS network though StBox and earn FIL block rewards accordingly.

Technically, StBox will adopt Fountain codes as the channel code and build a reliable transport protocol to ensure high quality data transport. This protocol combines Supplementary BBR Congestion Control Algorithm with Fountain codes to enhance the efficiency of data transport. Once Stbox gets a storage deal from IPFS/Filecoin network, it will encode receiving data and send them to home devices aggregate cluster. All the home devices within one aggregate cluster is sorted by their storage quality. The higher its storage quality is, the better chance a home device receives new storage task. After applying Fountain codes，the existence of every piece of redundant data can double the reliability of the original data. There are limited storage capacity and bandwidth of home devices, so the encoded data will be sent to multiple home devices at the same time. When receiving data retrieval request, Stbox’s Fountain codes based transport protocol can simultaneously retrieve data from hundreds of home devices within its aggregate cluster in the most efficient manner. This transport protocol turns hundreds of home devices with limited storage capacity into a powerful storage array. Moreover, Fountain code’s rateless feature results in massive savings on the number of storage units for a given level of redundancy and reliability. StBox’s special data transport protocol will fully use each home device’s upstream bandwidth and combine them to hundreds of Mbps high speed virtual link to connect home devices to Filecoin/IPFS network, in this way, many home devices with limited storage capacity and bandwidth can join Filecoin/IPFS network easily.

## Value

Stbox provide paid storage service based on IPFS/Filecoin network. If this project works out as we planned, Stbox will bring many home devices into IPFS/Filecoin network and enable individual clients to use IPFS/Filecoin storage easily, which accelerates the process of IPFS network to achieve massive adoption. Moreover, Stbox will provide paid storage service to enterprise clients when the project develops to mature stage, which will bring a lot of valuable business data to IPFS network.

Stbox has an aggregate node in IPFS/Filecoin network. There will be a lot of home devices within Stbox’s umbrella. If our transport protocol doesn’t work well or any home device loses data, the collaterals Stbox pledged for the home devices will be lost. That’s the risk our team have to bear. If paid enterprise clients lost their business data, we might have legal issues. But overall, the potential risk of our project is under control and much less than its benefits.  Even the project fails, it won’t bring negative effects to IPFS/Filecoin network.

When we executing our project, we may face the following problems and risks
- Stbox paid service will accept both Filecoin and Fiat currency payments from users, the high volatility of cryptocurrency will result in the fluctuation of storage service price and may cause some difficulties in practice.

## Deliverables

- An Open Source Client Application
  - Cross platform, IOS/MAC/Windows/Android
  - Storage order
  - Data uploading
  - Monitor system for data storage expiration
  - Billing system
  - Instant photo storage service
  - Home device storage space rental service
  - Device ID Login/Logout
- An Open Source Storage Service
  - Run on Linux and OpenWrt
  - Sub node data storage space management
  - Sub node data retrieval
- An Open Source Sub Node Management Service
  - Sub node management service
  - Encoding Service
  - Data pushing service
  - Sub node data retrieval service
  - Billing system and reward distribution system
  - Multipath transportation protocol

## Development Roadmap

Please break up your development work into a clear set of milestones. This section needs to be very detailed (will vary on the project, but aim for around 2 pages for this section).

For each milestone, please describe:
- The software functionality that we can expect after the completion of each milestone. This should be detailed enough that it can be used to ensure that the software meets the specification you outlined in the Deliverables.
- How many people will be working on each milestone and their roles
- The amount of funding required for each milestone
- How much time this milestone will take to achieve (using real dates)

| Milestone NO. | Milestone Description | People | Roles | Funding | Estimated Timeframe | Output |
|---------------|-----------------------|--------|-------|---------|---------------------|--------|
| 1 | Clarify the scope of this project and design business architecture | 2 | Zhao KK: Requirement analysis and analysis on how to combine Stbox project with Filecoin/IPFS network in technical level<br>Jin Xuelong: Requirement analysis and business architecture design | $1000 | 2020/8/30 | 1) Requirement Specification; <br>2) StBox Whitepaper; <br>3) Application Business Architecture Report. |
| 2 |
| 3 |
| 4 |
| 5 |
| 6 |
| 7 |
| 8 |
| 9 |
| 10 |
| 11 |
| 12 |
| 13 |
| 14 |

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
