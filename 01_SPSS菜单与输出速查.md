# SPSS菜单与输出速查

## 数据录入先会这几件事

变量视图：

- Name：变量名，只用英文或拼音，不能有空格。
- Type：类型，一般用 Numeric。
- Label：变量说明，可以写中文，如“治疗前血压”。
- Values：分类变量的编码说明，如 1=男，2=女；1=治疗组，2=对照组。
- Measure：计量资料选 Scale；无序分类选 Nominal；等级资料选 Ordinal。

数据视图：

- 一行代表一个研究对象。
- 一列代表一个变量。
- 分组变量用数字编码，再在 Values 里解释。

## 常用菜单

| 任务 | SPSS菜单 | 主要输出 | 看哪里 |
|---|---|---|---|
| 计量资料描述 | Analyze > Descriptive Statistics > Explore | Descriptives、Tests of Normality | 均数、标准差、中位数、Shapiro-Wilk |
| 频数/构成比 | Analyze > Descriptive Statistics > Frequencies | Frequency Table | 频数、百分比 |
| 单样本t检验 | Analyze > Compare Means > One-Sample T Test | One-Sample Test | Sig.(2-tailed) |
| 配对t检验 | Analyze > Compare Means > Paired-Samples T Test | Paired Samples Test | Sig.(2-tailed) |
| 独立样本t检验 | Analyze > Compare Means > Independent-Samples T Test | Independent Samples Test | 先Levene，再Sig.(2-tailed) |
| 单因素方差分析 | Analyze > Compare Means > One-Way ANOVA | ANOVA | Sig. |
| 多因素方差分析 | Analyze > General Linear Model > Univariate | Tests of Between-Subjects Effects | 每个因素对应Sig. |
| χ²检验 | Analyze > Descriptive Statistics > Crosstabs | Chi-Square Tests | Pearson Chi-Square |
| 非参数检验 | Analyze > Nonparametric Tests > Legacy Dialogs | Test Statistics | Asymp. Sig. |
| 相关分析 | Analyze > Correlate > Bivariate | Correlations | Pearson Correlation、Sig. |
| 线性回归 | Analyze > Regression > Linear | Model Summary、ANOVA、Coefficients | R²、模型P、B和P |
| Logistic回归 | Analyze > Regression > Binary Logistic | Variables in the Equation | B、Sig.、Exp(B) |
| 作图 | Graphs > Chart Builder | 图形 | 图形类型是否匹配资料 |

## 输出怎么看

### 独立样本t检验

1. 先看 Levene's Test for Equality of Variances。
2. 如果 Levene 的 Sig. > 0.05，看 Equal variances assumed 那一行。
3. 如果 Levene 的 Sig. < 0.05，看 Equal variances not assumed 那一行。
4. 再看 Sig.(2-tailed)，判断是否有统计学意义。

### 方差分析

1. 看方差齐性检验。
2. 看 ANOVA 表的 Sig.。
3. P<0.05：至少有两组总体均数不同或不全相同。
4. P<0.05 后才考虑 Post Hoc 两两比较。

### χ²检验

1. 看 Chi-Square Tests 表。
2. 常规看 Pearson Chi-Square 的 Asymp. Sig.。
3. 2×2表如果理论频数偏小，留意 Continuity Correction 或 Fisher's Exact Test。

### 线性回归

1. Model Summary：R Square 表示模型解释比例。
2. ANOVA：看整个模型是否有统计学意义。
3. Coefficients：看每个自变量的 B、t、Sig.。

### Logistic回归

1. Variables in the Equation：看 B、Sig.、Exp(B)。
2. Exp(B) 就是 OR。
3. β>0 时 OR>1；β<0 时 OR<1。

