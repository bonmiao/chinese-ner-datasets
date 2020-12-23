# chinese-ner-datasets
本repo主要记录下中文命名实体识别任务（NER）里面的一些常见的数据集，公开的数据集给出了下载的链接，有些数据集是需要自己去搞定，这里就不做传播。

## 一、公开数据集
常见的一些NLP任务里面的一些数据集及算法的表现都是能够在paperswithcode网站上面看见。下面的连接就是到了ner各种中文数据集上面的sota表现。

[https://www.paperswithcode.com/task/chinese-named-entity-recognition](https://www.paperswithcode.com/task/chinese-named-entity-recognition)

### 1.1 MSRA数据集
MSRA是微软的公开数据集。该数据集的具体信息为：

|数据集名称|数据大小|
|:-: | :-: | 
|训练集|12.7 Mb|
|验证集|1.4 Mb|
|测试集|1.1 Mb|

数据是BIO的格式，抽取PER、LOC、ORG，也就是我们常说的人民、地名和机构名。


 **下载地址**：[http://download.fastnlp.top/dataset/MSRA_NER.zip](http://download.fastnlp.top/dataset/MSRA_NER.zip)
 
### 1.2 人民日报数据集

人民日报语料数据集其实还是挺多的，这里应该是收集得比较全的。

|语料时间|原始语料大小|下载链接|
|:---:|:---:|:---:|
|199801-06|63.52Mb|链接: [ https://pan.baidu.com/s/1GWhIHWWC9lKZALTDqc_ovw](https://pan.baidu.com/s/1GWhIHWWC9lKZALTDqc_ovw)  密码: ec9u|
|200001-12|137.66Mb|链接: [https://pan.baidu.com/s/1tkMLVxJ-p0U4OVbtNL1keQ](https://pan.baidu.com/s/1tkMLVxJ-p0U4OVbtNL1keQ)  密码: d519|
|2014|177.47Mb|链接: [https://pan.baidu.com/s/1OoTogt6zDEeJfimWKnb0zw]( https://pan.baidu.com/s/1OoTogt6zDEeJfimWKnb0zw)  密码: n8c3|


例子
```
京华/ntc 时报/n]/nz 讯/ng （/w 记者/nnt 李秋萌/nr ）/w 昨天/t ，/w 记者/nnt 从/p [朝阳区/ns 政府/nis]/nto 了解到/v ，/w 为/p 缓解/v 百姓/n 买菜/nz 难/a 、/w 买菜/nz 贵/a 问题/n ，/w 将/d 于/p 2014年/t 新增/v [50/m 个/q]/mq 左右/f 菜/n 站/vi ，/w 并/cc 在/p 每个/r 街道/ns 配/v 建/v [2/m 个/q]/mq 公益性/n 蔬菜/n 零售点/n 。/w
```

这里需要去看看人民日报语料进行标注时候的词性。然后可以根据所需要抽取的实体，来编写程序输入到模型里面去训练，得到你想要的抽取实体。

### 1.3 BosonNLP数据集
主要是2000条的新闻数据，可以抽取人名、地名、组织名、公司名、产品名、时间：

|抽取字段|人名|地名|组织名|公司名|产品名|时间|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|标签|person_name|location|org_name|company_name|product_name|time|
|实体数量|5144|4599|2692|2379|4130|4255|


数据比较少，用模型做出来的效果不是非常好，好像80%左右的效果吧。

 **下载地址**：[https://github.com/quincyliang/nlp-public-dataset/tree/master/ner-data/boson](https://github.com/quincyliang/nlp-public-dataset/tree/master/ner-data/boson)

### 1.4 WeiboNER

**Tags**: PER(人名), LOC(地点名), GPE(行政区名), ORG(机构名)   

|Label|Tag|Meaning|
|:-:|:-:|:--|
|PER|PER.NAM|名字（张三）|
||PER.NOM|代称、类别名（穷人）|
|LOC|LOC.NAM|特指名称（紫玉山庄）|
||LOC.NOM|泛称（大峡谷、宾馆）|
|GPE|GPE.NAM|行政区的名称（北京）|
|ORG|ORG.NAM|特定机构名称（通惠医院）|
||ORG.NOM|泛指名称、统称（文艺公司）|

数据量不多，看训练集、验证集和测试集的话，就是1890条句子，具体的实体数量情况看下表：

|数据集名称|句数|字符数|PER.NAM数|PER.NOM数|LOC.NAM数|LOC.NOM数|GPE.NAM数|ORG.NAM数|ORG.NOM数|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|训练集|1350|73778|574|766|56|51|205|183|42|
|验证集|270|14509|90|208|6|6|26|47|5|
|测试集|270|14842|111|170|19|9|47|39|17|

 **下载地址**：[http://download.fastnlp.top/dataset/weibo_NER.zip](http://download.fastnlp.top/dataset/weibo_NER.zip)

### 1.5 Resume NER
 数据的格式不是非常好，要是你们有这个更好的数据集，可以提个pr给我。
 
 **下载地址**：[https://github.com/YiDai-03/Chinese_NLP_Dataset/tree/master/Resume-NER](https://github.com/YiDai-03/Chinese_NLP_Dataset/tree/master/Resume-NER)

### 1.6 SighanNER

也是新闻类型的的数据，里面进行了标注人名、地名、机构名。具体的实体数量如下。

|抽取字段|人名|地名|组织名|
|:---:|:---:|:---:|:---:|
|标签|PER|LOC|ORG|
|个数|19588|39394|21902|


**下载地址**：[https://github.com/yzwww2019/Sighan-2006-NER-dataset](https://github.com/yzwww2019/Sighan-2006-NER-dataset)

### 1.7 OntoNotes

该数据需要自行去申请。具体的操作可以去网上搜索一下如何获取OntoNotes的数据集，基本上在校生都是能够申请到这个数据集的，具体的版本还是去他们的具体网站弄吧。

## 二、竞赛数据集

竞赛相关数据需要小伙伴自己去找一下，这里我就不放任何的数据集下载的链接了。

### 2.1 CCKS-面向电子病历的命名实体识别系列
**竞赛连接**：  
[https://www.biendata.xyz/competition/CCKS2017_2](https://www.biendata.xyz/competition/CCKS2017_2)  
[https://www.biendata.xyz/competition/CCKS2018_1](https://www.biendata.xyz/competition/CCKS2018_1)    
[https://www.biendata.xyz/competition/ccks_2019_1](https://www.biendata.xyz/competition/ccks_2019_1)
[https://www.biendata.xyz/competition/ccks_2020_2_1](https://www.biendata.xyz/competition/ccks_2020_2_1)
[https://www.biendata.xyz/competition/chip_2020_1](https://www.biendata.xyz/competition/chip_2020_1)

**赛题任务**：  
对于给定的一组电子病历文档（纯文本文件），任务的目标是识别并抽取出与医学临床相关的实体名字（entity mention），并将它们归类到预先定义好的类别（pre-defined categories），比如疾病、症状、检查等。

### 2.2 互联网金融新实体发现
**竞赛连接**:  
[https://www.datafountain.cn/competitions/361](https://www.datafountain.cn/competitions/361)  

**赛题任务**：   
从提供的金融文本中识别出现的未知金融实体，包括金融平台名、企业名、项目名称及产品名称。
持有金融牌照的银行、证券、保险、基金等机构、知名的互联网企业如腾讯、淘宝、京东等和训练集中出现的实体认为是已知实体。

### 2.3 文本实体识别及关系抽取
**竞赛连接**:  
[https://www.datafountain.cn/competitions/371](https://www.datafountain.cn/competitions/371)

**赛题任务**：  
本赛题利用经过特定处理的公共数据集SemEval2010，数据集中的文本共包括9种实体关系，希望参赛者可以对句子进行实体抽取，并根据语义及其他信息来判断实体之间的关系

### 2.4 第二届海南大数据创新应用大赛 - 智能算法大赛
**竞赛连接**:  
[https://tianchi.aliyun.com/competition/entrance/231771/introduction](https://tianchi.aliyun.com/competition/entrance/231771/introduction)

**竞赛任务**:    
脱敏之后的简历数据，需要抽取18个字段的实体。

## 三、可以关注的repo

[CLUEDatasetSearch](https://github.com/CLUEbenchmark/CLUEDatasetSearch)  
[nlp_chinese_corpus](https://github.com/brightmart/nlp_chinese_corpus)

To be continued