# JLU-CCST-DMWIS

## NLP_相关数据集总结

-----
# Content 

* NLP_相关数据集总结
    * [命名实体识别](#命名实体识别)
        * [1. CoNLL-2003 | 地址](#1conll-2003--地址)
        * [2. 中文CLUENER-2020 | 地址](#2中文cluener-2020--地址)
    * [关系抽取](#关系抽取)
        * [1. 汉语文学数据集 | 地址](#1汉语文学数据集--地址)
        * [2. SemEval-2010 (Json格式) | 地址](#2semeval-2010-json格式---地址)
        * [3. Wiki80 | 地址](#3wiki80---地址)
        * [4. NYT10 For Distant Supervision | 地址](#4nyt10-for-distant-supervision---地址)
        * [5. FewRel | 地址](#5fewrel--地址)
    * [情感分析](#情感分析)
        * [1. SentiHood | 地址](#1sentihood---地址)
        * [2. SemEval-2014 Task4 | 地址](#2semeval-2014-task4--地址)
        * [3. SemEval-2016 Task5 (English) | 地址](#3semeval-2016-task5-english--地址)
    * [CLUE BenchMark](#clue-benchmark)
        * [0. CLUECorpus-2020：语言建模、预训练或生成型任务]
        * [1. AFQMC 蚂蚁金融语义相似度 Ant Financial Question Matching Corpus]
        * [2. TNEWS' 今日头条中文新闻（短文本）分类 Short Text Classificaiton for News]
        * [3. IFLYTEK' 长文本分类 Long Text classification]
        * [4. CMNLI 语言推理任务 Chinese Multi-Genre NLI]
        * [5. CLUEWSC2020: WSC Winograd模式挑战中文版，新版2020-03-25发布]
        * [6. CSL 论文关键词识别 Keyword Recognition]
        * [7. CMRC2018 简体中文阅读理解任务 Reading Comprehension for Simplified Chinese]
        * [8. DRCD 繁体阅读理解任务 Reading Comprehension for Traditional Chinese]
        * [9. ChID 成语阅读理解填空 Chinese IDiom Dataset for Cloze Test]
        * [10. C3中文多选阅读理解 Multiple-Choice Chinese Machine Reading Comprehension]
    * [中文医疗NLP数据集](#中文医疗nlp数据集)
        * [1. Yidu-S4K：医渡云结构化4K数据集]
        * [2. 瑞金医院糖尿病数据集]
        * [3. Yidu-N7K：医渡云标准化7K数据集]
        * [4. 中文医学问答数据集]
        * [5. 平安医疗科技疾病问答迁移学习比赛]
        * [6. 天池新冠肺炎问句匹配比赛]
        * [7. 中文医患问答对话数据]
        * [8. 中文医学问答数据]
        * [9. CHIP2020各项评测已开放]
        * [10. 医学数据挖掘与算法评测大赛]
        * [11. 中文医疗对话数据集]
        * [12. 阿里发布的中文医疗标准数据集合]
    * [中文医学知识图谱](#中文医学知识图谱)
        * [CMeKG]
    * [英文医疗NLP数据集](#英文医疗nlp数据集)
        * [PubMedQA: A Dataset for Biomedical Research Question Answering]
        * [COMETA: A Corpus for Medical Entity Linking in the Social Media]
    * [参考链接](参考链接)
-----

### 命名实体识别

#### 1.CoNLL-2003 | [地址](https://www.clips.uantwerpen.be/conll2003/ner/)

* **年份**：2003年
* **任务**：命名实体识别
* **示例**：
```
U.N.         NNP  I-NP  I-ORG 
official     NN   I-NP  O 
Ekeus        NNP  I-NP  I-PER 
heads        VBZ  I-VP  O 
for          IN   I-PP  O 
Baghdad      NNP  I-NP  I-LOC 
.            .    O     O 
```

#### 2.中文CLUENER-2020 | [地址]()

* **年份**：2020年
* **任务**：中文细粒度NER
* **统计数据**：
    * 10个类别
    * 数据分为两列：text & label
    * train集：10748
    * val集：1343
* **例子**：
```
{
    "text": "浙商银行企业信贷部叶老桂博士则从另一个角度对五道门槛进行了解读。叶老桂认为，对目前国内商业银行而言，", 
    "label": {
        "name": {"叶老桂": [[9, 11]]}, 
        "company": {"浙商银行": [[0, 3]]}
        }
}
```

-----

### 关系抽取

#### 1.汉语文学数据集 | [地址](https://github.com/lancopku/Chinese-Literature-NER-RE-Dataset)

* **年份**：2017年
* **任务**：
    * Named Entity Recognition (NER) 
    * Relation Extraction (RE)
* **基本统计数据**：7类实体和9类关系，还有一些针对汉语文学的附加类别。
* **基本使用说明**：
* **数据存储结构说明**：
    * 实体(Entity)：每个实体都由带有多个属性的T标签标识。
        * Type：实体类别。
        * Begin Index：实体的起始索引,从0开始
        * End Index：实体的结束索引,从0开始
        
    * 关系(Relation):每个关系由R标签标识。
        * ID：标识文档中关系的唯一编号，从0开始
        * Arg1和Arg2：与某个关系关联的两个实体。
        * Type：关系类别。

示例：
```
记 得   上      世     纪     5      0      年      代     中     期   
O  O B_Time I_Time I_Time I_Time I_Time I_Time I_Time I_Time I_Time
```

#### 2.SemEval-2010 (Json格式)  | [地址](https://github.com/thunlp/OpenNRE/tree/master/benchmark)

* **年份**：2010年
* **任务**：关系抽取

* **基本统计数据**：包含 9+1（Other）个关系。

* **基本使用说明**：
    * **semeval_rel2id.json**: 各类关系及其索引对照表，同一种关系由于两个实体e1、e2的前后位置不同构成不同关系（例如“Product-Producer(e2,e1)&Product-Producer(e1,e2)），所以算上关系”Other”一共是19种关系.

    * **semeval_train.txt & semeval_val.txt**: 原始数据集一共有8000个train样本，这里将原始的train分割成了train（6507个）以及val(1493个)，且同一关系的样本分布在一起。
    * **semeval_test.txt**:与train以及val中的样本格式一致，包含2717个样本
* **数据存储结构说明**：数据以json形式存储
    * "token":句子
    * "h":头实体及位置
    * "t":尾实体及位置
    * "relation":两个实体的关系，

样本：
```
{
    "token": ["trees", "grow", "seeds", "."],
    "h": 
    {
        "name": "trees", 
        "pos": [0, 1]
    },
    "t": 
    {
        "name": "seeds", 
        "pos": [2, 3]
    }, 
    "relation": "Product-Producer(e2,e1)"
}
```

#### 3.Wiki80  | [地址](https://github.com/thunlp/OpenNRE/tree/master/benchmark)

* Wiki80是由清华发布的数据集FewRel上提取的
* **年份**：2019年
* **任务**：关系抽取

* **基本统计数据**：80种关系，各关系700样本，合计56000个样本
* **基本使用说明**：数据集不包含测试集，样本格式同SemEval-2010几乎一致
* **数据存储结构说明**：

```
{
    "token": ["Vahitahi", "has", "a", "territorial", "airport", "."], 
    "h": 
    {
        "name": "territorial airport", 
        "id": "Q16897548", 
        "pos": [3, 5]
    }, 
    "t": 
    {
        "name": "vahitahi", 
        "id": "Q1811472", 
        "pos": [0, 1]
    }, 
    "relation": "place served by transport hub"
}
```

#### 4.NYT10 For Distant Supervision  | [地址](https://github.com/thunlp/OpenNRE/tree/master/benchmark)

* **年份**：2019年
* **任务**：远程监督关系抽取

* **基本统计数据**：一共包含52+1（NA）个关系。
    * Nyt10_rel2id.json : 包含53个关系及其各自对应的索引
    * Nyt10_train.txt : 包含466876个样本
    * Nyt10_val.txt : 包含55167个样本
    * Nyt10_test.txt : 包含172448个样本

* **基本使用说明**：
* **数据存储结构说明**：
```
{
    "text": "Hundreds of bridges were added to the statewide inventory after an earthquake in 1994 in Northridge , a suburb of Los Angeles .", 
    "relation": "/location/neighborhood/neighborhood_of",
    "h":
    {
        "id":"/guid/9202a8c04000641f800000000008fe6d", 
        "name": "Northridge", 
        "pos": [89, 99]
    }, 
    "t": 
    {
        "id": "/guid/9202a8c04000641f80000000060b2879", 
        "name": "Los Angeles", 
        "pos": [114, 125]
    }
}
```

#### 5.FewRel | [地址](http://www.zhuhao.me/fewrel/)
* **年份**：2018年
* **任务**：Few-shot 关系抽取
* **基本统计数据**：100种关系，每个关系700实例，共计70000训练实例
    * 64个关系train
    * 16个关系val
    * 20个关系test
* **数据存储结构说明**：

```
{
    "tokens": 
        ["In", "June", "1987", ",", "the", "Missouri", "Highway", "and", "Transportation", "Department", "approved", "design", "location", "of", "a", "new", "four", "-", "lane", "Mississippi", "River", "bridge", "to", "replace", "the", "deteriorating", "Cape", "Girardeau", "Bridge", "."], 
    "h": ["cape girardeau bridge", "Q5034838", [[26, 27, 28]]], 
    "t": ["mississippi river", "Q1497", [[19, 20]]]
}
```

-----
### 情感分析

#### 1.SentiHood  | [地址]()

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

#### 2.SemEval-2014 Task4 | [地址]()

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

#### 3.SemEval-2016 Task5 (English) | [地址]()

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

-----
### CLUE BenchMark

#### 0.CLUECorpus-2020：语言建模、预训练或生成型任务

> 可用于语言建模、预训练或生成型任务等，数据量超过14G，近4000个定义良好的txt文件、50亿个字。主要来自于[nlp_chinese_corpus项目](https://github.com/brightmart/nlp_chinese_corpus)

> 当前语料库按照【预训练格式】处理，内含有多个文件夹；每个文件夹有许多不超过4M大小的小文件，文件格式符合预训练格式：每句话一行，文档间空行隔开。

包含如下子语料库（总共14G语料）：

* 1、<a href="https://pan.baidu.com/s/195M7H5w3N8shYlqCjVL0_Q">新闻语料 news2016zh_corpus</a>: 8G语料，分成两个上下两部分，总共有2000个小文件。  密码:mzlk

* 2、<a href="https://pan.baidu.com/s/1Vk2PihMiZNmWvA2agPb1iA">社区互动-语料 webText2019zh_corpus</a>：3G语料，包含3G文本，总共有900多个小文件。 密码:qvlq

* 3、<a href="https://pan.baidu.com/s/1XrM-x70PY4JEb0xCoB_mUw">维基百科-语料 wiki2019zh_corpus</a>：1.1G左右文本，包含300左右小文件。  密码:rja4

* 4、<a href="https://pan.baidu.com/s/16cPwCcPduMNGdRSuILhEuQ">评论数据-语料 comments2019zh_corpus</a>：2.3G左右文本，共784个小文件，包括点评评论547个、亚马逊评论227个，合并<a href="https://github.com/InsaneLife/ChineseNLPCorpus">ChineseNLPCorpus</a>的多个评论数据，清洗、格式转换、拆分成小文件。  密码:5kwk

>这些语料，你可以通过上面这两个项目，清洗数据并做格式转换获得；
>你也可以通过邮件申请（chineseGLUE#163.com）获得单个项目的语料，告知单位或学校、姓名、语料用途；
>如需获得ChineseGLUE项目下的所有语料，需成为ChineseGLUE组织成员，并完成一个（小）任务。

#### 1. AFQMC 蚂蚁金融语义相似度 Ant Financial  Question Matching Corpus
```
     数据量：训练集（34334）验证集（4316）测试集（3861）
     例子：
     {"sentence1": "双十一花呗提额在哪", "sentence2": "里可以提花呗额度", "label": "0"}
     每一条数据有三个属性，从前往后分别是 句子1，句子2，句子相似度标签。其中label标签，1 表示sentence1和sentence2的含义类似，0表示两个句子的含义不同。
```
  <a href="https://storage.googleapis.com/cluebenchmark/tasks/afqmc_public.zip" > AFQMC'数据集下载</a>

#### 2.TNEWS' 今日头条中文新闻（短文本）分类 Short Text Classificaiton for News
该数据集来自今日头条的新闻版块，共提取了15个类别的新闻，包括旅游，教育，金融，军事等。
```
     数据量：训练集(53,360)，验证集(10,000)，测试集(10,000)
     例子：
     {"label": "102", "label_des": "news_entertainment", "sentence": "江疏影甜甜圈自拍，迷之角度竟这么好看，美吸引一切事物"}
     每一条数据有三个属性，从前往后分别是 分类ID，分类名称，新闻字符串（仅含标题）。
```
   <a href="https://storage.googleapis.com/cluebenchmark/tasks/tnews_public.zip" > TNEWS'数据集下载</a>

#### 3.IFLYTEK' 长文本分类 Long Text classification
该数据集共有1.7万多条关于app应用描述的长文本标注数据，包含和日常生活相关的各类应用主题，共119个类别："打车":0,"地图导航":1,"免费WIFI":2,"租车":3,….,"女性":115,"经营":116,"收款":117,"其他":118(分别用0-118表示)。
```
    数据量：训练集(12,133)，验证集(2,599)，测试集(2,600)
    例子：
    {"label": "110", "label_des": "社区超市", "sentence": "朴朴快送超市创立于2016年，专注于打造移动端30分钟即时配送一站式购物平台，商品品类包含水果、蔬菜、肉禽蛋奶、海鲜水产、粮油调味、酒水饮料、休闲食品、日用品、外卖等。朴朴公司希望能以全新的商业模式，更高效快捷的仓储配送模式，致力于成为更快、更好、更多、更省的在线零售平台，带给消费者更好的消费体验，同时推动中国食品安全进程，成为一家让社会尊敬的互联网公司。,朴朴一下，又好又快,1.配送时间提示更加清晰友好2.保障用户隐私的一些优化3.其他提高使用体验的调整4.修复了一些已知bug"}
    每一条数据有三个属性，从前往后分别是 类别ID，类别名称，文本内容。
```
   <a href="https://storage.googleapis.com/cluebenchmark/tasks/iflytek_public.zip" > IFLYTEK'数据集下载</a>

#### 4.CMNLI 语言推理任务 Chinese Multi-Genre NLI

CMNLI数据由两部分组成：XNLI和MNLI。数据来自于fiction，telephone，travel，government，slate等，对原始MNLI数据和XNLI数据进行了中英文转化，保留原始训练集，合并XNLI中的dev和MNLI中的matched作为CMNLI的dev，合并XNLI中的test和MNLI中的mismatched作为CMNLI的test，并打乱顺序。该数据集可用于判断给定的两个句子之间属于蕴涵、中立、矛盾关系。

```
    数据量：train(391,782)，dev(12,426)，test(13,880)
    例子：
    {"sentence1": "新的权利已经足够好了", "sentence2": "每个人都很喜欢最新的福利", "label": "neutral"}
    每一条数据有三个属性，从前往后分别是 句子1，句子2，蕴含关系标签。其中label标签有三种：neutral，entailment，contradiction。
```
<a href="https://storage.googleapis.com/cluebenchmark/tasks/cmnli_public.zip" > CMNLI数据集下载</a>



#### 5. CLUEWSC2020: WSC Winograd模式挑战中文版，新版2020-03-25发布  

Winograd Scheme Challenge（WSC）是一类代词消歧的任务。新版与原CLUE项目WSC内容不同

即判断句子中的代词指代的是哪个名词。题目以真假判别的方式出现，如：

句子：这时候放在床上枕头旁边的手机响了，我感到奇怪，因为欠费已被停机两个月，现在它突然响了。需要判断“它”指代的是“床”、“枕头”，还是“手机”？

数据来源：数据有CLUE benchmark提供，从中国现当代作家文学作品中抽取，再经语言专家人工挑选、标注。

数据形式：

     {"target": 
         {"span2_index": 37, 
         "span1_index": 5, 
         "span1_text": "床", 
         "span2_text": "它"}, 
     "idx": 261, 
     "label": "false", 
     "text": "这时候放在床上枕头旁边的手机响了，我感到奇怪，因为欠费已被停机两个月，现在它突然响了。"}
     "true"表示代词确实是指代span1_text中的名词的，"false"代表不是。

数据集大小：
- 训练集：1244
- 开发集：304

  <a href='https://storage.googleapis.com/cluebenchmark/tasks/cluewsc2020_public.zip'>CLUEWSC2020数据集下载</a>


#### 6. CSL 论文关键词识别 Keyword Recognition
[中文科技文献数据集(CSL)](https://github.com/P01son6415/chinese-scientific-literature-dataset)取自中文论文摘要及其关键词，论文选自部分中文社会科学和自然科学核心期刊。
使用tf-idf生成伪造关键词与论文真实关键词混合，构造摘要-关键词对，任务目标是根据摘要判断关键词是否全部为真实关键词。
```
    数据量：训练集(20,000)，验证集(3,000)，测试集(3,000)
    例子： 
    {"id": 1, "abst": "为解决传统均匀FFT波束形成算法引起的3维声呐成像分辨率降低的问题,该文提出分区域FFT波束形成算法.远场条件下,以保证成像分辨率为约束条件,以划分数量最少为目标,采用遗传算法作为优化手段将成像区域划分为多个区域.在每个区域内选取一个波束方向,获得每一个接收阵元收到该方向回波时的解调输出,以此为原始数据在该区域内进行传统均匀FFT波束形成.对FFT计算过程进行优化,降低新算法的计算量,使其满足3维成像声呐实时性的要求.仿真与实验结果表明,采用分区域FFT波束形成算法的成像分辨率较传统均匀FFT波束形成算法有显著提高,且满足实时性要求.", "keyword": ["水声学", "FFT", "波束形成", "3维成像声呐"], "label": "1"}
    每一条数据有四个属性，从前往后分别是 数据ID，论文摘要，关键词，真假标签。
    
```
   <a href="https://storage.googleapis.com/cluebenchmark/tasks/csl_public.zip" > CSL数据集下载</a>

#### 7.CMRC2018 简体中文阅读理解任务 Reading Comprehension for Simplified Chinese
https://hfl-rc.github.io/cmrc2018/
```
数据量：训练集(短文数2,403，问题数10,142)，试验集(短文数256，问题数1,002)，开发集(短文数848，问题数3,219)  
例子：
{
  "version": "1.0",
  "data": [
    {
        "title": "傻钱策略",
        "context_id": "TRIAL_0",
        "context_text": "工商协进会报告，12月消费者信心上升到78.1，明显高于11月的72。另据《华尔街日报》报道，2013年是1995年以来美国股市表现最好的一年。这一年里，投资美国股市的明智做法是追着“傻钱”跑。所谓的“傻钱”策略，其实就是买入并持有美国股票这样的普通组合。这个策略要比对冲基金和其它专业投资者使用的更为复杂的投资方法效果好得多。",
        "qas":[
                {
                "query_id": "TRIAL_0_QUERY_0",
                "query_text": "什么是傻钱策略？",
                "answers": [
                     "所谓的“傻钱”策略，其实就是买入并持有美国股票这样的普通组合",
                     "其实就是买入并持有美国股票这样的普通组合",
                     "买入并持有美国股票这样的普通组合"
                    ]
                },
                {
                "query_id": "TRIAL_0_QUERY_1",
                "query_text": "12月的消费者信心指数是多少？",
                "answers": [
                    "78.1",
                    "78.1",
                    "78.1"
                    ]
                },
                {
                "query_id": "TRIAL_0_QUERY_2",
                "query_text": "消费者信心指数由什么机构发布？",
                "answers": [
                    "工商协进会",
                    "工商协进会",
                    "工商协进会"
                    ]
                }
            ]
        }
    ]
}
```

   <a href="https://storage.googleapis.com/cluebenchmark/tasks/cmrc2018_public.zip" > CMRC2018数据集下载</a>


#### 8.DRCD 繁体阅读理解任务 Reading Comprehension for Traditional Chinese
台達閱讀理解資料集 Delta Reading Comprehension Dataset (DRCD)(https://github.com/DRCKnowledgeTeam/DRCD) 屬於通用領域繁體中文機器閱讀理解資料集。 本資料集期望成為適用於遷移學習之標準中文閱讀理解資料集。  
```
数据量：训练集(8,016个段落，26,936个问题)，验证集(1,000个段落，3,524个问题)，测试集(1,000个段落，3,493个问题)  
例子：
{
  "version": "1.3",
  "data": [
    {
      "title": "基督新教",
      "id": "2128",
      "paragraphs": [
        {
          "context": "基督新教與天主教均繼承普世教會歷史上許多傳統教義，如三位一體、聖經作為上帝的啟示、原罪、認罪、最後審判等等，但有別於天主教和東正教，新教在行政上沒有單一組織架構或領導，而且在教義上強調因信稱義、信徒皆祭司， 以聖經作為最高權威，亦因此否定以教宗為首的聖統制、拒絕天主教教條中關於聖傳與聖經具同等地位的教導。新教各宗派間教義不盡相同，但一致認同五個唯獨：唯獨恩典：人的靈魂得拯救唯獨是神的恩典，是上帝送給人的禮物。唯獨信心：人唯獨藉信心接受神的赦罪、拯救。唯獨基督：作為人類的代罪羔羊，耶穌基督是人與上帝之間唯一的調解者。唯獨聖經：唯有聖經是信仰的終極權威。唯獨上帝的榮耀：唯獨上帝配得讚美、榮耀",
          "id": "2128-2",
          "qas": [
            {
              "id": "2128-2-1",
              "question": "新教在教義上強調信徒皆祭司以及什麼樣的理念?",
              "answers": [
                {
                  "id": "1",
                  "text": "因信稱義",
                  "answer_start": 92
                }
              ]
            },
            {
              "id": "2128-2-2",
              "question": "哪本經典為新教的最高權威?",
              "answers": [
                {
                  "id": "1",
                  "text": "聖經",
                  "answer_start": 105
                }
              ]
            }
          ]
        }
      ]
    }
  ]
}
```
数据格式和squad相同，如果使用简体中文模型进行评测的时候可以将其繁转简(本项目已提供)
   <a href="https://storage.googleapis.com/cluebenchmark/tasks/drcd_public.zip" > DRCD2018数据集下载</a>

#### 9.ChID 成语阅读理解填空 Chinese IDiom Dataset for Cloze Test
https://arxiv.org/abs/1906.01265  
成语完形填空，文中多处成语被mask，候选项中包含了近义的成语。
```
    数据量：训练集(84,709)，验证集(3,218)，测试集(3,231)
    例子：
    {
      "content": [
        # 文段0
        "……在热火22年的历史中，他们已经100次让对手得分在80以下，他们在这100次中都取得了胜利，今天他们希望能#idiom000378#再进一步。", 
        # 文段1
        "在轻舟发展过程之中，是和业内众多企业那样走相似的发展模式，去#idiom000379#？还是迎难而上，另走一条与众不同之路。诚然，#idiom000380#远比随大流更辛苦，更磨难，更充满风险。但是有一条道理却是显而易见的：那就是水往低处流，随波逐流，永远都只会越走越低。只有创新，只有发展科技，才能强大自己。", 
        # 文段2
        "最近十年间，虚拟货币的发展可谓#idiom000381#。美国著名经济学家林顿·拉鲁什曾预言：到2050年，基于网络的虚拟货币将在某种程度上得到官方承认，成为能够流通的货币。现在看来，这一断言似乎还嫌过于保守……", 
        # 文段3
        "“平时很少能看到这么多老照片，这次图片展把新旧照片对比展示，令人印象深刻。”现场一位参观者对笔者表示，大多数生活在北京的人都能感受到这个城市#idiom000382#的变化，但很少有人能具体说出这些变化，这次的图片展按照区域发展划分，展示了丰富的信息，让人形象感受到了60年来北京的变化和发展。", 
        # 文段4
        "从今天大盘的走势看，市场的热点在反复的炒作之中，概念股的炒作#idiom000383#，权重股走势较为稳健，大盘今日早盘的震荡可以看作是多头关前的蓄势行为。对于后市，大盘今日蓄势震荡后，明日将会在权重和题材股的带领下亮剑冲关。再创反弹新高无悬念。", 
        # 文段5
        "……其中，更有某纸媒借尤小刚之口指出“根据广电总局的这项要求，2009年的荧屏将很难出现#idiom000384#的情况，很多已经制作好的非主旋律题材电视剧想在卫视的黄金时段播出，只能等到2010年了……"],
      "candidates": [
        "百尺竿头", 
        "随波逐流", 
        "方兴未艾", 
        "身体力行", 
        "一日千里", 
        "三十而立", 
        "逆水行舟", 
        "日新月异", 
        "百花齐放", 
        "沧海一粟"
      ]
    }
```

   <a href="https://storage.googleapis.com/cluebenchmark/tasks/chid_public.zip" > CHID数据集下载</a>
   
#### 10.C<sup>3</sup> 中文多选阅读理解 Multiple-Choice Chinese Machine Reading Comprehension  
https://arxiv.org/abs/1904.09679  
中文多选阅读理解数据集，包含对话和长文等混合类型数据集。训练和验证集中的d,m分别代表对话、多种文本类型混合。  
```
    数据量：训练集(11,869)，验证集(3,816)，测试集(3,892)
    例子：
    [
      [
        "男：你今天晚上有时间吗?我们一起去看电影吧?",
        "女：你喜欢恐怖片和爱情片，但是我喜欢喜剧片，科幻片一般。所以……"
      ],
      [
       {
        "question": "女的最喜欢哪种电影?",
        "choice": [
         "恐怖片",
         "爱情片",
         "喜剧片",
         "科幻片"
        ],
        "answer": "喜剧片"
       }
      ],
    "25-35"
    ],
    [
      [
       "男：足球比赛是明天上午八点开始吧?",
       "女：因为天气不好，比赛改到后天下午三点了。"
      ],
      [
       {
        "question": "根据对话，可以知道什么?",
        "choice": [
         "今天天气不好",
         "比赛时间变了",
         "校长忘了时间"
        ],
        "answer": "比赛时间变了"
       }
      ],
    "31-109"
    ]
```
   <a href="https://storage.googleapis.com/cluebenchmark/tasks/c3_public.zip" > C3数据集下载</a>

-----
### 中文医疗NLP数据集

#### 1. Yidu-S4K：医渡云结构化4K数据集

数据集描述：

> Yidu-S4K 数据集源自CCKS 2019 评测任务一，即“面向中文电子病历的命名实体识别”的数据集，包括两个子任务：
> 1）医疗命名实体识别：由于国内没有公开可获得的面向中文电子病历医疗实体识别数据集，本年度保留了医疗命名实体识别任务，对2017年度数据集做了修订，并随任务一同发布。本子任务的数据集包括训练集和测试集。
> 2）医疗实体及属性抽取（跨院迁移）：在医疗实体识别的基础上，对预定义实体属性进行抽取。本任务为迁移学习任务，即在只提供目标场景少量标注数据的情况下，通过其他场景的标注数据及非标注数据进行目标场景的识别任务。本子任务的数据集包括训练集（非目标场景和目标场景的标注数据、各个场景的非标注数据）和测试集（目标场景的标注数据

[数据集地址](http://openkg.cn/dataset/yidu-s4k)

度盘下载地址：https://pan.baidu.com/s/1QqYtqDwhc_S51F3SYMChBQ

提取码：flql

#### 2.瑞金医院糖尿病数据集

数据集描述：

>数据集来自天池大赛。此数据集旨在通过糖尿病相关的教科书、研究论文来做糖尿病文献挖掘并构建糖尿病知识图谱。参赛选手需要设计高准确率，高效的算法来挑战这一科学难题。第一赛季课题为“基于糖尿病临床指南和研究论文的实体标注构建”，第二赛季课题为“基于糖尿病临床指南和研究论文的实体间关系构建”。

官方提供的数据只包含训练集，真正用于最终排名的测试集没有给出。

[数据集地址](https://tianchi.aliyun.com/competition/entrance/231687/information)

度盘下载地址：https://pan.baidu.com/s/1CWKblBNBqR-vs2h0xiXSdQ

提取码：0c54

#### 3.Yidu-N7K：医渡云标准化7K数据集

数据集描述：

>Yidu-N4K 数据集源自CHIP 2019 评测任务一，即“临床术语标准化任务”的数据集。
>临床术语标准化任务是医学统计中不可或缺的一项任务。临床上，关于同一种诊断、手术、药品、检查、化验、症状等往往会有成百上千种不同的写法。标准化（归一）要解决的问题就是为临床上各种不同说法找到对应的标准说法。有了术语标准化的基础，研究人员才可对电子病历进行后续的统计分析。本质上，临床术语标准化任务也是语义相似度匹配任务的一种。但是由于原词表述方式过于多样，单一的匹配模型很难获得很好的效果。

[数据集地址](http://openkg.cn/dataset/yidu-n7k)

#### 4.中文医学问答数据集

数据集描述：

>中文医药方面的问答数据集，超过10万条。

数据说明:

>questions.csv：所有的问题及其内容。answers.csv ：所有问题的答案。
>train_candidates.txt， dev_candidates.txt， test_candidates.txt ：将上述两个文件进行了拆分。

[数据集地址](https://www.kesci.com/home/dataset/5d313070cf76a60036e4b023/document)

[数据集github地址](https://github.com/zhangsheng93/cMedQA2)

#### 5.平安医疗科技疾病问答迁移学习比赛

数据集描述：

>本次比赛是chip2019中的评测任务二，由平安医疗科技主办。chip2019会议详情见链接：http://cips-chip.org.cn/evaluation
>迁移学习是自然语言处理中的重要一环，其主要目的是通过从已学习的相关任务中转移知识来改进新任务的学习效果，从而提高模型的泛化能力。
>本次评测任务的主要目标是针对中文的疾病问答数据，进行病种间的迁移学习。具体而言，给定来自5个不同病种的问句对，要求判定两个句子语义是否相同或者相近。所有语料来自互联网上患者真实的问题，并经过了筛选和人工的意图匹配标注。

[数据集地址(需注册)](https://www.biendata.com/competition/chip2019/)

#### 6.天池新冠肺炎问句匹配比赛

数据集描述：

>本次大赛数据包括：脱敏之后的医疗问题数据对和标注数据。医疗问题涉及“肺炎”、“支原体肺炎”、“支气管炎”、“上呼吸道感染”、“肺结核”、“哮喘”、“胸膜炎”、“肺气肿”、“感冒”、“咳血”等10个病种。
>数据共包含train.csv、dev.csv、test.csv三个文件，其中给参赛选手的文件包含训练集train.csv和验证集dev.csv，测试集test.csv 对参赛选手不可见。
>每一条数据由 Category，Query1，Query2，Label构成，分别表示问题类别、问句1、问句2、标签。Label表示问句之间的语义是否相同，若相同，标为1，若不相同，标为0。其中，训练集Label已知，验证集和测试集Label未知。
>示例
>类别：肺炎
>问句1：肺部发炎是什么原因引起的？
>问句2：肺部发炎是什么引起的
>标签:1
>类别：肺炎
>问句1：肺部发炎是什么原因引起的？
>问句2：肺部炎症有什么症状
>标签:0

[数据集地址(需注册)](https://tianchi.aliyun.com/competition/entrance/231776/information)

[线上第四名解决方案及代码](https://github.com/Makaixin/similar-sentence-pairs-in-epidemic)

[线上第一名解决方案及代码](https://github.com/zzy99/epidemic-sentence-pair)

#### 7.中文医患问答对话数据

数据说明: 
> 来自某在线求医产品的中文医患对话数据。

> 原始描述:The MedDialog dataset contains conversations (in Chinese) between doctors and patients. It has 1.1 million dialogues and 4 million utterances. The data is continuously growing and more dialogues will be added. The raw dialogues are from haodf.com. All copyrights of the data belong to haodf.com.

[项目地址](https://github.com/UCSD-AI4H/Medical-Dialogue-System)

度盘下载地址: https://pan.baidu.com/s/1ZwzNgvAAMQk4klerTspsoA

提取码: lbo4

#### 8.中文医学问答数据

数据说明: 
> 包含六个科室的医学问答数据，来源不明。

[项目地址](https://github.com/Toyhom/Chinese-medical-dialogue-data)

#### 9.CHIP2020各项评测已开放

> CHIP2020各项评测已开放，包括医学领域的实体识别，关系抽取，文本生成，术语标准化等任务，可以前往官网查阅。

[CHIP2020官方网址](http://cips-chip.org.cn/2020/)

#### 10.医学数据挖掘与算法评测大赛

> 新鲜出炉，详情参看paperweekly公众号。[文章链接](https://mp.weixin.qq.com/s/3hiJy8m0VohYfEH5ISta5w)

#### 11.中文医疗对话数据集

> github开源数据

[项目地址](https://github.com/Toyhom/Chinese-medical-dialogue-data)

#### 12.阿里发布的中文医疗标准数据集合

> 阿里团队发布的中文医疗NLP相关评测数据集合Chinese_BLUE,发表于WSDM2020。另外:项目中说此项目非阿里的官方产品，所以仅供参考。

[项目地址](https://github.com/alibaba-research/ChineseBLUE)

[论文地址](https://arxiv.org/pdf/2008.10813.pdf)

-----
### 中文医学知识图谱

#### CMeKG

[地址](http://cmekg.pcl.ac.cn/)

> 简介：CMeKG（Chinese Medical Knowledge Graph）是利用自然语言处理与文本挖掘技术，基于大规模医学文本数据，以人机结合的方式研发的中文医学知识图谱。CMeKG的构建参考了ICD、ATC、SNOMED、MeSH等权威的国际医学标准以及规模庞大、多源异构的临床指南、行业标准、诊疗规范与医学百科等医学文本信息。CMeKG 1.0包括：6310种疾病、19853种药物（西药、中成药、中草药）、1237种诊疗技术及设备的结构化知识描述，涵盖疾病的临床症状、发病部位、药物治疗、手术治疗、鉴别诊断、影像学检查、高危因素、传播途径、多发群体、就诊科室等以及药物的成分、适应症、用法用量、有效期、禁忌证等30余种常见关系类型，CMeKG描述的概念关系实例及属性三元组达100余万。

-----
### 英文医疗NLP数据集

#### PubMedQA: A Dataset for Biomedical Research Question Answering

> 基于Pubmed提取的医学问答数据集。PubMedQA has 1k expert-annotated, 61.2k unlabeled and 211.3k artificially gen- erated QA instances. 

[论文地址](https://arxiv.org/abs/1909.06146)

#### COMETA: A Corpus for Medical Entity Linking in the Social Media

> 社交媒体中的医疗实体链接数据。发表于EMNLP2020。

> 数据获取方式:
COMETA is available by contacting the last author via e-mail or following the instructions on https://www.siphs.org/. We release the
pre-trained embeddings and the code to replicate our baselines online at https://github.com/ cambridgeltl/cometa.

[论文地址](https://arxiv.org/pdf/2010.03295.pdf)

-----

### 参考链接

* [医疗NLP领域（主要关注中文） 评测数据集 与 论文等相关资源。](https://github.com/lrs1353281004/Chinese_medical_NLP)
* [CLUE baseline & dataset](https://github.com/CLUEbenchmark/CLUE)
* https://github.com/brightmart/nlp_chinese_corpus
