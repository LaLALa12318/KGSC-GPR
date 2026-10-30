# 道路地下病害电磁物理语义知识库

版本：1.0 文献审校版。检索与整理日期：2026-10-14。

**GPT 不生成新的物理结论。** 本库将既有理论、实验观察和工程解释归纳为统一中文描述；来源与适用条件决定知识能否使用。已做来源内容核对，但尚未由研究者逐条签核，也未与本地病害数据逐条验证。

## 规模与计数

| 类别 | K1 电性与反射 | K2 传播与响应 | K3 形态与空间 | 合计 |
|---|---:|---:|---:|---:|
| 空洞 | 15 | 15 | 15 | 45 |
| 脱空 | 15 | 15 | 15 | 45 |
| 严重疏松 | 15 | 15 | 15 | 45 |
| 合计 | 45 | 45 | 45 | 135 |

135 是类别与模块的**知识记录数**，不是135个类别独有、互不重复的物理定律。共享理论会在不同类别中条件化复用。按概念标识统计，共有 101 个主题；实验消融时应同时控制共享主题、文本长度和信息冗余。

## 适用边界

1. 空洞、脱空和严重疏松采用本项目的操作定义，不宣称存在统一规范的互斥分类。体积空隙与沿界面薄分离带可能交叠，应与数据标注规则一致。
2. 文献主要验证一般疏松、压实或空隙率；**未找到足以建立跨材料“严重疏松”统一雷达阈值的证据**。严重程度需采用项目已有外部工程标签。
3. 书本边界公式提供机制，不能直接证明某类病害必然出现某种图谱。跨工程域资料仅按部分或背景支撑使用。
4. 两篇引用不自动等于两个独立同情境实验；每条保留证据角色、内容位置和条件，未声称独立重复实验数量。
5. 引用核验与人工/本地数据核验分开：本版 `source_content_checked=true`，`human_review_status=not_performed`，`verified_for_local_dataset=false`。

## 本地使用

`knowledge.json` 包含元数据、来源表、公式附录和 `knowledge` 数组；`knowledge.jsonl` 一行一条，可直接作为原方案的输入。文本编码只读取 `knowledge_text`。DOI、来源编号与审校备注不进入编码。适用边界已尽可能写入短文本，仍需同步查看 `conditions` 和 `limitations`。

知识数增加后仍沿用9个模块原型与3个类别原型；本文没有生成向量或验证检测收益。`verified_for_local_dataset=false` 不表示公式无效，而表示没有完成本地对象与标签核验。

## 知识条目

## 空洞

### K1 介质电性与界面反射

#### cavity-K1-001 · 空气与围岩电性反差

空气填充空洞与常见土体或道路材料通常存在介电反差，空洞边界因波阻抗不连续而产生反射。实际是否可见还取决于反差和观测条件。

- 适用条件：空气填充；边界可被照射。
- 限制：反射存在不保证可检测。
- 类型：`theory_application`；概念：`air_contrast`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R08](https://doi.org/10.1016/j.ndteint.2024.103103)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R08：Abstract；Highlights；部分支撑。混凝土板控制实验；填充辨识与尺寸能力受具体设备与方法限制。

#### cavity-K1-002 · 法向反射系数

对低损耗、非磁性介质的平面空洞顶界面，法向电场反射系数由两侧介电常数决定；它描述界面反射而非仪器接收幅度。

- 适用条件：法向入射；平面界面；低损耗；非磁性。
- 限制：弯曲或强损耗边界不能直接套用简式。
- 类型：`theory_application`；概念：`fresnel`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。

#### cavity-K1-003 · 介质顺序与极性

在统一电场和波形约定下，从较高介电常数围介质进入空气空洞与反向传播的反射系数符号相反。图像黑白次序必须结合仪器极性标定解释。

- 适用条件：相同极性约定；界面反射可分辨。
- 限制：不以黑白颜色直接固定类别。
- 类型：`theory_application`；概念：`polarity_order`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R23](https://doi.org/10.3390/app16199835)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

#### cavity-K1-004 · 水填充改变电性

空洞由空气填充变为富水填充时，其介电性质及与围介质的阻抗反差会改变，雷达极性和幅度可能随之变化。

- 适用条件：区分空气与水填充；已知背景。
- 限制：富水不能默认等同于纯水参数。
- 类型：`theory_application`；概念：`water_fill`。
- 来源：[R08](https://doi.org/10.1016/j.ndteint.2024.103103), [R23](https://doi.org/10.3390/app16199835)。
  - R08：Abstract；Highlights；部分支撑。混凝土板控制实验；填充辨识与尺寸能力受具体设备与方法限制。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

#### cavity-K1-005 · 背景含水率

围介质含水率改变其介电性质，从而改变空气空洞的反差；含水状态应与空洞响应一并解释。

- 适用条件：相近矿物组成与测量频带。
- 限制：含水率不是反射强度的唯一变量。
- 类型：`theory_application`；概念：`background_moisture`。
- 来源：[R03](https://doi.org/10.1029/wr016i003p00574), [R08](https://doi.org/10.1016/j.ndteint.2024.103103)。
  - R03：Abstract；四种矿质土的实验范围；部分支撑。TDR 土体实验；不能直接给道路病害反射幅值或跨材料严重程度。
  - R08：Abstract；Highlights；部分支撑。混凝土板控制实验；填充辨识与尺寸能力受具体设备与方法限制。

#### cavity-K1-006 · 损耗介质阻抗

在导电或介电损耗不可忽略的围介质中，空洞界面的阻抗和反射系数具有复数性质，幅度与相位共同受电磁参数控制。

- 适用条件：线性介质；频率域描述。
- 限制：不能只用实介电常数解释强损耗条件。
- 类型：`theory_application`；概念：`complex_properties`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R24](https://doi.org/10.1190/geo2012-0266.1)。
  - R33：§9.2.4，教材页269–273；部分支撑。高损耗条件不可使用低损耗实参数简式。
  - R24：Abstract；magnetite–sand laboratory experiments；部分支撑。磁性材料例外；不是一般疏松或空洞直接实验。

#### cavity-K1-007 · 非磁性近似边界

普通道路介质常采用非磁性近似；若空洞周围含显著磁性矿物，则磁导率影响传播和反射，单纯介电模型可能不足。

- 适用条件：区分一般材料与磁性材料。
- 限制：不能将非磁性近似作为普适事实。
- 类型：`theory_application`；概念：`magnetic_boundary`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R24](https://doi.org/10.1190/geo2012-0266.1)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R24：Abstract；magnetite–sand laboratory experiments；部分支撑。磁性材料例外；不是一般疏松或空洞直接实验。

#### cavity-K1-008 · 斜入射反射

空洞边界的局部倾斜会改变入射角；斜入射时反射与折射遵循相应边界条件，不能仅按法向反射估计强度。

- 适用条件：局部平面近似；已知入射几何。
- 限制：接收幅度还受天线方向图影响。
- 类型：`theory_application`；概念：`oblique_incidence`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr)。
  - R33：§9.2.1–9.2.2，教材页260–268；部分支撑。需满足局部平面与相应介质近似。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。

#### cavity-K1-009 · 极化相关反射

斜入射空洞界面上的 TE 与 TM 分量一般具有不同反射系数，因此天线极化和界面方向会影响响应。

- 适用条件：斜入射；明确入射面与极化。
- 限制：不是空洞独有的响应规律。
- 类型：`theory_application`；概念：`polarization`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R31](https://doi.org/10.1190/1.1635047)。
  - R33：§9.2.1–9.2.2，教材页260–268；部分支撑。需满足局部平面与相应介质近似。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。

#### cavity-K1-010 · 反射与透射分配

空洞顶界面将入射能量分为反射和透射部分；顶界面反射较强并不意味着全部能量被反射，底界面仍可能受到照射。

- 适用条件：低损耗可用能量守恒；明确界面。
- 限制：有损条件还需计入吸收。
- 类型：`theory_application`；概念：`transmission_energy`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R08](https://doi.org/10.1016/j.ndteint.2024.103103)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R08：Abstract；Highlights；部分支撑。混凝土板控制实验；填充辨识与尺寸能力受具体设备与方法限制。

#### cavity-K1-011 · 顶底边界电性

空洞顶部与底部对应不同方向的介质跃迁；两个边界的反射可共同影响记录，且不能默认具有相同接收幅度。

- 适用条件：空洞具有可定义顶底界面。
- 限制：底部回波可能无法观测。
- 类型：`theory_application`；概念：`two_boundaries`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R08](https://doi.org/10.1016/j.ndteint.2024.103103)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R08：Abstract；Highlights；部分支撑。混凝土板控制实验；填充辨识与尺寸能力受具体设备与方法限制。

#### cavity-K1-012 · 低反差空洞

当空洞填充物与围介质的电磁性质接近时，界面反射减弱，几何空隙存在仍可能缺少明显雷达异常。

- 适用条件：填充物与背景阻抗接近。
- 限制：未见强反射不能证明无空洞。
- 类型：`theory_application`；概念：`weak_contrast`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R23](https://doi.org/10.3390/app16199835)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

#### cavity-K1-013 · 混合填充界面

部分充水或含残留土体的空洞具有多个介质界面，其响应不能简单归入纯空气空洞或纯水空洞的单一反射模式。

- 适用条件：存在混合填充；多界面结构。
- 限制：作为多界面理论的条件化应用；非专门实测结论。
- 类型：`theory_application`；概念：`partial_fill`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R33：§8.1.2–8.1.3，教材页232–236；部分支撑。TEM 例子仅支撑叠加原理；道路薄层具体结果由专门论文补充。

#### cavity-K1-014 · 反差与观测幅值

空洞界面的理论反射系数与记录幅度不同；传播损耗、几何扩散和地面耦合会改变接收幅度。

- 适用条件：比较采用一致采集与处理。
- 限制：幅度不能直接换算空洞体积。
- 类型：`theory_application`；概念：`contrast_vs_observed`。
- 来源：[R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr), [R31](https://doi.org/10.1190/1.1635047)。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。

#### cavity-K1-015 · 同类反射的非唯一性

强电性反差也可来自管线、金属或材料界面；单一强反射不能独立确认空洞类别。

- 适用条件：城市道路存在多类地下目标。
- 限制：须结合空间形态与验证。
- 类型：`theory_application`；概念：`material_confounds`。
- 来源：[R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr), [R32](https://doi.org/10.3390/s25185713)。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。
  - R32：Abstract；三相混凝土模型及钻孔验证说明；部分支撑。混凝土骨料情境；不把伪曲线推广为所有完整材料表现。

### K2 电磁波传播与信号响应

#### cavity-K2-001 · 围介质波速

低损耗、非磁性近似下，空洞上覆介质的雷达速度约随相对介电常数平方根的倒数变化，走时转换需使用当地速度。

- 适用条件：低损耗；非磁性；局部均匀。
- 限制：不直接用空气速度换算空洞埋深。
- 类型：`theory_application`；概念：`velocity`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr)。
  - R33：§2.2–2.3.3；§9.2.2；部分支撑。对道路对象是条件化理论应用，不是密实度或病害等级实验。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。

#### cavity-K2-002 · 顶部两程走时

近垂直传播条件下，空洞顶面深度由上覆各层的两程传播时间累积决定；层状介质中不能只用单层参数解释走时。

- 适用条件：近零偏移；已知时间零点和层速度。
- 限制：有限收发间距需考虑路径。
- 类型：`theory_application`；概念：`two_way_time`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr)。
  - R33：§2.2–2.3.3；§9.2.2；部分支撑。对道路对象是条件化理论应用，不是密实度或病害等级实验。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。

#### cavity-K2-003 · 腔内传播延迟

相同腔高条件下，空气与富水填充的传播速度不同，顶底回波的间隔不能用同一填充速度解释。

- 适用条件：顶底回波可辨；填充状态已知。
- 限制：回波间隔难辨时不可靠估厚。
- 类型：`theory_application`；概念：`fill_delay`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R08](https://doi.org/10.1016/j.ndteint.2024.103103)。
  - R33：§2.2–2.3.3；§9.2.2；部分支撑。对道路对象是条件化理论应用，不是密实度或病害等级实验。
  - R08：Abstract；Highlights；部分支撑。混凝土板控制实验；填充辨识与尺寸能力受具体设备与方法限制。

#### cavity-K2-004 · 顶底回波分辨

空洞厚度较小或有效带宽不足时，顶底回波会叠加；可识别异常不等于可准确恢复腔高。

- 适用条件：有限带宽脉冲；两界面结构。
- 限制：不存在跨设备通用最小可测厚度。
- 类型：`theory_application`；概念：`resolution`。
- 来源：[R23](https://doi.org/10.3390/app16199835), [R08](https://doi.org/10.1016/j.ndteint.2024.103103)。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。
  - R08：Abstract；Highlights；部分支撑。混凝土板控制实验；填充辨识与尺寸能力受具体设备与方法限制。

#### cavity-K2-005 · 多次反射

空洞及上覆层中的反射与透射可产生多次回波；后续波列不应未经核验就解释为多个独立空洞。

- 适用条件：可发生界面往返传播。
- 限制：脉冲振铃亦可产生相似波列。
- 类型：`theory_application`；概念：`multiples`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R23](https://doi.org/10.3390/app16199835)。
  - R33：§8.1.2–8.1.3，教材页232–236；部分支撑。TEM 例子仅支撑叠加原理；道路薄层具体结果由专门论文补充。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

#### cavity-K2-006 · 导电上覆层衰减

高导电性上覆土层会吸收雷达能量，削弱到达空洞和返回地表的信号，限制探测深度。

- 适用条件：考虑土层电导率和损耗。
- 限制：高含水率与高电导率不应完全等同。
- 类型：`theory_application`；概念：`conductive_attenuation`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr)。
  - R33：§9.2.4，教材页269–273；部分支撑。高损耗条件不可使用低损耗实参数简式。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。

#### cavity-K2-007 · 传播几何扩散

随着传播距离增大，雷达能量在空间扩散，深部空洞的幅度可因距离增加而降低。

- 适用条件：可比较的目标反差与几何。
- 限制：实际衰减并非仅由几何扩散决定。
- 类型：`theory_application`；概念：`spreading`。
- 来源：[R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr), [R30](https://doi.org/10.1177/03611981211004585)。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。
  - R30：Abstract；static and dynamic tests；部分支撑。支持采集混杂；不验证任何地下病害类别。

#### cavity-K2-008 · 频率与探测尺度

较高频率有利于分辨较小空洞结构，但其有效探测深度受材料损耗和系统带宽约束，频率选择需匹配目标深度和尺度。

- 适用条件：具体设备与现场材料。
- 限制：不能把中心频率直接当作分辨率。
- 类型：`theory_application`；概念：`frequency_tradeoff`。
- 来源：[R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr), [R27](https://doi.org/10.1049/iet-rsn.2015.0133)。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。
  - R27：Abstract；§2.1 材料性质说明；部分支撑。Ku 波段与普通道路 GPR 频带不同；不可迁移数值阈值。

#### cavity-K2-009 · 有限目标绕射走时

有限空洞边缘或小目标可形成绕射曲线；在简化均匀介质观测中，测线位置改变传播距离而形成近双曲线走时。

- 适用条件：均匀速度近似；有限目标或边缘。
- 限制：双曲线不是空洞专属形态。
- 类型：`theory_application`；概念：`diffraction_hyperbola`。
- 来源：[R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr), [R09](https://doi.org/10.1155/2019/1365759)。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。
  - R09：Abstract；道路与模型场试验比较；部分支撑。只支持其测试条件；经验公式不作跨场景标准。

#### cavity-K2-010 · 尺度与波形

空洞尺寸相对于波长的变化会影响响应波形和边界可辨程度；同类空洞可以表现为不同雷达形态。

- 适用条件：明确波长与目标尺度。
- 限制：不采用固定波形作为类别充分条件。
- 类型：`theory_application`；概念：`size_wavelength`。
- 来源：[R23](https://doi.org/10.3390/app16199835), [R32](https://doi.org/10.3390/s25185713)。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。
  - R32：Abstract；三相混凝土模型及钻孔验证说明；部分支撑。混凝土骨料情境；不把伪曲线推广为所有完整材料表现。

#### cavity-K2-011 · 背景散射遮蔽

混凝土骨料等非均匀成分可产生散射和伪异常，使薄小空洞回波被遮蔽或边界失真。

- 适用条件：骨料非均匀混凝土路面。
- 限制：数值和工程情境需对应。
- 类型：`theory_application`；概念：`scattering_background`。
- 来源：[R32](https://doi.org/10.3390/s25185713), [R31](https://doi.org/10.1190/1.1635047)。
  - R32：Abstract；三相混凝土模型及钻孔验证说明；部分支撑。混凝土骨料情境；不把伪曲线推广为所有完整材料表现。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。

#### cavity-K2-012 · 钢筋回波干扰

钢筋产生的显著反射及曲线形态可能覆盖空洞响应，使空洞横向尺度解译困难。

- 适用条件：钢筋混凝土覆盖结构。
- 限制：不把钢筋曲线作为空洞边缘。
- 类型：`theory_application`；概念：`rebar_masking`。
- 来源：[R08](https://doi.org/10.1016/j.ndteint.2024.103103), [R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr)。
  - R08：Abstract；Highlights；部分支撑。混凝土板控制实验；填充辨识与尺寸能力受具体设备与方法限制。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。

#### cavity-K2-013 · 底部可见性

空洞顶界面可见时，其底界面仍可能因传播路径、叠加或损耗而不可辨；缺失底部回波不证明空洞没有底部。

- 适用条件：有限带宽和信噪比。
- 限制：腔高测量需要额外条件。
- 类型：`theory_application`；概念：`bottom_visibility`。
- 来源：[R08](https://doi.org/10.1016/j.ndteint.2024.103103), [R23](https://doi.org/10.3390/app16199835)。
  - R08：Abstract；Highlights；部分支撑。混凝土板控制实验；填充辨识与尺寸能力受具体设备与方法限制。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

#### cavity-K2-014 · 偏移与速度

适当速度下的偏移处理可聚焦空洞边缘绕射并改善位置解释；速度误差会影响聚焦和几何恢复。

- 适用条件：偏移模型适合现场；速度已校准。
- 限制：处理后的尺寸仍需实测验证。
- 类型：`theory_application`；概念：`migration_velocity`。
- 来源：[R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr), [R09](https://doi.org/10.1155/2019/1365759)。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。
  - R09：Abstract；道路与模型场试验比较；部分支撑。只支持其测试条件；经验公式不作跨场景标准。

#### cavity-K2-015 · 处理后的幅度

增益补偿和归一化会改变空洞异常的显示强度，处理后的亮度不能直接作为原始反射能量。

- 适用条件：记录并统一处理流程。
- 限制：处理不能恢复未被采集的信息。
- 类型：`theory_application`；概念：`processed_amplitude`。
- 来源：[R16](https://doi.org/10.3389/fmats.2026.1839264), [R30](https://doi.org/10.1177/03611981211004585)。
  - R16：§3.1中增益处理段落（滤波讨论之后）；Fig.9；部分支撑。仅使用增益段落，不使用该节不相干的生理信号滤波解释。
  - R30：Abstract；static and dynamic tests；部分支撑。支持采集混杂；不验证任何地下病害类别。

### K3 病害形态与工程空间关系

#### cavity-K3-001 · 体积性空隙

空洞在本知识库中指具有有限三维范围、局部缺失连续固体骨架的空隙体；其几何范围与松散但仍含材料的区域应分别描述。

- 适用条件：工程分类约定；允许空气或水填充。
- 限制：该定义为项目操作定义，不是统一规范分类。
- 类型：`engineering_definition`；概念：`volume_definition`。
- 来源：[R16](https://doi.org/10.3389/fmats.2026.1839264), [R08](https://doi.org/10.1016/j.ndteint.2024.103103)。
  - R16：§2.1.2.2；§3.2；§3.3.2–3.3.3；Limitations；部分支撑。1600 MHz 小尺度拼装试件；未验证严重等级；排除§3.1中与生理信号有关的异常措辞和可疑滤波解释。
  - R08：Abstract；Highlights；部分支撑。混凝土板控制实验；填充辨识与尺寸能力受具体设备与方法限制。

#### cavity-K3-002 · 相对层位

道路空洞可位于结构层内或结构层下方，解释异常时需记录其与面层、基层和路基的相对位置。

- 适用条件：层位可追踪或有钻孔资料。
- 限制：仅凭深度不能确认病害类别。
- 类型：`engineering_interpretation`；概念：`layer_position`。
- 来源：[R23](https://doi.org/10.3390/app16199835), [R32](https://doi.org/10.3390/s25185713)。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。
  - R32：Abstract；三相混凝土模型及钻孔验证说明；部分支撑。混凝土骨料情境；不把伪曲线推广为所有完整材料表现。

#### cavity-K3-003 · 顶面几何

空洞顶面的平缓、倾斜或起伏会改变反射的横向走时与连续性；反射同相轴形态应结合顶面几何解释。

- 适用条件：界面反射可追踪；速度模型已知。
- 限制：同相轴起伏也可能由速度变化造成。
- 类型：`engineering_interpretation`；概念：`roof_geometry`。
- 来源：[R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr), [R21](https://doi.org/10.2113/gseegeosci.20.2.109)。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。
  - R21：Abstract；covered karst collapse and sagging cases；背景支撑。岩溶工程与道路空洞不同，仅支持条件化空间背景解释。

#### cavity-K3-004 · 边缘位置

有限空洞的侧缘可产生绕射，异常的横向起止位置需结合边缘响应与连续顶面反射判定。

- 适用条件：测线穿过目标；边缘可见。
- 限制：图上最外端不必等于物理边缘。
- 类型：`engineering_interpretation`；概念：`edge_diffraction`。
- 来源：[R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr), [R09](https://doi.org/10.1155/2019/1365759)。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。
  - R09：Abstract；道路与模型场试验比较；部分支撑。只支持其测试条件；经验公式不作跨场景标准。

#### cavity-K3-005 · 平面范围偏差

原始雷达异常的宽度可能大于实际空洞宽度，天线照射范围和绕射使响应范围与真实平面边界不同。

- 适用条件：空洞尺度估计；特定采集几何。
- 限制：经验校正公式不能跨现场直接使用。
- 类型：`engineering_interpretation`；概念：`plan_size_bias`。
- 来源：[R09](https://doi.org/10.1155/2019/1365759), [R23](https://doi.org/10.3390/app16199835)。
  - R09：Abstract；道路与模型场试验比较；部分支撑。只支持其测试条件；经验公式不作跨场景标准。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

#### cavity-K3-006 · 厚度与平面尺度

空洞的平面范围与腔高是不同几何量；能够恢复横向异常范围并不保证能够恢复厚度。

- 适用条件：明确尺寸定义与评价方向。
- 限制：不能将平面分割结果当作体积测量。
- 类型：`engineering_interpretation`；概念：`height_vs_width`。
- 来源：[R23](https://doi.org/10.3390/app16199835), [R08](https://doi.org/10.1016/j.ndteint.2024.103103)。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。
  - R08：Abstract；Highlights；部分支撑。混凝土板控制实验；填充辨识与尺寸能力受具体设备与方法限制。

#### cavity-K3-007 · 埋深解释误差

空洞埋深由走时与速度共同决定，含水变化或分层速度误差会引入深度偏差。

- 适用条件：速度需现场校准。
- 限制：层位对应应保留不确定性。
- 类型：`engineering_interpretation`；概念：`depth_geometry_uncertainty`。
- 来源：[R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr), [R19](https://doi.org/10.1038/s41467-023-39236-4)。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。
  - R19：Methods 中钻孔校准、波速与时深转换说明；背景支撑。深搅桩工程；仅支持验证与标定方法，不支持三类病害专属形态。

#### cavity-K3-008 · 三维连通范围

多测线或三维雷达的横断面与水平切片可用于检查空洞异常的空间连通性；单条测线只提供有限截面。

- 适用条件：测线配准；采样覆盖充分。
- 限制：连通反射不自动等于真实连通空腔。
- 类型：`engineering_interpretation`；概念：`three_dimensional_extent`。
- 来源：[R23](https://doi.org/10.3390/app16199835), [R32](https://doi.org/10.3390/s25185713)。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。
  - R32：Abstract；三相混凝土模型及钻孔验证说明；部分支撑。混凝土骨料情境；不把伪曲线推广为所有完整材料表现。

#### cavity-K3-009 · 测线交会位置

穿过空洞中心与侧缘的测线会得到不同截面和响应宽度，单个截面不能唯一确定完整空洞形状。

- 适用条件：有限三维目标；不同测线位置。
- 限制：作为几何观测限制，不是病害独有规律。
- 类型：`engineering_interpretation`；概念：`survey_intersection`。
- 来源：[R09](https://doi.org/10.1155/2019/1365759), [R23](https://doi.org/10.3390/app16199835)。
  - R09：Abstract；道路与模型场试验比较；部分支撑。只支持其测试条件；经验公式不作跨场景标准。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

#### cavity-K3-010 · 不规则边界

工程空洞可具有不规则形状，规则矩形或圆形模型只能代表特定几何条件，不能固定为所有空洞的形态。

- 适用条件：区分控制模型与现场对象。
- 限制：规则模型参数不可直接当作工程统计。
- 类型：`engineering_interpretation`；概念：`irregular_shape`。
- 来源：[R16](https://doi.org/10.3389/fmats.2026.1839264), [R09](https://doi.org/10.1155/2019/1365759)。
  - R16：§2.1.2.2；§3.2；§3.3.2–3.3.3；Limitations；部分支撑。1600 MHz 小尺度拼装试件；未验证严重等级；排除§3.1中与生理信号有关的异常措辞和可疑滤波解释。
  - R09：Abstract；道路与模型场试验比较；部分支撑。只支持其测试条件；经验公式不作跨场景标准。

#### cavity-K3-011 · 空隙与残留骨架

残留土体或局部回填使空洞内部出现空间非均匀性；工程解译应区分连续空隙与含松散骨架的体积区。

- 适用条件：填充和骨架状态可核验。
- 限制：类别边界按项目统一标注规则执行。
- 类型：`engineering_interpretation`；概念：`rubble_fill`。
- 来源：[R16](https://doi.org/10.3389/fmats.2026.1839264), [R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)。
  - R16：§2.1.2.2；§3.2；§3.3.2–3.3.3；Limitations；部分支撑。1600 MHz 小尺度拼装试件；未验证严重等级；排除§3.1中与生理信号有关的异常措辞和可疑滤波解释。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。

#### cavity-K3-012 · 管线与空洞区分

管线也可产生曲线异常；空洞判别应结合多测线中的延展方向、层位及地下设施资料。

- 适用条件：城市道路管线背景。
- 限制：曲线形态不足以单独区分管线与空洞。
- 类型：`engineering_interpretation`；概念：`pipe_confusion`。
- 来源：[R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr), [R08](https://doi.org/10.1016/j.ndteint.2024.103103)。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。
  - R08：Abstract；Highlights；部分支撑。混凝土板控制实验；填充辨识与尺寸能力受具体设备与方法限制。

#### cavity-K3-013 · 空洞与层间脱空区分

沿结构界面延展的薄分离带与体积性空洞可能具有相似反射；本项目按层间位置及三维几何组织类别。

- 适用条件：工程操作定义；已知层位。
- 限制：两类可有几何交集，需固定标注规则。
- 类型：`engineering_definition`；概念：`interlayer_vs_volume`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R23](https://doi.org/10.3390/app16199835)。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

#### cavity-K3-014 · 周围层位变形

周围层位弯曲或中断可为地下空隙和塌陷解译提供空间背景，但层位变形不能单独证明存在空洞。

- 适用条件：有背景层位参照。
- 限制：岩溶塌陷研究对道路对象仅属条件化迁移。
- 类型：`engineering_interpretation`；概念：`deformation_context`。
- 来源：[R21](https://doi.org/10.2113/gseegeosci.20.2.109), [R02](https://doi.org/10.1111/j.1365-2478.1989.tb02221.x)。
  - R21：Abstract；covered karst collapse and sagging cases；背景支撑。岩溶工程与道路空洞不同，仅支持条件化空间背景解释。
  - R02：Abstract；borehole corroboration case histories；背景支撑。对道路病害仅提供一般空间解释背景。

#### cavity-K3-015 · 几何实测核验

钻孔、内窥或开挖可核查空洞存在与局部几何；雷达范围估计应与相应空间尺度的实测资料比较。

- 适用条件：核验位置与雷达配准。
- 限制：单钻孔不能验证全部平面范围。
- 类型：`engineering_interpretation`；概念：`ground_truth_geometry`。
- 来源：[R09](https://doi.org/10.1155/2019/1365759), [R23](https://doi.org/10.3390/app16199835)。
  - R09：Abstract；道路与模型场试验比较；部分支撑。只支持其测试条件；经验公式不作跨场景标准。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

## 脱空

### K1 介质电性与界面反射

#### debonding-K1-001 · 层间接触不连续

脱空或脱黏改变相邻道路结构层的接触状态；当其引入电磁性质不同的夹层时，原界面反射条件会发生变化。

- 适用条件：存在可产生电性变化的分离或夹层。
- 限制：纯接触力学劣化不必产生足够雷达反差。
- 类型：`theory_application`；概念：`contact_discontinuity`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。

#### debonding-K1-002 · 空气夹层反差

空气填充的层间间隙与道路结构材料通常具有介电反差，从而增加不同介质边界。

- 适用条件：明确空气夹层；非磁性近似。
- 限制：新增边界未必分别可辨。
- 类型：`theory_application`；概念：`air_contrast`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R07](https://doi.org/10.1016/j.conbuildmat.2023.132834)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。

#### debonding-K1-003 · 富水脱空电性

脱空内积水会改变夹层介电性质及界面阻抗，其响应不能按空气脱空模型解释。

- 适用条件：明确填充与含水状态。
- 限制：实验中的含水替代材料不等同于现场纯水。
- 类型：`theory_application`；概念：`water_fill`。
- 来源：[R07](https://doi.org/10.1016/j.conbuildmat.2023.132834), [R08](https://doi.org/10.1016/j.ndteint.2024.103103)。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。
  - R08：Abstract；Highlights；部分支撑。混凝土板控制实验；填充辨识与尺寸能力受具体设备与方法限制。

#### debonding-K1-004 · 夹层界面反射系数

在低损耗平面近似下，脱空上、下边界的电场反射系数分别由相邻介质的阻抗决定。

- 适用条件：平面分层；低损耗；法向入射。
- 限制：需分别考虑两个界面。
- 类型：`theory_application`；概念：`fresnel`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R28](https://doi.org/10.1016/j.conbuildmat.2017.06.132)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R28：Abstract；Highlights；Introduction；Data acquisition；部分支撑。小于主导波长四分之一的条件性结果；实验用石膏和泡沫替代材料。

#### debonding-K1-005 · 上下面反射符号

由结构材料进入低介电空气夹层与由空气进入结构材料的反射符号通常相反，符号解释应遵循统一波形约定。

- 适用条件：低损耗；相同电场约定。
- 限制：记录的复合波形不必呈现两段独立反相回波。
- 类型：`theory_application`；概念：`polarity_order`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R28](https://doi.org/10.1016/j.conbuildmat.2017.06.132)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R28：Abstract；Highlights；Introduction；Data acquisition；部分支撑。小于主导波长四分之一的条件性结果；实验用石膏和泡沫替代材料。

#### debonding-K1-006 · 有限厚度等效反射

脱空夹层的整体反射是多界面传播与叠加结果，其等效反射同时受夹层电性、厚度和频率影响。

- 适用条件：分层夹层模型；线性波传播。
- 限制：不能将整体幅度当作单界面系数。
- 类型：`theory_application`；概念：`equivalent_thin_layer`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R28](https://doi.org/10.1016/j.conbuildmat.2017.06.132)。
  - R33：§8.1.2–8.1.3，教材页232–236；部分支撑。TEM 例子仅支撑叠加原理；道路薄层具体结果由专门论文补充。
  - R28：Abstract；Highlights；Introduction；Data acquisition；部分支撑。小于主导波长四分之一的条件性结果；实验用石膏和泡沫替代材料。

#### debonding-K1-007 · 无明显电性反差的脱黏

若脱黏未形成明显空气、水或其他夹层，两侧电磁性质变化较小，力学接触变差也可能缺少清晰雷达响应。

- 适用条件：脱黏程度与填充状态分别描述。
- 限制：不把无雷达异常解释为黏结完好。
- 类型：`theory_application`；概念：`weak_contrast`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R06](https://doi.org/10.1016/j.jappgeo.2022.104722)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。

#### debonding-K1-008 · 相邻层含水状态

脱空两侧材料的含水变化可改变其介电参数，影响夹层与背景之间的反差。

- 适用条件：比较时控制材料与含水率。
- 限制：夹层响应变化不唯一代表脱空扩大。
- 类型：`theory_application`；概念：`background_moisture`。
- 来源：[R03](https://doi.org/10.1029/wr016i003p00574), [R07](https://doi.org/10.1016/j.conbuildmat.2023.132834)。
  - R03：Abstract；四种矿质土的实验范围；部分支撑。TDR 土体实验；不能直接给道路病害反射幅值或跨材料严重程度。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。

#### debonding-K1-009 · 夹层导电损耗

导电水或高损耗填充会改变脱空夹层的复阻抗并吸收能量，反射相位与幅度需共同解释。

- 适用条件：线性损耗介质；明确频带。
- 限制：不能仅用纯水实介电常数解释导电积水。
- 类型：`theory_application`；概念：`complex_properties`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R07](https://doi.org/10.1016/j.conbuildmat.2023.132834)。
  - R33：§9.2.4，教材页269–273；部分支撑。高损耗条件不可使用低损耗实参数简式。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。

#### debonding-K1-010 · 倾斜界面入射

道路层位或脱空界面倾斜时，局部入射角影响反射与透射；法向反射简式仅适用于相应近似。

- 适用条件：局部平面界面；已知几何。
- 限制：不是脱空特有的电磁规律。
- 类型：`theory_application`；概念：`oblique_incidence`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr)。
  - R33：§9.2.1–9.2.2，教材页260–268；部分支撑。需满足局部平面与相应介质近似。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。

#### debonding-K1-011 · 界面极化响应

脱空界面斜入射时，TE 与 TM 分量具有不同边界响应，极化条件影响可接收的反射。

- 适用条件：明确极化与入射面。
- 限制：不同天线通道不能直接比较未经校准幅值。
- 类型：`theory_application`；概念：`polarization`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R07](https://doi.org/10.1016/j.conbuildmat.2023.132834)。
  - R33：§9.2.1–9.2.2，教材页260–268；部分支撑。需满足局部平面与相应介质近似。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。

#### debonding-K1-012 · 非空气填充脱空

砂、土工材料或缺少黏层形成的接触异常与理想空气夹层不同，需按实际填充材料描述脱空电性。

- 适用条件：参照具体人工脱黏模型与现场材料。
- 限制：人工处理类型不是通用工程分类标准。
- 类型：`theory_application`；概念：`fill_materials`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。

#### debonding-K1-013 · 上层透射限制

脱空响应依赖雷达波先透过上覆结构层；上部强反射或损耗会改变到达层间异常的能量。

- 适用条件：考虑上覆层及夹层。
- 限制：不能只按脱空本身介电反差预测可见性。
- 类型：`theory_application`；概念：`transmission_energy`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。

#### debonding-K1-014 · 正常层界反射

完整道路的正常材料界面也会产生反射；识别脱空需相对完整结构的界面响应评估异常。

- 适用条件：有完整结构参照；采集条件一致。
- 限制：连续强层界不是脱空充分证据。
- 类型：`theory_application`；概念：`material_confounds`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R07](https://doi.org/10.1016/j.conbuildmat.2023.132834)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。

#### debonding-K1-015 · 幅值与脱空程度

接收幅值同时受脱空夹层、传播、耦合和处理影响，不能建立未经校准的通用幅值—脱空程度对应关系。

- 适用条件：同设备与相同处理；限定材料。
- 限制：特定荷载实验趋势不可直接推广。
- 类型：`theory_application`；概念：`contrast_vs_observed`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R30](https://doi.org/10.1177/03611981211004585)。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R30：Abstract；static and dynamic tests；部分支撑。支持采集混杂；不验证任何地下病害类别。

### K2 电磁波传播与信号响应

#### debonding-K2-001 · 薄层回波叠加

薄脱空的两界面回波可能在时域重叠，传统共同偏移剖面难以直接分开上、下界面。

- 适用条件：薄夹层；有限脉冲宽度。
- 限制：可检测异常与可测厚度需分别评价。
- 类型：`theory_application`；概念：`resolution`。
- 来源：[R29](https://doi.org/10.3390/s16122067), [R07](https://doi.org/10.1016/j.conbuildmat.2023.132834)。
  - R29：§2.5–2.6；Figs.9–10；§3 Results；部分支撑。文内假定验收阈值不是道路严重疏松统一标准。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。

#### debonding-K2-002 · 厚度控制干涉

脱空厚度改变夹层内传播相位，从而改变两界面回波的干涉状态与复合波形。

- 适用条件：分层波传播；同一系统波形。
- 限制：幅度不一定随厚度单调增大。
- 类型：`theory_application`；概念：`interference_thickness`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R28](https://doi.org/10.1016/j.conbuildmat.2017.06.132)。
  - R33：§8.1.2–8.1.3，教材页232–236；部分支撑。TEM 例子仅支撑叠加原理；道路薄层具体结果由专门论文补充。
  - R28：Abstract；Highlights；Introduction；Data acquisition；部分支撑。小于主导波长四分之一的条件性结果；实验用石膏和泡沫替代材料。

#### debonding-K2-003 · 频谱包含夹层信息

脱空的多界面叠加可改变复合反射的频谱，时间—频率表征能补充单一时域幅值信息。

- 适用条件：明确分析窗和系统带宽。
- 限制：频谱变化并非脱空专属指标。
- 类型：`theory_application`；概念：`phase_frequency`。
- 来源：[R28](https://doi.org/10.1016/j.conbuildmat.2017.06.132), [R06](https://doi.org/10.1016/j.jappgeo.2022.104722)。
  - R28：Abstract；Highlights；Introduction；Data acquisition；部分支撑。小于主导波长四分之一的条件性结果；实验用石膏和泡沫替代材料。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。

#### debonding-K2-004 · 薄空气层频峰变化

在已有分层空气间隙模型中，间隙厚度小于主导波长四分之一时，复合反射的峰值瞬时频率高于完整界面。

- 适用条件：对应 Liu 等分层模型及实验；空气夹层。
- 限制：该条件性结果不能写成所有脱空频率升高。
- 类型：`context_specific_observation`；概念：`thin_air_frequency_shift`。
- 来源：[R28](https://doi.org/10.1016/j.conbuildmat.2017.06.132), [R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)。
  - R28：Abstract；Highlights；Introduction；Data acquisition；强支撑（仅限所列情境）。小于主导波长四分之一的条件性结果；实验用石膏和泡沫替代材料。
  - R33：§8.1.2–8.1.3，教材页232–236；部分支撑。TEM 例子仅支撑叠加原理；道路薄层具体结果由专门论文补充。

#### debonding-K2-005 · 荷载后的频谱变化

特定加速加载人工脱黏路面中，随加载循环增加，归一化幅度增大且反射中心频率下移。

- 适用条件：Hui 等 2600 MHz 人工脱黏加载实验。
- 限制：不能据此给现场脱空规定普适增长规律。
- 类型：`context_specific_observation`；概念：`loading_spectrum`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R28](https://doi.org/10.1016/j.conbuildmat.2017.06.132)。
  - R06：Abstract；2600 MHz 加速加载试验；强支撑（仅限所列情境）。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R28：Abstract；Highlights；Introduction；Data acquisition；强支撑（仅限所列情境）。小于主导波长四分之一的条件性结果；实验用石膏和泡沫替代材料。

#### debonding-K2-006 · 薄结构波导频散

薄沥青结构中的导波可具有频散；不同频率的相位速度与模式特征可反映层间状态变化。

- 适用条件：对应薄层波导结构与 WARR 测量。
- 限制：不能移植为所有普通 B 扫的响应规律。
- 类型：`theory_application`；概念：`waveguide_dispersion`。
- 来源：[R07](https://doi.org/10.1016/j.conbuildmat.2023.132834), [R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。
  - R33：§2.2–2.3.3；§9.2.2；部分支撑。对道路对象是条件化理论应用，不是密实度或病害等级实验。

#### debonding-K2-007 · 空气脱空截止频率

特定薄沥青波导模型及实验中，空气间隙增厚使部分模式截止频率降低，变化在薄间隙阶段较敏感。

- 适用条件：He 等波导模型；空气夹层；可提取频散曲线。
- 限制：实验趋势不能替代普通走时测厚。
- 类型：`context_specific_observation`；概念：`air_cutoff`。
- 来源：[R07](https://doi.org/10.1016/j.conbuildmat.2023.132834), [R28](https://doi.org/10.1016/j.conbuildmat.2017.06.132)。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；强支撑（仅限所列情境）。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。
  - R28：Abstract；Highlights；Introduction；Data acquisition；强支撑（仅限所列情境）。小于主导波长四分之一的条件性结果；实验用石膏和泡沫替代材料。

#### debonding-K2-008 · 富水夹层相速度

在已研究薄沥青波导实验中，含水夹层引起模式相速度下降，可与空气间隙的模式变化共同辅助辨识填充状态。

- 适用条件：He 等 WARR 配置；材料参数对应。
- 限制：饱和棉布替代水层的实验边界须保留。
- 类型：`context_specific_observation`；概念：`water_phase_velocity`。
- 来源：[R07](https://doi.org/10.1016/j.conbuildmat.2023.132834), [R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；强支撑（仅限所列情境）。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。
  - R33：§2.2–2.3.3；§9.2.2；部分支撑。对道路对象是条件化理论应用，不是密实度或病害等级实验。

#### debonding-K2-009 · 观测方式影响信息

共同偏移剖面与宽角反射折射测量提供的信息不同；利用频散识别薄脱空需要相应多偏移资料。

- 适用条件：区分 COP 与 WARR。
- 限制：不把 WARR 能力声明为固定偏移设备能力。
- 类型：`theory_application`；概念：`warr_vs_cop`。
- 来源：[R07](https://doi.org/10.1016/j.conbuildmat.2023.132834), [R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr)。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。

#### debonding-K2-010 · 层状结构多次波

脱空附近的道路层界可产生多次反射，与夹层回波叠加后改变波列和相位。

- 适用条件：多层传播；层界具有反差。
- 限制：多重同相轴不能直接等同于多层脱空。
- 类型：`theory_application`；概念：`multiples`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R07](https://doi.org/10.1016/j.conbuildmat.2023.132834)。
  - R33：§8.1.2–8.1.3，教材页232–236；部分支撑。TEM 例子仅支撑叠加原理；道路薄层具体结果由专门论文补充。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。

#### debonding-K2-011 · 上覆损耗与薄层遮蔽

上覆高损耗材料及其强回波可削弱或遮蔽薄脱空的接收响应。

- 适用条件：明确材料损耗和信噪比。
- 限制：未检测到薄层不代表无层间分离。
- 类型：`theory_application`；概念：`conductive_attenuation`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R32](https://doi.org/10.3390/s25185713)。
  - R33：§9.2.4，教材页269–273；部分支撑。高损耗条件不可使用低损耗实参数简式。
  - R32：Abstract；三相混凝土模型及钻孔验证说明；部分支撑。混凝土骨料情境；不把伪曲线推广为所有完整材料表现。

#### debonding-K2-012 · 带宽与薄层分辨

薄夹层的时域可分辨程度与有效带宽和介质速度有关，中心频率升高并不自动保证可靠测厚。

- 适用条件：实际有效带宽；材料速度已知。
- 限制：不规定未经校准的统一厚度阈值。
- 类型：`theory_application`；概念：`frequency_tradeoff`。
- 来源：[R28](https://doi.org/10.1016/j.conbuildmat.2017.06.132), [R27](https://doi.org/10.1049/iet-rsn.2015.0133)。
  - R28：Abstract；Highlights；Introduction；Data acquisition；部分支撑。小于主导波长四分之一的条件性结果；实验用石膏和泡沫替代材料。
  - R27：Abstract；§2.1 材料性质说明；部分支撑。Ku 波段与普通道路 GPR 频带不同；不可迁移数值阈值。

#### debonding-K2-013 · 参照幅度归一化

在一致采集条件下，脱空区相对完整区的幅度比较可减少部分系统差异，但仍需保持材料、耦合和处理条件可比。

- 适用条件：设置完整区参照；统一流程。
- 限制：归一化不能消除所有混杂因素。
- 类型：`theory_application`；概念：`baseline_normalization`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R30](https://doi.org/10.1177/03611981211004585)。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R30：Abstract；static and dynamic tests；部分支撑。支持采集混杂；不验证任何地下病害类别。

#### debonding-K2-014 · 处理与频谱稳定性

滤波和增益会改变薄脱空复合波形的幅度及频谱，进行时频比较时必须使用一致处理与分析窗。

- 适用条件：相同滤波、增益和时间窗。
- 限制：处理相关频峰不能当作未校正物理特征。
- 类型：`theory_application`；概念：`processed_amplitude`。
- 来源：[R16](https://doi.org/10.3389/fmats.2026.1839264), [R30](https://doi.org/10.1177/03611981211004585)。
  - R16：§3.1中增益处理段落（滤波讨论之后）；Fig.9；部分支撑。仅使用增益段落，不使用该节不相干的生理信号滤波解释。
  - R30：Abstract；static and dynamic tests；部分支撑。支持采集混杂；不验证任何地下病害类别。

#### debonding-K2-015 · 检测与厚度反演

薄脱空可以通过复合波形或频散变化被识别，而上、下边界仍不能在时域可靠分离；存在性检测与厚度反演须分开。

- 适用条件：薄层及有限带宽。
- 限制：厘米级个案检测不等同于跨现场厘米级精度。
- 类型：`theory_application`；概念：`detect_vs_measure`。
- 来源：[R07](https://doi.org/10.1016/j.conbuildmat.2023.132834), [R23](https://doi.org/10.3390/app16199835)。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

### K3 病害形态与工程空间关系

#### debonding-K3-001 · 层间分离位置

本项目将脱空定义为道路结构界面附近的局部接触缺失或分离带，其类别判断依赖层位关系与填充状态。

- 适用条件：工程操作定义；可识别相邻结构层。
- 限制：脱黏、分层和板底脱空不是完全同义术语。
- 类型：`engineering_definition`；概念：`interlayer_definition`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R07](https://doi.org/10.1016/j.conbuildmat.2023.132834)。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。

#### debonding-K3-002 · 横向延展

脱空常以沿界面延展的局部分离区建模，描述时应同时记录平面延展范围与法向厚度。

- 适用条件：对应层间病害；有空间覆盖。
- 限制：不设统一长厚比阈值。
- 类型：`engineering_interpretation`；概念：`lateral_extent`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R23](https://doi.org/10.3390/app16199835)。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

#### debonding-K3-003 · 黏结损失与开口区别

失去黏结可先于形成可分辨间隙；工程脱黏范围与雷达能识别的开口范围不一定一致。

- 适用条件：区分接触力学与电磁反差。
- 限制：不以雷达开口范围代表全部黏结损失。
- 类型：`engineering_interpretation`；概念：`contact_loss_vs_gap`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。

#### debonding-K3-004 · 完整界面参照

脱空定位应沿周围完整结构界面追踪，使异常位置与正常层界对齐，而非仅依靠图像亮度。

- 适用条件：存在邻近完整路段或设计层位。
- 限制：完整区也可能存在隐蔽异常。
- 类型：`engineering_interpretation`；概念：`layer_tracking`。
- 来源：[R07](https://doi.org/10.1016/j.conbuildmat.2023.132834), [R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。

#### debonding-K3-005 · 局部脱空与整层差异

有限脱空只改变局部层间接触；完整分离整层与局部斑块在测线覆盖和边缘响应上不同。

- 适用条件：明确模拟的空间范围。
- 限制：无限平层模型不能直接估算斑块面积。
- 类型：`engineering_interpretation`；概念：`finite_extent`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R23](https://doi.org/10.3390/app16199835)。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

#### debonding-K3-006 · 脱空端部响应

局部夹层的横向端部可产生边缘响应，与中部平层反射叠加，需分别分析边缘和内部形态。

- 适用条件：有限夹层；测线跨越端部。
- 限制：理论条件化应用，不承诺所有端部可见。
- 类型：`engineering_interpretation`；概念：`edge_diffraction`。
- 来源：[R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr), [R23](https://doi.org/10.3390/app16199835)。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

#### debonding-K3-007 · 反射范围与面积

雷达异常范围受照射与处理影响，层间脱空面积不能直接由单幅剖面的强反射宽度确定。

- 适用条件：有多线或三维资料。
- 限制：范围阈值需现场标定。
- 类型：`engineering_interpretation`；概念：`plan_size_bias`。
- 来源：[R09](https://doi.org/10.1155/2019/1365759), [R23](https://doi.org/10.3390/app16199835)。
  - R09：Abstract；道路与模型场试验比较；部分支撑。只支持其测试条件；经验公式不作跨场景标准。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

#### debonding-K3-008 · 平面范围与厚度区别

脱空平面范围与夹层厚度是不同属性；大面积层间分离也可能只有很薄的法向开口。

- 适用条件：分别描述平面与法向维度。
- 限制：不由平面面积推定厚度。
- 类型：`engineering_interpretation`；概念：`thickness_vs_plan`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R07](https://doi.org/10.1016/j.conbuildmat.2023.132834)。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。

#### debonding-K3-009 · 测线方向与截面

不同方向测线穿过局部脱空时可获得不同截面长度，二维剖面中的长度不唯一决定其平面形状。

- 适用条件：测线位置已配准。
- 限制：作为有限目标几何观测限制。
- 类型：`engineering_interpretation`；概念：`survey_direction`。
- 来源：[R09](https://doi.org/10.1155/2019/1365759), [R23](https://doi.org/10.3390/app16199835)。
  - R09：Abstract；道路与模型场试验比较；部分支撑。只支持其测试条件；经验公式不作跨场景标准。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

#### debonding-K3-010 · 水平切片与连通性

多测线和水平切片有助于评估层间异常的连通范围，但需在相同层位和深度校准后比较。

- 适用条件：三维采样与速度校准。
- 限制：同一时间切片可能切过不同物理深度。
- 类型：`engineering_interpretation`；概念：`three_dimensional_extent`。
- 来源：[R23](https://doi.org/10.3390/app16199835), [R19](https://doi.org/10.1038/s41467-023-39236-4)。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。
  - R19：Methods 中钻孔校准、波速与时深转换说明；背景支撑。深搅桩工程；仅支持验证与标定方法，不支持三类病害专属形态。

#### debonding-K3-011 · 荷载引起的几何变化

人工脱黏路面的加速加载研究显示，层间病害状态会随交通加载变化，几何解释宜使用同位置的重复观测。

- 适用条件：对应人工加载试验；重复配准。
- 限制：不推断现场病害必然持续扩大。
- 类型：`engineering_interpretation`；概念：`loading_geometry`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R07](https://doi.org/10.1016/j.conbuildmat.2023.132834)。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R07：§2–4；PDF页2–9，特别是§3.1、§3.2、Conclusion；部分支撑。WARR 观测；含水实验用饱和棉布，模拟用纯水；不能声明普通 B 扫同等能力。

#### debonding-K3-012 · 人工夹层类型

人工脱黏试验使用砂填充、土工材料或缺黏层等不同设置；这些几何与接触状态需分别记录。

- 适用条件：控制实验材料与设置明确。
- 限制：不把某种人工材料当作现场脱空普遍填充。
- 类型：`engineering_interpretation`；概念：`sand_geotextile_context`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。

#### debonding-K3-013 · 薄分离带与体积空洞

脱空与空洞可共享空气或水反射机制，本项目优先依据界面关联和三维几何区分类别。

- 适用条件：工程标注约定；有层位信息。
- 限制：边界样本需用统一裁决规则。
- 类型：`engineering_definition`；概念：`interlayer_vs_volume`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R23](https://doi.org/10.3390/app16199835)。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

#### debonding-K3-014 · 非理想接触界面

实际层间接触可不均匀，粗糙与局部分离会使响应偏离理想平层模型，边界解译应保留这种空间非均匀性。

- 适用条件：有限不均匀接触；模型与现场对应。
- 限制：平层模型不能给出真实界面全部细节。
- 类型：`engineering_interpretation`；概念：`rough_boundary`。
- 来源：[R31](https://doi.org/10.1190/1.1635047), [R32](https://doi.org/10.3390/s25185713)。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。
  - R32：Abstract；三相混凝土模型及钻孔验证说明；部分支撑。混凝土骨料情境；不把伪曲线推广为所有完整材料表现。

#### debonding-K3-015 · 层间状态核验

层间脱空或脱黏的标签需要与钻芯、开挖或可知人工设置对应；雷达异常本身不能同时充当标签和验证依据。

- 适用条件：核验位置与层位配准。
- 限制：局部核验不等于整片区域均已验证。
- 类型：`engineering_interpretation`；概念：`ground_truth_geometry`。
- 来源：[R06](https://doi.org/10.1016/j.jappgeo.2022.104722), [R23](https://doi.org/10.3390/app16199835)。
  - R06：Abstract；2600 MHz 加速加载试验；部分支撑。人工脱黏不等同纯空气薄层；80,000 次加载个案不能推广为普适趋势。
  - R23：Abstract；2026-10-04 出版记录；部分支撑。泡沫替代空气、容器替代富水目标；现场只有一例；不设通用尺寸阈值。

## 严重疏松

### K1 介质电性与界面反射

#### severe_looseness-K1-001 · 骨架与孔隙介质

疏松区仍包含固体骨架及孔隙中的空气或水，其电磁性质应按多相介质描述，不能默认整个区域为空气。

- 适用条件：适用于含材料骨架的疏松；区分土与沥青。
- 限制：严重程度须另行工程标定。
- 类型：`theory_application`；概念：`porous_skeleton`。
- 来源：[R10](https://doi.org/10.1016/j.jappgeo.2016.01.019), [R16](https://doi.org/10.3389/fmats.2026.1839264)。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。
  - R16：§2.1.2.2；§3.2；§3.3.2–3.3.3；Limitations；部分支撑。1600 MHz 小尺度拼装试件；未验证严重等级；排除§3.1中与生理信号有关的异常措辞和可疑滤波解释。

#### severe_looseness-K1-002 · 密度与孔隙率

在固体组分与颗粒密度相同的条件下，干密度降低对应孔隙率增加；疏松的电性变化需结合孔隙填充状态。

- 适用条件：材料组成可比；采用干密度概念。
- 限制：含水湿密度不能直接代替干密度。
- 类型：`theory_application`；概念：`density_porosity`。
- 来源：[R36](https://www.epa.gov/environmental-geophysics/porosity), [R10](https://doi.org/10.1016/j.jappgeo.2016.01.019)。
  - R36：Porosity 页面密度—孔隙率—饱和度式及变量定义；部分支撑。空气质量忽略、颗粒组成固定；湿密度与干密度需区分。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。

#### severe_looseness-K1-003 · 干燥孔隙增加

对组成可比的干燥材料，空气孔隙增加通常使有效介电常数降低；这一趋势不能直接推广至积水疏松区。

- 适用条件：干燥；相同固体成分；混合模型适用。
- 限制：沥青经验关系不能直接套用到所有土体。
- 类型：`theory_application`；概念：`dry_air_fraction`。
- 来源：[R11](https://doi.org/10.1016/j.ndteint.2014.08.008), [R12](https://doi.org/10.3390/app14020614)。
  - R11：Abstract；Case studies；Mathematical modeling of in-place air Voids；部分支撑。干燥或可比材料条件的密实度研究；不能直接推广至所有土体或水饱和区。
  - R12：§3 Materials and Methods；式8、14及校准试件说明；部分支撑。新铺沥青特定配方；其密度定义不替代土体干密度定义。

#### severe_looseness-K1-004 · 孔隙水替代空气

疏松孔隙由空气转为水填充会改变有效介电常数，孔隙率相同的区域可因含水状态不同而产生不同响应。

- 适用条件：材料组成与孔隙率可比。
- 限制：不以介电常数方向唯一判断疏松。
- 类型：`theory_application`；概念：`water_air_tradeoff`。
- 来源：[R03](https://doi.org/10.1029/wr016i003p00574), [R10](https://doi.org/10.1016/j.jappgeo.2016.01.019)。
  - R03：Abstract；四种矿质土的实验范围；部分支撑。TDR 土体实验；不能直接给道路病害反射幅值或跨材料严重程度。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。

#### severe_looseness-K1-005 · 质量与体积含水率

质量含水率与体积含水率不是同一量；密度变化时，比较疏松与密实材料须说明采用何种含水率定义。

- 适用条件：明确密度和水含量计量基础。
- 限制：相同质量含水率不代表相同体积含水率。
- 类型：`theory_application`；概念：`water_basis`。
- 来源：[R36](https://www.epa.gov/environmental-geophysics/porosity), [R10](https://doi.org/10.1016/j.jappgeo.2016.01.019)。
  - R36：Porosity 页面密度—孔隙率—饱和度式及变量定义；部分支撑。空气质量忽略、颗粒组成固定；湿密度与干密度需区分。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。

#### severe_looseness-K1-006 · 有效介电模型标定

混合模型可联系孔隙组分与有效介电性质，但模型参数和经验曲线需要按材料与实验条件标定。

- 适用条件：明确材料组分、频率及校准数据。
- 限制：不使用未经校准的通用介电—疏松等级曲线。
- 类型：`theory_application`；概念：`mixing_calibration`。
- 来源：[R12](https://doi.org/10.3390/app14020614), [R11](https://doi.org/10.1016/j.ndteint.2014.08.008)。
  - R12：§3 Materials and Methods；式8、14及校准试件说明；部分支撑。新铺沥青特定配方；其密度定义不替代土体干密度定义。
  - R11：Abstract；Case studies；Mathematical modeling of in-place air Voids；部分支撑。干燥或可比材料条件的密实度研究；不能直接推广至所有土体或水饱和区。

#### severe_looseness-K1-007 · 细颗粒与水状态

土体电性不仅取决于密度，也受水分状态和材料组成影响；压实相关的自由水与结合水变化会影响雷达响应。

- 适用条件：对应土体实验；区分水状态。
- 限制：不能把密度看作唯一电性控制量。
- 类型：`theory_application`；概念：`texture_boundwater`。
- 来源：[R10](https://doi.org/10.1016/j.jappgeo.2016.01.019), [R03](https://doi.org/10.1029/wr016i003p00574)。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。
  - R03：Abstract；四种矿质土的实验范围；部分支撑。TDR 土体实验；不能直接给道路病害反射幅值或跨材料严重程度。

#### severe_looseness-K1-008 · 电性实部与损耗

疏松介质的介电储能与损耗属于不同电磁属性；孔隙增加不必同时使反射增强或衰减减小。

- 适用条件：线性有效介质；明确电导率。
- 限制：不规定所有疏松区的统一衰减方向。
- 类型：`theory_application`；概念：`complex_properties`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R10](https://doi.org/10.1016/j.jappgeo.2016.01.019)。
  - R33：§9.2.4，教材页269–273；部分支撑。高损耗条件不可使用低损耗实参数简式。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。

#### severe_looseness-K1-009 · 材料组成混杂

集料与结合料组成变化也能改变道路材料的介电性质，低介电异常不一定由压实不足造成。

- 适用条件：沥青混合料；组成需可比。
- 限制：不把沥青结论泛化到所有路基材料。
- 类型：`theory_application`；概念：`composition_confound`。
- 来源：[R27](https://doi.org/10.1049/iet-rsn.2015.0133), [R12](https://doi.org/10.3390/app14020614)。
  - R27：Abstract；§2.1 材料性质说明；部分支撑。Ku 波段与普通道路 GPR 频带不同；不可迁移数值阈值。
  - R12：§3 Materials and Methods；式8、14及校准试件说明；部分支撑。新铺沥青特定配方；其密度定义不替代土体干密度定义。

#### severe_looseness-K1-010 · 电性空间起伏

非均匀疏松区的介电性质可随位置起伏；平均电性不能完整代表其内部非均匀程度。

- 适用条件：存在空间非均匀性。
- 限制：一般随机介质理论的条件化应用。
- 类型：`theory_application`；概念：`spatial_fluctuation`。
- 来源：[R31](https://doi.org/10.1190/1.1635047), [R16](https://doi.org/10.3389/fmats.2026.1839264)。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。
  - R16：§2.1.2.2；§3.2；§3.3.2–3.3.3；Limitations；部分支撑。1600 MHz 小尺度拼装试件；未验证严重等级；排除§3.1中与生理信号有关的异常措辞和可疑滤波解释。

#### severe_looseness-K1-011 · 疏松区边界反射

疏松区与周围密实材料的有效阻抗不同可形成边界反射；内部仍存在骨架，并不等同于空洞界面。

- 适用条件：有可辨有效电性反差。
- 限制：过渡边界可能不产生清晰单次反射。
- 类型：`theory_application`；概念：`boundary_contrast`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R10](https://doi.org/10.1016/j.jappgeo.2016.01.019)。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。

#### severe_looseness-K1-012 · 渐变边界限制

若疏松到密实的电性变化分布在过渡带中，尖锐单界面的反射模型不足以描述全部响应。

- 适用条件：渐变或非均匀介质。
- 限制：对疏松为理论条件化应用，非所有病害边界均渐变。
- 类型：`theory_application`；概念：`gradient_boundary`。
- 来源：[R31](https://doi.org/10.1190/1.1635047), [R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。
  - R33：§9.1.4，式9.1.19–20，教材页258–259；部分支撑。支持边界规律；不直接验证任何道路病害类别或接收幅度。

#### severe_looseness-K1-013 · 水分与疏松混淆

含水变化可产生与密实度变化相关的电性异常，单一介电或幅度指标难以唯一确定疏松状态。

- 适用条件：现场水分与密实度共同变化。
- 限制：需密度、含水率或工程核验。
- 类型：`theory_application`；概念：`material_confounds`。
- 来源：[R03](https://doi.org/10.1029/wr016i003p00574), [R10](https://doi.org/10.1016/j.jappgeo.2016.01.019)。
  - R03：Abstract；四种矿质土的实验范围；部分支撑。TDR 土体实验；不能直接给道路病害反射幅值或跨材料严重程度。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。

#### severe_looseness-K1-014 · 频带适用性

有效介电参数与测量频带有关，使用其他频率获得的材料标定关系解释疏松区时需核查适用性。

- 适用条件：明确测量频带与材料状态。
- 限制：不跨频带直接复用经验参数。
- 类型：`theory_application`；概念：`frequency_dependence`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R27](https://doi.org/10.1049/iet-rsn.2015.0133)。
  - R33：§9.2.4，教材页269–273；部分支撑。高损耗条件不可使用低损耗实参数简式。
  - R27：Abstract；§2.1 材料性质说明；部分支撑。Ku 波段与普通道路 GPR 频带不同；不可迁移数值阈值。

#### severe_looseness-K1-015 · 反射幅度与严重程度

疏松区幅度受边界反差、内部散射、传播和处理共同控制；没有跨材料通用的幅度阈值可以确认严重疏松。

- 适用条件：项目须定义严重程度的外部指标。
- 限制：不以强反射等同严重疏松。
- 类型：`theory_application`；概念：`contrast_vs_observed`。
- 来源：[R10](https://doi.org/10.1016/j.jappgeo.2016.01.019), [R16](https://doi.org/10.3389/fmats.2026.1839264)。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。
  - R16：§2.1.2.2；§3.2；§3.3.2–3.3.3；Limitations；部分支撑。1600 MHz 小尺度拼装试件；未验证严重等级；排除§3.1中与生理信号有关的异常措辞和可疑滤波解释。

### K2 电磁波传播与信号响应

#### severe_looseness-K2-001 · 有效介电与波速

在低损耗、非磁性有效介质近似下，疏松区的波速由有效介电常数控制；波速差异不能脱离含水与组成解释。

- 适用条件：有效介质尺度成立。
- 限制：速度异常不是密实度唯一指标。
- 类型：`theory_application`；概念：`velocity`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R10](https://doi.org/10.1016/j.jappgeo.2016.01.019)。
  - R33：§2.2–2.3.3；§9.2.2；部分支撑。对道路对象是条件化理论应用，不是密实度或病害等级实验。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。

#### severe_looseness-K2-002 · 走时变化

疏松区改变传播路径上的电性分布，可能改变穿过该区域的走时；走时变化需与厚度和速度联合分析。

- 适用条件：传播路径经过异常区。
- 限制：不能仅由走时差反演疏松等级。
- 类型：`theory_application`；概念：`travel_time_anomaly`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R10](https://doi.org/10.1016/j.jappgeo.2016.01.019)。
  - R33：§2.2–2.3.3；§9.2.2；部分支撑。对道路对象是条件化理论应用，不是密实度或病害等级实验。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。

#### severe_looseness-K2-003 · 内部散射

疏松区内部的电性非均匀性可散射雷达波，使响应包含内部散射而不只是外边界反射。

- 适用条件：内部电性起伏；尺度与频率相匹配。
- 限制：一般非均匀介质机制不等于直接证明严重程度。
- 类型：`theory_application`；概念：`volume_scattering`。
- 来源：[R31](https://doi.org/10.1190/1.1635047), [R16](https://doi.org/10.3389/fmats.2026.1839264)。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。
  - R16：§2.1.2.2；§3.2；§3.3.2–3.3.3；Limitations；部分支撑。1600 MHz 小尺度拼装试件；未验证严重等级；排除§3.1中与生理信号有关的异常措辞和可疑滤波解释。

#### severe_looseness-K2-004 · 非均匀尺度与波长

散射取决于非均匀尺度相对于波长的大小；孔隙或集料不能无条件作为逐个可分辨目标。

- 适用条件：明确相关尺度和波长。
- 限制：微小孔隙通常仅通过有效电性或散射统计体现。
- 类型：`theory_application`；概念：`scattering_scale`。
- 来源：[R31](https://doi.org/10.1190/1.1635047), [R18](https://doi.org/10.1002/2016wr019783)。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。
  - R18：Abstract；theoretical modelling 与 peat monolith analyses；背景支撑。泥炭气泡不是道路疏松；仅作散射尺度机理的背景证据。

#### severe_looseness-K2-005 · 干燥低密度情境

组成相近且低损耗的干燥疏松材料若有效介电常数降低，波速可增大；含水变化可改变这一趋势。

- 适用条件：条件同时满足；有效模型适用。
- 限制：不是所有疏松区的固定速度方向。
- 类型：`theory_application`；概念：`dry_velocity_context`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R12](https://doi.org/10.3390/app14020614)。
  - R33：§2.2–2.3.3；§9.2.2；部分支撑。对道路对象是条件化理论应用，不是密实度或病害等级实验。
  - R12：§3 Materials and Methods；式8、14及校准试件说明；部分支撑。新铺沥青特定配方；其密度定义不替代土体干密度定义。

#### severe_looseness-K2-006 · 导电损耗

疏松区中的导电孔隙水和损耗成分会吸收能量，使穿过该区的反射信号衰减。

- 适用条件：明确电导率及孔隙水。
- 限制：疏松结构本身不保证高电导率。
- 类型：`theory_application`；概念：`conductive_attenuation`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R10](https://doi.org/10.1016/j.jappgeo.2016.01.019)。
  - R33：§9.2.4，教材页269–273；部分支撑。高损耗条件不可使用低损耗实参数简式。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。

#### severe_looseness-K2-007 · 散射与吸收区别

散射将能量转移到其他方向，吸收则在介质中耗散能量；疏松区下方回波减弱不应只归因于一种机制。

- 适用条件：非均匀有损介质。
- 限制：阴影区不唯一证明疏松。
- 类型：`theory_application`；概念：`intrinsic_vs_scattering`。
- 来源：[R31](https://doi.org/10.1190/1.1635047), [R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。
  - R33：§9.2.4，教材页269–273；部分支撑。高损耗条件不可使用低损耗实参数简式。

#### severe_looseness-K2-008 · 杂乱反射与连续性

在特定松土现场中，疏松区表现为杂乱反射；响应连续性变化可作为线索，但不是所有疏松区的必要条件。

- 适用条件：参照堤防松土现场；道路迁移需校准。
- 限制：该来源不是道路严重疏松直接验证。
- 类型：`context_specific_observation`；概念：`clutter_coherence`。
- 来源：[R15](https://doi.org/10.1038/s41598-025-27047-0), [R16](https://doi.org/10.3389/fmats.2026.1839264)。
  - R15：Results: GPR imaging outcomes；Ground truth validation；Discussion；Fig.6；强支撑（仅限所列情境）。跨工程域部分支撑；未验证城市道路严重疏松，不能移用其误差为本项目精度。
  - R16：§2.1.2.2；§3.2；§3.3.2–3.3.3；Limitations；强支撑（仅限所列情境）。1600 MHz 小尺度拼装试件；未验证严重等级；排除§3.1中与生理信号有关的异常措辞和可疑滤波解释。

#### severe_looseness-K2-009 · 较弱条带响应

在人工道路疏松模型中，松散回填区域出现较弱条带及变形反射；这一情境说明疏松不必表现为强幅值异常。

- 适用条件：对应人工回填道路模型。
- 限制：局部试验观察不能固定为通用图谱。
- 类型：`context_specific_observation`；概念：`weak_banded_context`。
- 来源：[R16](https://doi.org/10.3389/fmats.2026.1839264), [R10](https://doi.org/10.1016/j.jappgeo.2016.01.019)。
  - R16：§2.1.2.2；§3.2；§3.3.2–3.3.3；Limitations；强支撑（仅限所列情境）。1600 MHz 小尺度拼装试件；未验证严重等级；排除§3.1中与生理信号有关的异常措辞和可疑滤波解释。
  - R10：Abstract；Highlights；500 MHz 室内外试验；强支撑（仅限所列情境）。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。

#### severe_looseness-K2-010 · 散射频谱依赖

非均匀介质散射可具有频率依赖，观测频谱反映波传播与尺度效应；不能用固定频移方向概括所有疏松区。

- 适用条件：一般非均匀介质；限定波长尺度。
- 限制：泥炭气泡研究仅作机制背景，非道路实证。
- 类型：`theory_application`；概念：`spectrum_scattering`。
- 来源：[R18](https://doi.org/10.1002/2016wr019783), [R31](https://doi.org/10.1190/1.1635047)。
  - R18：Abstract；theoretical modelling 与 peat monolith analyses；背景支撑。泥炭气泡不是道路疏松；仅作散射尺度机理的背景证据。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。

#### severe_looseness-K2-011 · 分布反射叠加

多个内部或边界反射可以在有限带宽下叠加，形成复杂波列；图上多条带不必代表多个独立疏松层。

- 适用条件：非均匀或多界面区域。
- 限制：理论条件化应用。
- 类型：`theory_application`；概念：`superposed_events`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R31](https://doi.org/10.1190/1.1635047)。
  - R33：§8.1.2–8.1.3，教材页232–236；部分支撑。TEM 例子仅支撑叠加原理；道路薄层具体结果由专门论文补充。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。

#### severe_looseness-K2-012 · 耦合变化混杂

地表粗糙及天线离地高度改变耦合和接收幅值，判断疏松响应前应控制这些采集因素。

- 适用条件：记录地表与天线高度。
- 限制：幅度变化可能来自采集条件。
- 类型：`theory_application`；概念：`coupling_confound`。
- 来源：[R31](https://doi.org/10.1190/1.1635047), [R30](https://doi.org/10.1177/03611981211004585)。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。
  - R30：Abstract；static and dynamic tests；部分支撑。支持采集混杂；不验证任何地下病害类别。

#### severe_looseness-K2-013 · 探测频率与尺度

疏松区的边界和内部细节能否被区分受频带、介质损耗和非均匀尺度共同影响。

- 适用条件：设备频带与材料条件已知。
- 限制：提高频率不能保证改善所有疏松检测。
- 类型：`theory_application`；概念：`frequency_tradeoff`。
- 来源：[R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr), [R31](https://doi.org/10.1190/1.1635047)。
  - R34：Basic Concept；Theory；Applications；部分支撑。官方通用原理说明，不提供三类病害专属阈值。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。

#### severe_looseness-K2-014 · 增益后的纹理

增益和归一化会改变疏松区反射纹理与幅度的相对显示，处理后图像不能直接用于比较原始能量。

- 适用条件：相同处理与对照窗口。
- 限制：需保存原始数据及流程。
- 类型：`theory_application`；概念：`processed_amplitude`。
- 来源：[R16](https://doi.org/10.3389/fmats.2026.1839264), [R30](https://doi.org/10.1177/03611981211004585)。
  - R16：§3.1中增益处理段落（滤波讨论之后）；Fig.9；部分支撑。仅使用增益段落，不使用该节不相干的生理信号滤波解释。
  - R30：Abstract；static and dynamic tests；部分支撑。支持采集混杂；不验证任何地下病害类别。

#### severe_looseness-K2-015 · 压实实验响应边界

已有土体压实实验观察到波速与体密度相关，并在较高贯入阻力条件下观测到较低幅度和较快衰减；这些为特定土体结果。

- 适用条件：Wang 等 500 MHz 土体室内外实验。
- 限制：不能反向推成所有严重疏松必然高幅值。
- 类型：`context_specific_observation`；概念：`compaction_empirical`。
- 来源：[R10](https://doi.org/10.1016/j.jappgeo.2016.01.019), [R15](https://doi.org/10.1038/s41598-025-27047-0)。
  - R10：Abstract；Highlights；500 MHz 室内外试验；强支撑（仅限所列情境）。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。
  - R15：Results: GPR imaging outcomes；Ground truth validation；Discussion；Fig.6；强支撑（仅限所列情境）。跨工程域部分支撑；未验证城市道路严重疏松，不能移用其误差为本项目精度。

### K3 病害形态与工程空间关系

#### severe_looseness-K3-001 · 疏松骨架与空洞区别

本项目的严重疏松类别保留松散材料骨架，空洞类别强调连续空隙；是否残留骨架需要工程验证。

- 适用条件：项目操作定义；材料状态可核验。
- 限制：严重阈值不是由雷达图像自行决定。
- 类型：`engineering_definition`；概念：`skeleton_vs_cavity`。
- 来源：[R16](https://doi.org/10.3389/fmats.2026.1839264), [R10](https://doi.org/10.1016/j.jappgeo.2016.01.019)。
  - R16：§2.1.2.2；§3.2；§3.3.2–3.3.3；Limitations；部分支撑。1600 MHz 小尺度拼装试件；未验证严重等级；排除§3.1中与生理信号有关的异常措辞和可疑滤波解释。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。

#### severe_looseness-K3-002 · 体积区与薄夹层区别

疏松可表现为结构层内部的材料状态异常，不宜无条件用一层纯空气薄片代替含骨架体积区。

- 适用条件：多相材料状态与几何分别表述。
- 限制：已有薄空气层疏松模型不作为体积疏松直接证据。
- 类型：`engineering_interpretation`；概念：`distributed_volume`。
- 来源：[R16](https://doi.org/10.3389/fmats.2026.1839264), [R31](https://doi.org/10.1190/1.1635047)。
  - R16：§2.1.2.2；§3.2；§3.3.2–3.3.3；Limitations；部分支撑。1600 MHz 小尺度拼装试件；未验证严重等级；排除§3.1中与生理信号有关的异常措辞和可疑滤波解释。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。

#### severe_looseness-K3-003 · 材料层位区分

面层、基层与路基的组成不同，疏松知识需要标注所在层位，不能将沥青空隙率经验式直接用于土质路基。

- 适用条件：层位明确；分开材料域。
- 限制：跨材料应用需重新校准。
- 类型：`engineering_interpretation`；概念：`layer_position`。
- 来源：[R12](https://doi.org/10.3390/app14020614), [R10](https://doi.org/10.1016/j.jappgeo.2016.01.019)。
  - R12：§3 Materials and Methods；式8、14及校准试件说明；部分支撑。新铺沥青特定配方；其密度定义不替代土体干密度定义。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。

#### severe_looseness-K3-004 · 过渡范围

疏松区的几何边界与电性过渡范围可能不同，阈值划出的雷达异常范围不自动等于材料状态边界。

- 适用条件：存在空间起伏或渐变。
- 限制：条件化观测限制；非必然渐变边界。
- 类型：`engineering_interpretation`；概念：`transition_extent`。
- 来源：[R31](https://doi.org/10.1190/1.1635047), [R15](https://doi.org/10.1038/s41598-025-27047-0)。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。
  - R15：Results: GPR imaging outcomes；Ground truth validation；Discussion；Fig.6；部分支撑。跨工程域部分支撑；未验证城市道路严重疏松，不能移用其误差为本项目精度。

#### severe_looseness-K3-005 · 空间非均匀性

疏松材料状态可在区域内部不均匀分布，用均一参数模型时需区分其平均性质和局部起伏。

- 适用条件：非均匀填土或混合材料。
- 限制：不把随机模型统计参数当作现场真值。
- 类型：`engineering_interpretation`；概念：`patchiness`。
- 来源：[R31](https://doi.org/10.1190/1.1635047), [R16](https://doi.org/10.3389/fmats.2026.1839264)。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。
  - R16：§2.1.2.2；§3.2；§3.3.2–3.3.3；Limitations；部分支撑。1600 MHz 小尺度拼装试件；未验证严重等级；排除§3.1中与生理信号有关的异常措辞和可疑滤波解释。

#### severe_looseness-K3-006 · 层内异常参照

解释疏松区时，应将异常与相邻完整层的反射结构比较，判断它位于层内还是界面附近。

- 适用条件：有完整区与层位参照。
- 限制：正常材料非均匀性也会产生异常。
- 类型：`engineering_interpretation`；概念：`layer_tracking`。
- 来源：[R16](https://doi.org/10.3389/fmats.2026.1839264), [R32](https://doi.org/10.3390/s25185713)。
  - R16：§2.1.2.2；§3.2；§3.3.2–3.3.3；Limitations；部分支撑。1600 MHz 小尺度拼装试件；未验证严重等级；排除§3.1中与生理信号有关的异常措辞和可疑滤波解释。
  - R32：Abstract；三相混凝土模型及钻孔验证说明；部分支撑。混凝土骨料情境；不把伪曲线推广为所有完整材料表现。

#### severe_looseness-K3-007 · 多测线空间范围

多测线可检查疏松异常的横向持续范围与连通性；单个剖面不能唯一决定其三维体积。

- 适用条件：测线配准；覆盖充分。
- 限制：异常连通性不等于力学弱区连续性。
- 类型：`engineering_interpretation`；概念：`three_dimensional_extent`。
- 来源：[R16](https://doi.org/10.3389/fmats.2026.1839264), [R15](https://doi.org/10.1038/s41598-025-27047-0)。
  - R16：§2.1.2.2；§3.2；§3.3.2–3.3.3；Limitations；部分支撑。1600 MHz 小尺度拼装试件；未验证严重等级；排除§3.1中与生理信号有关的异常措辞和可疑滤波解释。
  - R15：Results: GPR imaging outcomes；Ground truth validation；Discussion；Fig.6；部分支撑。跨工程域部分支撑；未验证城市道路严重疏松，不能移用其误差为本项目精度。

#### severe_looseness-K3-008 · 边界深度不确定性

疏松区电性变化会影响时间—深度转换，其顶部和底部位置应结合速度标定解释。

- 适用条件：局部速度变化可评估。
- 限制：不能固定用完整区速度进行所有异常测厚。
- 类型：`engineering_interpretation`；概念：`depth_geometry_uncertainty`。
- 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf), [R19](https://doi.org/10.1038/s41467-023-39236-4)。
  - R33：§2.2–2.3.3；§9.2.2；部分支撑。对道路对象是条件化理论应用，不是密实度或病害等级实验。
  - R19：Methods 中钻孔校准、波速与时深转换说明；背景支撑。深搅桩工程；仅支持验证与标定方法，不支持三类病害专属形态。

#### severe_looseness-K3-009 · 电磁与力学属性区别

雷达观测电磁结构，工程疏松状态还涉及密度或贯入等力学指标；两者对应关系须在同类材料中核验。

- 适用条件：材料域一致；有外部工程测量。
- 限制：电磁异常不直接等同低承载力或严重等级。
- 类型：`engineering_interpretation`；概念：`mechanical_proxy`。
- 来源：[R10](https://doi.org/10.1016/j.jappgeo.2016.01.019), [R15](https://doi.org/10.1038/s41598-025-27047-0)。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。
  - R15：Results: GPR imaging outcomes；Ground truth validation；Discussion；Fig.6；部分支撑。跨工程域部分支撑；未验证城市道路严重疏松，不能移用其误差为本项目精度。

#### severe_looseness-K3-010 · 严重程度操作边界

严重疏松的程度应由项目采用的密实度、贯入或其他工程验收依据明确，再检验其雷达表现。

- 适用条件：工程阈值须在标注规范中给出。
- 限制：当前资料未支持三类通用严重疏松雷达阈值。
- 类型：`engineering_definition`；概念：`severity_definition`。
- 来源：[R10](https://doi.org/10.1016/j.jappgeo.2016.01.019), [R29](https://doi.org/10.3390/s16122067)。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。
  - R29：§2.5–2.6；Figs.9–10；§3 Results；部分支撑。文内假定验收阈值不是道路严重疏松统一标准。

#### severe_looseness-K3-011 · 富水区域空间混淆

富水区可能产生电性异常并与疏松区重叠，空间上应区分水分变化范围和已核验的疏松范围。

- 适用条件：有水分或工程核验。
- 限制：富水和疏松不能互相自动推出。
- 类型：`engineering_interpretation`；概念：`moisture_spatial_context`。
- 来源：[R03](https://doi.org/10.1029/wr016i003p00574), [R15](https://doi.org/10.1038/s41598-025-27047-0)。
  - R03：Abstract；四种矿质土的实验范围；部分支撑。TDR 土体实验；不能直接给道路病害反射幅值或跨材料严重程度。
  - R15：Results: GPR imaging outcomes；Ground truth validation；Discussion；Fig.6；部分支撑。跨工程域部分支撑；未验证城市道路严重疏松，不能移用其误差为本项目精度。

#### severe_looseness-K3-012 · 沉降空间背景

沉降和层位变形可与疏松区域同时出现，但可观测沉降不是确认疏松材料或严重程度的充分条件。

- 适用条件：有层位或地表变形资料。
- 限制：铁路沉降案例只作相关工程背景。
- 类型：`engineering_interpretation`；概念：`settlement_context`。
- 来源：[R02](https://doi.org/10.1111/j.1365-2478.1989.tb02221.x), [R15](https://doi.org/10.1038/s41598-025-27047-0)。
  - R02：Abstract；borehole corroboration case histories；背景支撑。对道路病害仅提供一般空间解释背景。
  - R15：Results: GPR imaging outcomes；Ground truth validation；Discussion；Fig.6；部分支撑。跨工程域部分支撑；未验证城市道路严重疏松，不能移用其误差为本项目精度。

#### severe_looseness-K3-013 · 雷达与取样尺度

雷达观测体积与钻芯或取样体积不同，密实度空间变化时，两种测量未必逐点一致。

- 适用条件：配准并比较相应体积或深度范围。
- 限制：不以单一芯样代表整个异常区。
- 类型：`engineering_interpretation`；概念：`footprint_sampling`。
- 来源：[R35](https://rosap.ntl.bts.gov/view/dot/28605), [R27](https://doi.org/10.1049/iet-rsn.2015.0133)。
  - R35：官方交通研究档案 Abstract；密度梯度与探测体积说明；部分支撑。报告个案；其深度和相关系数不作为所有设备标准。
  - R27：Abstract；§2.1 材料性质说明；部分支撑。Ku 波段与普通道路 GPR 频带不同；不可迁移数值阈值。

#### severe_looseness-K3-014 · 正常非均匀背景

完整道路材料也有骨料与孔隙结构并能产生散射；识别疏松需比较超出正常材料背景的异常。

- 适用条件：同材料完整区参照。
- 限制：杂乱图像不是严重疏松充分证据。
- 类型：`engineering_interpretation`；概念：`intact_heterogeneity`。
- 来源：[R32](https://doi.org/10.3390/s25185713), [R31](https://doi.org/10.1190/1.1635047)。
  - R32：Abstract；三相混凝土模型及钻孔验证说明；部分支撑。混凝土骨料情境；不把伪曲线推广为所有完整材料表现。
  - R31：Abstract；FDTD 随机介质结果；部分支撑。一般天线与随机土体模型，对严重疏松是部分机理支撑。

#### severe_looseness-K3-015 · 疏松范围与外部核验

钻孔、取样密度或贯入试验可为疏松标签和空间范围提供独立依据；不同工程域的结果需分别记录。

- 适用条件：核验位置与雷达配准。
- 限制：堤防松土案例不能直接验证道路严重疏松。
- 类型：`engineering_interpretation`；概念：`ground_truth_geometry`。
- 来源：[R15](https://doi.org/10.1038/s41598-025-27047-0), [R10](https://doi.org/10.1016/j.jappgeo.2016.01.019)。
  - R15：Results: GPR imaging outcomes；Ground truth validation；Discussion；Fig.6；部分支撑。跨工程域部分支撑；未验证城市道路严重疏松，不能移用其误差为本项目精度。
  - R10：Abstract；Highlights；500 MHz 室内外试验；部分支撑。土体压实研究，未建立道路严重疏松类别及通用雷达阈值。

## 标准理论公式

- F01：`R_E = (eta_2-eta_1)/(eta_2+eta_1) = (sqrt(epsilon_r1)-sqrt(epsilon_r2))/(sqrt(epsilon_r1)+sqrt(epsilon_r2))`。第二式限同磁导率、低损耗、法向平面界面；R_E 为反射电场/入射电场。 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)，§9.1.4，式9.1.19。
- F02：`v ≈ c/sqrt(epsilon_r); lambda = v/f`。低损耗、非磁性、局部均匀；不是强导电介质通式。 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)，§2.2–2.3.3；§9.2.2。
- F03：`t_TWT ≈ 2 * sum(h_i/v_i)`。近垂直、近零偏移、分层速度已知且时间零点已校正。 来源：[R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr)，Theory。
- F04：`epsilon_eff = epsilon - j*sigma/omega`。采用 exp(j omega t) 约定；若 epsilon 已包含同一导电损耗，不得重复加入 sigma 项。 来源：[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)，§9.2.4，式9.2.53。
- F05：`n = 1-rho_d/rho_s`。土体干密度定义，rho_s 为颗粒密度；材料组成固定，忽略空气质量；由已列密度体积关系的干燥情境表示。 来源：[R36](https://www.epa.gov/environmental-geophysics/porosity)，Porosity 密度—孔隙率式，干燥S=0情境。
- F06：`AV = 1-G_mb/G_mm; RD = G_mb/G_mm`。沥青混合料空隙率与相对密度定义，不能把 G_mm 直接当作土粒密度。 来源：[R12](https://doi.org/10.3390/app14020614)，§3，式8、14。

## 参考来源

- **[R01](https://doi.org/10.1016/b978-0-444-53348-7.00001-6)** Annan, A.P. (2009). Electromagnetic Principles of Ground Penetrating Radar. *Ground Penetrating Radar Theory and Applications*, 1-40. 内容读取：metadata_only。已核实书章身份和 DOI，未逐页读取原章；不作为135条的唯一实质证据。
- **[R02](https://doi.org/10.1111/j.1365-2478.1989.tb02221.x)** DAVIS, J. L.; ANNAN, A. P. (1989). GROUND‐PENETRATING RADAR FOR HIGH‐RESOLUTION MAPPING OF SOIL AND ROCK STRATIGRAPHY. *Geophysical Prospecting*, 37, 531-551. 内容读取：crossref_deposited_abstract。
- **[R03](https://doi.org/10.1029/wr016i003p00574)** Topp, G. C.; Davis, J. L.; Annan, A. P. (1980). Electromagnetic determination of soil water content: Measurements in coaxial transmission lines. *Water Resources Research*, 16, 574-582. 内容读取：abstract。
- **[R06](https://doi.org/10.1016/j.jappgeo.2022.104722)** Hui, Venus Ho Yan; Dérobert, Xavier; Lai, Wallace Wai Lok (2022). A study of artificial debond pavement under controlled traffic by Ground Penetrating Radar. *Journal of Applied Geophysics*, 204, 104722. 内容读取：publisher_and_author_repository_abstract。作者机构网页的简略引用仅显示部分作者；按 Crossref 与出版社记录保留 Hui、Dérobert、Lai 三位作者。
- **[R07](https://doi.org/10.1016/j.conbuildmat.2023.132834)** He, Wenchao; Lai, Wallace Wai-Lok; Sui, Xin; Giannopoulos, Antonios (2023). Delamination characterization in thin asphalt pavement structure using dispersive GPR data. *Construction and Building Materials*, 402, 132834. 内容读取：full_text。Crossref 的第二作者姓名字段顺序异常；按作者机构论文全文首页规范化为 Wallace Wai-Lok Lai。
- **[R08](https://doi.org/10.1016/j.ndteint.2024.103103)** Kang, Seonghun; Lee, Jong-Sub; Kim, Namsun; Lee, Dongsoo; Park, Junghee (2024). Detection of air- and water-filled cavities beneath concrete plate using electromagnetic and acoustic waves. *NDT & E International*, 144, 103103. 内容读取：publisher_abstract。
- **[R09](https://doi.org/10.1155/2019/1365759)** Park, Jeong-Jun; Chung, Yoonseok; Hong, Gigwon (2019). A Method for Cavity Scale Estimation Based on Ground‐Penetrating Radar (GPR) Explorations: An Experimental Study. *Advances in Civil Engineering*, 2019. 内容读取：abstract_and_publisher_sections。
- **[R10](https://doi.org/10.1016/j.jappgeo.2016.01.019)** Wang, Ping; Hu, Zhenqi; Zhao, Yanling; Li, Xinju (2016). Experimental study of soil compaction effects on GPR signals. *Journal of Applied Geophysics*, 126, 128-137. 内容读取：publisher_abstract。
- **[R11](https://doi.org/10.1016/j.ndteint.2014.08.008)** Chen, Dar-Hao; Hong, Feng; Zhou, Wujun; Ying, Peng (2014). Estimating the hotmix asphalt air voids from ground penetrating radar. *NDT & E International*, 68, 120-127. 内容读取：publisher_abstract_and_sections。
- **[R12](https://doi.org/10.3390/app14020614)** Primusz, Péter; Abdelsamei, Enas; Ali, Ahmed M.; Sipos, György; Fi, István; Herceg, András; Tóth, Csaba (2024). Assessment of In Situ Compactness and Air Void Content of New Asphalt Layers Using Ground-Penetrating Radar Measurements. *Applied Sciences*, 14, 614. 内容读取：publisher_full_text_sections。
- **[R13](https://doi.org/10.1038/s41598-023-33278-w)** Hou, Zhezhe; Zhao, Weigang; Yang, Yong (2023). Identification of railway subgrade defects based on ground penetrating radar. *Scientific Reports*, 13. 内容读取：full_text。
- **[R15](https://doi.org/10.1038/s41598-025-27047-0)** Li, Changzheng; Zhao, Xiang (2025). Topographic correction for ground penetrating radar for enhanced detection of dike subsurface anomalies. *Scientific Reports*, 15. 内容读取：full_text。
- **[R16](https://doi.org/10.3389/fmats.2026.1839264)** Jiao, Xiaodong; Liu, Shengjie; Xiong, Jianping; Li, Xiaochao; Li, Hui; Liu, Jianan (2026). Characterization of concealed pavement distresses based on ground-penetrating radar: an integrated experimental and numerical study. *Frontiers in Materials*, 13. 内容读取：full_text。
- **[R17](https://doi.org/10.1016/j.ndteint.2017.04.002)** Wai-Lok Lai, Wallace; Dérobert, Xavier; Annan, Peter (2018). A review of Ground Penetrating Radar application in civil engineering: A 30-year journey from Locating and Testing to Imaging and Diagnosis. *NDT & E International*, 96, 58-78. 内容读取：author_repository_full_text。DOI 含2017，正式卷期为2018年96卷58–78页；采用正式卷期年份2018。
- **[R18](https://doi.org/10.1002/2016wr019783)** Terry, Neil; Slater, Lee (2017). Gas bubble size estimation in peat soils from EM wave scattering observed with ground penetrating radar. *Water Resources Research*, 53, 2755-2769. 内容读取：crossref_deposited_abstract。
- **[R19](https://doi.org/10.1038/s41467-023-39236-4)** Shen, Hongyan; Li, Xinsheng; Duan, Ruifeng; Zhao, Yong; Zhao, Jing; Che, Han; Liu, Guoxin; Xue, Zhijia; Yan, Changgen; Liu, Jiwei; Jiang, Chao; Li, Boke; Chang, Hong; Gao, Jianqiang; Yan, Yueying (2023). Quality evaluation of ground improvement by deep cement mixing piles via ground-penetrating radar. *Nature Communications*, 14. 内容读取：full_text。
- **[R20](https://doi.org/10.1038/s41586-025-10072-4)** Asai, Akari; He, Jacqueline; Shao, Rulin; Shi, Weijia; Singh, Amanpreet; Chang, Joseph Chee; Lo, Kyle; Soldaini, Luca; Feldman, Sergey; D’Arcy, Mike; Wadden, David; Latzke, Matt; Sparks, Jenna; Hwang, Jena D.; Kishore, Varsha; Tian, Minyang; Ji, Pan; Liu, Shengyan; Tong, Hao; Wu, Bohao; Xiong, Yanyu; Zettlemoyer, Luke; Neubig, Graham; Weld, Daniel S.; Downey, Doug; Yih, Wen-tau; Koh, Pang Wei; Hajishirzi, Hannaneh (2026). Synthesizing scientific literature with retrieval-augmented language models. *Nature*, 650, 857-863. 内容读取：full_text。2026-02-04 正式发表；出版社页面有 updated 提示，未进一步判定更新内容；仅作知识溯源方法背景。
- **[R21](https://doi.org/10.2113/gseegeosci.20.2.109)** RODRIGUEZ, V.; GUTIERREZ, F.; GREEN, A. G.; CARBONEL, D.; HORSTMEYER, H.; SCHMELZBACH, C. (2014). Characterizing Sagging and Collapse Sinkholes in a Mantled Karst by Means of Ground Penetrating Radar (GPR). *Environmental & Engineering Geoscience*, 20, 109-132. 内容读取：publisher_abstract_via_official_EPA。
- **[R23](https://doi.org/10.3390/app16199835)** He, Jun; Yu, Jiangmiao; Tang, Jiaming; Chen, Bo; Zang, Bo; Fan, Zhenting; Xiong, Xuetang (2026). GPR-Based Characterization of Pavement Void: A Comprehensive Analysis via Numerical Simulation, Physical Modeling, and Field Verification. *Applied Sciences*, 16, 9835. 内容读取：crossref_abstract_and_publisher_search。
- **[R24](https://doi.org/10.1190/geo2012-0266.1)** Van Dam, Remke L.; Hendrickx, Jan M. H.; Cassidy, Nigel J.; North, Ryan E.; Dogan, Mine; Borchers, Brian (2013). Effects of magnetite on high-frequency ground-penetrating radar. *Geophysics*, 78, H1-H11. 内容读取：crossref_deposited_abstract。
- **[R27](https://doi.org/10.1049/iet-rsn.2015.0133)** Olkkonen, Martta‐Kaisa (2016). Ku band ground penetrating radar for asphalt layer measurement. *IET Radar, Sonar & Navigation*, 10, 76-81. 内容读取：crossref_abstract_and_publisher_sections。
- **[R28](https://doi.org/10.1016/j.conbuildmat.2017.06.132)** Liu, Hai; Deng, Zhihao; Han, Feng; Xia, Yuanyou; Liu, Qing Huo; Sato, Motoyuki (2017). Time-frequency analysis of air-coupled GPR data for identification of delamination between pavement layers. *Construction and Building Materials*, 154, 1207-1215. 内容读取：publisher_abstract_and_sections。
- **[R29](https://doi.org/10.3390/s16122067)** Dong, Zehua; Ye, Shengbo; Gao, Yunze; Fang, Guangyou; Zhang, Xiaojuan; Xue, Zhongjun; Zhang, Tao (2016). Rapid Detection Methods for Asphalt Pavement Thicknesses and Defects by a Vehicle-Mounted Ground Penetrating Radar (GPR) System. *Sensors*, 16, 2067. 内容读取：publisher_full_text_sections。
- **[R30](https://doi.org/10.1177/03611981211004585)** Cao, Qingqing; Al-Qadi, Imad L. (2021). Signal Stability and the Height-Correction Method for Ground-Penetrating Radar In Situ Asphalt Concrete Density Prediction. *Transportation Research Record: Journal of the Transportation Research Board*, 2675, 835-847. 内容读取：crossref_deposited_abstract。
- **[R31](https://doi.org/10.1190/1.1635047)** Lampe, Bernhard; Holliger, Klaus (2003). Effects of fractal fluctuations in topographic relief, permittivity and conductivity on ground-penetrating radar antenna radiation. *Geophysics*, 68, 1934-1944. 内容读取：crossref_deposited_abstract。
- **[R32](https://doi.org/10.3390/s25185713)** Wei, Shuaishuai; Zhang, Huan; Fu, Jiancun; Han, Wenyang (2025). Study on the Ground-Penetrating Radar Response Characteristics of Pavement Voids Based on a Three-Phase Concrete Model. *Sensors*, 25, 5713. 内容读取：crossref_deposited_abstract。
- **[R33](https://ocw.mit.edu/courses/6-013-electromagnetics-and-applications-spring-2009/d3be4ea78b036a6362230fb41780cf54_MIT6_013S09_notes.pdf)** Staelin, David H. (2011). Electromagnetics and Applications. *MIT OpenCourseWare course notes*. 内容读取：full_text。课程页面名含2009；下载教材首页版权为2011，因此按2011记录。
- **[R34](https://www.epa.gov/environmental-geophysics/ground-penetrating-radar-gpr)** United States Environmental Protection Agency (n.d.). Ground Penetrating Radar (GPR). *Environmental Geophysics*. 内容读取：official_document_full_text。页面最后更新2026-03-30；不把更新时间伪填为首次发表年。
- **[R35](https://rosap.ntl.bts.gov/view/dot/28605)** Maser, Ken; Carmichael, Adam (2015). Ground penetrating radar evaluation of new pavement density.. *Washington State Department of Transportation / National Transportation Library*. 内容读取：official_report_abstract。发布日期2015-02-01；未读取完整报告，仅使用官方摘要中的体积差异说明。
- **[R36](https://www.epa.gov/environmental-geophysics/porosity)** United States Environmental Protection Agency (n.d.). Porosity. *Environmental Geophysics*. 内容读取：official_document_full_text。页面最后更新2026-01-06；不把更新时间作为首次发表年。
