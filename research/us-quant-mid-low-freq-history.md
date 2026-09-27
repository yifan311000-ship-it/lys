# 美国量化投资发展史：以中低频策略为主线

> 研究范围：美国量化投资从理论萌芽（1900s）到当下（2026）的演进，重点是**中低频**策略，即持仓周期在数天到数月、以日频或更低频数据为主、靠"信号质量 + 组合构建 + 风险控制"而不是"速度"赚钱的策略。高频交易（HFT）、做市只作为背景出现。
>
> 说明：文中数字（规模、收益、回撤）多为公开报道或学术文献中的近似值，用来说明量级，不能当作精确数据引用。标"据报道"的内容，建议使用前再找原始来源核对。

---

## 目录

1. [什么是"中低频量化"](#1-什么是中低频量化)
2. [总览：六个阶段](#2-总览六个阶段)
3. [第一阶段（1900–1970）：理论奠基](#3-第一阶段19001970理论奠基)
4. [第二阶段（1970–1990）：从学术走向实践](#4-第二阶段19701990从学术走向实践)
5. [第三阶段（1990–2007）：因子模型与量化机构化](#5-第三阶段19902007因子模型与量化机构化)
6. [第四阶段（2007–2009）：量化地震与金融危机](#6-第四阶段20072009量化地震与金融危机)
7. [第五阶段（2010–2020）：Smart Beta、因子动物园与"量化寒冬"](#7-第五阶段20102020smart-beta因子动物园与量化寒冬)
8. [第六阶段（2020–至今）：价值回归、CTA复兴、多策略平台与AI](#8-第六阶段2020至今价值回归cta复兴多策略平台与ai)
9. [分策略演进](#9-分策略演进)
10. [推动演进的底层力量](#10-推动演进的底层力量)
11. [规律总结](#11-规律总结)
12. [对中国市场的参照意义](#12-对中国市场的参照意义)
13. [附录A：大事年表](#附录a大事年表)
14. [附录B：必读文献清单](#附录b必读文献清单)
15. [附录C：代表性机构](#附录c代表性机构)

---

## 1. 什么是"中低频量化"

| 维度 | 高频 / 超短线 | **中频** | **低频** |
|---|---|---|---|
| 典型持仓 | 毫秒到分钟 | 1天到数周 | 数周到数月甚至更长 |
| 数据 | tick、订单簿 | 日频价量、盘口统计、新闻、分析师数据 | 财报、宏观、日/周/月频价格 |
| 收益来源 | 速度、微观结构、返佣 | 短期反转、统计套利、事件驱动、情绪/另类数据 | 风险溢价与行为偏差：价值、动量、质量、低波、趋势、carry |
| 核心竞争力 | 延迟、基础设施 | 信号广度、交易成本控制 | 研究深度、组合构建、风险模型、容量 |
| 容量 | 小 | 中 | 大（可管理数百亿美元） |
| 美国代表 | Virtu、Jump、早期 Getco | D.E. Shaw、Two Sigma、WorldQuant、各平台型基金的量化团队 | AQR、DFA、BGI/BlackRock SAE、Acadian、Winton/Man AHL（英国）、各类 CTA |

美国量化的主体资金一直在**中低频**。原因是：容量大，适合养老金、捐赠基金这类机构资金；逻辑能用学术语言讲清楚，便于通过投委会；在"机构投资者 → 投资顾问 → 量化管理人"这条链路里容易销售。

---

## 2. 总览：六个阶段

```
1900 ─── 1952 ─────── 1970 ─────── 1990 ─────── 2007 ── 2009 ─────── 2020 ───── 2026
 │ 理论萌芽  │  现代组合理论  │ 指数/风险模型 │ 因子模型+机构化 │ 量化地震 │ Smart Beta   │ 价值回归/
 │ Bachelier │ Markowitz/CAPM │ BARRA/CTA起步 │ Fama-French/AQR │ /危机    │ 因子动物园   │ CTA复兴/
 │ Cowles    │ EMH            │ Thorp/统计套利│ LTCM            │          │ 量化寒冬     │ 平台化/AI
```

一句话概括：**先有理论（什么是风险、什么是定价），再有工具（数据库、风险模型、指数），再有"异象"（能赚超额的规律），异象被系统化成因子，因子变得拥挤、被产品化成 beta，于是 alpha 往更细、更快、更另类的方向迁移。**

---

## 3. 第一阶段（1900–1970）：理论奠基

### 3.1 随机游走与"市场不可预测"
- **1900 年 Louis Bachelier**《投机理论》用布朗运动描述价格，是随机游走思想的源头（当时基本无人关注，1950 年代被 Savage、Samuelson 重新发现）。
- **1932 年 Cowles Commission** 成立。Alfred Cowles 1933 年的论文《股市预测者能预测吗？》用统计方法检验了投资通讯的荐股表现，结论是基本没有预测能力。这是"用数据检验投资主张"的早期范例。
- **1965 年 Samuelson** 证明"被正确预期的价格随机波动"；**Fama（1965、1970）** 系统提出**有效市场假说（EMH）**，分弱式、半强式、强式。

### 3.2 现代组合理论与资本资产定价
- **1952 年 Harry Markowitz**《Portfolio Selection》：把投资问题形式化为"均值-方差"优化，第一次把**风险**定义成可计算的量（方差/协方差）。今天几乎所有中低频量化的组合优化器都从这里出发。
- **1958 年 Tobin** 两基金分离定理。
- **1961–1966 年 CAPM**（Treynor、Sharpe 1964、Lintner 1965、Mossin 1966）：收益 = 无风险利率 + β × 市场风险溢价。它带来两个影响深远的后果：
  1. "**alpha / beta**"的语言从此确立；
  2. 为指数基金提供了理论依据：如果市场组合是有效的，就应该持有市场组合。

### 3.3 数据基础设施
- **1960 年芝加哥大学成立 CRSP**（证券价格研究中心，美林资助，Lorie 与 Fisher 主持），1964 年发布从 1926 年起的美股月度收益磁带。
- **1962 年前后 Compustat** 开始提供标准化财务数据。

**意义**：CRSP + Compustat 让"横截面回测"第一次成为可能。美国中低频量化的学术优势，很大程度上来自这两套数据库比其他国家早了几十年。

---

## 4. 第二阶段（1970–1990）：从学术走向实践

### 4.1 指数化：第一个"量化产品"
- **1971 年 Wells Fargo**（McQuown、Fouse 等）为新秀丽（Samsonite）养老金建立第一只指数化组合；**1973 年**推出基于 S&P 500 的版本。
- **1974 年 ERISA 法案**规范养老金"审慎人"义务，推动养老金寻找有理论依据、可解释的投资方法，指数化和量化因此受益。
- **1976 年 Vanguard** 推出第一只面向散户的指数基金。

这里值得一提：**被动指数本身就是最早、也是规模最大的"低频量化策略"**。之后的 Smart Beta、因子 ETF，都是在指数框架上加入"规则化的偏离"。

### 4.2 风险模型：BARRA
- **1975 年 Barr Rosenberg 创立 BARRA**，推出多因子风险模型（行业 + 风格因子，如规模、价值、动量、波动率）。
- 影响：机构第一次能把组合风险拆成"行业暴露、风格暴露、特质风险"，并且可以**控制跟踪误差**。这套语言后来成为量化股票的通用语言。Rosenberg 后来又创立 Rosenberg Institutional Equity Management（1985，后为 AXA Rosenberg）。

### 4.3 "异象"的发现：EMH 的裂缝
这一阶段学术界陆续找到一些 CAPM 解释不了的规律，也就是后来所有因子的原型：

| 年份 | 作者 | 发现 | 后来演变为 |
|---|---|---|---|
| 1968 | Ball & Brown | 盈利公告后价格持续漂移（PEAD） | 盈利动量、事件驱动 |
| 1972 | Black, Jensen & Scholes | 低 β 股票的风险调整后收益更高 | 低波 / BAB |
| 1975 | Haugen & Heins | 低波动率股票不比高波动率差 | 低波因子 |
| 1977 | Basu | 低市盈率股票跑赢 | 价值因子 |
| 1981 | Banz | 小市值股票跑赢 | 规模因子 |
| 1985 | De Bondt & Thaler | 3–5 年长期输家反转 | 长期反转、行为金融 |
| 1976 | Ross | 套利定价理论（APT） | 多因子模型的理论基础 |

### 4.4 最早的量化实践者
- **Ed Thorp**：数学家，1962 年出版《击败庄家》（21 点算牌），1967 年出版《击败市场》（权证/可转债对冲）。**1969 年创立 Princeton-Newport Partners**，做可转债套利、权证定价（比 Black-Scholes 公式发表还早），并在 1980 年代初开展统计套利研究。长期年化约 20% 且波动很低，基金 1988–89 年因监管调查（与其自身策略无关）关闭。
- **Batterymarch（1969，Dean LeBaron）**：最早一批用计算机做选股的机构管理人。
- **1981 年 LOR（Leland O'Brien Rubinstein）** 推出"投资组合保险"（动态复制看跌期权）。**1987 年 10 月 19 日"黑色星期一"**，组合保险与程序化卖盘被普遍认为加剧了下跌，这是量化第一次被公众当作"危机推手"。教训：**同质化的机械策略在压力下会形成正反馈。**

### 4.5 统计套利的诞生
- **1980 年代中期，摩根士丹利 APT 组**：Gerry Bamberger 先开始做配对交易，Nunzio Tartaglia 随后扩大规模，本质是基于价格相对关系的均值回复。
- 这个团队走出了几位后来的领军人物，其中 **David E. Shaw** 于 **1988 年创立 D.E. Shaw**，把统计套利做成了工业级业务。
- 统计套利是典型的**中频**策略（持仓天到周），后来随着竞争加剧持续向更高频率演化。

### 4.6 CTA 与趋势跟踪：另一条低频主线
- **1949 年 Richard Donchian** 创立 Futures Inc.，是第一批公开募集的商品期货基金之一，提出"唐奇安通道"和系统化趋势跟踪规则，被称为"趋势跟踪之父"。
- **1974 年 CFTC 成立**，确立 CTA（商品交易顾问）的监管框架。
- 早期代表：**Dunn Capital（1974）**、**Campbell & Company（1970年代初）**、**John W. Henry & Co.（1981）**、Millburn、Chesapeake。
- **1983–84 年"海龟实验"**：Richard Dennis 与 William Eckhardt 招募新人，用一套完全规则化的突破系统交易，证明**趋势跟踪可以被教授和复制**。
- 趋势跟踪是**美国历史最长、最连续的中低频量化策略**。它主要交易期货，不依赖选股，在后来的多次危机中表现出"危机 alpha"特征。

### 4.7 Renaissance：一个特例
- 1978 年 James Simons 创立 Monemetrics，1982 年更名为 Renaissance Technologies，**1988 年推出 Medallion 基金**。Medallion 早期交易期货，偏中短周期，后来转向更高频的股票统计套利，只对内部员工开放，扣费前的长期年化收益据报道超过 60%。
- 它更多代表的是"中高频 + 海量信号"的路线；Renaissance 面向外部的低频产品（RIEF 等）表现平平，这本身就说明**中低频和中高频是两门不同的生意**。

---

## 5. 第三阶段（1990–2007）：因子模型与量化机构化

### 5.1 学术上的突破：Fama-French
- **1992 年 Fama & French**《The Cross-Section of Expected Stock Returns》：β 对横截面收益几乎没有解释力，**规模和账面市值比（B/M）才有**，这对 CAPM 是一记重击。
- **1993 年三因子模型**（市场、SMB、HML）。
- **1993 年 Jegadeesh & Titman**：过去 3–12 个月的赢家继续跑赢，这就是**动量**。
- **1997 年 Carhart** 加入动量，形成四因子模型，成为基金业绩归因的标准工具。

从此，"因子"从学术概念变成了**产品设计单位**。

### 5.2 实践上的方法论：Grinold & Kahn
- **1989 年 Grinold**《主动管理基本定律》：**IR ≈ IC × √Breadth**（信息比率 ≈ 信息系数 × 独立下注次数的平方根）。
- **1995 年 Grinold & Kahn《Active Portfolio Management》**：把"alpha 预测 → 风险模型 → 组合优化 → 交易成本"整合成一套完整的工业流程，被称为量化股票的"圣经"。
- 它的核心思想直接解释了中低频量化股票的做法：**单个信号的预测能力很弱（IC 往往只有 0.02–0.05），但覆盖上千只股票、组合几十个信号，就能得到稳定的信息比率。**

### 5.3 机构化：量化管理人的黄金年代
| 机构 | 成立 | 特点 |
|---|---|---|
| Dimensional Fund Advisors（DFA） | 1981 | Booth & Sinquefield 创立，把小盘、价值溢价产品化，与 Fama、French 深度合作，是"学术因子 → 低成本产品"的先驱 |
| PanAgora | 1985 | 量化股票，后来提出"风险平价"一词 |
| Acadian | 1986 | 全球量化股票 |
| Jacobs Levy | 1986 | 多因子、复杂交互效应 |
| Numeric Investors | 1989 | 量化股票（2014 年被 Man Group 收购） |
| Barclays Global Investors（BGI） | 1995（前身 Wells Fargo Nikko） | 指数 + 主动量化（"Alpha Tilts"）双引擎，2000 年推出 iShares |
| LSV | 1994 | Lakonishok、Shleifer、Vishny 三位行为金融学者创立，系统化价值投资 |
| AQR | 1998 | Cliff Asness 等人从高盛资产管理的量化团队出走创立，把价值、动量、carry、防御因子推广到全资产类别 |
| Two Sigma | 2001 | Overdeck 与 Siegel 创立，技术公司式的数据与工程驱动 |
| 高盛资产管理量化股票（GSAM QIS） | 1990s | 投行系量化的代表，2007 年受重创 |

这一时期，美国大型养老金普遍采用"**核心被动 + 量化增强（enhanced index）+ 主动卫星**"的结构。量化增强（跟踪误差 1–3%，追求稳定超额）成为中低频量化股票最大的资金来源。

### 5.4 风险平价与系统化宏观
- **1996 年 Bridgewater 推出 All Weather**，按风险而非资金分配资产。
- **2005 年 PanAgora 的钱恩平（Edward Qian）**正式提出"Risk Parity"一词。风险平价在 2008 年后迅速普及。

### 5.5 LTCM：杠杆的教训（1994–1998）
- 长期资本管理公司由 John Meriwether 与诺奖得主 Merton、Scholes 等创立，做固定收益相对价值（利差收敛交易），属于**低频、高杠杆**的量化套利。
- 1998 年俄罗斯违约引发流动性危机，所有"必然收敛"的价差同时扩大，最后由美联储牵头 14 家银行注资约 36 亿美元接管。
- 教训："**市场保持非理性的时间，可能比你保持偿付能力的时间更长**"；模型没有考虑到**拥挤与流动性**，也没有考虑到极端情况下相关性会趋向 1。

### 5.6 市场结构变化让高频分家
- **2001 年美股十进制报价**、**2005 年通过、2007 年实施的 Reg NMS**，让电子化与碎片化交易迅速发展，HFT 从此自成一派。
- 中低频量化开始更加重视**交易成本分析（TCA）与算法执行**，因为执行质量直接吞噬中低频 alpha。

---

## 6. 第四阶段（2007–2009）：量化地震与金融危机

### 6.1 2007 年 8 月"量化地震"（Quant Quake）
- **2007 年 8 月 6–9 日**，大量量化股票多空基金在几天内同时出现罕见亏损，高盛 Global Equity Opportunities 一周亏损约 30%，随后获得约 30 亿美元注资。而同期**市场指数波动并不大**。
- **Khandani & Lo（2007）《What Happened to the Quants in August 2007?》** 的解释是：大量基金持有相似的因子组合（价值、动量、盈利质量等），某个多策略机构为了应对其他资产的亏损而**被迫去杠杆**，抛售引发同类组合连锁亏损，形成"**拥挤交易的踩踏**"。
- 这是中低频量化历史上**最重要的一课**：
  1. 因子策略的风险不只是市场风险，还有"**同行风险**"（其他人持仓一样）；
  2. 回测看不到拥挤度；
  3. 杠杆 + 同质化 = 流动性危机。

### 6.2 2008 年：CTA 的高光时刻
- 次贷危机中股票、信用同时暴跌，**趋势跟踪 CTA 却普遍大涨**（主流趋势跟踪指数当年涨约两成），"**危机 alpha**"一词流行开来，管理期货的规模在随后几年大幅增长。

### 6.3 2009 年：动量崩溃
- 2009 年 3–5 月市场 V 形反转，过去跌得最惨的高 β、高杠杆股票领涨，**动量因子出现历史级回撤**。
- **Daniel & Moskowitz（2016）《Momentum Crashes》** 指出：动量崩溃往往发生在熊市后的急速反弹中，可以通过动态调整波动率来部分规避。

### 6.4 行业格局洗牌
- **2009 年 BlackRock 以约 135 亿美元收购 BGI**，将其量化团队并入，即后来的 BlackRock Systematic Active Equity。
- 高盛等投行系量化规模收缩；独立量化机构（AQR、Two Sigma、D.E. Shaw、Renaissance）占据主导。
- **2010 年"闪崩"**与此后的 Dodd-Frank、Volcker 规则进一步将自营交易赶出投行，人才流向对冲基金。

---

## 7. 第五阶段（2010–2020）：Smart Beta、因子动物园与"量化寒冬"

### 7.1 Smart Beta / 因子 ETF：把 alpha 变成 beta
- 源头：**2005 年 Arnott、Hsu、Moore《Fundamental Indexation》**（Research Affiliates）提出按基本面而不是市值加权。
- 2010 年代，MSCI 最小波动、iShares / SPDR / Invesco 等**单因子、多因子 ETF** 大量涌现，费率只有几个基点到几十个基点。
- **影响深远**：价值、动量、低波、质量这些曾经可以按 1.5%/20% 收费的"alpha"，被产品化成**廉价 beta**。主动量化管理人被迫往**更细的信号、更多数据、更好的组合构建**方向升级，否则就会被费率挤压。

### 7.2 学术界的因子扩张
| 年份 | 文献 | 贡献 |
|---|---|---|
| 1996 | Sloan | 应计利润异象 |
| 2000 | Piotroski | F-Score 质量筛选 |
| 2006 | Ang, Hodrick, Xing, Zhang | 特质波动率异象 |
| 2006 | Gatev, Goetzmann, Rouwenhorst | 配对交易的系统检验 |
| 2012 | Moskowitz, Ooi, Pedersen | **时间序列动量**（给 CTA 提供了学术基础） |
| 2013 | Novy-Marx | 毛利率 / 盈利能力因子 |
| 2013 | Asness, Moskowitz, Pedersen | **《Value and Momentum Everywhere》**：价值和动量在各类资产中普遍存在 |
| 2014 | Frazzini & Pedersen | **Betting Against Beta** |
| 2015 | Fama & French | **五因子模型**（加入盈利 RMW、投资 CMA） |
| 2015 | Hou, Xue, Zhang | **q 因子模型**（基于投资的资产定价） |
| 2017 | Hurst, Ooi, Pedersen | 《A Century of Evidence on Trend-Following》，趋势跟踪百年回测 |
| 2018 | Koijen, Moskowitz, Pedersen, Vrugt | 跨资产 **Carry** |
| 2019 | Asness, Frazzini, Pedersen | **Quality Minus Junk** |

### 7.3 "因子动物园"与复制危机
- **Cochrane 2011 年 AFA 主席演讲**提出"因子动物园"（factor zoo）一词：文献中的因子太多了。
- **Harvey, Liu & Zhu（2016）**：统计了 316 个"显著"因子，提出多重检验下 t 值门槛应提高到 **3.0** 左右。
- **McLean & Pontiff（2016）**：异象在样本外平均衰减约 26%，**论文发表后衰减约 58%**，说明学术发表本身会"消耗"alpha。
- **Hou, Xue & Zhang（2020）《Replicating Anomalies》**：在 452 个异象中，控制微盘股影响后大部分无法复制。
- 反方：**Jensen, Kelly & Pedersen（2023）《Is There a Replication Crisis in Finance?》** 用贝叶斯方法认为，大部分因子在全球范围内是可以复制的。
- **实务结论**：顶级量化机构越来越重视**经济逻辑先验、样本外与跨市场验证、交易成本后的净收益**，而不是单纯追求回测 t 值。

### 7.4 另类数据与机器学习
- 2010 年代中后期，卫星图像、信用卡消费、网页爬虫、App 数据、新闻与社交媒体情绪、供应链关系等**另类数据**进入中低频量化，数据供应商生态形成。
- NLP 从词典法（Loughran & McDonald 2011 金融情感词典）逐步演进到深度学习。
- **Gu, Kelly & Xiu（2020）《Empirical Asset Pricing via Machine Learning》**：树模型与神经网络在美股横截面预测上显著优于线性模型，收益主要来自**非线性交互**。这篇论文成了"机器学习选股"的学术基准。
- **众包模式**：WorldQuant（2007，Igor Tulchinsky）的"alpha 工厂"模式，靠海量弱信号组合；Quantopian（2011–2020，最终关闭）；Numerai（2015，加密激励的模型众包）。

### 7.5 平台型多经理基金崛起
- Millennium、Citadel（旗下 Global Quantitative Strategies）、Point72（旗下 Cubist）、Balyasny 等平台，把量化团队当成独立"pod"管理，**严格止损、市场中性、低相关**。
- 这种模式偏好**中频、高夏普、低容量**的策略，与 AQR、DFA 这类"低频、大容量、风险溢价"模式形成两极。

### 7.6 "量化寒冬"（约 2018–2020）
- **价值因子遭遇"失落的十年"**：美国 HML 从 2007 年起长期跑输，2018–2020 年跌到历史级回撤。原因的讨论包括：无形资产让账面价值失真、低利率抬高了长久期成长股估值、科技巨头集中度上升等。
- **趋势跟踪 CTA 在 2012–2019 年大多表现平平**（央行压低波动、趋势断续）。
- 多家头部量化机构规模明显缩水（例如 AQR 管理规模从 2018 年约 2000 多亿美元的高点降到 2020 年约 1400 亿美元）。
- **2020 年**：新冠冲击中部分量化股票策略大幅亏损；Renaissance 面向外部的 RIEF 等基金当年亏损约两成；**2020 年 11 月 9 日辉瑞疫苗消息**引发动量对价值的剧烈轮动，动量单日暴跌。

---

## 8. 第六阶段（2020–至今）：价值回归、CTA复兴、多策略平台与AI

### 8.1 价值回归与 CTA 复兴（2021–2022）
- 2021–2022 年通胀和加息下，**价值因子强劲反弹**，量化股票多空策略迎来多年来最好的表现。
- **2022 年是趋势跟踪的丰收年**：股债双杀，利率、商品、美元都走出单边趋势，主流趋势指数当年涨约 25%–30%，"危机 alpha"叙事重新成立。

### 8.2 平台化与人才战
- 2021–2024 年，多经理平台规模与人才薪酬快速上升，量化 pod 成为平台的重要组成部分。
- 趋势：量化与主观"**quantamental**"融合；主观基金普遍配置数据科学团队。

### 8.3 AI 与大语言模型
- **Kelly, Malamud & Zhou（2024）《The Virtue of Complexity in Return Prediction》**：认为参数远多于样本的"复杂"模型在收益预测上可以更好，引发了"过度参数化是否适用于金融"的讨论。
- **Lopez-Lira & Tang（2023）**：用 ChatGPT 解读新闻标题预测次日收益，引发了大量 LLM 做文本信号的研究。
- 实务中，LLM 主要用于：**非结构化文本特征提取**（财报电话会、公告、新闻）、研究员效率工具（代码、数据清洗）、以及更大规模的因子挖掘。它更像"**信号工厂的生产力工具**"，而不是替代组合构建与风控。
- 需要警惕的问题：LLM 训练数据的**前视偏差**（模型"知道"未来）、信号同质化（大家用同一批模型）、算力成本。

### 8.4 近两年的压力测试（2025，据媒体报道，建议核对原始数据）
- **2025 年 4 月关税冲击**：市场先暴跌后急速反弹，趋势跟踪 CTA 在上半年普遍明显回撤。这再次说明趋势策略怕"**V 形反转与震荡**"。
- **2025 年年中**：据报道，部分量化股票多空基金因高空头比例、低质量股票的逼空式上涨而短期承压，市场再次讨论"拥挤度"和"做空端风险"。
- 这些事件与 2007、2009、2020 的逻辑一脉相承：**拥挤 + 急速反转 = 中低频量化的主要尾部风险**。

---

## 9. 分策略演进

### 9.1 股票多因子（Equity Multi-Factor）
```
CAPM单因子 → BARRA风险模型(1975) → Fama-French三因子(1993) → Carhart四因子(1997)
 → 量化增强/多空(1990s-2000s) → Smart Beta产品化(2005-2015) → 五因子/q因子(2015)
 → 另类数据+ML非线性(2015-) → LLM文本信号(2023-)
```
- **alpha 来源的迁移**：经典风格因子（价值/动量/规模）→ 质量/低波/盈利 → 分析师预期、盈利修正、供应链、情绪 → 另类数据与非线性交互。
- **组合构建的迁移**：分组排序 → 均值方差优化 + 风险模型 → 考虑交易成本的多期优化 → 因子择时（争议较大）与拥挤度监控。
- **规模**：美国量化股票中，最大的一块仍是**低跟踪误差的指数增强 / 系统化主动**，面向养老金与主权基金。

### 9.2 统计套利（Stat Arb）
- 1980 年代摩根士丹利配对交易 → 1990 年代 D.E. Shaw 等将其扩展为多股票残差均值回复 → **Avellaneda & Lee（2010）** 的 PCA/ETF 残差框架 → 如今融合短期反转、订单流、新闻事件等。
- 规律：竞争越激烈，**持仓周期越短**，逐渐从中频滑向中高频；容量与收益同步下降。

### 9.3 趋势跟踪 / 管理期货（CTA）
- 唐奇安通道 → 海龟突破系统 → 均线组合、多周期 → **波动率目标 + 风险平价式仓位** → 时间序列动量理论化（2012）→ 加入 carry、宏观、另类市场（小众期货品种）。
- 特征：**正偏度、危机 alpha、长时间"磨损"**。收益高度依赖少数大趋势年份（如 2008、2014、2022）。
- 行业分化：大型 CTA 为了容量交易主流合约；中小型 CTA 靠"另类市场"获得分散化。

### 9.4 风险平价与系统化宏观 / 多资产风险溢价
- All Weather（1996）→ Risk Parity（2005 命名）→ 2008 年后普及 → **另类风险溢价（ARP）**：在多资产上系统化收取价值、动量、carry、防御溢价（AQR、各投行 QIS 指数）。
- 痛点：**2022 年股债同跌**让传统风险平价明显受伤，暴露出它对"股债负相关"的依赖。

### 9.5 事件驱动量化
- PEAD（1968 年发现，至今仍是最稳健的异象之一）、盈利惊喜、分析师评级调整、指数调整、并购套利系统化、内部人交易信号等。
- 现代版本把 NLP 用于财报文本、电话会语气、监管文件（10-K / 8-K）差异分析（例如 Cohen, Malloy & Nguyen 2020《Lazy Prices》）。

### 9.6 期权与波动率
- 系统化卖出波动率（收取方差风险溢价），也包括尾部对冲。2018 年 2 月"Volmageddon"（做空 VIX 产品爆仓）是这个领域的典型尾部事件。

---

## 10. 推动演进的底层力量

1. **数据**：CRSP/Compustat（1960s）→ I/B/E/S 分析师预期（1970s）→ 日内数据（1990s）→ 另类数据（2010s）→ 非结构化文本 + LLM（2020s）。**每一次新数据的普及都会先产生 alpha，然后被竞争消灭。**
2. **计算能力**：大型机 → PC 与工作站 → 分布式集群 → GPU/云。它降低了回测和优化的门槛，也加速了 alpha 的衰减。
3. **学术-产业管道**：芝加哥、MIT、宾大、耶鲁等高校 → DFA、AQR、LSV 等机构（学者直接创业）。美国是全球唯一一个**顶级金融学者大规模下场管钱**的市场，理论和实践高度同步。
4. **监管与制度**：ERISA（1974）推动机构化；CFTC（1974）规范 CTA；Reg NMS（2007）让高频分家；Dodd-Frank / Volcker（2010）让投行自营人才外流；1940 年法案下的 ETF 让因子产品化。
5. **费率压力**：指数基金与 Smart Beta 不断把 alpha 重新定义为 beta，逼迫主动量化往更难复制的方向升级。
6. **拥挤与反身性**：策略越成功，资金越多，拥挤度越高，尾部风险越大（1987、1998、2007、2009、2020）。

---

## 11. 规律总结

1. **alpha 的生命周期**：发现（学术 / 业界）→ 秘密使用 → 发表或扩散 → 产品化为 beta → 拥挤 → 周期性崩溃 → 长期溢价缩小但通常不会归零。
2. **"风险溢价"与"行为偏差"都能长期存在**：价值、动量、低波、趋势在美国（以及全球）有长达数十年乃至上百年的证据，但都可能经历**长达十年的逆风**（价值 2007–2020、CTA 2012–2019）。能否坚持，取决于资金方的耐心与管理人的沟通能力。
3. **组合构建与风险控制的价值往往大于单一信号**：Grinold 的 IR = IC × √Breadth 决定了中低频量化的核心是"**广度 + 分散 + 成本控制**"。
4. **最大的风险来自同行**：2007 年量化地震说明，因子策略的尾部风险来自"大家持有同样的东西"，而不是市场本身。
5. **频率会自发上移**：同一类信号竞争加剧后，持仓周期缩短、容量下降（统计套利是典型例子）。中低频要保持优势，就要依靠**独特数据、独特的组合构建，或者更长期的耐心资本**。
6. **杠杆放大模型风险**：LTCM（1998）、2007 量化地震、2018 波动率产品爆仓，都是"模型没错，但杠杆和流动性让你撑不到对的那一天"。
7. **机器学习是加法，不是替代**：ML/LLM 提升了信号挖掘效率和非线性建模能力，但低信噪比、非平稳、样本少是金融数据的根本约束，过拟合风险比其他领域高得多。

---

## 12. 对中国市场的参照意义

| 维度 | 美国 | 中国（A 股） |
|---|---|---|
| 起步 | 1970s 机构化，1990s 成熟 | 2010 年股指期货上市后起步，2014–2015、2019–2021 两轮快速扩张 |
| 主流频率 | 中低频为主，高频自成一派 | 中高频（日内到数日）占比更高，量价因子占主导 |
| 收益来源 | 风险溢价 + 行为偏差，基本面因子更重要 | 散户占比高，量价、反转、流动性因子更有效，小市值溢价长期显著 |
| 产品形态 | 指数增强、多空市场中性、CTA、Smart Beta ETF | 指数增强（500/1000 增强）、市场中性、CTA、"雪球"等结构化产品 |
| 对冲工具 | 融券、互换、期货、期权都很充分 | 对冲工具与融券相对受限，基差成本影响中性策略 |
| 典型危机 | 1987、1998、2007、2009、2020 | 2015 股灾、2017 小票转大票、2021 年末、2024 年初小微盘流动性危机 |

**可以借鉴的地方**：
- 2024 年初 A 股小微盘踩踏的逻辑，与 **2007 年美国量化地震**高度相似：同质化暴露（小市值、微盘）+ 杠杆 / 衍生品（雪球敲入、中性产品基差）+ 被迫去杠杆。
- 随着监管与市场结构变化（例如对程序化交易的监管、融券限制），A 股量化可能沿着美国的路径，**逐步从中高频量价向中低频基本面、另类数据和多资产方向扩展**，同时更加重视风险模型和拥挤度管理。
- 美国经验提示：因子被产品化（A 股已有大量指数增强、因子 ETF）之后，超额收益会趋于下降，**管理人的差异化将更多来自数据、组合构建与风控，而不是单一因子**。

---

## 附录A：大事年表

| 年份 | 事件 |
|---|---|
| 1900 | Bachelier《投机理论》 |
| 1932 | Cowles Commission 成立 |
| 1949 | Donchian 创立 Futures Inc.，系统化趋势跟踪的起点 |
| 1952 | Markowitz《Portfolio Selection》 |
| 1960 | 芝加哥大学 CRSP 成立 |
| 1964 | Sharpe CAPM |
| 1969 | Thorp 创立 Princeton-Newport；Batterymarch 成立 |
| 1970 | Fama 系统阐述有效市场假说 |
| 1971 | Wells Fargo 第一个指数化组合 |
| 1973 | Black-Scholes 期权定价 |
| 1974 | ERISA；CFTC 成立；Dunn Capital 成立 |
| 1975 | BARRA 成立 |
| 1976 | Vanguard 首只指数基金；Ross APT |
| 1977 | Basu 市盈率效应 |
| 1981 | Banz 规模效应；DFA 成立；JWH 成立；LOR 组合保险 |
| 1982 | Renaissance Technologies 更名成立 |
| 1983 | 海龟交易实验 |
| 1985 | 摩根士丹利 APT 组统计套利（1985 年前后） |
| 1987 | 黑色星期一，组合保险受到指责 |
| 1988 | D.E. Shaw 成立；Medallion 基金成立 |
| 1989 | Grinold 主动管理基本定律 |
| 1992–93 | Fama-French 三因子；Jegadeesh-Titman 动量 |
| 1994 | LTCM 成立；LSV 成立 |
| 1995 | BGI 成立；Grinold & Kahn《Active Portfolio Management》 |
| 1996 | Bridgewater All Weather |
| 1997 | Carhart 四因子 |
| 1998 | LTCM 崩溃；AQR 成立 |
| 2000 | iShares 推出 |
| 2001 | 美股十进制；Two Sigma 成立 |
| 2005 | Fundamental Indexation；"Risk Parity"命名；Reg NMS 通过 |
| 2007 | 8 月量化地震；WorldQuant 成立 |
| 2008 | 金融危机，CTA "危机 alpha" |
| 2009 | 动量崩溃；BlackRock 收购 BGI |
| 2010 | 闪崩；Dodd-Frank |
| 2011 | Cochrane "因子动物园" |
| 2012 | 时间序列动量论文 |
| 2013 | 《Value and Momentum Everywhere》 |
| 2015 | Fama-French 五因子；q 因子 |
| 2016 | Harvey-Liu-Zhu 多重检验；McLean-Pontiff 发表后衰减 |
| 2018 | 2 月 Volmageddon；价值因子进入深度回撤 |
| 2020 | Gu-Kelly-Xiu 机器学习资产定价；新冠冲击；11 月疫苗日动量崩溃；Quantopian 关闭 |
| 2021–22 | 价值回归；2022 年趋势跟踪大年 |
| 2023 | LLM 文本信号研究兴起；Jensen-Kelly-Pedersen 复制性研究 |
| 2024 | Kelly-Malamud-Zhou "复杂性的优点" |
| 2025 | 关税冲击下 CTA 回撤；年中量化多空承压（据报道） |

---

## 附录B：必读文献清单

**理论基础**
1. Markowitz, H. (1952). Portfolio Selection. *Journal of Finance*.
2. Sharpe, W. (1964). Capital Asset Prices. *Journal of Finance*.
3. Fama, E. (1970). Efficient Capital Markets: A Review of Theory and Empirical Work. *Journal of Finance*.
4. Ross, S. (1976). The Arbitrage Theory of Capital Asset Pricing. *Journal of Economic Theory*.

**因子与异象**
5. Fama, E. & French, K. (1992, 1993, 2015). 三因子与五因子系列。
6. Jegadeesh, N. & Titman, S. (1993). Returns to Buying Winners and Selling Losers. *Journal of Finance*.
7. Carhart, M. (1997). On Persistence in Mutual Fund Performance. *Journal of Finance*.
8. Asness, C., Moskowitz, T. & Pedersen, L. (2013). Value and Momentum Everywhere. *Journal of Finance*.
9. Frazzini, A. & Pedersen, L. (2014). Betting Against Beta. *Journal of Financial Economics*.
10. Hou, K., Xue, C. & Zhang, L. (2015). Digesting Anomalies. *Review of Financial Studies*.

**方法论与实务**
11. Grinold, R. & Kahn, R. (1995/1999). *Active Portfolio Management*.
12. Harvey, C., Liu, Y. & Zhu, H. (2016). …and the Cross-Section of Expected Returns. *Review of Financial Studies*.
13. McLean, R. & Pontiff, J. (2016). Does Academic Research Destroy Stock Return Predictability? *Journal of Finance*.
14. Lopez de Prado, M. (2018). *Advances in Financial Machine Learning*.

**危机与拥挤**
15. Khandani, A. & Lo, A. (2007/2011). What Happened to the Quants in August 2007?
16. Daniel, K. & Moskowitz, T. (2016). Momentum Crashes. *Journal of Financial Economics*.
17. Lowenstein, R. (2000). *When Genius Failed*（LTCM）。

**趋势跟踪 / 多资产**
18. Moskowitz, T., Ooi, Y. H. & Pedersen, L. (2012). Time Series Momentum. *Journal of Financial Economics*.
19. Hurst, B., Ooi, Y. H. & Pedersen, L. (2017). A Century of Evidence on Trend-Following Investing. *Journal of Portfolio Management*.
20. Koijen, R., Moskowitz, T., Pedersen, L. & Vrugt, E. (2018). Carry. *Journal of Financial Economics*.

**机器学习**
21. Gu, S., Kelly, B. & Xiu, D. (2020). Empirical Asset Pricing via Machine Learning. *Review of Financial Studies*.
22. Kelly, B., Malamud, S. & Zhou, K. (2024). The Virtue of Complexity in Return Prediction. *Journal of Finance*.
23. Lopez-Lira, A. & Tang, Y. (2023). Can ChatGPT Forecast Stock Price Movements? Working paper.

**历史与人物（通俗读物）**
24. Bernstein, P. (1992). *Capital Ideas*（现代金融理论如何进入华尔街）。
25. Patterson, S. (2010). *The Quants*（2007 量化地震前后）。
26. Zuckerman, G. (2019). *The Man Who Solved the Market*（Renaissance 与 Simons）。
27. Thorp, E. (2017). *A Man for All Markets*（Thorp 自传）。
28. Covel, M. (2004/2017). *Trend Following*；Faith, C. (2007). *Way of the Turtle*。

---

## 附录C：代表性机构

| 类型 | 机构 | 主要风格 |
|---|---|---|
| 学术因子 / 大容量 | DFA、AQR、LSV、Research Affiliates | 价值、规模、盈利、动量、防御，长期持有 |
| 机构量化股票 | BlackRock SAE（原 BGI）、Acadian、Jacobs Levy、PanAgora、State Street、GSAM QIS | 指数增强、多空、全球量化股票 |
| 技术驱动型 | Two Sigma、D.E. Shaw、Renaissance（外部基金） | 多数据源、ML、中频为主 |
| 众包 / Alpha 工厂 | WorldQuant、Numerai | 海量弱信号组合 |
| 平台型量化 pod | Citadel GQS、Millennium、Point72 Cubist | 中频、市场中性、严格风控 |
| CTA / 趋势跟踪 | Dunn、Campbell、Millburn、Chesapeake、JWH（已退出） | 期货趋势跟踪 |
| 风险平价 / 宏观 | Bridgewater All Weather、PanAgora、AQR | 风险预算、多资产 |

---

*下一步可以展开的方向：（1）选一两个经典因子（如价值、动量）用公开数据（Ken French 数据库）复现其美国百年表现与回撤；（2）深入对比美国 2007 量化地震与 A 股 2024 年初小微盘危机；（3）梳理美国 CTA 指数的长期收益与危机表现；（4）研究 LLM 在中低频选股中的最新实证。*
