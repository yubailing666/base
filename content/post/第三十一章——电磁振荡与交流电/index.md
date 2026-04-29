---
title: "第三十一章——电磁振荡与交流电"
description: "LC振荡、RLC电路、交流电、谐振、变压器"
date: 2026-04-29
draft: false
math: true
tags: [物理, 交流电, 谐振, 电磁振荡]
categories: [大学物理]
---

---

### 1. LC 振荡电路

#### 直觉引入

想象一个**弹簧振子**：
- 弹簧储能（势能） ↔ **电容器**储能（电场能）
- 质量块动能 ↔ **电感**储能（磁场能）

LC 电路就是"电能 ↔ 磁能"来回倒腾，跟弹簧振子"势能 ↔ 动能"来回倒腾一模一样。

#### 公式推导

**基尔霍夫电压定律 (KVL)**：

$$\frac{q}{C} + L\frac{di}{dt} = 0$$

代入 $i = -dq/dt$（放电时电流方向），得：

$$L\frac{d^2q}{dt^2} + \frac{q}{C} = 0 \quad\Rightarrow\quad \frac{d^2q}{dt^2} + \frac{1}{LC}q = 0$$

这是标准的**简谐振动方程**，类比弹簧：$\displaystyle \frac{d^2x}{dt^2} + \frac{k}{m}x = 0$

所以令 $\omega = 1/\sqrt{LC}$，解为：

$$q(t) = Q\cos(\omega t + \varphi) \quad\leftarrow\text{电量振荡}$$
$$i(t) = -\omega Q\sin(\omega t + \varphi) \quad\leftarrow\text{电流振荡}$$

#### 关键公式

| 物理量 | 公式 |
|--------|------|
| **角频率 $\omega$** | $\omega = 1/\sqrt{LC}$ |
| **周期 $T$** | $T = 2\pi\sqrt{LC}$ |
| **电容器储能 $U_E$** | $U_E = q^2/2C$ |
| **电感储能 $U_B$** | $U_B = Li^2/2$ |
| **总能量** | $U_{\text{total}} = Q^2/2C = LI_{\text{max}}^2/2$（守恒）|

#### 📝 记忆方法

- $\omega = 1/\sqrt{LC}$ → "LC 在分母，越大越慢"
- 类比弹簧：$C \rightarrow 1/k$（电容大=弹簧软），$L \rightarrow m$（电感大=质量大）
- $\omega = \sqrt{k/m}$ → $\omega = \sqrt{1/(LC)} = 1/\sqrt{LC}$

#### 题型总结

1. **求 $\omega$ 或 $T$** → 直接套 $\omega = 1/\sqrt{LC}$
2. **求 $q(t)$ 或 $i(t)$** → 解微分方程或用能量守恒
3. **能量转换** → 电场能最大时磁场能为0，反之亦然

---

### 2. RLC 电路（阻尼振荡）

#### 直觉引入

LC 理想无损耗，实际电路中一定有 **电阻 $R$** 耗能 → 振幅指数衰减。类比弹簧加了阻尼。

#### 公式推导

KVL（加上电阻的电压降）：

$$L\frac{d^2q}{dt^2} + R\frac{dq}{dt} + \frac{q}{C} = 0$$

令 **阻尼系数 $\beta = R/2L$**，得：

$$\frac{d^2q}{dt^2} + 2\beta\frac{dq}{dt} + \omega_0^2 q = 0 \quad (\omega_0 = 1/\sqrt{LC})$$

特征方程：$r^2 + 2\beta r + \omega_0^2 = 0$

$$r = -\beta \pm \sqrt{\beta^2 - \omega_0^2}$$

#### 三种情况

| 类型 | 条件 | 行为 |
|------|------|------|
| **Overdamped（过阻尼）** | $\beta > \omega_0$ $(R > 2\sqrt{L/C})$ | 无振荡，直接指数衰减 |
| **Critically damped（临界阻尼）** | $\beta = \omega_0$ $(R = 2\sqrt{L/C})$ | 最快的无振荡衰减 |
| **Underdamped（欠阻尼）** | $\beta < \omega_0$ $(R < 2\sqrt{L/C})$ | 振幅指数衰减的振荡 |

**欠阻尼解**：

$$q(t) = Q e^{-\beta t} \cos(\omega' t + \varphi)$$

其中 $\omega' = \sqrt{\omega_0^2 - \beta^2}$（阻尼振荡频率）

#### 现实情景对比

| 类型 | 现实例子 |
|------|---------|
| **Overdamped**（过阻尼） | 🚽 马桶盖缓降、油压缓冲门（慢慢关上，不反弹）|
| **Critically damped**（临界阻尼）| 🚗 **汽车减震器**（过坑后最快恢复稳定）；指针仪表（快速到位）|
| **Underdamped**（欠阻尼） | 🛎️ 敲音叉/钟声；秋千荡停；弹簧挂重物放手后弹几下 |

📝 **直觉**：门在**蜂蜜**里关（过阻尼）/ **水**里关（临界）/ **空气**里关（欠阻尼 Duang Duang Duang）

#### 题型总结

1. **判断阻尼类型** → 比较 $R$ 与 $2\sqrt{L/C}$
2. **求欠阻尼 $\omega'$** → $\omega' = \sqrt{1/LC - R^2/4L^2}$
3. **能量衰减速率** → $e^{-Rt/L}$

---

### 3. 交流电基础 & 三种基本元件

#### 直觉引入

接上交流电源后，每个元件的"阻力"和相位都不一样：
- **$R$**：老老实实，电压电流同相
- **$C$**：电流先冲进去填满→电压才起来 → **电流领先电压 90°**
- **$L$**：电压先推→电流慢慢起来 → **电压领先电流 90°**

**🌧️ 越雨的神比喻：**
- **电容像「预判家」** — 电压还没起来，电流就已经先冲上去了，永远抢先一步
- **电感像「拖油瓶」** — 电压已经推上去了，电流还在后面磨蹭，永远慢半拍

一句话：电容冲在前，电感拖在后。

#### 三种元件对照

| 元件 | 电压-电流相位 | 阻抗 | 平均功率 |
|------|:------------:|:----:|:--------:|
| **$R$（电阻）** | 同相 $(\phi=0)$ | $R$（电阻） | $>0$（耗能）|
| **$C$（电容）** | **电流领先 $90^\circ$** | $X_C = 1/(\omega C)$（容抗） | $=0$（储能）|
| **$L$（电感）** | **电压领先 $90^\circ$** | $X_L = \omega L$（感抗） | $=0$（储能）|

---

#### 电阻 $R$ 电路

$$v = V_{\text{max}}\cos\omega t,\quad i = \frac{v}{R} = \frac{V_{\text{max}}}{R}\cos\omega t = I_{\text{max}}\cos\omega t$$

- 同相，无相位差
- $I_{\text{max}} = V_{\text{max}} / R$

---

#### 详细推导——纯电容 $C$ 电路

##### 基本关系（核心方程！）

$$i = C \frac{dv}{dt}$$

电流 $\neq$ 电压的原因：电容是**积累电荷**的元件，电流流入后电荷慢慢堆积，电压才逐渐建立起来。所以是**电流决定电压的变化速率**，而不是直接等于电压。

##### 设电压，求电流

令 $v(t) = V_{\text{max}}\cos\omega t$：

$$
\begin{aligned}
i &= C \frac{d}{dt}[V_{\text{max}}\cos\omega t] \\
  &= C \cdot V_{\text{max}} \cdot (-\omega\sin\omega t) \\
  &= -\omega C V_{\text{max}} \sin\omega t \\
  &= \omega C V_{\text{max}} \cos(\omega t + 90^\circ)
\end{aligned}
$$

📌 **关键三角变换**：$-\sin\theta = \cos(\theta + 90^\circ)$ —— 这就是相位差 $+90^\circ$ 的来源。

##### 相位结论

$$v(t) = V_{\text{max}}\cos\omega t$$
$$i(t) = I_{\text{max}}\cos(\omega t + 90^\circ)$$

> **电流领先电压 $90^\circ$**

**物理直觉**：电压刚要从 0 往上升的那一瞬间，**斜率 $dv/dt$ 最大**，由 $i = C\,dv/dt$ 可知电流此时已经到峰值了。等电压升到顶峰（$dv/dt = 0$），电流降至 0。所以电流总是**跑在电压前面** $90^\circ$。

##### 振幅关系

$$I_{\text{max}} = \omega C V_{\text{max}} = \frac{V_{\text{max}}}{X_C}$$

其中 **容抗** $X_C = \dfrac{1}{\omega C}$，单位 $\Omega$

##### 参数变化分析

| 条件变化 | $X_C$ | $I_{\text{max}}$ | 物理原因 |
|:---------|:-----:|:----------------:|:---------|
| $\omega \uparrow$（频率变高） | $\downarrow$ | $\uparrow$ | 频率高→充放电快→电流容易通过 |
| $\omega \downarrow$（频率变低） | $\uparrow$ | $\downarrow$ | 频率低→充放电慢→电流受阻 |
| $\omega \to 0$（**直流！**） | $\to \infty$ | $\to 0$ | **直流不能通过电容**！隔直通交 |
| $C \uparrow$（电容变大） | $\downarrow$ | $\uparrow$ | 电容大→储电多→同电压下电流更大 |

📝 **一句话**：电容**通高频阻低频，隔直流通交流**。

---

#### 详细推导——纯电感 $L$ 电路

##### 基本关系（核心方程！）

$$v = L \frac{di}{dt}$$

电流 $\neq$ 电压的原因：电感通过磁场**抵抗电流变化**，电流不能突变。外加电压是为了克服这个"惯性"把电流推起来，所以**电压先来，电流后到**。

##### 设电压，求电流

令 $v(t) = V_{\text{max}}\cos\omega t$：

$$
\begin{aligned}
i &= \frac{1}{L}\int v\,dt \\
  &= \frac{1}{L}\int V_{\text{max}}\cos\omega t\,dt \\
  &= \frac{V_{\text{max}}}{\omega L}\sin\omega t \\
  &= \frac{V_{\text{max}}}{\omega L}\cos(\omega t - 90^\circ)
\end{aligned}
$$

📌 **关键三角变换**：$\sin\theta = \cos(\theta - 90^\circ)$ —— 这就是相位差 $-90^\circ$ 的来源。

##### 相位结论

$$v(t) = V_{\text{max}}\cos\omega t$$
$$i(t) = I_{\text{max}}\cos(\omega t - 90^\circ)$$

> **电压领先电流 $90^\circ$**（等价于电流落后电压 $90^\circ$）

**物理直觉**：电感的电流有"惯性"（磁场维持），电压要先加上去对抗这个惯性，电流才慢慢建立。等电压过了峰值开始下降，电流还在继续上涨（因为磁场还在释放能量）。所以电压总是**跑在电流前面** $90^\circ$。

##### 振幅关系

$$I_{\text{max}} = \frac{V_{\text{max}}}{\omega L} = \frac{V_{\text{max}}}{X_L}$$

其中 **感抗** $X_L = \omega L$，单位 $\Omega$

##### 参数变化分析

| 条件变化 | $X_L$ | $I_{\text{max}}$ | 物理原因 |
|:---------|:-----:|:----------------:|:---------|
| $\omega \uparrow$（频率变高） | $\uparrow$ | $\downarrow$ | 高频→磁场变化快→感应反电动势大→阻碍电流 |
| $\omega \downarrow$（频率变低） | $\downarrow$ | $\uparrow$ | 低频→磁场变化慢→阻碍小→电流容易通过 |
| $\omega \to 0$（**直流！**） | $\to 0$ | $\to V_{\text{max}}/R$ | **直流下电感相当于导线**（仅保留线圈电阻）|
| $L \uparrow$（电感变大） | $\uparrow$ | $\downarrow$ | 电感大→"惯性"大→电流更难建立 |

📝 **一句话**：电感**通低频阻高频，通直流阻交流**（和电容完全相反！）。

---

#### 记忆方法

**CIVIL 口诀**：

```
C 电路：I → V（电流领先电压 Current leads Voltage）
L 电路：V → I（电压领先电流 Voltage leads Current）
```

| 口诀                 | 含义                         |
| ------------------ | -------------------------- |
| $X_C = 1/\omega C$ | "C 在分母，频率越高容抗越小"——高频更容易过电容 |
| $X_L = \omega L$   | "L 在分子，频率越高感抗越大"——高频更难过电感  |

**英语单词 & 记忆法：**

| 中文 | 英文 | 符号 | 公式 | 记忆法 |
|------|------|:----:|:----:|:-------|
| **感抗** | **Inductive Reactance** | $X_L$ | $X_L = \omega L$ | **React** = 抵抗、反抗。电感**抵抗**电流变化，所以叫 Reactance。"Inductive" 来自 Inductor（电感）|
| **容抗** | **Capacitive Reactance** | $X_C$ | $X_C = 1/\omega C$ | 同样是 Reactance，"Capacitive" 来自 Capacitor（电容）|

**公式推导记忆：**

- **$X_L = \omega L$**：从 $v = L\,di/dt$ 出发，设 $i = I\cos\omega t$，得 $v = -\omega L I\sin\omega t$，振幅 $V_{\text{max}} = \omega L I_{\text{max}}$，所以 $X_L = V_{\text{max}}/I_{\text{max}} = \omega L$
- **$X_C = 1/\omega C$**：从 $i = C\,dv/dt$ 出发，设 $v = V\cos\omega t$，得 $i = -\omega C V\sin\omega t$，振幅 $I_{\text{max}} = \omega C V_{\text{max}}$，所以 $X_C = V_{\text{max}}/I_{\text{max}} = 1/\omega C$

**☝️ 关键记忆：**
- $X_L = \omega L$ → **L 在分子**，$
obreakspace\omega \uparrow$ → $X_L \uparrow$（高频难过电感）
- $X_C = 1/\omega C$ → **C 在分母**，$
obreakspace\omega \uparrow$ → $X_C \downarrow$（高频容易过电容）
- 两个公式正好**互为倒数**的感觉（一个是 $\omega L$，一个是 $1/\omega C$），对比着记不会混

#### 题型总结

1. **求 $X_C$ 或 $X_L$** → $X_C = 1/\omega C$, $X_L = \omega L$
2. **求 $I_{\text{max}}$** → 纯电阻电路 $V_{\text{max}}/R$，纯电容 $V_{\text{max}}/X_C$，纯电感 $V_{\text{max}}/X_L$
3. **相位判断** → CIVIL 口诀

---

### 4. 串联 RLC 电路

#### 直觉引入

三个元件串联，总电压是 $v_R + v_L + v_C$。但因为三个电压相位不同（$v_R$ 同相、$v_L$ 领先 $90^\circ$、$v_C$ 落后 $90^\circ$），不能直接代数相加，要**矢量相加**。

#### 关键概念

| 概念 | 公式 | 说明 |
|------|------|:----|
| **Impedance $Z$（阻抗）** | $Z = \sqrt{R^2 + (X_L - X_C)^2}$ | 总"阻力"，勾股定理 |
| $I_{\text{max}}$ | $I_{\text{max}} = V_{\text{max}} / Z$ | 类似 $V = IR$ |
| **相位差 $\phi$** | $\tan\phi = (X_L - X_C)/R$ | $\phi>0$：电流落后（感性）；$\phi<0$：电流领先（容性）|

#### 公式推导

设电流 $i = I_{\text{max}}\cos(\omega t - \phi)$，则各元件电压：

$$v_R = I_{\text{max}}R\cos(\omega t - \phi)$$
$$v_L = -I_{\text{max}}X_L\sin(\omega t - \phi)$$
$$v_C = I_{\text{max}}X_C\sin(\omega t - \phi)$$

KVL：$v_R + v_L + v_C = V_{\text{max}}\cos\omega t$

将 $v_L$ 写成 $\cos(\omega t - \phi + 90^\circ)$、$v_C$ 写成 $\cos(\omega t - \phi - 90^\circ)$，利用矢量合成，最终得：

$$V_{\text{max}}^2 = I_{\text{max}}^2[R^2 + (X_L - X_C)^2]$$

$$\boxed{Z = \sqrt{R^2 + (X_L - X_C)^2}}$$

**三个电压的相位关系**（用相量图理解）：

```
        V_L (↑, 领先90°)
         ↑
         │
    V_R →┼→ (→, 同相)
         │
         ↓
        V_C (↓, 落后90°)
```

$V_L - V_C$ 的差值决定整体是感性（偏上）还是容性（偏下）。

#### 三种情况

| 条件 | $\phi$ | 电路性质 | 电流 vs 电压 |
|------|:------:|:---------|:-------------|
| $X_L > X_C$ | $\phi > 0$ | **Inductive（感性）** | 电流**落后**电压 |
| $X_L < X_C$ | $\phi < 0$ | **Capacitive（容性）** | 电流**领先**电压 |
| $X_L = X_C$ | $\phi = 0$ | **Resistive（纯阻性/谐振）** | 同相，电流最大 |

#### 题型总结

1. **求 $Z$** → 算 $X_L$ 和 $X_C$ → 相减 → 勾股定理
2. **求 $\phi$** → $\tan\phi = (X_L - X_C)/R$
3. **判断电路性质** → 比较 $X_L$ 和 $X_C$

---

### 5. 谐振 (Resonance)

#### 直觉引入

当 $X_L = X_C$ 时，感抗和容抗恰好互相抵消，总阻抗最小 $Z = R$，电流达到最大。就像荡秋千，推的频率刚好等于固有频率 → 振幅最大。

#### 关键公式

$$\text{谐振条件：}\quad \omega L = \frac{1}{\omega C} \;\Rightarrow\; \omega_0 = \frac{1}{\sqrt{LC}}$$

$$\text{谐振时：}\quad Z = R,\quad I_{\text{max}} = \frac{V_{\text{max}}}{R}\text{（最大！）}$$

**品质因子 $Q$**（注意不是电荷）：

$$Q = \frac{\omega_0 L}{R} = \frac{1}{\omega_0 R C}$$

$Q$ 越大 → 谐振峰越尖锐 → **选择性越好**

#### 📝 记忆方法

- $\omega_0 = 1/\sqrt{LC}$ 和 LC 自由振荡频率一模一样
- $Q = \omega_0 L/R$ → "$L$ 越大 $R$ 越小 → 峰越尖"
- "谐振时 $Z$ 最小电流最大" → 阻抗抵消了，R 说了算

#### 题型总结

1. **求谐振频率** → $\omega_0 = 1/\sqrt{LC}$ 或 $f_0 = 1/(2\pi\sqrt{LC})$
2. **谐振 $I_{\text{max}}$** → $I_{\text{max}} = V_{\text{max}}/R$
3. **求 $Q$** → $Q = \omega_0 L/R = 1/(\omega_0 RC)$

---

### 6. 交流电功率

#### 直觉引入

交流电压电流不断变化，瞬时功率也在变。我们关心的是**平均功率**。

#### RMS 值（有效值）

$$I_{\text{rms}} = \frac{I_{\text{max}}}{\sqrt{2}},\quad V_{\text{rms}} = \frac{V_{\text{max}}}{\sqrt{2}}$$

📝 **万用表显示的是 RMS！** 家用 220V = RMS → 峰值 $220\times\sqrt{2} \approx 311$V

#### 平均功率

$$P_{\text{avg}} = I_{\text{rms}}^2 R = V_{\text{rms}} I_{\text{rms}} \cos\phi$$

- $\cos\phi = R/Z$（**power factor**，功率因数）
- 纯电阻：$\cos\phi = 1$；纯电容/纯电感：$\cos\phi = 0$（平均功率=0，储能不耗能）

#### 题型总结

1. **RMS 值** → 峰值 $/\sqrt{2}$
2. **平均功率** → $P_{\text{avg}} = I_{\text{rms}}^2 R = V_{\text{rms}}I_{\text{rms}}\cos\phi$
3. **功率因数** → $\cos\phi = R/Z$，越接近 1 效率越高

---

### 7. 变压器 (Transformer)

$$\frac{V_2}{V_1} = \frac{N_2}{N_1},\qquad \frac{I_2}{I_1} = \frac{N_1}{N_2}$$

- $N_2 > N_1$ → **step-up（升压）**
- $N_2 < N_1$ → **step-down（降压）**
- 能量守恒：$V_1 I_1 = V_2 I_2$
- 阻抗变换：$Z_{\text{in}} = (N_1/N_2)^2 \cdot Z_{\text{load}}$

📝 "升压降流，降压升流" — 哪边匝数多，哪边电压高

---

### 8. 易混淆概念对比

| 易混点 | 区别 |
|--------|------|
| **$X_L$ vs $X_C$** | $X_L = \omega L$（正比 $\omega$），$X_C = 1/\omega C$（反比 $\omega$）|
| **$Q$（电荷）vs $Q$（品质因子）** | 电荷单位 C，品质因子无量纲 |
| **$\omega$ vs $f$** | $\omega = 2\pi f$ |
| **谐振 $\omega_0$ vs 阻尼 $\omega'$** | $\omega_0 = 1/\sqrt{LC}$，$\omega' = \sqrt{\omega_0^2 - \beta^2}$|
| **$I_{\text{max}}$ vs $I_{\text{rms}}$** | 考试看清问 peak 还是 rms |

---

### 9. 公式速查

| 公式 | 用途 |
|------|------|
| $\omega_0 = 1/\sqrt{LC}$ | 谐振/振荡角频率 |
| $\beta = R/2L$ | 阻尼系数 |
| $X_L = \omega L$ | 感抗 |
| $X_C = 1/(\omega C)$ | 容抗 |
| $Z = \sqrt{R^2 + (X_L - X_C)^2}$ | RLC 总阻抗 |
| $\tan\phi = (X_L - X_C)/R$ | 相位差 |
| $I_{\text{max}} = V_{\text{max}}/Z$ | 电流振幅 |
| $I_{\text{rms}} = I_{\text{max}}/\sqrt{2}$ | 有效值 |
| $P_{\text{avg}} = I_{\text{rms}}^2 R = V_{\text{rms}} I_{\text{rms}} \cos\phi$ | 平均功率 |
| $V_2/V_1 = N_2/N_1$ | 变压器电压比 |

---

> 🗓 最后更新：2026-04-28 | 来源：SUSTC General Physics II Ch.31


---