# SPSS考前操作总复习

适用场景：医学统计学 SPSS 操作题、机考大题、输出结果判读题。  
核心目标：看到题目后，能快速判断方法、找到菜单、看对输出表、写出规范结论。

## 1. 考场总流程：先判断，再点菜单

拿到题目先写下 4 个关键词：

1. 因变量是什么：要被描述、比较或预测的变量。
2. 因变量类型：计量资料、计数资料、等级资料、二分类结局。
3. 分组或自变量是什么：有无分组、几组、是否配对。
4. 研究目的是什么：描述、比较、关联、预测、影响因素分析。

一句话口诀：

> 计量看均数，计数看率；两组看独立或配对，多组看方差；分类看卡方，等级偏态走非参；计量结局线性回归，二分类结局 Logistic。

## 2. 数据录入与变量设置

### 2.1 数据视图

- 一行代表一个研究对象。
- 一列代表一个变量。
- 分组变量尽量用数字编码，例如 `1=治疗组，2=对照组`。
- 不要把“治疗组”“对照组”直接混在同一列计量结果里，应该用一个分组变量加一个结果变量。

### 2.2 变量视图

| 项目 | 怎么填 | 考试提醒 |
|---|---|---|
| Name | 英文或拼音变量名，如 `group`、`bp` | 不要有空格 |
| Type | 一般选 Numeric | 分类变量也常用数字编码 |
| Label | 中文解释，如“治疗后血压” | 方便看输出 |
| Values | 编码说明，如 `1=男，2=女` | 分组变量必须会设置 |
| Measure | Scale / Nominal / Ordinal | 计量=Scale，分类=Nominal，等级=Ordinal |

### 2.3 汇总表数据要先加权

如果题目给的是已经汇总好的频数表，例如：

| group | outcome | count |
|---|---|---:|
| 1 | 1 | 35 |
| 1 | 0 | 15 |
| 2 | 1 | 22 |
| 2 | 0 | 28 |

操作前先做：

`Data > Weight Cases > Weight cases by count`

做完分析后记得取消：

`Data > Weight Cases > Do not weight cases`

## 3. 方法选择速查表

| 题目关键词 | 资料/设计 | 统计方法 | SPSS菜单 | 主要看哪里 |
|---|---|---|---|---|
| 描述一个计量变量 | 计量资料 | 描述统计、正态性 | Analyze > Descriptive Statistics > Explore | Descriptives、Tests of Normality |
| 描述分类变量 | 计数资料 | 频数、率、构成比 | Analyze > Descriptive Statistics > Frequencies | Frequency Table |
| 样本均数与已知总体均数比较 | 单组计量资料 | 单样本 t 检验 | Analyze > Compare Means > One-Sample T Test | One-Sample Test 的 Sig.(2-tailed) |
| 同一对象前后比较 | 配对计量资料 | 配对 t 检验 | Analyze > Compare Means > Paired-Samples T Test | Paired Samples Test |
| 两个独立组均数比较 | 两独立组计量资料 | 独立样本 t 检验 | Analyze > Compare Means > Independent-Samples T Test | Levene 后选对应行的 Sig.(2-tailed) |
| 三组及以上均数比较 | 多独立组计量资料 | 单因素方差分析 | Analyze > Compare Means > One-Way ANOVA | ANOVA 表 Sig. |
| 多个因素影响均数 | 计量结局+多个分类因素 | 多因素方差分析 | Analyze > General Linear Model > Univariate | Tests of Between-Subjects Effects |
| 两个分类变量关联 | 计数资料 | 卡方检验 | Analyze > Descriptive Statistics > Crosstabs | Chi-Square Tests |
| 等级资料/偏态/小样本 | 非正态或等级资料 | 秩和检验 | Analyze > Nonparametric Tests > Legacy Dialogs | Test Statistics 的 Asymp. Sig. |
| 两个计量变量相关 | 计量资料 | Pearson/Spearman 相关 | Analyze > Correlate > Bivariate | r 和 Sig. |
| 计量结局预测 | 因变量为计量 | 线性回归 | Analyze > Regression > Linear | Model Summary、ANOVA、Coefficients |
| 二分类结局影响因素 | 因变量为 0/1 | 二元 Logistic 回归 | Analyze > Regression > Binary Logistic | Variables in the Equation 的 Sig.、Exp(B) |
| 画统计图 | 按资料类型选择图 | 条图、箱线图、散点图等 | Graphs > Chart Builder | 图形类型是否匹配资料 |

## 4. 描述统计

### 4.1 计量资料描述

菜单：

`Analyze > Descriptive Statistics > Explore`

常用设置：

- Dependent List：放计量变量。
- Factor List：如果要分组描述，把分组变量放这里。
- Plots：可勾选 Normality plots with tests。

输出判读：

- 近似正态：报告 `均数 ± 标准差`。
- 偏态分布：报告 `中位数 M` 和 `四分位数间距 P25-P75`。
- 正态性常看 Shapiro-Wilk 或 Kolmogorov-Smirnov 的 Sig.。

答题模板：

`采用 Explore 进行描述统计。该变量均数为……，标准差为……；若资料偏态，则中位数为……，四分位数间距为……。`

### 4.2 分类资料描述

菜单：

`Analyze > Descriptive Statistics > Frequencies`

输出判读：

- Frequency：频数。
- Percent：百分比。
- Valid Percent：排除缺失后的百分比。

答题模板：

`采用频数分析描述分类变量，报告各类别频数和百分比。`

## 5. t 检验

### 5.1 单样本 t 检验

适用：一个样本均数与已知总体均数比较。

菜单：

`Analyze > Compare Means > One-Sample T Test`

设置：

- Test Variable(s)：放计量变量。
- Test Value：填已知总体均数。

看输出：

- `One-Sample Test` 表。
- 看 `Sig.(2-tailed)`。

结论模板：

`采用单样本 t 检验，结果显示 P=……。按 alpha=0.05 水准，样本均数与已知总体均数差异有/无统计学意义。`

### 5.2 配对 t 检验

适用：同一对象处理前后、左右侧、配对设计。

菜单：

`Analyze > Compare Means > Paired-Samples T Test`

设置：

- 把 `before` 和 `after` 配成一对。

看输出：

- `Paired Samples Test` 表。
- 看 `Sig.(2-tailed)`。

结论模板：

`采用配对 t 检验比较处理前后均数，P=……，差异有/无统计学意义。`

### 5.3 独立样本 t 检验

适用：两独立组均数比较，例如治疗组 vs 对照组。

菜单：

`Analyze > Compare Means > Independent-Samples T Test`

设置：

- Test Variable(s)：放计量结局变量。
- Grouping Variable：放分组变量，点 Define Groups 填两组编码。

看输出的顺序：

1. 先看 `Levene's Test for Equality of Variances`。
2. Levene 的 Sig. > 0.05：看 `Equal variances assumed` 行。
3. Levene 的 Sig. < 0.05：看 `Equal variances not assumed` 行。
4. 在对应行看 `Sig.(2-tailed)`。

结论模板：

`采用独立样本 t 检验比较两组均数。Levene 方差齐性检验 P=……，故读取……行结果；t 检验 P=……，差异有/无统计学意义。`

## 6. 方差分析

### 6.1 单因素方差分析

适用：三组及以上独立样本均数比较。

菜单：

`Analyze > Compare Means > One-Way ANOVA`

设置：

- Dependent List：放计量结局变量。
- Factor：放分组变量。
- Options：勾选 Descriptive、Homogeneity of variance test。
- Post Hoc：如果需要两两比较，方差齐可选 LSD/Bonferroni，方差不齐可选 Tamhane。

看输出：

- `Test of Homogeneity of Variances`：方差齐性。
- `ANOVA` 表：看 Sig.。
- P<0.05 只能说明“至少两组总体均数不同”，不能写成“所有组都不同”。

结论模板：

`采用单因素方差分析比较多组均数。ANOVA 表显示 P=……，说明各组总体均数差异有/无统计学意义。若 P<0.05，需进一步做两两比较。`

### 6.2 多因素方差分析

适用：因变量为计量资料，自变量为两个或多个分类因素。

菜单：

`Analyze > General Linear Model > Univariate`

设置：

- Dependent Variable：计量结局变量。
- Fixed Factor(s)：分类因素。
- Model：一般先选 Full factorial，可分析主效应和交互作用。
- Options：勾选 Descriptive statistics、Homogeneity tests。

看输出：

- `Tests of Between-Subjects Effects`。
- 每个因素和交互项都有一行 Sig.。

结论模板：

`多因素方差分析结果显示，因素 A 的 P=……，因素 B 的 P=……，交互作用 A*B 的 P=……。按 alpha=0.05 水准，判断其主效应或交互作用是否有统计学意义。`

## 7. 卡方检验

适用：两个分类变量之间的差异或关联，例如两组有效率比较。

菜单：

`Analyze > Descriptive Statistics > Crosstabs`

设置：

- Row(s)：一个分类变量。
- Column(s)：另一个分类变量。
- Statistics：勾选 Chi-square。
- Cells：建议勾选 Observed、Expected、Row percent、Column percent。

看输出：

- 常规看 `Pearson Chi-Square` 的 `Asymp. Sig.`。
- 2x2 表理论频数偏小时，留意 `Continuity Correction` 或 `Fisher's Exact Test`。
- 如果是汇总频数表，务必先 Weight Cases。

结论模板：

`采用 chi-square 检验分析两个分类变量之间的关系。Pearson chi-square 检验 P=……，按 alpha=0.05 水准，差异/关联有或无统计学意义。`

## 8. 非参数检验

适用：等级资料、偏态计量资料、小样本或不满足参数检验条件的资料。

| 设计 | 方法 | SPSS菜单 |
|---|---|---|
| 两个相关样本 | Wilcoxon 符号秩检验 | Analyze > Nonparametric Tests > Legacy Dialogs > 2 Related Samples |
| 两个独立样本 | Mann-Whitney U 检验 | Analyze > Nonparametric Tests > Legacy Dialogs > 2 Independent Samples |
| 多个独立样本 | Kruskal-Wallis H 检验 | Analyze > Nonparametric Tests > Legacy Dialogs > K Independent Samples |
| 多个相关样本 | Friedman 检验 | Analyze > Nonparametric Tests > Legacy Dialogs > K Related Samples |

看输出：

- `Test Statistics`。
- 看 `Asymp. Sig.` 或 Exact Sig.。

结论模板：

`由于资料为等级资料/偏态分布/不满足参数检验条件，采用……秩和检验。结果 P=……，差异有/无统计学意义。`

## 9. 相关与回归

### 9.1 相关分析

适用：两个变量之间是否存在线性相关或等级相关。

菜单：

`Analyze > Correlate > Bivariate`

选择：

- 两个计量变量且近似正态：Pearson。
- 等级资料或明显偏态：Spearman。

看输出：

- `Pearson Correlation` 或 `Spearman's rho`：相关系数 r。
- `Sig.`：P 值。

结论模板：

`相关分析显示 r=……，P=……。两变量之间存在/不存在统计学相关；r>0 为正相关，r<0 为负相关。`

### 9.2 简单/多元线性回归

适用：因变量为计量资料，分析一个或多个自变量对它的影响。

菜单：

`Analyze > Regression > Linear`

设置：

- Dependent：计量因变量。
- Independent(s)：自变量。
- Statistics：可勾选 Estimates、Model fit、Confidence intervals、Collinearity diagnostics。

看输出：

- `Model Summary`：R Square 表示解释比例。
- `ANOVA`：看整体模型是否有统计学意义。
- `Coefficients`：看每个自变量的 B、t、Sig.。
- 多元回归中如果勾选共线性诊断，可看 VIF；VIF 很大提示共线性问题。

结论模板：

`线性回归结果显示，模型整体 P=……，R Square=……。自变量……的回归系数 B=……，P=……，提示其对因变量有/无统计学影响。`

## 10. 二元 Logistic 回归

适用：因变量为二分类结局，例如患病/未患病、有效/无效。

菜单：

`Analyze > Regression > Binary Logistic`

设置：

- Dependent：二分类结局变量，通常编码为 0/1。
- Covariates：自变量。
- Categorical：把分类自变量放进去并设置参照组。
- Options：可勾选 CI for exp(B)，常用 95%。

看输出：

- `Variables in the Equation`。
- `B`：回归系数。
- `Sig.`：P 值。
- `Exp(B)`：OR 值。
- OR>1：该因素可能增加结局发生优势。
- OR<1：该因素可能降低结局发生优势。

结论模板：

`二元 Logistic 回归结果显示，自变量……的 OR=……，95%CI 为……，P=……。按 alpha=0.05 水准，该因素与结局发生有/无统计学关联。`

注意：

- 不是“自变量很多就用 Logistic”，关键看因变量是不是二分类。
- Exp(B) 是 OR，不是均数差，也不是相关系数。

## 11. 统计图常用选择

菜单：

`Graphs > Chart Builder`

| 目的 | 推荐图形 | 常见变量 |
|---|---|---|
| 比较各类别频数/率 | 条图 Bar chart | 分类变量 |
| 看计量资料分布 | 直方图 Histogram | 一个计量变量 |
| 比较多组计量资料分布 | 箱线图 Boxplot | 分组变量 + 计量变量 |
| 看两个计量变量关系 | 散点图 Scatterplot | 两个计量变量 |
| 看随时间变化 | 线图 Line chart | 时间变量 + 指标 |

写图题时先说明图形目的：

`为比较不同组的率，选择条图；为观察两个计量变量的关系，选择散点图。`

## 12. 输出判读统一规则

### 12.1 P 值

- P<0.05：差异/关联/回归关系有统计学意义。
- P>=0.05：差异/关联/回归关系无统计学意义。
- 不要写“证明没有差异”，应写“未发现统计学差异”或“差异无统计学意义”。

### 12.2 常见输出指标

| 输出指标 | 含义 | 常出现位置 |
|---|---|---|
| Mean | 均数 | 描述统计、t 检验 |
| Std. Deviation | 标准差 | 描述统计 |
| Sig. | P 值 | 几乎所有检验 |
| Sig.(2-tailed) | 双侧 P 值 | t 检验、相关 |
| Pearson Chi-Square | 卡方统计量 | Crosstabs |
| F | F 统计量 | 方差分析、回归 ANOVA |
| r | 相关系数 | 相关分析 |
| R Square | 决定系数 | 线性回归 |
| B | 回归系数 | 线性/Logistic 回归 |
| Exp(B) | OR 值 | Logistic 回归 |

## 13. 操作题万能答题框架

每道 SPSS 大题都按这个顺序写：

```text
本题因变量为……，属于……资料；分组变量/自变量为……。
根据研究目的和资料类型，选择……检验/分析。
SPSS菜单路径为：……
主要查看……表中的……指标。
结果显示 P=……。按 alpha=0.05 水准，差异/关联/回归关系有或无统计学意义。
```

## 14. 最容易丢分的 10 个点

1. 独立样本 t 检验忘记先看 Levene，导致读错行。
2. 方差分析 P<0.05 后写成“所有组均不同”，正确说法是“至少两组不同”。
3. 用卡方检验去比较均数，或用 t 检验去比较率。
4. 汇总频数资料做卡方前忘记 Weight Cases。
5. 配对设计误当成独立样本。
6. 等级资料、偏态资料仍硬做 t 检验。
7. Logistic 回归忘记解释 Exp(B)=OR。
8. 看到多个自变量就直接选 Logistic，忘记先看因变量类型。
9. 只写 P<0.05，不写所用方法和结论对象。
10. 输出截图只截了一半，没有包含统计量和 P 值。

## 15. 考前 15 分钟只背这些菜单

```text
计量描述：Analyze > Descriptive Statistics > Explore
频数/率：Analyze > Descriptive Statistics > Frequencies
单样本 t：Analyze > Compare Means > One-Sample T Test
配对 t：Analyze > Compare Means > Paired-Samples T Test
独立样本 t：Analyze > Compare Means > Independent-Samples T Test
单因素 ANOVA：Analyze > Compare Means > One-Way ANOVA
多因素 ANOVA：Analyze > General Linear Model > Univariate
卡方：Analyze > Descriptive Statistics > Crosstabs
非参数：Analyze > Nonparametric Tests > Legacy Dialogs
相关：Analyze > Correlate > Bivariate
线性回归：Analyze > Regression > Linear
Logistic回归：Analyze > Regression > Binary Logistic
作图：Graphs > Chart Builder
加权：Data > Weight Cases
```

最后记住一句话：  
**先看资料类型，再看设计类型；先选方法，再看对应输出；结论永远围绕 P 值和研究问题写。**
