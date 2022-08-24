# HPF
机器学习项目——HousePriceForecast：kaggle的一个关于Ames的房价预测问题。数据集中用79个解释变量描述影响住宅的各个方面，通过对这些数据的研究来找到影响房价的主要因素和次要因素，然后对最终的房价进行预测，得出结论。

# 房价预测项目报告
## 1.项目的选题和意义
本学期的机器学习项目，我们小组选择的是kaggle的一个关于Ames的房价预测问题。数据集中用79个解释变量描述影响住宅的各个方面，我们通过对这些数据的研究来找到影响房价的主要因素和次要因素，然后对最终的房价进行预测，得出结论。
作为一个机器学习的入门级项目，房价预测问题在提高我们机器学习方面的能力有较大的帮助，扩宽了我们机器学习知识的视野，激发了我们对机器学习方面的兴趣。另一方面，房价预测问题有较高的现实意义，随着房地产的发展和人们对家的追求，房价的升降牵动着每一个买房者的心。同样，房价的预测对房地产厂商也有较大的意义。虽然这个题目所给的条件没有现实生活中那么复杂，但是通过不断的修正和改善，真正将其运用到生活中，一定会给人们的决策作出巨大的改变。
总而言之，房价的预测问题对个人的能力提升和为人民造福方面有重大意义。

## 2.实验设置
本项目以jupyter notebook为平台，编译语言为python3，引用了numpy、pandas、torch、seaborn、missingno、xgboost、optuna、LazyRegressor、sklearn等函数库。
   
## 3.数据分析
目前在网上已经有很多研究成果，从训练数据和测试数据来说，大家都分析了数据规模、前几条数据、数据类型、缺省值及可视化。
同样，我们参考了一些网上的数据分析的方法，借鉴了很多大佬的思路。对训练集和测试集的数据维度、类型、缺省值及其相关性、分布等进行了分析，对比了训练数据和测试数据的类型、缺失数据及各种数据的特征及相关性。

## 4.数据与处理
本项目的数据处理分为两个方面：数据分析和数据预处理，前文已经概括了数据分析的大致步骤，本章主要介绍数据预处理的具体操作。
数据预处理一般包括数据审核、数据筛选和数据排序三个步骤。数据审核对于原始数据主要从完整性和准确性两个方面去审核。完整性审核主要是检查应调查的单位或个体是否有遗漏，所有的调查项目或指标是否填写齐全。准确性审核主要是包括两个方面：一是检查数据资料是否真实地反映了客观实际情况，内容是否符合实际；二是检查数据是否有错误，计算是否正确等。数据审核后，我们需要对审核过程中发现的错误应尽可能予以纠正。调查结束后，当数据发现的错误不能予以纠正，或者有些数据不符合调查的要求而又无法弥补时，就需要对数据进行筛选。数据筛选包括两方面的内容：一是将某些不符合要求的数据或有明显错误地数据予以剔除；二是将符合某种特定条件的数据筛选出来，对不符合特定条件的数据予以剔除。数据排序是按照一定顺序将数据排列，以便于研究者通过浏览数据发现一些明显的特征或趋势，找到解决问题的线索。除此之外，排序还有助于对数据检查纠错，为重新归类或分组等提供依据。
数据预处理中有数据清洗、数据集成、数据变换、数据规约等方法，本项目数据预处理主要涉及数据清洗。数据处理主要分为以下方法：
1.解决不完整数据（即值缺失）的方法
大多数情况下，缺失的值必须手工填入（即手工清理）。当然，某些缺失值可以从本数据源或其它数据源推导出来，这就可以用平均值、最大值、最小值或更为复杂的概率估计代替缺失的值，从而达到清理的目的。
2.错误值的检测及解决方法
用统计分析的方法识别可能的错误值或异常值，如偏差分析、识别不遵守分布或回归方程的值，也可以用简单规则库（常识性规则、业务特定规则等）检查数据值，或使用不同属性间的约束、外部的数据来检测和清理数据。
3.重复记录的检测及消除方法
数据库中属性值相同的记录被认为是重复记录，通过判断记录间的属性值是否相等来检测记录是否相等，相等的记录合并为一条记录（即合并/清除)。合并/清除是消重的基本方法。
4.不一致性（数据源内部及数据源之间）的检测及解决方法
从多数据源集成的数据可能有语义冲突，可定义完整性约束用于检测不一致性，也可通过分析数据发现联系，从而使得数据保持一致。开发的数据清理工具大致可分为三类。
本项目主要以上述方法为参照对数据进行处理。
数据预处理方法：主要使用numpy、pandas、sklearn第三方库进行数据分析，使用matplotlib进行图表分析。
（1）	特征删除
（2）	修改与时间相关的特征
（3）	填充缺失值
（4）	将某些数值型特征转换为非数值型特征
（5）	使用sklearn中的PowerTransformer使其更具高斯分布
（6）	对非数值特征中的某些特征进行融合
（7）	对非数值特征进行编码
在数据预处理中，我们根据之前数据分析得出数据集的规模、影响房价的因素数量以及房价的大致分布。


    
