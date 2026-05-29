# SPSS操作题答题模板

## 通用作答四步

1. 判断资料类型：计量、计数、等级。
2. 判断设计类型：独立、配对、多组、多因素。
3. 选择统计方法并写出SPSS菜单。
4. 看输出表的P值，写结论。

## 标准结论模板

`采用……检验，结果显示 P=……。按 α=0.05 水准，P<0.05，差异有统计学意义；P≥0.05，差异无统计学意义。`

考试时不要写太花，稳稳写清楚“方法、P值、结论”。

## 各题型模板

### 描述统计

资料类型：计量资料。  
SPSS菜单：Analyze > Descriptive Statistics > Explore。  
报告：

`该变量均数为……，标准差为……。若资料偏态，则报告中位数……和四分位数间距……。`

### 独立样本t检验

资料类型：两独立组计量资料。  
SPSS菜单：Analyze > Compare Means > Independent-Samples T Test。  
输出阅读：

- Levene方差齐性检验 P>0.05：看 Equal variances assumed。
- Levene方差齐性检验 P<0.05：看 Equal variances not assumed。

报告：

`采用独立样本t检验比较两组均数。结果显示 P=……，按 α=0.05 水准，差异有/无统计学意义。`

### 配对t检验

资料类型：同一对象前后或配对设计计量资料。  
SPSS菜单：Analyze > Compare Means > Paired-Samples T Test。  
报告：

`采用配对t检验比较处理前后均数。结果显示 P=……，差异有/无统计学意义。`

### 方差分析

资料类型：三组及以上计量资料。  
SPSS菜单：Analyze > Compare Means > One-Way ANOVA。  
报告：

`采用单因素方差分析比较多组均数。结果显示 P=……，说明各组总体均数差异有/无统计学意义。`

如果 P<0.05：

`进一步进行两两比较，以判断具体哪些组之间存在差异。`

### χ²检验

资料类型：两个分类变量。  
SPSS菜单：Analyze > Descriptive Statistics > Crosstabs。  
报告：

`采用χ²检验分析两个分类变量之间的关系。Pearson χ²检验 P=……，按 α=0.05 水准，差异有/无统计学意义。`

### 非参数检验

资料类型：偏态计量资料、等级资料、或不满足参数检验条件。  
SPSS菜单：Analyze > Nonparametric Tests > Legacy Dialogs。  
报告：

`采用……秩和检验。结果显示 P=……，差异有/无统计学意义。`

### 相关分析

资料类型：两个计量变量。  
SPSS菜单：Analyze > Correlate > Bivariate。  
报告：

`Pearson相关分析显示 r=……，P=……。两变量之间存在/不存在统计学相关。`

### 线性回归

资料类型：因变量为计量资料。  
SPSS菜单：Analyze > Regression > Linear。  
报告：

`线性回归结果显示模型 P=……，R²=……。自变量……的回归系数 B=……，P=……，提示其对因变量有/无统计学影响。`

### Logistic回归

资料类型：因变量为二分类变量。  
SPSS菜单：Analyze > Regression > Binary Logistic。  
报告：

`Logistic回归结果显示，自变量……的 OR=……，P=……。按 α=0.05 水准，该因素与结局发生有/无统计学关联。`

