---

## Ch.33 电磁波与光（续）

---

### 1. EM Waves in Matter（介质中的电磁波）

真空中光速为 $$c$$。在介质中：

$$v = \frac{c}{n}$$

其中 $$n$$ 为**折射率（Index of Refraction）**：

$$n = \sqrt{K K_m} \approx \sqrt{K} \quad (K_m \approx 1)$$

- $$K$$ = 介电常数（dielectric constant）
- 频率对 $$K$$ 有影响（色散的原因）
- 水的 $$K_{\text{static}} = 80$$，但在可见光频率下 $$K = 1.8$$

**光通过介质时**：
- 频率 $$f$$ **不变**
- 波长 $$\lambda$$ **变小**：$$\lambda_{\text{medium}} = \frac{\lambda_{\text{vacuum}}}{n}$$

---

### 2. 能量回顾 — Poynting Vector & Intensity

（同 Ch.32，复习）

$$\mathbf{S} = \frac{1}{\mu_0} \mathbf{E} \times \mathbf{B}, \quad I = S_{\text{avg}} = \frac{E_0 B_0}{2\mu_0}$$

点光源：$$I = \frac{P}{4\pi r^2}$$

---

### 3. 例题：太阳能 & 手机信号

**太阳能**：$$I \approx 1 \; \text{kW/m}^2$$

- $$E_0 = \sqrt{2\mu_0 c I} \approx 870 \; \text{V/m}$$
- $$B_0 = E_0/c \approx 2.9 \; \mu\text{T}$$

**手机信号**：发射功率 0.6 W，接收灵敏度 $$E_0 = 1.2 \; \text{mV/m}$$

- 最大距离 $$r \approx I \rightarrow P/4\pi r^2 \rightarrow$$ 代入公式算出

---

### 4. Polarization（偏振）

**偏振方向**：取电场 $$\mathbf{E}$$ 的振动方向作为偏振方向。

| 类型 | 说明 |
|:---|:-----|
| **Linearly Polarized（线偏振）** | E 在一个平面内振动 |
| **Circularly Polarized（圆偏振）** | E 矢量旋转（左旋/右旋）|
| **Unpolarized（自然光）** | E 随机方向，可分解为两个垂直分量 |

**起偏器（Polarizer）**：
- 自然光通过一个偏振片 → 强度减半（$$I_1 = I_0/2$$）
- 偏振光通过另一个偏振片（分析器）→ **Malus's Law（马吕斯定律）**：

$$I = I_0 \cos^2 \theta$$

其中 $$\theta$$ 为两偏振片透光轴的夹角。

**例题**：三个偏振片叠加放，中间一个旋转 $$45^\circ$$：
- A: $$I_0/2$$, B: $$I_0/2 \cdot \cos^2 45^\circ = I_0/4$$, C: $$I_0/4 \cdot \cos^2 45^\circ = I_0/8$$
- 如果去掉中间的偏振片，C 处光强 = **0**（两片垂直）

📝 **记忆**：偏振片的夹角越大，透过的光越少。$$90^\circ$$ 完全挡光。

**LCD 工作原理**：液晶在不通电时扭转 $$90^\circ$$（光能通过第二片偏振片），通电时液晶分子沿电场排列（不扭转，光被挡住）。

---

### 5. Reflection & Refraction（反射与折射）

**Snell's Law（斯涅尔定律）**：

$$n_1 \sin \theta_1 = n_2 \sin \theta_2$$

**反射定律**：$$\theta_1 = \theta_3$$（入射角 = 反射角）

---

### 6. Total Internal Reflection（全内反射）

条件：光从光密介质到光疏介质（$$n_1 > n_2$$）

**临界角（Critical Angle）**：

$$\sin \theta_c = \frac{n_2}{n_1}$$

当 $$\theta_1 > \theta_c$$ 时 → 全反射

💡 **应用**：光纤通信

---

### 7. Chromatic Dispersion（色散）

**折射率 $$n$$ 依赖于波长** — 不同颜色的光在介质中速度不同。

蓝光在玻璃中走得比红光慢 → 折射角不同 → 彩虹。

**彩虹形成三步**：
1. **折射**（太阳光进入水滴）
2. **反射**（水滴内壁一次反射）
3. **色散**（不同颜色折射角不同，分开）

视角：彩虹出现在太阳对面约 $$42^\circ$$ 处，红光在外侧（$$\sim 42.5^\circ$$），蓝紫在内侧（$$\sim 40.8^\circ$$）。

---

### 8. 易混淆概念对比

| 概念 | 区别 |
|:----|:----|
| **$$I_0/2$$** vs **$$I_0\cos^2\theta$$** | 前者是自然光过偏振片，后者是偏振光再过另一片 |
| **吸收** vs **反射** 的辐射压 | 反射是吸收的两倍 |
| **n 与频率有什么关系** | 频率越高（蓝光），n 越大，折射越厉害 |
| **彩虹颜色顺序** | 外红内紫（红光偏折最小）|

---

### 9. 公式速查

| 公式 | 用途 |
|:----|:-----|
| $$v = c/n$$ | 介质中光速 |
| $$n_1 \sin\theta_1 = n_2 \sin\theta_2$$ | Snell's Law |
| $$\sin\theta_c = n_2/n_1$$ | 全内反射临界角 |
| $$I = I_0\cos^2\theta$$ | 马吕斯定律（偏振片）|
| $$I_{\text{unpolarized}} = I_0/2$$ | 自然光过偏振片 |
| $$P_{\text{rad}} = I/c$$ | 辐射压力 |
