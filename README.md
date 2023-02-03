# 复旦大数据 Data Mining-数据挖掘实务

- 作者：[周嘉楠](https://www.zhoujianan.com)
- 教师：[朱雪宁](https://xueningzhu.github.io/)
- 时间：2020 年春季学期
- 编号：DATA620007

## [Introduction](https://github.com/jrothschild33/FudanUniversity-DataMining)

本部分内容为复旦大学大数据学院 2020 年春季学期由朱雪宁副教授开设课程，主要学习了主流的数据挖掘算法，包括：

- 线性回归模型：Linear Regression Model
- 逻辑回归模型：Logistic Regression Model
- 线性判别分析：Linear Discriminant Analysis
- K 近邻分类模型：K-Nearest Neighbour
- 朴素贝叶斯模型：Naive Bayes Classifier
- 决策树模型：Decision Tree Model
- 提升算法模型：AdaBoost、Gradient Boosting Decision Tree(GBDT)、XGBoost
- 随机森林模型：Random Forest Model
- 支持向量机：Support Vector Machine
- 主成分分析法：Principal Component Analysis(PCA)

除了以上模型的理论部分讲解之外，还在 6 大商业场景进行了应用：

- 新冠疫情分析：掌握数据描述性统计方法，使用 Matplotlib 绘制柱状图、折线图、箱线图、地图等。
- 餐饮数据分析：运用 Word Cloud 词云模块对数据进行分析，并使用线性回归模型建模。
- 信用违约分析：对海量银行信用卡数据进行分析，建立逻辑回归模型，利用 BIC 准则进行变量筛选；对样本进行预测，计算 AUC 值，并绘制 ROC 曲线。
- 通信数据分析：对数据中的词汇进行词频分析，针对性地提升业务效率。
- 社交数据分析：运用决策树、Boosting 模型、随机森林、SVM 模型对真实社交约会数据建模，分析人群画像。
- 美国房价分析：分析全美房地产最大网站 Zillow 数据，综合运用各种数据分析图表，并建立 7 大模型对房价进行预测：Linear regression Model、Polynomial regression Model、Lasso Regression Model、Elastic Nets Regression Model、Ridge Regression Model、Decision Tree Model、Random Forest Model，最终对结果进行综合对比。

## [CASE 1 Cov19 新冠肺炎疫情报告](https://zhoujianan.com/assets/school/FDU_Data_Mining/HTML/1.COVID-19.html)

### 数据说明

- `ncov_311.csv`：全国疫情时序数据（1 月 20 日至 3 月 11 日），来自于来自国家卫健委官方网站的数据，包含变量：

1. 日期（Date）
2. 全国当日新增确诊人数（new_confirmed）
3. 全国当日累计确诊人数（confirmed_count）
4. 全国当日死亡人数（dead_count）
5. 全国当日治愈人数（cure_count）
6. 全国当日正在接受医学观察的人数（observe_count）
7. 全国新增密切接触人数（new_contact）
8. 湖北省当日正在接受医学观察的人数（Hubei_observe_count）
9. 湖北省当日新增确诊人数（Hubei_new_confirmed）
10. 湖北省当日累计确诊人数（Hubei_confirmed_count）
11. 湖北新增密切接触人数（Hubei_new_contact）

- `CityTS_219.xlsx`：8 省 13 市疫情时序数据（1 月 28 日至 2 月 19 日）

8 省分别为湖北、浙江、广东、河南、湖南、安徽、江西，黑龙江，13 市分为湖北城市（武汉、孝感、黄冈、随州、襄阳），一线城市（北上广深），重点关注城市（杭州、温州、重庆、长沙）。所有地区的共同变量包括累计确诊人数，累计治愈人数，累计死亡人数，累计密切接触者人数，以及截至当日 24 时正在接受医学观察的人数。此外，湖北省根据《新型冠状病毒感染的肺炎诊疗方案（试行第五版）》在病例诊断分类中增加了“临床诊断”，湖北省及下属五市的数据额外包括累计临床诊断人数、累计临床诊断治愈人数、累计临床诊断死亡人数。

提示：除了给出的两个数据集，还可以从公开渠道获取其他的肺炎相关公开数据及进行进一步探索。

### 分析任务

1. 分别读入截至 3 月 11 日和截至 2 月 19 日的肺炎数据；
2. 应用描述分析，探索各个省份新型肺炎疫情的分布规律，并给出点评（提示：采用累计数目，使用柱状图、箱线图、地图等绘图方式进行描述分析）
3. 应用描述分析，探索各个省份新型肺炎疫情的发展情况，并给出点评（提示：通过折线图进行对比）
4. 自命题一个其他探索方向，使用公开数据进行探索。

### 格式要求

1. 写题目，宋体小四号，加粗居中。
2. 正文宋体五号单倍行距，段间距设置段前段后均为 0 行，文字两端对齐。篇幅上限：5 页；篇幅下限：2 页。
3. 报告用 WORD 进行撰写，保存成 PDF 格式提交。
4. 代码提交 HTML 格式（注：请自学 R markdown，并将代码输出为 HTML 格式），代码中最好有一定注释，增强可读性。

## [CASE 2 火锅团购数据分析](https://zhoujianan.com/assets/school/FDU_Data_Mining/HTML/2.catering.html)

### 数据介绍

`HotPoT.csv`：案例数据提供了某线上团购网站的西安市区内在 2017 年 01 月 05 日这一时间节点的共 2688 个火锅团购产品的销售数据，数据说明表如下：

![数据介绍](https://zhoujianan.com/assets/school/FDU_Data_Mining/HW2/data_introduction.jpg)

### 分析任务

1. 请完成数据读入与简单清洗；
2. 将团购的季均销量转换为对数，对季均销量、团购上线天数、折扣力度绘制分布直方图，简单陈述你观察到的现象；
3. 将火锅团购商家店名高频词统计出来，并绘制出词云，简单陈述你观察到的现象；提示：在统计火锅团购商家店名高频词时，可以将一些无意义的词组剔除，如“区”、“路”、“火锅”、“小区”、“分店”、“店”等；同时还需要先剔除非中文字符（数字和字母）。
4. 用箱线图表示销量与团购价的关系，及销量与节假日通用的关系；尝试解读这两个箱线图呈现的现象；
5. 用箱线图表示店名中包含的各类词汇与团购销量的关系，并尝试解读箱线图的含义；
6. 建立线性回归模型，探究影响团购销量的主要因素，并对模型结果进行适当解读。

## [CASE 3 征信建模数据分析](https://zhoujianan.com/assets/school/FDU_Data_Mining/HTML/3.credit.html)

### 数据说明

`simudata.csv`：此数据为某公司用户在第三方交易平台的用户的日常刷卡行为数据，数据提供了一批用户行为记录，包括：年龄、银行卡数、借贷比率、交易笔数、所有行为均值、所有行为最大值等。详细的变量含义及说明如下：

![数据说明](https://zhoujianan.com/assets/school/FDU_Data_Mining/HW3/data_introduction.png)

在营销领域，RFM 模型是用来衡量客户的价值和客户的创利能力的重要工具和手段。这个模型通过一个客户的近期购买行为、购买的总体频率以及花了多少钱三项指标来描述该客户的综合价值，具体如下：

1. R（Recency）：最近一次消费，指上一次购买的时间到现在的距离。理论上，上一次消费时间越近的用户应该是相对而言活跃的用户。
2. F（Frequency）：消费频率，即用户在限定的期间内产生购买的总次数。产生购买越频繁的用户，忠诚度越高。
3. M（Monetary）：某个用户所有消费金额的平均值。
4. S（StandardDeviation）：由于这三个指标并不能够衡量用户产生行为的波动性，所以我们增加一个指标 S 来衡量用户行为的波动性。

举例说明：对于购买游戏点卡类行为，我们可以定义 R 为用户最近一次购买游戏点卡距离数据提取时间的时间间隔，F 定义为一年内用户购买游戏点卡的次数，M 定义为一年内用户每次购买游戏点卡的平均金额，S 定义为用户每次购买游戏点卡金额的标准差。我们将所有变量记作类别名称加指标简称的形式，例如游戏 R，表示游戏类的 Recency。

用户行为的分类通过银行卡信息表，以及商户分类信息表，根据业务场景，我们提取了以下类别，每个类别都对应着以上我们已经定义好的 RFMS 四个指标。类别包括：

1. 借记类：刻画用户使用储蓄卡的交易行为。不同的用户习惯不同，采用储蓄卡和信用卡的倾向也可能不同。
2. 消费类：刻画用户的日常消费行为。日常消费行为的金额以及频次不同，用户的还款能力可能不同。
3. 信贷类：刻画用户之前的小额贷款类行为。用户之前如果有其他消费贷款类行为可能已经习惯进行消费贷款，从而可能具备更良好的信用状况。
4. 转账类：刻画用户的转账行为。经常通过熊小贷 APP 转账的用户可能与不转账的用户行为不同。
5. 话费类：刻画用户的话费充值交易行为。话费充值是否规律与充值金额多少都可能意味着用户群体不同。
6. 公缴类：刻画用户交水，电，煤气费等交易行为。公缴费用的多少与是否规律也可能说明用户群体的不同。
7. 游戏类：刻画用户购买游戏点卡的行为。经常玩游戏的用户群体可能与不玩游戏的人不同。
8. 四大行卡类以及中型银行卡类：四大行包括中国银行，中国农业银行，中国工商银行，中国建设银行，中型银行包括招商银行，浦发银行，兴业银行，平安银行等。这个指标的设定有以下两方面原因：a.不同公司的工资卡不同，小型创业公司一般采用中型银行的银行卡；b.四大行的信用卡发放较为保守，所以能够申请到四大行信用卡的人可能和采用其他银行信用卡的用户群体不同。
9. 白金及金卡类：通过卡标首可以对应到银行卡是属于哪家银行的哪种类型的卡，例如招商银行的金葵花卡。我们搜索整理了相应银行的金卡和白金卡卡种名称，并对应到每一个用户。我们初步认为，拥有白金卡和金卡的用户具备更高的还款能力，所以用户群体不同。

### 分析任务

1. 读入数据并了解各个自变量的含义；
2. 对变量交易笔数和所有用户行为均值分别绘制违约组和非违约组的对比箱线图，并分析是否违约与这些变量之间的关系，给出解读；
3. 用全部样本数据，以是否违约为因变量建立逻辑回归模型，利用 BIC 准则进行变量筛选，观察最终得到的回归系数并尝试解释对系数进行解释；
4. 使用任务 3 的模型，对全部样本进行预测，计算 AUC 值，并绘制 ROC 曲线，对模型的效果进行评估；
5. 任务 4 中对每个训练样本预测出了非违约的概率，按照非违约率从高到低排序，将全部样本分为 5 组人群：非违约率最高的 20%用户、…、非违约率最低的 20%用户，计算五类人群的平均非违约概率，从高到低排序，绘制柱状图；对结果的商业应用进行解读。

## [CASE 4 市长电话数据分析](https://zhoujianan.com/assets/school/FDU_Data_Mining/HTML/4.phones.html)

### 数据说明

`train_set.csv`、`test_set.csv`

市长电话数据集是某北方城市政府部门冬季收到的“12345”服务热线的来电信息记录。数据集中的变量包括:

1. 单位名称：即每一条来电信息记录最 终受理的政府部门；
2. 词汇出现的频数：已有词汇表中各个词汇在投诉建议的文本内容中出现的频数。

数据总共有 2000 行，每一行代表一条投诉建议中各个词汇的出现频数，第 2-6236 列的列名为某个词汇。

## [CASE 5 约会数据集分析](https://zhoujianan.com/assets/school/FDU_Data_Mining/HTML/5.socialdate.html)

### 数据说明

`SpeedDatingData.csv`
该数据是 Kaggle 网站提供的芝加哥商学院 Ray Fisman 教授和 Sheena Iyengar 教授 2002 年至 2004 年组织的相亲实验数据。实验的开始，组织者在该校网站上招募相亲者。志愿者需要在网站上注册，经审核后方可参与相亲活动。数据来源为：[https://www.kaggle.com/annavictoria/speed-dating-experiment](https://www.kaggle.com/annavictoria/speed-dating-experiment)

每一位参与者在约会前，都需要填写一张调查表，其中包括本人的个人信息（性别、年龄、种族、从事领域和兴趣等）和对理想型的各方面期望打分。在约会后，需要对实际相亲的对象各方面进行打分，并评估出好感度和成功牵手的可能性。该数据集中，每一条观测包含一对相亲成员（两位）的信息，但是是从其中一个人的角度展示的（以下称为“本人”），本人的 ID 是 iid 变量，对方的 ID 是 pid 变量，dec 表示本人（即 iid）做出的决策。

对于约会后打分的变量，【被打分】的是`pid`，【做出打分这个动作】的是`iid`，以 A 和 B 两位参与者为例：

- iid=A&pid=B 的数据中，期望打分是 A 在约会前对理想型的描述，约会主观打分是 A 给 B 打的分数；
- iid=B&pid=A 的数据中，期望打分是 B 在约会前对理想型的描述，约会主观打分是 B 给 A 打的分数；

完整数据中变量较多，在本次分析任务中将有可能使用到的变量含义及说明如下表所示：
![数据说明](https://zhoujianan.com/assets/school/FDU_Data_Mining/HW5/data_introduction.jpg)

### 分析任务

1. 读入数据，并选出上述表格所示的变量，并确定一个你感兴趣的选题方向；例如：什么因素与两人进一步发展有关？
2. 完成与你的选题相关的 2-3 个描述分析；形式：参考课上讲的描述分析内容；
3. 针对选题目的进行建模，并解读模型的结果；需要包含模型：**决策树、Boosting 模型、随机森林、SVM 模型**的比较
4. 结合任务 3-4 的结果，得出你的结论。

## [CASE 6 美国房价分析](https://zhoujianan.com/assets/school/FDU_Data_Mining/HTML/6.US-housing.html)

### 背景介绍

房地产业是美国国民经济的重要组成部分，是重要的基础产业。1992 年美国房地产业与整体国民经济的比例关系为：房地产业产值占所有产业产值之比为 0.95%,房地产业的工资总额与所有产业工资总额之和的比例为 1.2%，房地产业就业人口与所有产业总就业人口的比例为 1.3%。1997 年这些比例分别为房地产业产值占 0.94%, 工资额占 1.2%, 就业人口占 1.3%。虽然 1992 年与 1997 年的具体数字不同，但房地产业与整体国民经济的比例关系几乎完全一致，这不是偶然的，它说明了两个问题：一是房地产业发展与整体国民经济发展配合得非常协调，二是反映了房地产业与整体国民经济的合理比例关系，保持这种比例就足于满足生产和生活对房地产的需求。因为房地产业是作为生产和生活场所存在的，它的发展速度决定于经济增长和人们生活水平提高对其提出的需求。

![](https://zhoujianan.com/assets/school/FDU_Data_Mining/HW6/1.jpg)

在过去的二十年里，美国房地产业伴随着社会的整体国民经济发展，基本保持平稳向上的发展趋势。美国房地产业也表现出周期性，一般是 18~20 年左右经历一个周期循环，但周期波动幅度较小，较少大起大落。美国主要房地产参考指数之一的“NCREIF 指数”从近 20 年来的表现情况来看, 美国房地产投资回报呈现出平稳增长趋势，这也表明美国房地产市场是一个理性成熟的市场。从长线投资来看，在美国投资房地产具有风险低、收益稳定、回报率高等特点。

### 研究目标

本文将使用 Zillow 经济数据集分析美国房价具体情况，这是一份由 Zillow 的经济研究团队收集、整理和发布来自各种公共和专有资源的住房和经济数据，其中包括地方政府存档的不动产档案资料，包括契约合同、房屋登记信息和交易历史。文章将对房价数据集进行深入分析，探索美国房价的历史走势，并选取最具代表性的加利福尼亚州房价数据集，使用七种机器学习模型对房价进行预测。
