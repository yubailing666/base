---
title: "第三十二章——Maxwell's Equations & EM Waves"
description: "麦克斯韦方程组与电磁波"
date: 2026-04-29
draft: false
math: true
tags: [物理, 电磁学, 麦克斯韦方程组]
categories: [大学物理]
---

## Ch.32 Maxwell's Equations & Electromagnetic Waves

---

### 1. 麦克斯韦方程组回顾

四条方程，分别对应电场和磁场的两个基本规律：

| 名称 | 积分形式 | 物理意义 |
|------|---------|---------|
| **Gauss's Law for E**（电场高斯定律） | $$\oint \mathbf{E} \cdot d\mathbf{A} = \frac{Q_{\text{enc}}}{\varepsilon_0}$$ | 电通量 ∝ 内部电荷 |
| **Gauss's Law for B**（磁场高斯定律） | $$\oint \mathbf{B} \cdot d\mathbf{A} = 0$$ | 磁通量总为零（无磁单极）|
| **Faraday's Law**（法拉第定律） | $$\oint \mathbf{E} \cdot d\mathbf{l} = -\frac{d\Phi_B}{dt}$$ | 变化磁场 → 感应电场 |
| **Ampere's Law**（安培定律） | $$\oint \mathbf{B} \cdot d\mathbf{l} = \mu_0 I_{\text{enc}}$$ | 电流 → 磁场 |

**对称性疑问**：既然变化磁场 → 电场（法拉第），那变化电场 → 磁场吗？

---

### 2. 位移电流（Displacement Current）

麦克斯韦的贡献：给安培定律补上了缺失的一项。

安培定律在电容器充电时有矛盾——平行板间没有电流，但磁场依然存在。麦克斯韦指出：

$$\oint \mathbf{B} \cdot d\mathbf{l} = \mu_0 I_{\text{enc}} + \mu_0 \varepsilon_0 \frac{d\Phi_E}{dt}$$

其中 **位移电流（Displacement Current）** 定义为：

$$I_d = \varepsilon_0 \frac{d\Phi_E}{dt}$$

对于充电的平行板电容器：

$$I_d = \varepsilon_0 \frac{d(EA)}{dt} = \varepsilon_0 A \frac{dE}{dt} = \varepsilon_0 A \frac{d(\sigma/\varepsilon_0)}{dt} = A \frac{d\sigma}{dt}$$

📝 **位移电流不是真实电荷运动**，只是为了修正麦克斯韦方程组而引入的"虚构电流"，但它产生的磁场是真实的。

---

### 3. 完整的麦克斯韦方程组

假设无介质时：

| 方程 | 积分形式 | 微分形式 |
|:----|:---------|:---------|
| Gauss-E | $$\oint \! \mathbf{E} \! \cdot\! d\mathbf{A} = \frac{Q}{\varepsilon_0}$$ | $$\nabla \cdot \mathbf{E} = \frac{\rho}{\varepsilon_0}$$ |
| Gauss-B | $$\oint \! \mathbf{B} \! \cdot\! d\mathbf{A} = 0$$ | $$\nabla \cdot \mathbf{B} = 0$$ |
| Faraday | $$\oint \! \mathbf{E} \! \cdot\! d\mathbf{l} = -\frac{d\Phi_B}{dt}$$ | $$\nabla \times \mathbf{E} = -\frac{\partial \mathbf{B}}{\partial t}$$ |
| Ampere-Maxwell | $$\oint \! \mathbf{B} \! \cdot\! d\mathbf{l} = \mu_0 I + \mu_0 \varepsilon_0 \frac{d\Phi_E}{dt}$$ | $$\nabla \times \mathbf{B} = \mu_0 \mathbf{J} + \mu_0 \varepsilon_0 \frac{\partial \mathbf{E}}{\partial t}$$ |

---

### 4. 电磁波的推导

在真空中（无电荷无电流）$$\rho = 0, \mathbf{J} = 0$$：

$$\nabla \cdot \mathbf{E} = 0, \quad \nabla \times \mathbf{E} = -\frac{\partial \mathbf{B}}{\partial t}$$

$$\nabla \cdot \mathbf{B} = 0, \quad \nabla \times \mathbf{B} = \mu_0 \varepsilon_0 \frac{\partial \mathbf{E}}{\partial t}$$

对法拉第定律取旋度，得波动方程：

$$\nabla^2 \mathbf{E} = \mu_0 \varepsilon_0 \frac{\partial^2 \mathbf{E}}{\partial t^2}$$

这是一个标准的**波动方程**形式 $$\nabla^2 f = \frac{1}{v^2}\frac{\partial^2 f}{\partial t^2}$$

所以电磁波速度：

$$v = \frac{1}{\sqrt{\mu_0 \varepsilon_0}}$$

代入 $$\mu_0 = 4\pi \times 10^{-7}$$, $$\varepsilon_0 = 8.85 \times 10^{-12}$$：

$$v = 2.999 \times 10^8 \; \text{m/s} = c$$

**结论：光就是电磁波！**

一组解（平面波）：

$$\mathbf{E} = E_0 \cos(kx - \omega t) \hat{\mathbf{y}}$$
$$\mathbf{B} = B_0 \cos(kx - \omega t) \hat{\mathbf{z}}$$

其中 $$\frac{\omega}{k} = c$$, $$\frac{E_0}{B_0} = c$$

---

### 5. 电磁波的性质

| 性质 | 说明 |
|:---|:-----|
| **横波** | E 和 B 振动方向 ⊥ 传播方向 |
| **E ⊥ B** | E 和 B 互相垂直 |
| **同相** | E 和 B 同时到达最大值和最小值 |
| **速度恒定** | 真空中均为光速 $$c$$ |
| **E/B = c** | 电场峰值与磁场峰值之比等于光速 |

---

### 6. 电磁波谱

| 波段 | 波长范围 | 典型应用 |
|:---|:---------|:--------|
| **Radio（无线电波）** | > 0.1 m | 广播、通信 |
| **Microwave（微波）** | 0.1 m ~ 1 mm | 微波炉、雷达、WiFi |
| **THz（太赫兹）** | 1 mm ~ 0.1 mm | 安检扫描、光谱学 |
| **Infrared（红外）** | 0.1 mm ~ 700 nm | 热成像、遥控 |
| **Visible Light（可见光）** | 700 nm ~ 400 nm | 人眼可见 |
| **Ultraviolet（紫外）** | 400 nm ~ 10 nm | 消毒、荧光 |
| **X-ray（X射线）** | 10 nm ~ 0.01 nm | 医学成像 |
| **Gamma-ray（伽马射线）** | < 0.01 nm | 放射性、天文 |

---

### 7. 电磁波的能量：Poynting Vector

**能量密度**：

$$u_E = \frac{1}{2}\varepsilon_0 E^2, \quad u_B = \frac{1}{2\mu_0}B^2$$

对于电磁波，$$u_E = u_B$$，总能量密度：

$$u_{\text{total}} = \varepsilon_0 E^2 = \frac{B^2}{\mu_0}$$

**Poynting Vector（坡印廷矢量）** — 单位时间通过单位面积的能量（能流密度）：

$$\mathbf{S} = \frac{1}{\mu_0} \mathbf{E} \times \mathbf{B}$$

方向 = 电磁波传播方向，大小：

$$S = \frac{EB}{\mu_0} = \frac{E^2}{\mu_0 c} = c\varepsilon_0 E^2$$

**Intensity（强度）** — 时间平均值：

$$I = S_{\text{avg}} = \frac{E_0 B_0}{2\mu_0} = \frac{E_0^2}{2\mu_0 c} = \frac{c\varepsilon_0}{2}E_0^2$$

**点光源强度随距离衰减**：$$I = \frac{P}{4\pi r^2}$$

---

### 8. 辐射压力（Radiation Pressure）

光子有能量也有动量，所以电磁波可以施加压力。

$$p = \frac{U}{c} \quad \text{（光子动量）}$$

| 情况 | 辐射压力 |
|:----|:--------|
| **完全吸收** | $$P_{\text{rad}} = \frac{I}{c}$$ |
| **完全反射** | $$P_{\text{rad}} = \frac{2I}{c}$$ |

💡 **应用**：彗星尾巴（尘埃尾因辐射压力被推离太阳）、太阳帆飞船

---

### 9. 公式速查

| 公式 | 用途 |
|:----|:-----|
| $$v = 1/\sqrt{\mu_0\varepsilon_0}$$ | 真空中电磁波速度 |
| $$c = 3\times 10^8 \text{ m/s}$$ | 光速 |
| $$E/B = c$$ | 电磁波中电场与磁场的关系 |
| $$k = 2\pi/\lambda$$ | 波数 |
| $$\omega = 2\pi f$$ | 角频率 |
| $$I = E_0^2/(2\mu_0 c)$$ | 强度（能流密度的时间平均）|
| $$P_{\text{rad}} = I/c$$ | 完全吸收时的辐射压力 |
| $$S = (1/\mu_0)\mathbf{E}\times\mathbf{B}$$ | 坡印廷矢量 |
