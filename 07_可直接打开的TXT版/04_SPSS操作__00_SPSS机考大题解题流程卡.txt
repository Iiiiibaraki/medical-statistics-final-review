# SPSS机考大题解题流程卡

用途：考试时看到 SPSS 分析大题，不再先点软件，而是先按流程判断。

## 0. 先别急着点菜单

拿到题目先写 5 个字：

`变量-组数-目的`

也就是：

1. 因变量是什么？
2. 因变量是计量、分类、等级，还是二分类？
3. 自变量或分组变量是什么？
4. 是一组、两组、三组及以上？
5. 是独立组，还是同一对象前后配对？

## 1. 选方法流程

### A. 题目让你“描述”

一个计量变量：

- 正态或近似正态：均数±标准差。
- 偏态：中位数和四分位数。
- SPSS：`Analyze > Descriptive Statistics > Explore`
- 看：Descriptives、Tests of Normality。

一个分类变量：

- 用频数、率、构成比。
- SPSS：`Analyze > Descriptive Statistics > Frequencies`
- 看：Frequency Table。

### B. 题目让你“比较均数”

一个样本均数 vs 已知总体均数：

- 方法：单样本t检验。
- SPSS：`Analyze > Compare Means > One-Sample T Test`
- 看：One-Sample Test 的 `Sig.(2-tailed)`。

同一批对象前后比较：

- 方法：配对t检验。
- SPSS：`Analyze > Compare Means > Paired-Samples T Test`
- 看：Paired Samples Test 的 `Sig.(2-tailed)`。

两个独立组比较：

- 方法：独立样本t检验。
- SPSS：`Analyze > Compare Means > Independent-Samples T Test`
- 先看：Levene 方差齐性。
- 再看：对应行的 `Sig.(2-tailed)`。

三组及以上比较：

- 方法：单因素方差分析。
- SPSS：`Analyze > Compare Means > One-Way ANOVA`
- 看：ANOVA 表的 `Sig.`。
- 注意：P<0.05 后才说“至少两组均数不同”，再考虑两两比较。

### C. 题目是“分类变量之间是否有关”

两个分类变量：

- 方法：χ²检验。
- SPSS：`Analyze > Descriptive Statistics > Crosstabs`
- 点：Statistics 勾选 `Chi-square`。
- 看：Chi-Square Tests 的 `Pearson Chi-Square`。
- 2×2表理论频数太小时，留意连续性校正或 Fisher。

### D. 题目是“等级资料、偏态资料、小样本”

配对资料：

- 方法：Wilcoxon 符号秩检验。
- SPSS：`Analyze > Nonparametric Tests > Legacy Dialogs > 2 Related Samples`
- 看：Test Statistics 的 `Asymp. Sig.`。

两独立组：

- 方法：Mann-Whitney U 检验。
- SPSS：`Analyze > Nonparametric Tests > Legacy Dialogs > 2 Independent Samples`
- 看：Test Statistics 的 `Asymp. Sig.`。

多独立组：

- 方法：Kruskal-Wallis H 检验。
- SPSS：`Analyze > Nonparametric Tests > Legacy Dialogs > K Independent Samples`
- 看：Test Statistics 的 `Asymp. Sig.`。

### E. 题目问“两个计量变量关系”

两个计量变量是否相关：

- 方法：Pearson相关。
- SPSS：`Analyze > Correlate > Bivariate`
- 看：`Pearson Correlation` 和 `Sig.`。

### F. 题目问“影响因素”

因变量是计量资料：

- 方法：线性回归或多元线性回归。
- SPSS：`Analyze > Regression > Linear`
- 看：
  - Model Summary：`R Square`
  - ANOVA：整体模型 P 值
  - Coefficients：每个自变量的 B、t、Sig.

因变量是二分类：

- 方法：二元 Logistic 回归。
- SPSS：`Analyze > Regression > Binary Logistic`
- 看：
  - Variables in the Equation
  - `B`
  - `Sig.`
  - `Exp(B)`，也就是 OR

## 2. 操作题答题模板

每道 SPSS 大题按这个模板写：

```text
本题因变量为……，属于……资料；分组变量/自变量为……。
研究目的为……，故选择……检验/分析。
SPSS菜单路径为：……
主要查看……表中的……指标。
结果显示 P=……。
按 α=0.05 水准，P<0.05，差异/关联/回归关系有统计学意义；P≥0.05，则无统计学意义。
```

## 3. 软件界面空白时的急救顺序

如果坐在电脑前突然不知道点哪里，按这个顺序问自己：

1. 是描述吗？先找 `Descriptive Statistics`。
2. 是均数比较吗？先找 `Compare Means`。
3. 是分类变量吗？先找 `Crosstabs`。
4. 是偏态或等级资料吗？先找 `Nonparametric Tests`。
5. 是相关吗？先找 `Correlate`。
6. 是影响因素吗？先找 `Regression`。

记住这 6 个入口，SPSS 大题至少不会完全卡死。

## 4. 最容易丢分的地方

- 独立样本t检验忘记先看 Levene。
- 方差分析 P<0.05 后，把结论写成“所有组都不同”。
- χ²检验拿去比较均数。
- Logistic 回归忘记解释 `Exp(B)` 是 OR。
- 看到多个自变量就乱用 Logistic；先看因变量是不是二分类。
- 只写 P<0.05，不写采用什么检验和统计学意义结论。

## 5. 考前必须默写的菜单

- 描述统计：`Analyze > Descriptive Statistics > Explore`
- 频数：`Analyze > Descriptive Statistics > Frequencies`
- 独立样本t检验：`Analyze > Compare Means > Independent-Samples T Test`
- 配对t检验：`Analyze > Compare Means > Paired-Samples T Test`
- 单因素方差分析：`Analyze > Compare Means > One-Way ANOVA`
- χ²检验：`Analyze > Descriptive Statistics > Crosstabs`
- 非参数检验：`Analyze > Nonparametric Tests > Legacy Dialogs`
- 相关：`Analyze > Correlate > Bivariate`
- 线性回归：`Analyze > Regression > Linear`
- Logistic回归：`Analyze > Regression > Binary Logistic`
