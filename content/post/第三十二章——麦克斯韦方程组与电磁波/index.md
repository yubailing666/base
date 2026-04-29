---
title: "第三十二章——麦克斯韦方程组与电磁波"
description: "麦克斯韦方程组、位移电流、电磁波、坡印廷矢量"
date: 2026-04-29
draft: false
math: true
tags: [物理, 麦克斯韦方程组, 电磁波]
categories: [大学物理]
---

---

### 1. 麦克斯韦方程组（四条）

| 名称 | 积分形式 | 物理意义 |
|:----|:---------|:---------|
| **Gauss's Law for E** | $$\oint \mathbf{E} \cdot d\mathbf{A} = Q_{\text{enc}}/\varepsilon_0$$ | 电通量 ∝ 内部电荷 |
| **Gauss's Law for B** | $$\oint \mathbf{B} \cdot d\mathbf{A} = 0$$ | 无磁单极 |
| **Faraday's Law** | $$\oint \mathbf{E} \cdot d\mathbf{l} = -d\Phi_B/dt$$ | 变化磁通 → 感应电场 |
| **Ampere-Maxwell Law** | $$\oint \mathbf{B} \cdot d\mathbf{l} = \mu_0 I + \mu_0\varepsilon_0\,d\Phi_E/dt$$ | 修正后：电流 + 变化电通 → 磁场 |

**对称性思想**：变化磁通→电场，那变化电通→磁场？→ 引入位移电流！

---

### 2. 位移电流（Displacement Current）

麦克斯韦的核心贡献：$$I_d = \varepsilon_0 \frac{d\Phi_E}{dt}$$

- 不是真实电荷运动，是**虚构电流**
- 但它产生的磁场是**真实**的
- 充电电容器两极板间：$$I_d = I_{\text{导线}}$$

---


### 关键直觉：变化电场→磁场就是位移电流

**问题来源**：平行板电容器充电时，导线里有电流 I，但两极板之间没有电荷通过。取安培环路时，选不同的包围面会算出不同的磁场——矛盾。

**麦克斯韦的解**：两板之间虽然没有电荷流动，但电场在变化（E 在变大）。他把变化的电通量等效成一个"电流"：

$$I_d = \varepsilon_0 \frac{d\Phi_E}{dt}$$

**位移电流的物理图像**：

不是电荷在跑，是**电场在变**。极板间电场增强→等效于有电流穿过了极板间→产生磁场。

安培定律修正后：

$$\oint \mathbf{B} \cdot d\mathbf{l} = \mu_0 (I_{\text{enc}} + I_d)$$

无论取哪个包围面，算出来都一样。

**为什么叫"位移"**？因为极板上的电荷"位移"了——虽然电荷没有穿过极板之间的空间，但电场线的"位移"在极板间产生了等效的电流效应。

**记忆点**：
- 电容充电时，两极板间：$$I_d = I_{\text{导线}}$$
- 位移电流是**虚构**的（不是真实电荷移动），但它产生的磁场是**真实**的
- 这个修正让麦克斯韦方程组在数学上自洽，也预言了电磁波的存在


#### 考试技巧：用好光速 c 快速计算

公式中经常同时出现 \(\mu_0\) 和 \(\varepsilon_0\)，记住它们和光速的关系可以省很多事：

$$c = \frac{1}{\sqrt{\mu_0 \varepsilon_0}},\quad \mu_0 \varepsilon_0 = \frac{1}{c^2}$$

**常用简化**：
- $$\frac{1}{\mu_0 c} = \frac{\varepsilon_0}{\mu_0 \varepsilon_0 \cdot c} = \varepsilon_0 c$$
- 强度公式：$$I = \frac{E_0^2}{2\mu_0 c} = \frac{c\varepsilon_0}{2}E_0^2$$

**考场实操**：
- 知道 \(I\) 求 \(E_0\)：\(E_0 = \sqrt{2\mu_0 c I}\)，直接敲计算器
- 代入 \(\mu_0 = 4\pi \times 10^{-7},\; c = 3\times 10^8\) → \(\mu_0 c = 4\pi \times 10^{-7} \times 3\times 10^8 = 120\pi \approx 377\)（这就是真空阻抗！）
- 所以 \(I = E_0^2 / (2 \times 377) = E_0^2/754\)，反过来 \(E_0 = \sqrt{754I}\)

**记这个数**：\(\mu_0 c = 120\pi \approx 377\; \Omega\)（真空阻抗），考试直接用这个算强度，比拆开算快很多。

### 3. 电磁波波动方程

真空中 \(\rho = 0, \mathbf{J} = 0\)：

$$\nabla^2 \mathbf{E} = \mu_0\varepsilon_0 \frac{\partial^2 \mathbf{E}}{\partial t^2}$$

**波速**：$$c = \frac{1}{\sqrt{\mu_0\varepsilon_0}} = 3\times 10^8 \text{ m/s}$$

一组解（平面波）：
$$\mathbf{E} = E_0 \cos(kx - \omega t) \hat{\mathbf{y}},\quad \mathbf{B} = B_0 \cos(kx - \omega t) \hat{\mathbf{z}}$$

**关系**：$$\frac{\omega}{k} = c,\quad \frac{E_0}{B_0} = c$$

---

### 4. EM波性质

| 性质 | 说明 |
|:---|:-----|
| **横波** | E ⊥ B ⊥ 传播方向 |
| **E ⊥ B** | 互相垂直 |
| **同相** | E 和 B 同时达峰 |
| **速度恒定** | \(c = 3\times 10^8\) m/s |
| **E = cB** | 电场与磁场振幅比 |

---

### 5. 能量与 Poynting Vector

**能量密度**：$$u_E = \frac{1}{2}\varepsilon_0 E^2,\; u_B = \frac{1}{2\mu_0}B^2,\; u_E = u_B$$

**Poynting Vector**：$$\mathbf{S} = \frac{1}{\mu_0}\mathbf{E}\times\mathbf{B}$$

**强度（时间平均）**：$$I = S_{\text{avg}} = \frac{E_0 B_0}{2\mu_0} = \frac{E_0^2}{2\mu_0 c}$$

---

### 6. 辐射压力

完全吸收：$$P_{\text{rad}} = I/c$$，完全反射：$$P_{\text{rad}} = 2I/c$$

💡 彗星尘埃尾、太阳帆

---

### 7. 公式速查

| 公式 | 用途 |
|:----|:-----|
| \(c = 1/\sqrt{\mu_0\varepsilon_0}\) | 光速 |
| \(E/B = c\) | EM波场关系 |
| \(I = E_0^2/(2\mu_0 c)\) | 强度 |
| \(P_{\text{rad}} = I/c\) | 辐射压力（吸收）|
| \(\mathbf{S} = (1/\mu_0)\mathbf{E}\times\mathbf{B}\) | 坡印廷矢量 |


---