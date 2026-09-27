# 基本面量化的演进：美国与中国对照（带来源标注）

> **写作缘起**：梁文锋 2019 年演讲把 A 股股票量化分成四类：日间量价（约 2000 亿）、日内回转 T0（大几百亿）、基本面模型、事件驱动，并提到"公募还有 1200 亿左右在做基本面量化"。本文追问两件事：基本面量化在美国是怎么走过来的？在中国又是怎么走的？
>
> **来源与核实说明（请先读）**
> - 本文优先使用两类来源：**(D) 客观数据**（学术论文、监管文件、SEC 备案、数据商/券商金工统计）和 **(P) 业内代表人物的原话**（访谈、演讲、公司出版物）。媒体转述标 **(M)**。
> - 本次研究环境的网络策略屏蔽了绝大多数网站的全文抓取（新浪、雪球、知乎、21 经济网、中证网、AQR、Ken French 数据库等），所有引文都来自**搜索引擎返回的页面摘要**，未能打开原文逐句核对。每条后面标了核实等级：**[核]** 多个独立来源一致、或来自一手文件；**[摘]** 仅有搜索摘要，措辞可能与原文有出入；**[未核]** 只有单一二手来源或数字口径不明。
> - 引用前请自行打开链接核对，尤其是标 [摘] 和 [未核] 的部分。

---

## 0. 先给结论

1. **美国基本面量化的主线是"学术异象 → 因子 → 产品"**：从 1968 年 Ball & Brown 的盈利公告后漂移，到 1992 年 Fama-French、1996 年 Sloan 应计、2000 年 Piotroski、2013 年 Novy-Marx 盈利能力、2015 年五因子，几乎每个核心信号都先在会计/金融学术期刊发表，再被 DFA、LSV、AQR、BGI 等机构产品化，最后被 Smart Beta ETF 变成几个基点费率的 beta。
2. **美国基本面量化经历过三次大考**：2007 年 8 月量化地震（Khandani & Lo 指出震中正是"多账面市值比、空盈利动量"这类基本面因子组合）、2018–2020 年价值因子历史级回撤（AQR 规模从 2260 亿美元跌到约 1400 亿美元）、以及 2020 年新冠期间 Renaissance 对外基金亏 22%。三次都没有让基本面量化消失，2021–2022 价值反弹后，AQR、Acadian、BlackRock Systematic、DFA 的规模在 2025 年都创了新高。
3. **中国基本面量化的主线是"BGI 海归 → 公募指增 → 被量价私募压过 → 2023 年后回潮"**：2009 年李笑薇、2012 年田汉卿和黎海威从 BGI 回国建立公募量化团队，走的是美国 BGI 那套基本面多因子；2017 年"大票行情"重创偏小盘的公募量化；2018 年后私募以量价 + AI 迅速扩张到万亿规模；2023 年起量价超额收敛、监管限制高频，"降频、做基本面"成为行业共识，公募量化规模 2025 年底达到约 4000 亿。
4. **一个关键差别**：美国基本面量化的主要资金是养老金、捐赠基金这类耐心资本，能忍受价值因子十年逆风；中国基本面量化在私募端始终是配角（明汯裘慧明 2023 年称其策略中基本面因子只占约 5%），主因是 A 股散户占比高、量价 alpha 长期更肥、基本面数据质量与覆盖不足（九坤王琛）。梁文锋 2019 年说"程序最终也要抢夺基本面流派原来赚的钱，但达到量化高度仍需几个摩尔定律的周期"，到 2026 年看，这个判断基本成立：基本面量化在中国已从"不是重点"变成"重点方向"，但仍未成为主流收益来源。

---

## 1. 美国：基本面量化的演进

### 1.1 学术奠基（1968–2015）：每个因子都有一篇论文

| 年份 | 文献 | 核心发现 | 核实 |
|---|---|---|---|
| 1968 | Ball & Brown, *J. Accounting Research* | 盈利公告后价格持续漂移（PEAD），被称为"第一个被公认的股市异象"，五十年后仍存在 | [核] (D) [US-1][US-2] |
| 1977 | Basu, *J. Finance* | 低市盈率股票收益更高，价值效应的最早系统证据 | [核] (D) [US-3] |
| 1992/93 | Fama & French, *J. Finance* | "规模和账面市值比两个容易度量的变量，合起来就能解释平均收益的横截面差异……β 与平均收益的关系是平的" | [核] (D) [US-4] |
| 1994 | Lakonishok, Shleifer & Vishny, *J. Finance* | 价值策略赚钱是因为"利用了典型投资者的次优行为，而不是因为这些策略本质上风险更高" | [核] (D) [US-5] |
| 1996 | Sloan, *Accounting Review* | 应计异象：低应计公司跑赢高应计公司约 10%/年 | [摘] (D) [US-6][US-7] |
| 2000 | Piotroski, *J. Accounting Research* | F-Score 九项财务信号；二手资料称多空组合 1976–96 年化约 23.5% | [未核] 数字来自二手资料 [US-8] |
| 2013 | Novy-Marx, *JFE* | "盈利能力在预测横截面预期收益差异上的能力，与相对价格一样强" | [核] (D) [US-9] |
| 2015 | Fama & French 五因子 | 加入盈利（RMW）与投资（CMA），源于 Novy-Marx 2013 | [核] (D) [US-10][US-11] |

实务桥梁：Jacobs & Levy 1988 年 *FAJ* 论文《Disentangling Equity Return Regularities》提出多元回归的"纯因子收益"，是现代多因子选股的模板。[US-12] [核]

### 1.2 机构化（1971–2005）：从 Wells Fargo 到 AQR

- **Wells Fargo → BGI → BlackRock**：BGI 1980 年代中期推出"alpha tilts"增强指数，目标超越基准 150–200 bp；Grinold（BGI 全球研究总监 1994–2009）与 Kahn 的《Active Portfolio Management》（1994）把"信息比率 = 信息系数 × √广度"变成行业标准。[US-14][US-15] [核]
- **DFA（1981）**：Booth 与 Sinquefield 创立，第一个产品是基于芝加哥大学论文数据的美国小盘策略；小盘价值基金 DFSVX 1993 年成立。[US-17][US-18] [核]
- **LSV（1994）**：三位学者创立，自述理念是"系统性利用影响多数投资者决策的判断偏差与行为弱点"。[US-19] [核]
- **AQR（1998）**：Asness 等人从高盛资产管理出走创立。
- **Renaissance RIEF（2005）**：面向外部投资者，目标超越标普 500 每年 400–600 bp，持仓可达一年（Medallion 是天级），是"慢速、偏基本面"的一本书。[US-24] [核] (M)
- **2017 年 3 月 BlackRock** 把约 300 亿美元（约 11% 的主动股票）转为量化/模型驱动，Larry Fink 对《纽约时报》说："信息民主化让主动管理难得多了。我们必须改变生态——这意味着在量化和传统策略里更多依赖大数据、人工智能、因子和模型。"这是"quantamental"一词流行的起点。[US-52] [摘] (P, 经二手转引)

### 1.3 第一次大考：2007 年 8 月量化地震

- **Khandani & Lo（2007/2011）**："亏损很可能是由一个或多个大型量化股票市场中性组合的快速平仓引发，可能来自多策略基金或自营台因追缴保证金或降风险而被迫清算。"他们用"五个估值因子"构造的模拟多空组合发现，平仓"始于 2007 年 7 月，持续到年底"，并且**"始于金融板块股票、多账面市值比、空盈利动量"**——也就是说，震中就是经典的基本面价值和盈利修正因子。[US-25][US-26][US-27] [核] (D)
- 高盛 Global Alpha 峰值管理 120 亿美元，2007 年 7 月单月亏 7.7%；Global Equity Opportunities（约 36 亿美元）获高盛等注资 30 亿美元。高盛 8-K 自述亏损来自"遭遇流动性压力的量化股票市场中性策略"。[US-28][US-29] [核] (D, SEC 文件)

### 1.4 2010 年代：Smart Beta、因子动物园、价值失落的十年

**Smart Beta 把 alpha 变成 beta（数据商口径）**
- Morningstar：美国 strategic beta ETP 2022 年底约 1.36 万亿美元，"从 2000 年代初的零增长到占美国 ETF 资产近五分之一"，但份额增长"停滞，2020 年甚至逆转"。[US-30][US-31] [核] (D)
- ETFGI：全球 smart beta ETF 2023 年底 1.49 万亿美元，2024 年 2 月 1.56 万亿美元。[US-32] [核] (D)
- etf.com（2025）：美国 1139 只 smart beta ETF，2.1 万亿美元。[US-33] [摘] (D)

**因子动物园与复制危机（学术）**
- Harvey, Liu & Zhu（2016）：至少 316 个已发表因子，建议 t 值门槛从 2.0 提到 3.0。[US-34] [核] (D)
- McLean & Pontiff（2016）：97 个预测变量，发表后平均衰减"约 50%，统计上既不等于 0% 也不等于 100%"。[US-35] [核] (D)
- Hou, Xue & Zhang（2020）：452 个异象（含 69 个价值成长、38 个投资、79 个盈利能力、103 个无形资产类），用 NYSE 分界点和市值加权后 65% 不显著。[US-36] [核] (D)
- López de Prado："实证金融里的大多数发现都是假的，这是多重检验下选择偏差的结果。"[US-37][US-38] [核] (P)

**价值因子 2007–2020 回撤与争论**
- Fama & French《The Value Premium》（2020）：大盘股价值溢价从 0.36%/月（1963–1991）降到"微不足道的 0.05%"（1991–2019.6），但"月度溢价波动太大，无法拒绝两段预期溢价相同的假设"。[US-39][US-40] [核] (D)
- Ken French（2020 年 1 月）："没有办法判断"预期价值溢价是否已经下降。[US-41] [摘] (P)
- Arnott, Harvey, Kalesnik & Linnainmaa《Reports of Value's Death May Be Greatly Exaggerated》（2021）：HML 自 2007 年起回撤 55%（截至 2020 年中），归因于账面价值漏掉无形资产、以及价值变得相对更便宜；把无形资产资本化后"大幅跑赢传统度量"。[US-42][US-43] [核] (D)
- **Cliff Asness《Is (Systematic) Value Investing Dead?》（2020-05-08）**：开篇就是"No it's not."AQR 的复合价值利差是"有史以来最宽"，超过 2000 年科技泡沫和 2008 年；"我们相信坚持流程是获得长期收益的唯一途径"。他对 FT 说 2018–2020 是"我见过最艰难的一段"。[US-45][US-46][US-47] [核] (P, AQR 自有出版物)
- **AQR 规模**：2018 年峰值 2260 亿美元 → 2020 年约 1430 亿 → 2021 年 11 月 1370 亿（"近 40% 下滑"）；Form ADV 口径 2019 年 2489 亿 → 2020 年 1644 亿；员工数大约减半。[US-48][US-49][US-50] [核] (D/P)
- **Renaissance RIEF**：2020 年亏 22.62%（同年 Medallion +76%），规模从约 360 亿美元降到不足 200 亿。[US-51] [核] (P)

### 1.5 2020 年代：反弹、机器学习、另类数据、平台化

**价值反弹**：Fama-French 美国 HML 因子 2021 年 +13.2%、2022 年 +28.8%，Dimensional 称这是"有记录以来最好的两年之一"；Russell 1000 价值 2022 年跑赢成长 22 个百分点，2023 年又反过来输 23 个百分点。[US-53][US-54] [核] (D/F)

**机器学习进入基本面信号（学术）**
- Gu, Kelly & Xiu（2020, *RFS*）：树模型与神经网络最好，收益来自"非线性预测变量交互"，"某些情况下把基于回归的领先策略表现翻倍"。[US-56] [核] (D)
- Lopez-Lira & Tang（2023）：ChatGPT 给新闻标题打分能预测次日收益，GPT-1/2 和 BERT 不能，"收益可预测性是复杂模型的涌现能力"。[US-57] [核] (D)
- Kelly, Malamud & Zhou《The Virtue of Complexity in Return Prediction》（2024, *J. Finance*）：参数多于样本的模型预测更好。[US-58] [核] (D)

**从业者原话**
- **Bryan Kelly（AQR 机器学习负责人）**："有时你会在市场数据里发现可靠的规律，但对它为什么存在没有很好的经济直觉……如果仅仅因为不理解原因就丢掉可靠的预测信号，我会称之为糟糕的科学，当然也是糟糕的资产管理。"关于 LLM："在金融里问题非常不同……市场之所以有效，是因为它极度竞争。"[US-59][US-60] [摘] (P)
- **Igor Tulchinsky（WorldQuant，2025 年 5 月 Forbes）**："我们有几百万几百万个 alpha 的库存"；"我们交易涟漪，不交易浪潮"；"我们可以用 AI 和 LLM 在不同领域转换和发现 alpha"。[US-61][US-62] [摘] (P)
- **Ronald Kahn（BlackRock Systematic，2025 年 12 月 Bloomberg）**：BlackRock Systematic 两年净流入超过 400 亿美元、管理 3780 亿美元；Kahn 称系统"十年里有八九年会跑赢基金经理"。[US-63] [摘] (P)

**另类数据支出（数据商）**：Neudata 估计 2024 年投资管理行业在另类数据上至少花 25 亿美元（宽口径 127 亿），2024 年增速 34%；受访买方平均使用 20 家供应商、年均花费 160 万美元，最大的量化/多策略买方平均 43 个数据集。[US-65][US-66] [核] (D)

**多经理平台**：高盛主经纪商数据（经二手转引）显示多策略基金 2025 年达到 4280 亿美元，2017–23 年增长 175%（行业整体 13%）。[US-67] [未核] (二手)

### 1.6 现状（2024–2026）

| 机构 | 规模 | 时点 | 核实 |
|---|---|---|---|
| Dimensional | 全球 AUM 突破 1 万亿美元；ETF 资产 2023 年破 1000 亿，后破 2000 亿 | 2026-02-09 | [核] (F) [US-68][US-69] |
| AQR | 约 1790 亿美元（Bloomberg）；对冲基金 AUM 2025 年从 577 亿增至 1091 亿（+89%），取代 Bridgewater 登顶 | 2025 | [核] (P/D) [US-71][US-72][US-73] |
| BlackRock Systematic | 3780 亿美元 | 2025-12 | [摘] (P) [US-63] |
| Acadian | 1775 亿美元；2025 年连续八季净流入合计 294 亿 | 2025-12-31 | [核] (D, 10-K) [US-21] |
| LSV | 约 1230 亿美元 | 2026-06-30 | [核] (F) [US-19] |
| Two Sigma | 超过 700 亿美元（创纪录） | 2025 末 | [摘] (P) [US-75] |
| 美国 smart beta ETF | 2.1 万亿美元 | 2025 | [摘] (D) [US-33] |

**David Booth（DFA 破万亿新闻稿，2026-02-09）**："四十五年前，我们出发去帮助人们找到一种更好的投资方式。这是一种基于学术研究和对公开市场如何运作的合理理念的方法……"[US-68] [核] (F)

---

## 2. 中国：基本面量化的演进

### 2.1 起源（2002–2013）：BGI 海归潮

- 2002 年华安上证 180 指数增强被部分资料称为首只公募量化基金；2004 年光大保德信量化核心（证监基金字[2004]85 号）是最早以"量化"命名的基金之一。[CN-1][CN-2] [核] (D, 基金公告)
- **2009 年**：李笑薇（原 BGI 大中华主动股票投资总监）加盟富国，建立"国内首个公募量化投资团队"，2009-12-16 发行富国沪深 300 增强，被称为"国内首只量化增强基金"。[CN-3][CN-4] [核] (M)
- **2012 年**：田汉卿（原 BGI，2005–2008 管理香港市场中性策略）加盟华泰柏瑞；黎海威（原 BGI）加盟景顺长城。[CN-2][CN-5] [核] (M)
- 黎海威 2013 年 10 月专访称基本面量化"本质是主动投资"。[CN-6] [摘] (P)
- 2013-12-06 嘉实绝对收益策略成立，是首只公募对冲基金；到 2015-06-30 公募对冲产品 9 只、273 亿元。[CN-7] [摘] (M)

**这一代的方法论就是美国 BGI 那套**：基本面多因子 + 风险模型 + 低跟踪误差的指数增强。

### 2.2 公募量化规模（按年份）

| 时点 | 总规模 | 分项 | 来源 / 核实 |
|---|---|---|---|
| 2018-09-30 | 约 560 亿（162 只） | — | 银河证券 [CN-8] [摘] |
| 2019 年底 | 1605 亿 | 主动量化 682 / 指增 849 / 对冲 74 | 招商证券 [CN-10] [核] (D) |
| 2021 年底 | 2828 亿 | 主动量化 806 / 指增 1518 / 对冲 504 | 招商证券 [CN-10] [核] (D) |
| 2023 年底 | 2982 亿（498 只，同比 +25%） | 主动 1140（+56%）/ 指数型 1759；对冲较 2020 年末缩水超八成 | 中国基金报引 Wind [CN-11] [核] (D) |
| 2024 年底 | 接近 3000 亿 | 指增 2128 亿，创新高；新发 99 只/396 亿 | 中信建投 [CN-12] [核] (D) |
| 2025 年底 | 4041 亿（840 只） | 指增 67%、全市场量化选股 27%、行业主题 5%、对冲 1% | 年报盘点 [CN-13] [摘] |
| 2026 Q1 | 1.74 万亿（华泰金工口径，含指增 9987 亿） | — | [CN-14] [未核] 口径与上表差异原因不明 |

注意：梁文峰 2019 年说的"公募 1200 亿做基本面量化"，与招商证券 2019 年底 1605 亿（其中主动量化 682 亿 + 指增 849 亿）大体是一个量级，可以互相印证。2015 年公募量化总规模没有找到可靠数字。[未核]

### 2.3 关键事件

- **2017 年"大票行情"**：沪深 300 全年涨逾 20%，"许多暴露在小市值因子上的组合遭遇回撤"，量化基金全年平均收益不到 1%，长信量化先锋跑输沪深 300 达 35.5 个百分点，大摩多因子落后超 40 个百分点；而偏价值的景顺长城量化新动力以 33.2% 排股票型第 19。[CN-15][CN-16] [核] (M, 中证网)
  - **招商基金王平**因 2017 年回撤"大幅降低技术面因子权重，提高基本面因子权重"，形成 PB-ROE 框架。[CN-17] [摘] (P)
  - 这一年对应梁文峰说的"2017 年以前多因子是万能的，2017 年之后行业发生变化"。公募基本面量化的"小盘 + 反转"暴露在 2017 年被市场风格逆转打穿，而私募则转向量价 + AI。
- **2021 年指增爆发**：2021-11-15 首批指数增强 ETF 获批，中证 500/1000 指增成为公私募布局最密集的方向。[CN-18] [核] (M)
- **2023–2024 公募量化回归**：2023 年主动量化规模创 2018 年以来新高，2024 年指增规模新高、114 家基金公司布局，2025 年指增申报量激增 206%。[CN-11][CN-12][CN-19] [核] (D/M)
- **2025 年 4 月华泰金工《基本面量化的当下和未来：策略篇》**："在量价策略同质化加剧的背景下，基本面量化凭借清晰的投资逻辑、较大的策略容量和差异化优势重新受到市场关注"。[CN-20] [摘] (D, 券商研报)

### 2.4 私募：从量价 alpha 到"降频、做基本面"

**2010–2016**
- 2010-04-16 沪深 300 股指期货上市，市场中性策略成为可能；早期"低到中频、算法简单的 alpha 策略也能获得非常理想的超额"；2014 年末大小盘风格切换导致量化产品集体回撤。[CN-21] [摘] (M)
- 2015 年 9 月起中金所把非套保保证金提到 30%，股指期货"几近全面受限"，长期深度贴水拖累中性策略。[CN-22] [核] (D, 学术案例)

**2017–2021：量价 + AI，规模破万亿**
- **九坤王琛**："大概 2018 年之前，国内量化还是以量价数据 + 人工挖掘的方式为主。在 2018 年之后，整个市场开始逐渐进入 AI 算法的时代……到 2020 年，量化行业已经到了大数据 + AI 算法的阶段。"[CN-23] [摘] (P)
- **梁文峰 2019-08-30 演讲**（上海，2019 金牛私募高峰论坛暨第十届中国私募金牛奖颁奖典礼，题为《一名程序员眼里中国量化投资的未来》）。除截图中的四分类和"公募 1200 亿"外，搜索摘要还转述了：
  - "人类投资者分两个流派：技术面和基本面。现在量化赚的是技术面流派原来赚的钱……未来，程序最终也要抢夺基本面流派原来赚的钱，但达到量化高度仍需几个摩尔定律的周期。"
  - "量化私募的进步也符合摩尔定律，每 18 个月投资能力翻一番。"
  - "程序有两三千亿的钱每天在做同样的事情，使得市场的有效性大幅度提高了。"
  - "作为对冲基金，我们的使命是提高中国二级市场的有效性。"
  - 他估算当时投入中国市场的量化资金 2500–5000 亿，超过一半在股票策略。
  [CN-24][CN-25][CN-26] [摘] (P) — 全文转载在新浪财经（2025-01-26）、雪球、BigQuant，本环境无法抓取；2019 年原始发布链接未找到。
- **明汯裘慧明（2020）**："单就 A 股而言，统计套利策略容量能够在 5000–10000 亿之间，基本面量化容量在 3 万亿–10 万亿之间"；"基本面的量化策略是基于市场会把基本面的所有信息在几个月的周期上正确反映在价格上的一个假设"。[CN-27][CN-28] [摘] (P)
- **2021 年破万亿**：中信证券估算 2021 Q2 末量化证券私募 1.034 万亿，占证券私募的 21%；2021 年底百亿量化私募 27 家。[CN-29][CN-30] [核] (D)

**2022–2023：超额收敛，"降频"成共识**
- 中信证券测算 2023 Q3 量化私募 1.58 万亿，占证券私募约 27%。[CN-32] [核] (D)
- 中国基金报 2023-09-03《量化降频或成趋势，基本面量化策略渐受关注》："头部量化私募每年换手率约 40–60 倍……超额收益会逐渐收敛，量化降频将是行业未来发展的趋势。与此同时，基本面量化逐渐受到关注。"[CN-34] [摘] (M)
- **幻方徐进（2021 年前后）**："幻方近几年重点研究基本面因子……当市场竞争激烈后，仅依靠技术面因子获得稳定超额收益会变得越来越难，因此需要在基本面量化选股上进行下一步准备。"[CN-35] [摘] (P)
- **世纪前沿**：2020 年起"量价策略研究达到较高水平后，开始探索基本面数据、另类数据等更多信息源"；高/中/低频收益贡献约 10–15% / 40–45% / 40–45%。规模进入 300–400 亿后把高频占比从 50% 降到 30%。[CN-36] [摘] (P)
- **灵均马志宇**："量化基本面是海外的热门方向，即把主观看法形成数据因子……与传统量化结合会形成一定优势。"[CN-37][CN-38] [摘] (P)
- 浙商证券：2022 年中证 1000 指增超额高点 20.4%；2024 年 300 指增超额首次转负（-0.64%），500/1000 指增超额降到 6.2%/10.6%。[CN-39] [摘] (D)

**2024：小微盘危机、DMA 去杠杆、融券收紧**
- 2024-02-05 至 02-08 四个交易日，量化中性产品周度亏损约 7 个点，头部机构中性产品普遍跌超 10%；DMA 规模从峰值约 2500 亿降到不足 1500 亿；灵均 2024-02-19 因一分钟内卖出 13.72 亿深市股票被限制交易三日。[CN-40][CN-41] [核] (M, 多源一致)
- 2024-02 转融券 T+0 改 T+1，2024-07-11 起暂停转融券，融券保证金比例升至 100%（私募 120%）；"大部分管理人都在降频，往中低频走"。[CN-42][CN-43] [核] (D, 监管公告)
- 2024 年 6 月底股票量化私募规模降到约 7800 亿（较 2023 年底降逾 35%，中信证券）；2024 上半年量化多头平均超额 -2.49%（私募排排网）。[CN-33][CN-44] [核] (D)
- 2024-10-18 幻方公告"逐步将对冲全系产品投资仓位降低至 0"，退出市场中性。[CN-45] [核] (M)

**2025–2026：程序化交易新规与新一轮扩张**
- 沪深北交易所《程序化交易管理实施细则》2025-07-07 施行，高频认定：单账户每秒申报/撤单 ≥300 笔或全日 ≥20000 笔；媒体评价行业"从微秒级速度竞争转向中低频策略有效性竞争"。[CN-46] [核] (D, 新华网/交易所)
- 浙商证券金工：2025 年末量化基金总规模 3.22 万亿（占私募证券基金超 43%；2020 年仅 0.76 万亿），其中量化指增 1.19 万亿、股票中性 0.74 万亿、量化选股 0.54 万亿、量化 CTA 0.37 万亿。[CN-47] [摘] (D)
- 2025 年 12 月百亿量化私募 55 家，占 118 家百亿私募的 46.6%。[CN-49] [核] (D, 私募排排网)
- **基本面 vs 量价的资金占比没有任何官方统计**，只有定性描述"从纯高频量价向融合基本面的中低频策略转移"。[CN-50] [未核]
- 2026 年 7 月百亿量化单月亏损超 15%、幻方年内转负，超额再度"跌下神坛"。[CN-51] [摘] (M)

### 2.5 从业者对"基本面量化"的判断（原话汇总）

| 人物 | 机构 | 观点 | 核实 |
|---|---|---|---|
| 田汉卿 | 华泰柏瑞（原 BGI） | "基本面量化选股模型不同于算法，算法投资找算法就行了……而基本面量化不止如此，它需要有很强的投资逻辑。我们的理念是，投资逻辑在先，数据验证在后。""没有永远有效的因子。"2025 年 4 月退休。 | [摘] [CN-52][CN-53] |
| 李笑薇 | 富国（原 BGI） | "概率是量化投资的核心元素"；基本面量化"要看投资决策是否 make sense，有逻辑比单纯的模拟结果更重要"。 | [摘] [CN-3] |
| 黎海威 | 景顺长城（原 BGI），2024-04 | "近些年量价策略受到市场更多关注，主要是因为这类策略较好地利用了投资宽度与降息环境下的小市值效应共振；但随着宏观和市场的变化，基本面量化为导向的策略可能迎来阶段性的修复行情"；模型"在 AI 支持下演变成多周期、多模态……最终向基本面与机器学习深度结合的方向迈进"。景顺长城覆盖价值、质量、情绪、ESG 等 300 多个因子。 | [摘] [CN-54][CN-55] |
| 王平 | 招商基金 | 2017 年后"以基本面为主、技术面为辅"，PB-ROE 框架。 | [摘] [CN-17] |
| 盛丰衍 | 西部利得 | "七分量化、三分主观"；"做好基本面量化的核心在于分域建模：不同行业有不同的模型"；中证 1000"适合用非线性机器学习模型在量价数据中挖掘规律"。 | [摘] [CN-56] |
| 裘慧明 | 明汯，2023-04 | 明汯策略中"约有 5% 左右是基本面因子，但主流仍以价量类策略为主"；"长周期的投资来讲，主观投资更有优势；中短期的投资来看，量化更有优势"。因子储备覆盖量价、基本面、另类数据、事件驱动，"基本面因子容量更大、未来超额潜力更高"。 | [摘] [CN-57][CN-27] |
| 王琛 | 九坤，2021-07 | "大家都在想如何用量化去做基本面，这是所有量化公司都在考虑的问题。在 A 股做量化基本面……国内基本面的研究信息和数据对于量化来说并不是那么充分"，尝试用 NLP 从"几百万篇研究报告"提取信息。 | [摘] [CN-58] |
| 梁文峰 | 幻方，2019-08 | 见 2.4；"未来，程序最终也要抢夺基本面流派原来赚的钱，但达到量化高度仍需几个摩尔定律的周期"。 | [摘] [CN-24] |
| 媒体综述 | 2025 | "传统多因子不会消失，但它的'生产方式'已经从手工业升级为 AI 工厂"；某头部私募披露深度学习对收益贡献约 42%。 | [未核] [CN-59] |

---

## 3. 中美对照

| 维度 | 美国 | 中国 |
|---|---|---|
| 起点 | 1968–1993 学术异象 → 1981 DFA、1994 LSV、1998 AQR | 2009–2012 BGI 海归到公募建团队 |
| 方法论来源 | 自产：会计学 + 金融学期刊 | 进口：BGI/BARRA 框架，再本土化（PB-ROE、分域建模） |
| 主导资金 | 养老金、捐赠基金，容忍十年逆风 | 公募零售 + 私募高净值，对短期超额敏感 |
| 基本面在量化中的地位 | 主体（DFA、AQR、LSV、Acadian 的核心） | 配角（裘慧明：约 5%）；公募主战场，私募副线 |
| 为什么 | 机构化市场，量价 alpha 早已被 HFT 分走；基本面数据长、全、准 | 散户占比高，量价 alpha 肥；基本面数据"不够充分"（王琛）；换手率高、T+1 |
| 关键危机 | 2007 量化地震（基本面因子踩踏）、2018–2020 价值回撤、2020 新冠 | 2017 大票行情（小盘暴露）、2024 小微盘/DMA 危机、2026 年 7 月超额回撤 |
| 危机后的走向 | 坚守（Asness "No it's not"）+ 无形资产修正 + 机器学习 | 降频、退出中性（幻方）、转向基本面与另类数据 |
| 监管推力 | ERISA、Reg NMS、Dodd-Frank | 2015 股指期货限制、2024 融券收紧、2025 程序化交易细则 |
| 产品化 | Smart Beta ETF 2.1 万亿美元，费率几个 bp | 公募指增 2025 年底约 2700 亿人民币，费率仍有 1% 左右 |
| AI 的角色 | 信号工厂（WorldQuant 百万 alpha）、LLM 读文本（AQR Kelly） | 先在量价上 AI 化（2018–），再往基本面 + NLP 延伸（九坤读研报） |
| 现状（2025–26） | AQR、DFA、Acadian、BlackRock Systematic 规模创新高 | 量化私募 3.22 万亿、公募量化 4041 亿创新高，但基本面占比无统计 |

**对梁文峰 2019 年判断的回看**：
- "多因子 2017 年后被 AI 取代、2019 年后被集成框架取代"——这是**私募量价**路线的写照，公募基本面量化并没有走这条路，田汉卿、黎海威、王平至今强调"逻辑在先"。
- "程序最终也要抢夺基本面流派的钱，但需要几个摩尔定律周期"——2019 到 2026 约 4–5 个"18 个月"周期，基本面量化已经从"不是重点"变成头部私募的公开方向（幻方、九坤、明汯、世纪前沿、灵均都有表态），但从裘慧明的 5% 和"没有占比统计"看，还远没有成为主流收益来源。美国的经验是这个过程需要**数据基础设施**（CRSP/Compustat 领先几十年）和**耐心资本**两个条件，A 股这两个条件在 2026 年都还在建设中。

---

## 4. 我推荐的优质信息来源（按你的标准）

**客观数据**
- 美国：Ken French 数据库（因子月度序列，1926 年起）；SEC EDGAR（10-K、8-K、Form ADV，能查到 AQR、Acadian 等的真实规模）；Morningstar / ETFGI（Smart Beta 规模）；NBER / SSRN / RFS / JF / JFE（论文原文）。
- 中国：招商证券、中信建投、华泰金工、浙商金工的年度量化基金盘点（公募口径最一致）；中信证券对量化私募规模的测算；私募排排网、朝阳永续（百亿私募数量、超额统计）；交易所与证监会公告（监管文件原文）；巨潮资讯（基金招募说明书）。

**业内代表人物**
- 美国：Cliff Asness（AQR 官网 Perspectives 全文公开）、Andrew Lo（MIT 网页有 2007 论文）、Ken French / Eugene Fama（Fama-Miller 工作论文）、Rob Arnott（Research Affiliates）、Bryan Kelly（AQR）、Ronald Kahn（CFA Research Foundation 2018 专著免费）。
- 中国：梁文峰 2019 演讲全文（新浪财经 2025-01-26 转载）、裘慧明（复旦 FISF 讲堂、21 经济网）、王琛（上证报对话）、黎海威（景顺长城官网）、田汉卿（财新朱昂访谈）、盛丰衍（上证报）。

**本文未能核实、建议你优先核对的项目**
1. 梁文峰演讲中"1200 亿"一句的精确措辞与 2019 年原始发布链接；
2. Piotroski 23.5% 年化、Asness"4 个标准差"利差、多经理平台 4280 亿美元——均为二手；
3. 2015 年公募量化总规模；2026 Q1 华泰金工 1.74 万亿与其他口径的差异；
4. 2025–2026 年私募策略中基本面 vs 量价的任何占比统计——目前没有找到。

---

## 来源列表

### 美国（US-）
- [US-1] Ball & Brown after fifty years, https://www.sciencedirect.com/science/article/abs/pii/S0927538X18306395 (D)
- [US-2] PEAD review, https://jkatz.caltech.edu/documents/28622/peads.pdf (D)
- [US-3] https://en.wikipedia.org/wiki/Post%E2%80%93earnings-announcement_drift (二手)
- [US-4] Fama & French 1992, https://onlinelibrary.wiley.com/doi/10.1111/j.1540-6261.1992.tb04398.x (D)
- [US-5] LSV 1994, https://onlinelibrary.wiley.com/doi/abs/10.1111/j.1540-6261.1994.tb04772.x (D)
- [US-6] https://www.stockopedia.com/content/the-accrual-anomaly-why-investors-should-care-about-accruals-earnings-quality-63003/ (二手)
- [US-7] Dechow, Khimich & Sloan, https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1793364 (D)
- [US-8] Piotroski F-Score, https://www.anderson.ucla.edu/documents/areas/prg/asam/2019/F-Score.pdf (D)
- [US-9] Novy-Marx 2013, https://www.sciencedirect.com/science/article/abs/pii/S0304405X13000044 (D)
- [US-10] MSCI, https://www.msci.com/documents/10199/2ef5bba7-8448-44da-bdb3-0a102374c8d3 (D)
- [US-11] Robeco, https://www.robeco.com/en-int/insights/2024/10/fama-french-5-factor-model-why-more-is-not-always-better (F)
- [US-12] Jacobs Levy, https://jlem.com/who-we-are (F)
- [US-14] Grinold & Kahn, https://books.google.com/books/about/Active_Portfolio_Management_PB.html?id=aSDkFQtysy8C
- [US-15] Institutional Investor on BGI, https://www.institutionalinvestor.com/article/2btghxk28lv1wj4s8nx8g/home/for-whom-the-barbell-tolls (M)
- [US-17] Dimensional small-cap history, https://www.dimensional.com/us-en/insights/the-evolution-of-small-cap-investing-four-decades-of-innovation-at-dimensional (F)
- [US-18] https://www.optimizedportfolio.com/dfa-etfs/ (二手)
- [US-19] LSV, https://www.lsvasset.com/ (F)
- [US-21] Acadian 10-K, https://www.sec.gov/Archives/edgar/data/1748824/000162828026012856/aami-20251231.htm (D)
- [US-24] RIEF, https://www.institutionalinvestor.com/article/2bszs92ot4qg5gdk7uv40/portfolio/jim-simons-reaping-reward-for-patience-on-rief (M)
- [US-25] Khandani & Lo NBER w14465, https://www.nber.org/papers/w14465 (D)
- [US-26] https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1288988 (D)
- [US-27] https://web.mit.edu/Alo/www/Papers/august07b.html (D)
- [US-28] Goldman 8-K Aug 2007, https://www.sec.gov/Archives/edgar/data/0000886982/000089534507000454/ex99.htm (D)
- [US-29] https://www.cnbc.com/id/44549144 (M)
- [US-30] Morningstar, https://www.morningstar.com/funds/strategic-beta-etf-market-has-matured-that-doesnt-mean-partys-over (D)
- [US-31] Morningstar, https://www.morningstar.com/etfs/strategic-beta-landscape-today (D)
- [US-32] ETFGI, https://etfgi.com/news/press-releases/2024/03/etfgi-reports-assets-us156-trillion-are-invested-smart-beta-etfs-listed (D)
- [US-33] etf.com, https://www.etf.com/sections/news/morningstar-seek-smart-beta-etfs-volatile-markets (D)
- [US-34] Harvey, Liu & Zhu, https://www.nber.org/papers/w20592 (D)
- [US-35] McLean & Pontiff, https://onlinelibrary.wiley.com/doi/abs/10.1111/jofi.12365 (D)
- [US-36] Hou, Xue & Zhang, https://academic.oup.com/rfs/article-abstract/33/5/2019/5236964 (D)
- [US-37] López de Prado, https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3177057 (D)
- [US-38] Risk.net, https://www.risk.net/investing/quant-investing/6993166/some-quant-shops-doomed-to-struggle-lopez-de-prado (M)
- [US-39] Fama & French, The Value Premium, https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3525096 (D)
- [US-40] Chicago Booth Review, https://www.chicagobooth.edu/review/value-stock-premium-shrinking (M)
- [US-41] Ken French interview, https://www.institutionalinvestor.com/article/b1k3pd2z3ptx9g/Ken-French-There-Is-No-Way-to-Tell-If-Value-Premium-Is-Disappearing (P)
- [US-42] Arnott et al., https://people.duke.edu/~charvey/Research/Published_Papers/P149_Reports_of_values.pdf (D)
- [US-43] https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3488748 (D)
- [US-44] Israel, Laursen & Richardson, https://jpm.pm-research.com/content/early/2020/11/20/jpm.2020.1.194 (D/F)
- [US-45] Asness 2020-05-08, https://www.aqr.com/-/media/AQR/Documents/Perspectives/Cliffs-Perspective-5620-Is-Systematic-Value-Investing-Dead.pdf (P/F)
- [US-46] https://www.institutionalinvestor.com/article/2bsx9vf41a9s1m8ihrs3k/portfolio/cliff-asness-said-to-buy-value-the-market-quickly-and-violently-punished-him (M)
- [US-47] https://www.institutionalinvestor.com/article/2bswwnlydwnuijimpr4e8/portfolio/after-its-toughest-period-ever-aqr-is-making-a-big-comeback (M)
- [US-48] https://www.ai-cio.com/news/quant-hedge-fund-icon-aqr-cuts-back-as-investors-exit/ (M)
- [US-49] https://en.wikipedia.org/wiki/AQR_Capital_Management (二手)
- [US-50] AQR Funds 485BPOS, https://www.sec.gov/Archives/edgar/data/1444822/000119312522019888/d274837d485bpos.htm (D)
- [US-51] https://www.institutionalinvestor.com/article/2bswms7wco7as686o8ikg/portfolio/renaissances-medallion-fund-surged-76-in-2020-but-funds-open-to-outsiders-tanked (M)
- [US-52] https://medium.com/@quantavista/the-quantamental-investing-buzz-b7f2a1a5530d (二手，引 NYT 2017-03)
- [US-53] Dimensional, https://www.dimensional.com/us-en/insights/right-foot-green-for-value (F)
- [US-54] Oakmark, https://oakmark.com/news-insights/value-vs-growth-then-and-now-u-s-equity-market-commentary-3q23/ (F)
- [US-56] Gu, Kelly & Xiu, https://academic.oup.com/rfs/article/33/5/2223/5758276 (D)
- [US-57] Lopez-Lira & Tang, https://arxiv.org/abs/2304.07619 (D)
- [US-58] Kelly, Malamud & Zhou, https://onlinelibrary.wiley.com/doi/full/10.1111/jofi.13298 (D)
- [US-59] https://www.fa-mag.com/news/aqr-bets-on-machine-learning-as-cliff-asness-becomes-ai-believer-82224.html (M)
- [US-60] https://www.institutionalinvestor.com/article/2bsts3iaff2qv8b9rg8w0/portfolio/aqr-experiments-with-gpt-to-improve-returns (M)
- [US-61] Forbes on Tulchinsky, https://www.forbes.com/sites/johnhyatt/2025/05/16/this-billionaire-quant-is-turbocharging-his-trading-models-with-chatgpt-style-ai/ (P)
- [US-62] Bloomberg 2018, https://prod.cm.bloomberg.com/news/articles/2018-09-18/worldquant-s-tulchinsky-talks-bad-quants-100-million-alphas (P)
- [US-63] Bloomberg 2025-12-11, https://www.bloomberg.com/news/articles/2025-12-11/blackrock-s-crew-of-quant-phds-are-on-track-for-a-record-year ；镜像 https://www.fa-mag.com/news/blackrock-s-crew-of-quant-phds-are-on-track-for-a-record-year-85181.html (P)
- [US-64] Kahn, The Future of Investment Management, https://rpc.cfainstitute.org/sites/default/files/-/media/documents/book/rf-publication/2018/future-of-investment-management-kahn.pdf (P/D)
- [US-65] Neudata, https://www.neudata.co/press-release/alternative-data-spending-by-investment-management-firms-could-top-15-4bn-in-2025-according-to-neudata-s-latest-report (D)
- [US-66] https://www.prnewswire.com/news-releases/alternative-data-budgets-projected-to-rise-in-2025-according-to-neudatas-the-future-of-alternative-data-report-302251059.html (D)
- [US-67] https://navnoorbawa.substack.com/p/how-millennium-citadel-and-point72 (二手，引高盛)
- [US-68] Dimensional $1tn, https://www.dimensional.com/sg-en/newsroom/dimensional-fund-advisors-crosses-1-trillion-in-global-assets-under-management (F)
- [US-69] https://www.dimensional.com/us-en/newsroom/dimensional-crosses-100-billion-in-etf-assets-under-management (F)
- [US-71] Bloomberg 2025-12-15, https://www.bloomberg.com/news/articles/2025-12-15/aqr-roars-back-with-179-billion-in-assets-and-taste-for-secrecy (P)
- [US-72] Morningstar AQR, https://www.morningstar.com/asset-management-companies/aqr-BN00000BVN (D)
- [US-73] https://alternativefundinsight.com/aqr-tops-hedge-fund-power-list-after-89-aum-growth/ (M)
- [US-75] https://www.hedgeweek.com/two-sigma-raises-1-1bn-across-new-funds-as-assets-hit-record-70bn/ (M)

### 中国（CN-）
- [CN-1] 光大保德信量化核心招募说明书（巨潮），http://static.cninfo.com.cn/finalpage/2005-04-11/15206707.html (D)
- [CN-2] 《量化投资发展史：野蛮、乱象、科学》，https://finance.sina.com.cn/roll/2020-05-31/doc-iircuyvi5947270.shtml (M)
- [CN-3] 展恒基金《量化"增强基"首推者李笑薇》，https://www.myfund.com/article/1314.html (M)
- [CN-4] 《中国指数增强基金发展历程分析》2025-06-14，https://finance.sina.com.cn/roll/2025-06-14/doc-infaaauf9708666.shtml (M)
- [CN-5] 上证报《华泰柏瑞田汉卿：A 股量化投资渐入佳境》2017-03-06，https://paper.cnstock.com/html/2017-03/06/content_786877.htm (M)
- [CN-6] 黎海威 2013-10-16 专访，https://finance.sina.cn/sa/2013-10-16/detail-ikftssan5156694.d.html (P)
- [CN-7] 富善投资《秒懂量化对冲（二）》，https://www.fsfund.com/news/2015/08/13/103307/1.shtml (F)
- [CN-8] 银河证券量化基金分析 2018-12-25，https://bigquant.com/wiki/doc/_20181225_-qxzbl3zpje (D)
- [CN-9] BigQuant 公募量化基金大梳理，https://bigquant.com/square/paper/7d10844c-5569-470f-b96a-4dc0d9c9c4fe (D)
- [CN-10] 招商证券《公募量化基金 2021 年度盘点》，https://stock.finance.sina.com.cn/stock/go.php/vReport_Show/kind/11/rptid/695558170588/index.phtml (D)
- [CN-11] 《公募量化基金产品规模创下新高》2024-01-27，https://finance.sina.com.cn/money/fund/jjyj/2024-01-27/doc-inaeynxt8751493.shtml (M/引 Wind)
- [CN-12] 中信建投《公募量化基金 2024 年度盘点》，https://news.qq.com/rain/a/20250124A01U1E00 (D)
- [CN-13] 《2026 公募基金年报｜量化与指增》，https://www.sohu.com/a/989784351_121118715 (M)
- [CN-14] 华泰金工《公募量化产品一季度盘点》，https://www.sohu.com/a/1009629429_122014422 (D)
- [CN-15] 中证网 2017-07-16，https://www.cs.com.cn/xwzx/201707/t20170716_5375509.html (M)
- [CN-16] 中证网 2017-12-05，https://www.cs.com.cn/tzjj/201712/t20171205_5607793.html (M)
- [CN-17] 聪明投资者《招商王平"独善其身"的秘诀》，https://www.cmtzz.cn/article/56900 (P)
- [CN-18] 深圳新闻网 2021-11-26，https://www.sznews.com/news/content/2021-11/26/content_24771023.htm (M)
- [CN-19] 《指数增强产品申报量激增 206%》2025-04-07，https://finance.sina.com.cn/roll/2025-04-07/doc-inesincs1407788.shtml (M)
- [CN-20] 华泰金工《基本面量化的当下和未来：策略篇》2025-04-01，https://finance.sina.com.cn/roll/2025-04-01/doc-inersqma7122114.shtml (D)
- [CN-21] 《忽冷忽热！颠簸的量化私募发展史》，https://www.sohu.com/a/503656622_156758 (M)
- [CN-22] 人大《关于 2015 股指期货限制交易效应的案例研究》，http://sf.ruc.edu.cn/publish/sf/alk/alfl/jr/fb96371b1bc54ecf8a5410bc7f68cfe7.htm (D)
- [CN-23] 上证报《对话九坤投资 CEO 王琛》2022-07，https://edu.cnstock.com/e_jjdx/ejj_zf/202207/4927916.htm (P)
- [CN-24] 《梁文锋 2019 年演讲：所有原来人类做的策略，现在量化都在做》2025-01-26，https://finance.sina.com.cn/jjxw/2025-01-26/doc-ineiptpc4208799.shtml (P)
- [CN-25] 《DeepSeek 创始人梁文锋 5 年前的演讲》2025-02-14，https://finance.sina.com.cn/roll/2025-02-14/doc-inekmyqz0777228.shtml (P)
- [CN-26] BigQuant 转载，https://bigquant.com/wiki/doc/RneX6Adhum ；雪球 https://xueqiu.com/1039527614/367019423 (P)
- [CN-27] 21 经济网《明汯裘慧明：量化投资策略拥有万亿市场容量》2020-07-10，http://www.21jingji.com/article/20200710/herald/6e8928c72be8e9540bd7be22671d773e.html (P)
- [CN-28] 2020-05-12，https://finance.sina.com.cn/money/fund/fundzmt/2020-05-12/doc-iirczymk1251925.shtml (P)
- [CN-29] 第一财经《1 万亿：中国量化私募行业的里程碑》，https://www.yicai.com/news/101131948.html (M/引中信证券)
- [CN-30] 财联社，https://www.cls.cn/detail/939242 (M/引私募排排网)
- [CN-31] 2021 年度中国量化投资白皮书，https://d1.awsstatic.com/whitepapers/2021-china-quantitative-investment-white-paper.pdf (D)
- [CN-32] 《风暴眼中的量化私募｜回望 2023》，https://m.163.com/dy/article/IMQBNAPC0534A4SC.html (M/引中信证券)
- [CN-33] 每经《股票量化私募规模降至 7800 亿元》2024-07-15，https://www.nbd.com.cn/articles/2024-07-15/3468400.html (M/引中信证券)
- [CN-34] 中国基金报《量化降频或成趋势，基本面量化策略渐受关注》2023-09-03，https://www.chnfund.com/article/AR2023090312133374306500 (M)
- [CN-35] BigQuant《幻方量化徐进解析深度学习量化》，https://bigquant.com/wiki/doc/zZOS0YnfUx (P)
- [CN-36] 上证报《对话世纪前沿创始人陈家馨》2023-04，https://stock.cnstock.com/stock/smk_jjdx/202304/5040518.htm ；证券时报 2022-06 https://news.stcn.com/sd/202206/t20220605_4615729.html (P)
- [CN-37] 中国基金报《灵均马志宇：用量化重新定义投资之道》2020-10，https://www.chnfund.com/article/AR2020101314224162418589 (P)
- [CN-38] 中证网《灵均蔡枚杰：量化 3.0 时代的三大新趋势》2021-03-23，https://cs.com.cn/tzjj/jjks/202103/t20210323_6149412.html (P)
- [CN-39] 21 财经《量化私募超额收益跌下神坛》2026-08-03，https://m.21jingji.com/article/20260803/herald/175e2b8931ee37863844f794f420903c.html (M/引浙商证券)
- [CN-40] 《四天跌走投资者一年的预期收益》2024-02-20，https://finance.sina.cn/2024-02-20/detail-inaiszxw6675189.d.html (M)
- [CN-41] 21 经济网《公私募复盘量化危机始末》2024-02-21，https://m.21jingji.com/article/20240221/herald/f85c309ebeffb53edf282b0c4fa569b6.html (M)
- [CN-42] 21 经济网《转融券 T+1 正式实施 量化私募降频"进行时"》2024-03-18，https://www.21jingji.com/article/20240318/herald/cb9ad4a88e3517cd8b6cfea519ad999c.html (M)
- [CN-43] 证券时报《证监会出手！今日起暂停转融券业务》2024-07，https://www.stcn.com/article/detail/1255308.html (M)
- [CN-44] 中新经纬，https://www.jwview.com/jingwei/html/07-12/678910.shtml (M/引私募排排网)
- [CN-45] 中国基金报《量化巨头幻方宣布放弃中性策略》2024-10，https://www.chnfund.com/article/AR4be2a3ba-d3e3-9c83-a2b5-3a15b4e5352e (M)
- [CN-46] 新华网《三大交易所程序化交易管理细则 7 月 7 日起实施》2025-04-07，http://www.news.cn/money/20250407/3142c6f5fd1d4b1ebd9eb91910befc5e/c.html (D)
- [CN-47] 《量化基金规模达 3.22 万亿》（引浙商证券），https://www.sina.cn/news/detail/5325757938404961.html ；https://zhuanlan.zhihu.com/p/2041619856768890511 (D/M)
- [CN-48] 《三类资金涌入 规模首破 1.8 万亿元》2026-04-17，https://finance.sina.com.cn/jjxw/2026-04-17/doc-inhuvrey0849045.shtml (M)
- [CN-49] 《八大关键词见证 2025 私募业规模、质量双升》2025-12-31，https://finance.sina.cn/2025-12-31/detail-inherfce4033986.d.html (M)
- [CN-50] 21 经济网《量化步入黄金时代》2026-02-05，https://www.21jingji.com/article/20260205/herald/ba2c5b6526a2a0a01a8b72b8de0c3731.html (M)
- [CN-51] 21 经济网《超额收益祛魅，3 万亿量化私募淘汰赛开启》2026-08-07，https://m.21jingji.com/article/20260807/herald/198d546848d0b5e974e1ec073f456c3c.html (M)
- [CN-52] 财新博客（朱昂）《田汉卿：金牛量化团队的投资之道》，https://zhuang.blog.caixin.com/archives/236066 (P)
- [CN-53] 财联社《量化女将田汉卿退休谢幕》2025-04，https://www.cls.cn/detail/2019475 (M)
- [CN-54] 《景顺长城黎海威：量化投资已进入 AI 时代》2024-04-19，https://finance.sina.cn/fund/jjgdxw/2024-04-19/detail-inashsyn7116663.d.html (P)
- [CN-55] 景顺长城官网《黎海威：量化交易降低净值波动 基本面策略迎新机遇》，http://www.igwfmc.com/main/article/1066436/articleDetail.html (F)
- [CN-56] 上证报《西部利得盛丰衍：增强产品业绩韧性》2025-07-20，https://paper.cnstock.com/html/2025-07/20/content_2096232.htm ；https://zhuanlan.zhihu.com/p/540194205 (P)
- [CN-57] 《明汯裘慧明：量化多头策略核心是长期 Alpha》2023-04-17，https://finance.sina.com.cn/roll/2023-04-17/doc-imyqsaas9108433.shtml (P)
- [CN-58] 《九坤王琛：大数据 + AI 算法是量化行业未来主要增长来源》2021-07，https://www.sohu.com/a/477437852_140434 (P)
- [CN-59] 21 经济网《谁是下一个"幻方"？量化私募鏖战 AI》2025-02-28，https://www.21jingji.com/article/20250228/herald/a255048c111e6731b74e8e71305b12b2.html (M)
- [CN-60] 中信建投《基本面量化投资新时代——2019 年投资策略报告》2018-12，https://pdf.dfcfw.com/pdf/H3_DB201812111267298369_1.pdf (D)
- [CN-61] 招商证券《中国量化私募基金回顾，归因与展望》2021-01，https://www.cls.cn/detail/671312 (D)
