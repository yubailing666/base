---
title: "第十四章——Chemical Kinetics（新版）"
description: "化学动力学：以活化能为核心，串联碰撞理论、速率方程、Arrhenius 方程、催化剂与反应机理"
date: 2026-05-06
draft: false
math: true
tags: [化学, 动力学, 反应速率, 活化能, 催化剂]
categories: [大学化学]
---

> 📖 每个概念配一个生活例子 — 化学来自生活，记例子就是记概念。

---

## 核心：Activation Energy（活化能, $E_a$）

化学动力学的一切，从一个问题开始：**分子凭什么能反应？**

答案是：分子必须翻过一个能量屏障（Energy Barrier）。这个屏障的高度就是 **Activation Energy（活化能, $E_a$）**。

- $E_a$ 高 → 只有极少数分子有足够能量翻过去 → **反应慢**
- $E_a$ 低 → 大部分分子都能翻过去 → **反应快**

**生活例子 — "钻石恒久远"**
钻石（diamond）→ 石墨（graphite）的 $\Delta G < 0$，**热力学上自发**。但钻石在室温下放一万年也不会变成石墨 — 因为 $E_a$ 极高，分子根本翻不过去。**热力学告诉你"能不能"，动力学告诉你"要多久"**。所以钻石的"恒久远"其实是动力学给的，不是热力学。

---

## 枝1：分子怎么"翻越"屏障？

### Collision Theory（碰撞理论）—— 分子凭什么能反应

**Collision Theory（碰撞理论）** 回答了最基本的问题：分子为什么要碰撞才能反应？

三个必要条件：

| # | English | 中文 | 类比 — 扔篮球进篮筐 |
|:-:|:--------|:----|:-------------------|
| 1 | **Collision** | 分子必须**碰撞** | 球必须碰到篮筐才算数 |
| 2 | **Sufficient energy**（$\ge E_a$）| 能量要**超过活化能** | 力气要够大，否则球碰不到筐 |
| 3 | **Proper orientation** | 碰撞**取向要对** | 球要在合适的方向和角度投出去 |

```
必要条件 vs 充分条件：
  碰撞 ✓          + 够能量 ✓          + 方向对 ✓      = 有效碰撞（Effective Collision）
  缺一不可！       缺一不可！          缺一不可！
```

**为什么碰撞是必需的？**
因为反应需要旧键断裂、新键形成。键的断裂和形成只能通过分子靠近时电子的重新排布来完成 — 不靠近，不改键。

**Frequency Factor $A$** 就是 Collision Theory 的量化产物：
$$A = \text{Collision Frequency} \times \text{Orientation Factor}$$
- 撞得越多 → $A$ 越大
- 乱撞之中方向对的比例 → Orientation factor（通常远小于 1）

**生活例子 — 撞球**
桌球（pool）中，母球撞目标球：
- **Collision**：球A必须碰到球B
- **Sufficient energy**：碰到没用，得撞够用力才能把球B送进袋
- **Proper orientation**：即使力大，对着袋口反方向打也进不了 — 方向要对
- 和化学反应完全一样，**缺一不可**。

---

### Reaction Rate（反应速率）

$$v = -\frac{1}{a}\frac{d[A]}{dt} = \frac{1}{c}\frac{d[C]}{dt}$$

本质：**单位时间内翻过去的分子数**。

| 类型 | English | 说明 |
|:---|:--------|:----|
| 平均速率 | **Average rate** | 一段时间内的平均变化 |
| 瞬时速率 | **Instantaneous rate** | 某一时刻的斜率 |
| 起始速率 | **Initial rate** | $t=0$ 时的速率，**最受关注** |

**生活例子 — 开车**
- Average rate = 从广州到深圳的平均速度
- Instantaneous rate = 此刻仪表盘上的速度
- Initial rate = 绿灯亮起那一脚油门 — 这时路况最清晰

### Rate Law（速率方程）

$$v = k[A]^m[B]^n$$

| 符号 | English | 意义 | 它与 Ea 的关系 |
|:----|:--------|:----|:-------------|
| $k$ | **Rate constant**（速率常数） | 反映 **$E_a$ 的影响** | 温度和催化剂通过改变 $k$ 来加速反应 |
| $m, n$ | **Reaction order**（反应级数） | **实验确定**，不等于计量系数 | 告诉你反应的真实微观过程 |
| $[A]^m$ | Concentration term（浓度项） | 反映**碰撞频率** | 改变浓度不影响 $k$，只影响碰撞次数 |

⚠️ **三大铁律（反复考）**：
1. Rate law 必须由**实验**确定 — 不能从 balanced equation 直接写级数
2. Reaction order 只针对**reactant（反应物）**浓度
3. Reaction order 与 **stoichiometric coefficient（化学计量系数）** 无关

**生活例子 — 烤面包**
Rate constant $k$ 就像烤箱的温度设定，reaction order 就像面包片的数量对烤熟速度的影响。烤箱温度变了($k$ 变了)，烤得更快。面包多了（浓度高了），同时烤的面包多了，但每片单独烤熟的时间不变（$k$ 没变）。

### Reaction Order（反应级数）的物理意义

级数不是数学游戏，它告诉你反应的真实微观过程：

| Order | English | 物理含义 | 常见场景 |
|:----|:--------|:--------|:--------|
| **0** | **Zero-order** | 速率与浓度无关 | 表面催化、**酒精代谢** |
| **1** | **First-order** | 单分子过程 | 放射性衰变、**药物代谢** |
| **2** | **Second-order** | 双分子碰撞 | 大部分气相反应 |

**生活例子 — 喝酒代谢**
**酒精在体内的代谢是零级反应（zero-order）** — 无论你喝了多少酒，肝脏每小时只能代谢固定量的酒精（大约 10-15g/h）。因为乙醇脱氢酶（alcohol dehydrogenase）被饱和了。这就是为什么喝得越多，醉得越久 — 代谢不会变快。

**生活例子 — 咖啡因代谢**
**咖啡因在体内的代谢是一级反应（first-order）** — 半衰期大约 5 小时。一杯咖啡下肚，5 小时后体内还剩一半。这就是为什么下午喝咖啡会影响晚上睡眠。

**判断方法 — Initial Rate Method（初始速率法）**：

| 浓度变化 | 速率变化 | 结论 |
|:--------|:--------|:----|
| $\times 2$ | 不变 | Zero-order |
| $\times 2$ | $\times 2$ | First-order |
| $\times 2$ | $\times 4$ | Second-order |

公式：$(\text{concentration ratio})^n = \text{rate ratio}$ → 解 $n$

### Integrated Rate Laws & Half-life（积分速率方程与半衰期）

**Half-life（半衰期, $t_{1/2}$）**：浓度降到初始值一半所需的时间。

| Order | Integrated Rate Law | 线性图（Linear Plot） | Half-life | 关键特征 |
|:----|:-------------------|:---------------------|:----------|:--------|
| **0** | $[A] = [A]_0 - kt$ | $[A]$ vs $t$（斜率 $-k$） | $[A]_0/2k$ | 匀速消耗，与浓度成正比 |
| **1** | $\ln[A] = -kt + \ln[A]_0$ | $\ln[A]$ vs $t$（斜率 $-k$） | $0.693/k$ | **Half-life 与初始浓度无关！** |
| **2** | $1/[A] = 1/[A]_0 + kt$ | $1/[A]$ vs $t$（斜率 $k$） | $1/(k[A]_0)$ | Half-life 依赖浓度 |

**生活例子 — 碳-14 测年（Carbon-14 Dating）**
$\ce{^14C}$ 的衰变是 **first-order**，半衰期 5730 年。无论你有一克还是一吨 $\ce{^14C}$，减少到一半都需要 5730 年。考古学家就是靠这个判断文物年代的。

---

## 枝2：怎么影响"翻越"？

要加快反应（accelerate the reaction），只有**三条路**：

```
                     ┌ 路线A：Temperature ──── 给分子加能量（翻同一个屏障）
影响反应速率的本质 ──┼ 路线B：Catalyst ────── 给屏障降高度（走一条新路）
                     └ 路线C：Concentration ── 增加碰撞次数（不改 k）
```

### 路线A：Temperature（温度） — 改变分子的能量

**Arrhenius Equation（阿伦尼乌斯方程）：** 

$$k = Ae^{-E_a/RT}$$

拆开看：

| 部分 | English | 含义 | 谁控制？ |
|:----|:--------|:----|:--------|
| $A$ | **Frequency factor**（频率因子） | 碰撞频率 × 取向概率 | 分子本身性质 |
| $e^{-E_a/RT}$ | **Boltzmann factor**（玻尔兹曼因子） | 能量超过 $E_a$ 的分子比例 | **温度 $T$ 决定** |

**本质**：升温不是让每个分子跑得更快，而是让 **Boltzmann distribution（玻尔兹曼分布）的尾巴变肥** — 更多分子达到能量阈值。

$$\ln k = -\frac{E_a}{R}\left(\frac{1}{T}\right) + \ln A \quad \rightarrow \quad \text{作图求 } E_a$$

**Two-point form（两点式）**（考试最爱）：

$$\ln\frac{k_2}{k_1} = \frac{E_a}{R}\left(\frac{1}{T_1} - \frac{1}{T_2}\right)$$

**生活例子 — 冰箱**
冰箱的 4°C 让细菌代谢反应变慢，食物保质期从几小时延长到几天。这不是杀死细菌（杀菌要高温），而是降低反应速率 — 因为 $T$ 下降了，$k$ 变小了。

**生活例子 — 美拉德反应（Maillard Reaction）**
煎牛排时，高温（>140°C）触发氨基酸和糖的反应，产生焦香风味。低温烹饪（sous vide）虽然均匀，但缺少这种"锅气" — 因为温度不够高，$k$ 太小。

### 路线B：Catalyst（催化剂） — 改变屏障的高度

**本质**：同一起点到同一终点，但把"翻山"变成"钻隧道"。

Catalyst 通过提供一条 **alternative reaction pathway（替代反应路径）** 来 **lower the activation energy（降低活化能）**，自身不被消耗（not consumed）。

这是最容混淆的点 —— 温度 vs 催化剂：

```
温度：          ┌─────────────────┐
                │  分子有了更多能量  │
                │  去翻同一个屏障    │
                └─────────────────┘

催化剂：        ┌─────────────────┐
                │  屏障本身变低了   │
                │  分子用原来的能量  │
                │  就能翻过去       │
                └─────────────────┘
```

| | **Temperature** | **Catalyst** |
|:--|:---------------|:------------|
| 改变什么？ | **Kinetic energy** of molecules | **Reaction pathway** (降低 $E_a$) |
| 影响 $k$ 的哪个部分？ | Boltzmann factor $e^{-E_a/RT}$ 中的 $T$ | $E_a$ 本身 |
| 上限？ | 反应物分解温度 | Catalyst 失活温度 |
| 与 $E_a$ 关系 | **不改变** $E_a$ | **降低** $E_a$ |

⚠️ **Catalyst 不改变 Equilibrium Constant（平衡常数）**
$K = k_{forward}/k_{reverse}$，催化剂同时降低正逆反应的 $E_a$，分子分母同比例变化 → $K$ 不变。

⚠️ **Catalyst 不改变 $\Delta H$（焓变）**
因为起始和终点能量没变，变的只是中间过渡态。

#### 三种催化剂

| 类型 | English | 原理 | 生活例子 |
|:----|:--------|:----|:--------|
| **均相催化** | **Homogeneous catalysis** | 催化剂与反应物同相 | 胃酸（HCl）催化蛋白质水解 |
| **多相催化** | **Heterogeneous catalysis** | 固体表面吸附反应物 | 汽车 **Catalytic converter**（催化转化器）|
| **酶催化** | **Enzyme catalysis** | 活性位点稳定过渡态 | 唾液淀粉酶分解淀粉 |

**生活例子 — 双氧水滴在伤口上起泡**
药店买的 Hydrogen peroxide（过氧化氢, $\ce{H2O2}$）滴在伤口上会冒白泡 — 那是 **Catalase（过氧化氢酶）** 在催化分解：
$$\ce{2H2O2 ->[catalase] 2H2O + O2 ^}$$
血液和组织里的 Catalase 把 $E_a$ 从 75 kJ/mol 降到 8 kJ/mol — 反应速度加快了 $10^{11}$ 倍！

#### 催化剂与温度的交互

催化剂加速反应，但**催化剂本身也受温度影响**：

```
Rate vs Temperature（有 Catalyst）
     ↑
     │    ╱
     │   ╱
     │  ╱  ← 升温加速反应（Arrhenius）
     │ ╱
     │╱
     └────────→ Temperature
        \
         \  ← 温度太高，催化剂失活（酶变性、烧结、积碳）
          ↘

          ⚡ Optimal temperature（最适温度）= 两个效应的平衡点
```

**生活例子 — 发烧**
人体酶的最适温度（optimal temperature）是 37°C 左右。发烧到 39-40°C 时，酶活性先升高（反应加速），但继续升温到 42°C 以上 → 酶开始 **denature（变性）** → 催化能力崩溃。这就是高烧危险的生化本质。

**生活例子 — 汽车催化转化器**
为什么刚启动时尾气很臭？因为 **Catalytic converter** 需要 **warm-up** 到 ~300°C 才开始高效工作。冷启动（cold start）阶段是排放最高的 — 这就是催化剂也受温度制约的活例子。

### 路线C：Concentration（浓度） — 改变碰撞频率

最简单、最直觉：人多 → 撞得多 → 反应快。

但 **$k$ 不变** — 因为浓度只影响 collision frequency（碰撞频率），不影响 $E_a$ 或分子能量。

**生活例子 — 火**
- 纯氧中燃烧比空气中剧烈 5 倍 — 氧浓度高了（20% → 100%），碰撞频率增加
- 木屑比木块燃烧快得多 — 表面积大 → 更多反应位点暴露 → 有效碰撞增多了

---

## 枝3：多步"翻越"的路径 — Reaction Mechanism（反应机理）

### 基元反应

**Elementary reaction（基元反应）**：反应物直接碰撞生成产物的单步反应。对 elementary reaction，rate law 可以直接从 molecularity 写：

| Molecularity（分子数） | 含义 | Rate Law |
|:---------------------|:----|:--------|
| **Unimolecular** | 一个分子分解/重排 | $v = k[A]$ |
| **Bimolecular** | 两个分子碰撞 | $v = k[A][B]$ 或 $v = k[A]^2$ |
| **Termolecular** | 三个同时碰撞，极少见 | $v = k[A][B][C]$ |

### Rate-Determining Step（决速步, RDS）

多步反应中，**$E_a$ 最高的那一步最慢**，决定了整体速率。就像一群人翻山 — **最高那座山的难度决定全军速度**。

### Pre-Equilibrium Approximation（快平衡近似）

**套路**：快平衡（fast equilibrium）→ 慢反应（slow, RDS）→ 用 equilibrium constant 代换中间体。

**经典例题**：
$2NO + Br_2 \rightarrow 2NOBr$，实验测得 $v = k[NO]^2[Br_2]$

- Step 1（快）：$NO + Br_2 \rightleftharpoons NOBr_2$
- Step 2（慢/RDS）：$NOBr_2 + NO \rightarrow 2NOBr$

推导：
1. $v = k_2[NOBr_2][NO]$（从 RDS 写起）
2. 快平衡：$k_1[NO][Br_2] = k_{-1}[NOBr_2]$ → $[NOBr_2] = (k_1/k_{-1})[NO][Br_2]$
3. 代入：$v = k_2(k_1/k_{-1})[NO]^2[Br_2] = k[NO]^2[Br_2]$ ✓

**生活例子 — 为什么火柴（match）一擦就着？**
火柴头有红磷和氧化剂。擦火柴时摩擦生热 → 提供 $E_a$ → 红磷燃烧（RDS, 慢） → 引燃火柴杆。这就是一个 fast → slow 的序列反应。

---

## 联系地图

```
                    ┌── Thermodynamics（热力学）──┐
                    │  ΔG < 0 能发生吗？          │
                    │  但不是充分条件！            │
                    └─────────────┼───────────────┘
                                  │
                                  ▼
               ★ Activation Energy (Ea) ★
                   决定反应的速率
                      │
      ┌───────────────┼───────────────────┐
      │               │                   │
      ▼               ▼                   ▼
  Description      Acceleration        Mechanism
  怎么描述？        怎么加速？           怎么分步？
      │               │                   │
  ┌───┴───┐   ┌───┬───┴───┬────┐      ┌──┴───┐
  │       │   │   │       │    │      │      │
Rate   Order Temp Catalyst Conc. Surf.  Elem.  RDS
Law    (m,n)         │               rxn
      │              │
      │              └── Catalyst activity
      │                 受温度影响
      │                 (Optimal Temperature)
      │
      └── Arrhenius Eq.
          k = Ae^{-Ea/RT}
```

---

## 公式速查

| 公式 | English Name | 它在回答什么问题？ |
|:----|:------------|:----------------|
| $v = k[A]^m[B]^n$ | **Rate Law** | 反应速率取决于什么？ |
| $\ln[A] = -kt + \ln[A]_0$ | **1st Order Integrated Rate Law** | 一级反应中，浓度怎么随时间变化？ |
| $1/[A] = 1/[A]_0 + kt$ | **2nd Order Integrated Rate Law** | 二级反应呢？ |
| $t_{1/2} = 0.693/k$ | **Half-life (1st order)** | 一级反应，一半消耗掉要多久？ |
| $k = Ae^{-E_a/RT}$ | **Arrhenius Equation** | 温度和 $E_a$ 如何影响反应速度？ |
| $\ln(k_2/k_1) = \frac{E_a}{R}\left(\frac{1}{T_1} - \frac{1}{T_2}\right)$ | **Two-point Form** | 两个温度下的 $k$ 已知，$E_a$ 是多少？ |
