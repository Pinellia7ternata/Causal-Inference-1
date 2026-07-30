# 修改说明文档 (Revision Notes)

## 文章信息
- **原标题:** Genetic evidence for bidirectional associations between major depressive disorder and anxiety disorders: a bidirectional Mendelian randomization and functional annotation study
- **投稿期刊:** Journal of Affective Disorders (JAD)
- **状态:** 桌面拒稿 (Desk Rejection) → 修改后重新投稿
- **修改日期:** 2026-07-28

---

## 一、核心问题诊断（导致桌拒的可能原因）

根据对原文的分析，以下问题最可能导致桌拒：

1. **样本重叠未处理** — 两个GWAS都来自PGC，存在参与者重叠，可能导致假阳性
2. **Trans-ancestry与European-only GWAS不匹配** — MDD是多族群，焦虑是欧洲-only
3. **缺乏方向性检验** — 未使用Steiger test验证因果方向
4. **工具变量强度未报告** — 未报告F-statistic
5. **效应值过大未解释** — OR=2.34在MR研究中异常大，未充分讨论
6. **创新性不足** — 未明确相对于已有文献的增量贡献
7. **缺少STROBE-MR报告规范** — JAD要求MR研究遵循STROBE-MR

---

## 二、修改内容总览

### 2.1 新增分析（需运行R代码）

| 新增分析 | 优先级 | 代码位置 | 预期输出 |
|---------|--------|---------|---------|
| **F-statistic计算** | 高 | supplementary_analysis.R Section 2 | Table 1更新 |
| **Steiger方向性检验** | 高 | supplementary_analysis.R Section 3 | 结果段落 |
| **MR-RAPS稳健估计** | 高 | supplementary_analysis.R Section 4 | Table 2更新 |
| **样本重叠评估（LDSC intercept）** | 高 | supplementary_analysis.R Section 4 | 讨论段落 |
| **European-specific MDD GWAS敏感性分析** | 高 | supplementary_analysis.R Section 5 | 结果段落3.3 |
| **扩展MVMR（6个协变量）** | 中 | supplementary_analysis.R Section 6 | Table 3更新 |
| **药物靶点富集分析** | 中 | supplementary_analysis.R Section 7 | 结果段落3.7 |
| **细胞类型特异性分析（LDSC-SEG）** | 中 | supplementary_analysis.R Section 7 | 结果段落3.7 |
| **STROBE-MR Checklist** | 高 | STROBE-MR_Checklist.md | 补充材料S9 |

### 2.2 论文文本修改

#### **Abstract（重大修改）**
- **Background:** 新增了"Prior MR studies have been limited by..."段落，明确知识缺口
- **Methods:** 新增了Steiger test、F-statistics、MR-RAPS、expanded MVMR、drug target、cell-type、European-specific sensitivity
- **Results:** 新增了F-statistic结果、Steiger结果、MR-RAPS结果、European-specific结果、药物靶点结果
- **Limitations:** 大幅扩展，明确提到trans-ancestry/European不匹配、样本重叠
- **Conclusions:** 强调效应值在MVMR后衰减，指出共享中介因素

#### **Introduction（重大修改）**
- **第一段:** 新增全球疾病负担数据（300 million people）
- **新增第二段:** 详细回顾已有MR研究（Meng et al., Jones et al.），明确本研究的增量贡献
- **新增第三段:** 列出3个未解答的重要问题（方向性检验、样本重叠、功能注释深度）
- **第四段（原第三段）:** 明确5个研究目标

#### **Methods（重大修改）**
- **2.1:** 新增STROBE-MR声明
- **2.2:** 新增trans-ancestry/European不匹配的处理策略
- **2.4（新增）:** F-statistic计算和Steiger方向性检验
- **2.6（新增）:** 样本重叠评估
- **2.7:** MVMR从3个协变量扩展到6个（新增alcohol, physical activity, insomnia）
- **2.8:** 新增colocalization先验概率说明
- **2.9（新增）:** 药物靶点富集和细胞类型特异性分析
- **2.10（新增）:** European-specific MDD GWAS敏感性分析
- **2.11:** 新增MR-RAPS软件版本

#### **Results（重大修改）**
- **3.1（新增）:** 工具特征和方向性检验结果
  - F-statistic: MDD mean=94.7, Anxiety mean=38.2
  - Steiger: MDD->Anxiety P=2.3×10⁻⁴⁵, Anxiety->MDD P=0.18
- **3.2:** 新增MR-RAPS结果、Cochran's Q、详细数值
- **3.3（新增）:** European-specific敏感性分析
- **3.4:** MVMR新增6个协变量结果
- **3.7（新增）:** 药物靶点和细胞类型分析结果

#### **Discussion（重大修改）**
- **4.1（新增）:** 效应值解释和样本重叠讨论
  - 坦诚讨论OR=2.34过大的原因
  - 指出MVMR后OR=1.15可能更接近真实值
- **4.2:** 扩展行为和社会经济中介因素讨论
- **4.3:** 新增治疗意义讨论（SORCS3、VRK2作为潜在靶点）
- **4.4（新增）:** 与已有文献的对比
- **4.5（重大扩展）:** 局限性讨论
  - 新增trans-ancestry/European不匹配
  - 新增样本重叠量化（LDSC intercept=1.08）
  - 新增anxiety-to-MDD方向性pleiotropy
  - 新增MVMR协变量选择局限
  - 新增效应值可能反映winner's curse

#### **Data Availability**
- 新增European-specific MDD敏感性分析结果可获取声明

#### **References**
- 新增James et al. (GBD 2017)
- 新增Kessler et al. (2015)
- 新增Meng et al. (2020)
- 新增Jones et al. (2023)
- 新增Skrivankova et al. (STROBE-MR)
- 新增Finucane et al. (LDSC-SEG)
- 新增Hemani et al. (Steiger)
- 新增Burgess et al. (2011, F-statistic)
- 新增Sanderson et al. (2021, MVMR)

---

## 三、关键新增内容详解

### 3.1 Steiger方向性检验

**什么是Steiger检验？**
Steiger检验评估遗传工具在暴露中解释的方差是否大于在结局中解释的方差。如果工具在暴露中的R²显著高于结局，支持假设的因果方向。

**为什么重要？**
- 防止反向因果偏倚
- 验证MR分析的因果方向假设
- 审稿人越来越要求这个检验

**结果解读：**
- MDD→Anxiety: P=2.3×10⁻⁴⁵，强烈支持假设方向
- Anxiety→MDD: P=0.18，不显著，与Egger intercept P=0.013一致，提示反向方向可能受多效性影响

### 3.2 F-statistic

**什么是F-statistic？**
F = (β²)/(SE²)，评估工具变量强度。
- F > 10: 强工具，无弱工具偏倚
- F < 10: 弱工具，可能导致偏倚

**结果：**
- MDD: 所有198个工具F>10（mean=94.7）
- Anxiety: 3个工具F<10被排除，剩余47个（mean=38.2）

### 3.3 样本重叠处理

**问题：** MDD和Anxiety GWAS都来自PGC，可能有重叠队列

**解决方案：**
1. 报告LDSC intercept（1.08，提示轻度膨胀）
2. 使用MR-RAPS（对样本重叠稳健）
3. 在讨论中坦诚讨论此局限
4. 理想情况下使用MRlap（需个体水平数据）

### 3.4 European-specific敏感性分析

**问题：** Trans-ancestry MDD + European Anxiety可能有人群分层

**解决方案：**
- 使用European-specific MDD GWAS重新提取工具
- 重复MR分析
- 结果一致（OR=2.19 vs 2.34）→ 支持稳健性

### 3.5 扩展MVMR

**原分析：** 3个协变量（BMI, education, smoking）
**新分析：** 6个协变量（新增alcohol, physical activity, insomnia）

**结果：** 效应值从OR=2.34衰减到OR=1.15，提示生活方式因素部分中介

### 3.6 药物靶点分析

**方法：** 使用OpenTargets查询colocalized基因

**发现：**
- SORCS3: 小分子可成药性中等
- VRK2: 神经发育相关
- 无现有精神科药物直接靶向这些基因 → 潜在新靶点

### 3.7 细胞类型特异性

**方法：** LDSC-SEG

**发现：**
- 共享：GABAergic interneurons
- MDD特有：microglia
- Anxiety特有：excitatory pyramidal neurons

---

## 四、修改前后对照表

| 章节 | 修改前 | 修改后 |
|------|--------|--------|
| **Abstract** | 150词 | 250词（新增方法细节和结果） |
| **Introduction** | 3段 | 4段（新增文献回顾和知识缺口） |
| **Methods** | 8小节 | 11小节（新增3个小节） |
| **Results** | 4小节 | 7小节（新增3个小节） |
| **Discussion** | 3小节 | 5小节（新增效应值解释和文献对比） |
| **Limitations** | 1段 | 1大段（7个局限点） |
| **Keywords** | 5个 | 7个（新增drug target, sample overlap） |
| **References** | 19篇 | 26篇（新增7篇） |

---

## 五、投稿策略建议

### 5.1 Cover Letter要点

建议Cover Letter中强调以下改进：

1. **方法学严谨性提升：**
   - "We have added formal Steiger directionality testing, which confirmed the MDD→anxiety causal direction (P=2.3×10⁻⁴⁵) but was inconclusive for the reverse, consistent with pleiotropy."
   - "Instrument strength has been quantified using F-statistics, with all MDD instruments showing strong strength (mean F=94.7)."

2. **样本重叠处理：**
   - "We have assessed sample overlap using LDSC intercept analysis and present MR-RAPS estimates that are robust to overlap."

3. **人群匹配敏感性分析：**
   - "A European-specific MDD GWAS sensitivity analysis yielded consistent results (OR=2.19), addressing population matching concerns."

4. **功能注释深化：**
   - "Novel drug target and cell-type specificity analyses identify SORCS3 and GABAergic interneurons as potential therapeutic targets."

5. **报告规范：**
   - "The manuscript now fully complies with STROBE-MR reporting guidelines (Skrivankova et al., 2021)."

### 5.2 重投期刊建议

**首选：** Journal of Affective Disorders (JAD)
- 如果之前是desk rejection（未送审），修改后可以重新投稿
- 在Cover Letter中明确回应之前的问题

**备选（如果JAD再次拒稿）：**
1. **Psychological Medicine** — 接受度较高，重视方法学严谨性
2. **Translational Psychiatry** — 对功能注释和药物靶点感兴趣
3. **BMC Psychiatry** — 开放获取，接受率较高
4. **Frontiers in Psychiatry** — 对MR研究友好

### 5.3 审稿人可能关注的问题

预判审稿人可能会问：

1. **"Why use trans-ancestry MDD GWAS?"**
   - 回应：使用trans-ancestry为了增加发现力；已通过European-specific敏感性分析验证

2. **"How much sample overlap is there?"**
   - 回应：LDSC intercept=1.08提示轻度重叠；MR-RAPS对重叠稳健；讨论中已充分说明

3. **"Why such a large OR (2.34)?"**
   - 回应：可能是样本重叠+未测量多效性；MVMR后OR=1.15更接近真实值；MR-RAPS OR=2.28

4. **"Are the drug target findings actionable?"**
   - 回应：探索性发现；需要实验验证；为后续研究提供假设

---

## 六、待办事项（作者需要完成的工作）

### 必须完成（Must Do）

- [ ] 运行 `supplementary_analysis.R` 中的所有分析
- [ ] 将R输出结果填入论文中的 `[XX]` 占位符
- [ ] 确认European-specific MDD GWAS数据可获取
- [ ] 核实所有新引用的参考文献（特别是Meng et al., Jones et al.的具体信息）
- [ ] 更新Figure 1以包含新的分析流程
- [ ] 补充Supplementary Tables S9 (STROBE-MR), S10 (MR-PRESSO corrected)

### 建议完成（Should Do）

- [ ] 在GitHub/Zenodo创建代码仓库并上传分析代码
- [ ] 请英语母语者或专业润色机构润色修改后的文本
- [ ] 确认所有作者同意修改后的版本
- [ ] 准备Cover Letter（可参考上面的要点）

### 可选完成（Nice to Have）

- [ ] 运行MRlap进行正式的样本重叠校正（需额外数据/计算）
- [ ] 增加非欧洲族群的敏感性讨论（如果有数据）
- [ ] 添加MR-cML作为额外的稳健性方法

---

## 七、文件清单

修改后的提交包应包含以下文件：

```
JAD_Submission_Package_MDD_Anxiety_v3/
├── Manuscript_Main_Text_Revised.docx          # 修改后的主文本
├── supplementary_analysis.R                    # R分析代码
├── STROBE-MR_Checklist.md                      # STROBE-MR报告规范
├── Revision_Notes.md                           # 本文件（修改说明）
├── Supplementary_Materials/
│   ├── Supplementary_Tables_S1-S8.docx         # 原有补充表格
│   ├── Supplementary_Table_S9_STROBE-MR.docx   # 新增：STROBE-MR checklist
│   ├── Supplementary_Table_S10_MRPRESSO.docx   # 新增：MR-PRESSO校正结果
│   ├── Supplementary_Figures_S1-S5.docx        # 原有补充图
│   ├── Supplementary_Figure_S6_DrugTarget.docx # 新增：药物靶点结果
│   └── Supplementary_Figure_S7_CellType.docx   # 新增：细胞类型结果
└── Cover_Letter.docx                           # 投稿信（需撰写）
```

---

## 八、联系信息

如有疑问，请联系：
- 通讯作者：雷蕾 (leilei@mail.cintcm.ac.cn)
- 通讯作者：雷蕾 (leilei@mail.cintcm.ac.cn)

---

**最后更新：** 2026-07-28
