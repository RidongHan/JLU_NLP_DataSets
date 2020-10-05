# JLU-CCST-DMWIS

## NLP_信息抽取&情感分析相关数据集总结

-----
### 中文医疗NLP领域

[医疗NLP领域（主要关注中文） 评测数据集 与 论文等相关资源。](https://github.com/lrs1353281004/Chinese_medical_NLP)

-----

### 关系抽取

-----
### 情感分析

#### 1.SentiHood

* **年份**：2016年
* **任务**：the task of targeted aspect-based sentiment analysis（基于特定目标和方面的情感分析任务）

* **基本统计数据**：统计了来自Yahoo!问答平台的，与伦敦城各街道有关的回答，共5215个句子，其中3862个句子包含一个目标，1353个句子包含多个目标。

* **基本使用说明**：该数据集标注了每个句子中的目标（target）、方面（aspect）、极性（polarity）三元组，一个句子中可能有一个或多个这样的三元组，也可能没有。其中极性标签有三种：Positive、Negative、None。None表示当前句子中指定的目标与它的方面没有观点存在，也就是没有带情感的评价。研究者利用该数据集，可以判断模型对特定目标及其方面进行情感极性分类的性能。
* **数据存储结构说明**：数据以json形式存储在文件中，训练集、开发集与测试集也已经预先划分完毕，每一单元数据保存的信息有：opinion（目标-方面-极性三元组）、id、与text（句子文本），下面是一个示例：

```
{
    "opinions": [
        {
            "sentiment": "Positive",
            "aspect": "shopping",
            "target_entity": "LOCATION1"
        }
    ],
    "id": 302,
    "text": " LOCATION1 is just a normal area that happens to have an alternative market"
}
```

#### 2.SemEval-2014 Task4

* **年份**：2014年
* **任务**：Aspect Based Sentiment Analysis（ABSA）的四个子任务
    * Aspect term extraction（方面术语抽取）
    * Aspect term polarity（方面术语极性判断）
    * Aspect category detection（方面类别检测）
    * Aspect category polarity（方面类别极性判断）
* **统计数据**：提供笔记本电脑和餐厅两个领域的评论数据，包含超过6K个句子和细粒度的方面级人工注释。

* **使用说明**：
    * 笔记本电脑领域评论：由超过3K个英语句子组成，注释了句子的方面术语及其极性，该部分数据仅用于子任务1和2。
    * 餐厅领域评论：由超过3K个英语句子组成，原始数据集包括粗方面类别(子任务3)的注释和整体句子极性，修改后还包含了方面术语(子任务1)、方面术语极性(子任务2)和方面特定类别极性(子任务4)注释。
* **数据存储结构说明**：数据集中的句子是用XML标签标注的，

下面是两个领域数据的存储示例：
1）	笔记本电脑领域评论存储示例

```
<sentence id="353">
          <text>From the build quality to the performance, everything about it has been sub-par from what I would have expected from Apple.</text>
          <aspectTerms>
                    <aspectTerm term="build quality" polarity="negative" from="9" to="22"/>
                    <aspectTerm term="performance" polarity="negative" from="30" to="41"/>
          </aspectTerms>
</sentence>
```
2）	餐厅领域评论存储示例
```
<sentence id="813">
          <text>All the appetizers and salads were fabulous, the steak was mouth watering and the pasta was delicious!!!</text>
          <aspectTerms>
                    <aspectTerm term="appetizers" polarity="positive" from="8" to="18"/>
                    <aspectTerm term="salads" polarity="positive" from="23" to="29"/>
                    <aspectTerm term="steak" polarity="positive" from="49" to="54"/>
                    <aspectTerm term="pasta" polarity="positive" from="82" to="87"/>
          </aspectTerms>
          <aspectCategories>
                    <aspectCategory category="food" polarity="positive"/>
          </aspectCategories>
</sentence>
```

#### 3.SemEval-2016 Task5 (English)

* **年份**：2016年

* **任务**：Aspect Based Sentiment Analysis（ABSA）的两个子任务
    * Sentence-level ABSA，给定关于目标实体(例如一台笔记本电脑、一家餐厅或一家酒店)的评论文档，完成方面类别识别、目标表示抽取、情感极性判断；
    * Text-level ABSA，给定关于目标实体(例如一台笔记本电脑、一家餐厅或一家酒店)的评论，识别所有{方面，极性}元组集合，这些元组总结了每次评论中表达的意见。

* **基本统计数据**：该数据集提供了笔记本电脑和餐厅两个领域的评论数据，包含1000个评论文档（约6K个句子），以及细粒度的人工注释——（评价目标表示，方面类别，极性）。

* **基本使用说明**：
    * 笔记本电脑领域评论：注释元组为（目标实体#方面，极性），该部分数据可用于衡量模型识别方面类别、判断情感极性的性能。
    * 餐厅领域评论：注释元组为（目标实体#方面，目标表示，极性），该部分数据可用于衡量模型识别方面类别、抽取目标表示、判断情感极性的性能。

* **数据存储结构说明**：数据集中的句子是用XML标签标注的，下面是两个领域数据的存储示例：

1）笔记本电脑领域评论存储示例
```
<Review rid="10">
        <sentences>
            <sentence id="10:0">
                <text>the laptop was really good and it goes really fast just the way i thought it would of run.</text>
                <Opinions>
                    <Opinion category="LAPTOP#GENERAL" polarity="positive"/>
                    <Opinion category="LAPTOP#OPERATION_PERFORMANCE" polarity="positive"/>
                </Opinions>
            </sentence>
            <sentence id="10:1">
                <text>i would really recommend to any person out there to get this laptop cause its really worth it.</text>
                <Opinions>
                    <Opinion category="LAPTOP#GENERAL" polarity="positive"/>
                </Opinions>
            </sentence>
            <sentence id="10:2">
                <text>and its really cheap and you wont regret buying it.</text>
                <Opinions>
                    <Opinion category="LAPTOP#PRICE" polarity="positive"/>
                    <Opinion category="LAPTOP#GENERAL" polarity="positive"/>
                </Opinions>
            </sentence>
        </sentences>
</Review>
```
2）	餐厅领域评论存储示例

```
<Review rid="1028246">
        <sentences>
            <sentence id="1028246:0">
                <text>Went on a 3 day oyster binge, with Fish bringing up the closing, and I am so glad this was the place it O trip ended, because it was so great!</text>
                <Opinions>
                    <Opinion target="Fish" category="RESTAURANT#GENERAL" polarity="positive" from="35" to="39"/>
                </Opinions>
            </sentence>
            <sentence id="1028246:1">
                <text>Service was devine, oysters where a sensual as they come, and the price can't be beat!!!</text>
                <Opinions>
                    <Opinion target="Service" category="SERVICE#GENERAL" polarity="positive" from="0" to="7"/>
                    <Opinion target="oysters" category="FOOD#QUALITY" polarity="positive" from="20" to="27"/>
                    <Opinion target="NULL" category="RESTAURANT#PRICES" polarity="positive" from="0" to="0"/>
                </Opinions>
            </sentence>
            <sentence id="1028246:2">
                <text>You can't go wrong here.</text>
                <Opinions>
                    <Opinion target="NULL" category="RESTAURANT#GENERAL" polarity="positive" from="0" to="0"/>
                </Opinions>
            </sentence>
        </sentences>
    </Review>
```
