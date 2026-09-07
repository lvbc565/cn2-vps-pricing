# CN2 VPS购买：先搞清线路差别再下单，附搬瓦工全套餐价格与选购建议

很多人在搜 CN2 VPS 的时候，其实并不太清楚自己到底在买什么。光是"CN2"这两个字母背后，就藏着 GT、GIA、GIA-E、CTGNet 几种不同线路，价格差出好几倍，晚高峰表现也完全不一样。买贵了肉疼，买便宜了晚高峰卡到怀疑人生，这两种情况都不想遇到。

这篇文章就把 CN2 VPS 购买这件事拆开讲清楚：几种 CN2 线路到底差在哪、搬瓦工（BandwagonHost）现在在售的 CN2 套餐有哪些、每个套餐多少钱、什么配置、什么场景该选哪个。信息全部来自搬瓦工官网当前公开的产品数据，价格和配置都是实抓的，不是凭印象写的。

## CN2 到底是什么，为什么比普通线路贵

先说最基础的概念。中国电信对外提供的数据传输线路有好几档，从便宜到贵大致是这样：

**AS4134（ChinaNet / 163 网）** 是最普通的骨干网，绝大多数海外 VPS 默认走这条。便宜、容量大、能扛 DDoS，但晚高峰拥堵严重，丢包率有时能冲到 30% 以上。你租个几十块钱一年的廉价 VPS，访问国内卡得看不了视频，多半就是走这条线。

**AS4809 CN2 GT（Global Transit）** 是中间档，本来是为了缓解 163 拥堵推出的，但搬瓦工官网自己的说法是"自 2019 年起已经和 163 差不多拥堵了"。比 163 贵，体验却没拉开差距，性价比比较尴尬。

**AS4809 CN2 GIA（Global Internet Access）** 是目前对中国大陆方向最稳的线路。去程回程都走电信 CN2 高端路由，省级节点全程 59.43 开头，晚高峰丢包低、延迟稳。搬瓦工官网原文直接写："it is very stable"——这是他们自己给的评价。缺点也很直白：贵。CN2 GIA 的 IP transit 价格可以高到 $120/Mbps，1Gbps 满带宽跑一个月，账单能到十万美金级别。这也是为什么香港、东京这种纯 CN2 GIA 机房套餐价格动辄月付 $89.99 起。

**AS23764 CTGNet** 是电信新加的一档，搬瓦工官网说它在性能和定价上"基本等同于 CN2 GIA"，目前洛杉矶 DC9 等机房已经接入。

还有一个搬瓦工特有的概念叫 **CN2 GIA-E**，也就是 E-Commerce（电商版）套餐走的线路。它本质上是 CN2 GIA 的优化版本，带宽更大（最低 2.5Gbps，顶配 10Gbps），同时接入 CN2 GIA、CMIN2（中国移动精品线）、China Unicom Premium（联通精品线）三网优化，机房多、可互相迁移。对大多数用户来说，CN2 GIA-E 是"花得最值"的那一档。

## 搬瓦工 CN2 VPS 套餐体系：三个层级，定位完全不同

搬瓦工目前把 VPS 产品分成三大 tier，从官网产品接口可以直接看到：

- **Basic VPS**：基础线路，1Gbps 带宽，部分机房有本地 peering，但**不保证 CN2**。最便宜，适合预算优先、对国内访问质量要求不高的场景。
- **E-Commerce VPS（CN2 GIA-E）**：核心卖点是 CN2 GIA-E 线路 + 三网优化，2.5–10Gbps 大带宽，支持在洛杉矶 DC6/DC9、纽约、阿姆斯特丹、迪拜、东京等 15 个机房之间免费迁移。这是大多数人买 CN2 VPS 时真正应该看的档位。
- **Ultra VPS（纯 CN2 GIA）**：香港、东京、大阪、新加坡四个机房，走纯 CN2 GIA，延迟最低，但价格最高，且不能跨机房迁移。

理解这个分层很重要，因为同样是"搬瓦工 CN2 VPS"，年付 $49.99 的 Basic 和年付 $169.99 的 E-Commerce，体验完全是两个世界。

## 全套餐价格与配置对比

下面这张表覆盖搬瓦工官网当前在售的 CN2 相关套餐。Basic 系列虽然不走 CN2，但作为价格参照也一并列入，方便对比。

### Basic VPS（非 CN2 基础线路）

| 套餐 | CPU | 内存 | SSD | 月流量 | 带宽 | 价格 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 20G KVM PROMO | 2核 | 1GB | 20GB | 1TB | 1Gbps | $49.99/年 | [前往购买](https://bit.ly/BandWaGon) |
| 40G KVM PROMO | 3核 | 2GB | 40GB | 2TB | 1Gbps | $52.99/半年 或 $99.99/年 | [前往购买](https://bit.ly/BandWaGon) |
| 80G KVM PROMO | 4核 | 4GB | 80GB | 3TB | 1Gbps | $19.99/月 起 | [前往购买](https://bit.ly/BandWaGon) |
| 160G KVM PROMO | 5核 | 8GB | 160GB | 4TB | 1Gbps | $39.99/月 起 | [前往购买](https://bit.ly/BandWaGon) |
| 320G KVM PROMO | 6核 | 16GB | 320GB | 5TB | 1Gbps | $79.99/月 起 | [前往购买](https://bit.ly/BandWaGon) |
| 480G KVM PROMO | 7核 | 24GB | 480GB | 6TB | 1Gbps | $119.99/月 起 | [前往购买](https://bit.ly/BandWaGon) |

### E-Commerce VPS（CN2 GIA-E，三网优化，可跨 15 机房迁移）

| 套餐 | CPU | 内存 | SSD | 月流量 | 带宽 | 起步价格 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 20G CN2 GIA-E | 2核 | 1GB | 20GB | 1TB | 2.5Gbps | $49.99/季，$169.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| 40G CN2 GIA-E | 3核 | 2GB | 40GB | 2TB | 2.5Gbps | $89.99/季，$299.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| 80G CN2 GIA-E | 4核 | 4GB | 80GB | 3TB | 2.5Gbps | $56.99/月，$549.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| 160G CN2 GIA-E | 6核 | 8GB | 160GB | 5TB | 5Gbps | $86.99/月，$879.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| 320G CN2 GIA-E | 8核 | 16GB | 320GB | 8TB | 5Gbps | $159.99/月，$1599.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| 640G CN2 GIA-E | 10核 | 32GB | 640GB | 10TB | 10Gbps | $289.99/月，$2759.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| 1280G CN2 GIA-E | 12核 | 64GB | 1280GB | 12TB | 10Gbps | $549.99/月，$5499.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| 1280G HIBW 15T | 12核 | 64GB | 1280GB | 15TB | 10Gbps | $679/月 起 | [查看套餐](https://bit.ly/BandWaGon) |
| 1280G HIBW 20T | 12核 | 64GB | 1280GB | 20TB | 10Gbps | $899/月 起 | [查看套餐](https://bit.ly/BandWaGon) |

E-Commerce 系列可选机房包括：洛杉矶 DC6（CN2 GIA-E）、DC9（CN2 GIA）、DC2、纽约 USNY_6/USNY_8、阿姆斯特丹 EUNL_1/EUNL_2/EUNL_9、迪拜 AEDXB_1、东京 JPTY_1、温哥华 CABC_6、圣何塞 USCA_SJC5 等，购买后可在 KiwiVM 后台免费迁移。

### Ultra VPS — 香港 CN2 GIA

| 套餐 | CPU | 内存 | SSD | 月流量 | 带宽 | 起步价格 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| HK 40G | 2核 | 2GB | 40GB | 500GB | 1Gbps | $89.99/月，$899.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| HK 80G | 4核 | 4GB | 80GB | 1TB | 1Gbps | $155.99/月，$1559.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| HK 160G | 6核 | 8GB | 160GB | 2TB | 1Gbps | $299.99/月，$2999.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| HK 320G | 8核 | 16GB | 320GB | 4TB | 1Gbps | $589.99/月，$5899.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| HK 640G | 10核 | 32GB | 640GB | 6TB | 1Gbps | $989.99/月，$9989.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| HK 1280G | 12核 | 64GB | 1280GB | 8TB | 1Gbps | $1889.99/月，$18989.99/年 | [查看套餐](https://bit.ly/BandWaGon) |

### Ultra VPS — 东京 CN2 GIA（带宽 1.2Gbps）

| 套餐 | CPU | 内存 | SSD | 月流量 | 带宽 | 起步价格 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TOKYO 40G | 2核 | 2GB | 40GB | 500GB | 1.2Gbps | $89.99/月，$899.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| TOKYO 80G | 4核 | 4GB | 80GB | 1TB | 1.2Gbps | $155.99/月，$1559.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| TOKYO 160G | 6核 | 8GB | 160GB | 2TB | 1.2Gbps | $299.99/月，$2999.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| TOKYO 320G | 8核 | 16GB | 320GB | 4TB | 1.2Gbps | $589.99/月，$5899.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| TOKYO 640G | 10核 | 32GB | 640GB | 6TB | 1.2Gbps | $989.99/月，$9989.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| TOKYO 1280G | 12核 | 64GB | 1280GB | 8TB | 1.2Gbps | $1889.99/月，$18989.99/年 | [查看套餐](https://bit.ly/BandWaGon) |

### Ultra VPS — 大阪 CN2 GIA（带宽 1.5Gbps）

| 套餐 | CPU | 内存 | SSD | 月流量 | 带宽 | 起步价格 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| OSAKA 40G | 2核 | 2GB | 40GB | 500GB | 1.5Gbps | $49.99/月，$499.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| OSAKA 80G | 4核 | 4GB | 80GB | 1TB | 1.5Gbps | $86.99/月，$869.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| OSAKA 160G | 6核 | 8GB | 160GB | 2TB | 1.5Gbps | $165.99/月，$1665.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| OSAKA 320G | 8核 | 16GB | 320GB | 4TB | 1.5Gbps | $329.99/月，$3199.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| OSAKA 640G | 10核 | 32GB | 640GB | 6TB | 1.5Gbps | $549.99/月，$5549.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| OSAKA 1280G | 12核 | 64GB | 1280GB | 8TB | 1.5Gbps | $1059.99/月，$10559.99/年 | [查看套餐](https://bit.ly/BandWaGon) |

### Ultra VPS — 新加坡 CN2 GIA（带宽 1.5Gbps）

| 套餐 | CPU | 内存 | SSD | 月流量 | 带宽 | 起步价格 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| SINGAPORE 40G | 2核 | 2GB | 40GB | 500GB | 1.5Gbps | $49.99/月，$499.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| SINGAPORE 80G | 4核 | 4GB | 80GB | 1TB | 1.5Gbps | $86.99/月，$869.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| SINGAPORE 160G | 6核 | 8GB | 160GB | 2TB | 1.5Gbps | $165.99/月，$1665.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| SINGAPORE 320G | 8核 | 16GB | 320GB | 4TB | 1.5Gbps | $329.99/月，$3199.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| SINGAPORE 640G | 10核 | 32GB | 640GB | 6TB | 1.5Gbps | $549.99/月，$5549.99/年 | [查看套餐](https://bit.ly/BandWaGon) |
| SINGAPORE 1280G | 12核 | 64GB | 1280GB | 8TB | 1.5Gbps | $1059.99/月，$10559.99/年 | [查看套餐](https://bit.ly/BandWaGon) |

> 注意：香港、东京、大阪、新加坡这四档 Ultra 套餐走的是纯 CN2 GIA，延迟最低，但**不能跨机房迁移**，买之前想清楚要去哪个机房。

## 不同场景怎么选

**个人自用、科学上网、轻量建站**

直接看 E-Commerce 20G CN2 GIA-E，$49.99/季度起步，年付 $169.99。2核 1GB、20GB SSD、1TB 月流量、2.5Gbps 带宽，跑个博客、SSH 跳板、个人代理完全够用。这是搬瓦工目前卖得最好的 CN2 GIA-E 套餐，性价比最高，机房还能来回切。

如果预算更紧，只是偶尔用用、对晚高峰要求没那么极端，Basic 20G 年付 $49.99 也能凑合，但要心里有数：它不走 CN2 GIA，晚高峰体验和 E-Commerce 不是一回事。

**中等流量、跑多个站点、小团队**

E-Commerce 80G（$56.99/月）或 160G（$86.99/月）比较合适。80G 给到 4核 4GB、3TB 流量、2.5Gbps；160G 升到 6核 8GB、5TB 流量、5Gbps 带宽，跑几个 WordPress 站点或者中等并发业务都够。

**外贸企业站、对稳定性要求高**

搬瓦工还有一个 E-Commerce SLA 系列，机房在洛杉矶 USCA_5，提供 99.99% 服务等级协议，配置比普通 E-Commerce 更高（AMD 独享 CPU、NVMe RAID-10），适合不能接受掉线的生产业务。不过这个系列属于补货性质，不一定长期有货，需要的时候去 👉 [查看套餐](https://bit.ly/BandWaGon) 看是否在售。

**追求最低延迟、不差钱**

香港 CN2 GIA 到大陆延迟通常 30–60ms，是搬瓦工延迟最低的机房，月付 $89.99 起。东京 CN2 GIA 延迟和香港接近，带宽略大（1.2Gbps），价格一样。如果对延迟敏感但对预算没那么敏感，这两档是上限。

大阪和新加坡 CN2 GIA 价格便宜不少（$49.99/月起），带宽 1.5Gbps 反而更大，延迟比香港略高但比洛杉矶低。对东南亚或日韩方向业务，这两个机房是性价比之选。

## 购买流程和优惠码

搬瓦工购买流程不算复杂，但有几个点值得提前知道：

1. **注册账号**：用邮箱注册，支持支付宝、PayPal、信用卡、银联等多种支付方式，对国内用户友好。
2. **选套餐 + 选机房**：E-Commerce 系列购买时可以先选一个机房，后续在 KiwiVM 面板里免费迁移到其他可用机房，数据不丢。Ultra 系列则绑定机房，不能迁。
3. **填优惠码**：结账页面有 Promotional Code 输入框，填进去点 Validate Code 验证。
4. **支付 + 开通**：付款后一般几分钟内自动开通，KiwiVM 后台直接管理，支持重装系统、快照、rDNS、流量监控等。

关于优惠码，目前多个来源交叉确认仍然可用的是 **BWHCGLUKKB**，全场循环折扣 6.77%，新购和续费都适用。所谓"循环"是指每个计费周期续费时折扣都生效，不是只首单优惠。用了之后 E-Commerce 20G 季付从 $49.99 降到约 $46.59。

搬瓦工每年双十一、黑周五、新年会放出力度更大的临时优惠码（历史上有过 11%、12.22% 循环折扣），想省钱可以蹲这几个节点。平时如果不赶时间，结账时把 BWHCGLUKKB 填上验证一下，能省一点是一点。

👉 [使用优惠码前往购买](https://bit.ly/BandWaGon)

## 几个常见问题

**CN2 GIA-E 和纯 CN2 GIA 到底哪个好？**

严格说，纯 CN2 GIA（香港/东京/大阪/新加坡 Ultra 套餐）延迟更低、线路更纯粹，但价格贵、不能迁移机房、带宽上限低（1–1.5Gbps）。CN2 GIA-E 是电商优化版，接入三网精品线路，带宽大得多（2.5–10Gbps），机房多可迁移，价格便宜一半以上。对绝大多数用户，CN2 GIA-E 是更实际的选择；只有当你对延迟有近乎苛刻的要求、并且预算充裕时，纯 CN2 GIA 才值得考虑。

**搬瓦工的 CN2 VPS 晚高峰稳吗？**

根据搬瓦工官网自己的描述，CN2 GIA 是他们"观察到问题最少的网络，非常稳定"。E-Commerce 系列的 DC9 机房同时接入 CN2 GIA、CMIN2、China Unicom Premium 三网优化，晚高峰表现比只走单一线路的方案更抗拥堵。需要注意的是，CN2 GIA 容量有限，搬瓦工官网明确说它"不抗 DDoS，遇到攻击只能 nullroute"，如果你的业务容易招攻击，这点要考虑进去。

**买了之后能换机房吗？**

E-Commerce 系列可以在 15 个机房之间免费迁移，数据不丢，在 KiwiVM 后台操作。Ultra 系列（香港/东京/大阪/新加坡）不行，买的是哪个机房就锁死哪个。

**流量超了怎么办？**

搬瓦工按月流量计费，超量后可以购买流量包，或者等待下个计费周期自动恢复。KiwiVM 后台有实时流量监控，建议盯着点，尤其是跑大文件下载或视频业务的场景。

**支持哪些系统？**

KVM 虚拟化，支持 AlmaLinux、RockyLinux、CentOS、Debian、Ubuntu、CentOS Stream、Fedora，还可以挂载自定义 ISO，提需求的话官方会帮忙添加镜像。

## 选购建议小结

如果你看完前面还是不太确定该买哪个，这里给一个更直接的判断：

- **预算 $50/年以内**、能用就行：Basic 20G，但别期待晚高峰表现。
- **预算 $50/季度左右**、想要稳定 CN2 体验：E-Commerce 20G CN2 GIA-E，这是大多数人的最佳起点。
- **预算 $60–90/月**、跑正经业务：E-Commerce 80G 或 160G，带宽和配置都够用。
- **要最低延迟、不在乎价格**：香港或东京 CN2 GIA，$89.99/月起。
- **东南亚方向业务**：新加坡 CN2 GIA，$49.99/月起，比香港便宜一半。

CN2 VPS 购买这件事，核心就是把"线路"和"需求"对上号。同样写"CN2"，背后可能是 GT、GIA、GIA-E 三种完全不同的东西，价格和体验差出一大截。弄清楚自己到底需要哪种，再回头看套餐表格，选择会清楚很多。

👉 [进入搬瓦工查看全部 CN2 VPS 套餐](https://bit.ly/BandWaGon)
