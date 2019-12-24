# 项目名称：二货
## 产品说明文档

|  Title   |   Content  |
| --- | --- |
| Target release    |  2019/11   |
|  Epic   |  二货   |
|  Document status   |  进行中   |
|  Document owner   |  张霖   |
|  Designer   |  张霖   |
|  Developer   |  张霖   |
|  QA   |   张霖  |

## 简介
“二货”旨在帮助在校大学生处理闲置书籍，为二手书转让提供一个交易平台

## 背景
很多大学生或多或少都有不需要的闲置书籍，却不知道怎么处理，这时与其让书籍闲置，不如卖给其他有需要的人，既能回收成本，又能帮助他人

## 目标
- 书籍智能匹配：利用百度商品识别api，用户上传图片后自动检测图中书籍，进行自动匹配，找到类似商品
- 书籍智能识别：利用百度文字识别api，用户拍照后自动识别书籍封面文字，进行自动分类或智能搜索
- 语音自动搜索：利用百度语言识别api，用户可以在语音转文字后直接进行搜索

## 价值主张设计
### 加值宣言
- 平台的商品识别api可以智能识别图中书籍，并自动分配到相应分类，方便用户找到目标书籍
- 平台的文字识别api可以自动提取图中书籍的封面信息，包括书名、作者、出版社等，并自动分配到相应分类
- 平台的语言识别api可以通过语言转文字进行搜索，解放用户双手

### 核心价值
最小可行性产品是可以自动识别图片物体和文字的二手书交易app

### 核心价值与用户痛点
用户痛点：
- 卖家对书籍描述不够详尽，对书籍的分类定位也不明晰
- 书籍类的信息较繁杂，信息录入不方便
- 买家在使用时想偷懒，想通过语音进行搜索

### 人工智能概率性与用户痛点
- 商品识别的准确度受图片清晰度、大小、有无其他杂物等影响
- 文字识别的准确度受文字的字体、字号、颜色等影响
- 语音识别的准确度受用户发音、语速、语言等影响

### 需求列表与人工智能API加值
|  主题   |  用户案例   |  重要性   |  备注   |  api加值   |
| --- | --- | --- | --- | --- |
|  商品识别   |  买家A拍下自己想买的书籍，上传图片后自动检测出图中书籍，输出基本信息后进行自动匹配 |  重要   |  核心功能   |  百度商品识别api   |
|  文字识别   |  卖家B想卖书，但书名和作者名字是英文的，不想手动输入，在拍照后自动识别书籍基本信息并自动添加分类   |  重要   |  核心功能   |  百度文字识别api   |
|  语言识别   | 买家C懒得打字搜索，想直接用语音搜索   |  次重要   |  辅助功能  |  百度语音识别api   |

## 原型
### 交互及界面设计

### 信息设计

### 原型文档

### 口头操作说明

## API 产品使用关键AI或机器学习之API的输出入展示 
### 使用水平
- [百度商品图片搜索api技术文档](https://ai.baidu.com/ai-doc/IMAGESEARCH/Uk3bczr77)

输入：目标图片 输出：相似图片

![图片入库](https://github.com/171013100/API-PRD/blob/master/picture1.png)

![图片搜索](https://github.com/171013100/API-PRD/blob/master/picture2.png)

- [百度文字识别api技术文档](https://ai.baidu.com/ai-doc/OCR/zk3h7xz52)

输入：书籍图片 输出：书籍封面信息

![示例图片](https://github.com/171013100/API-PRD/blob/master/history.jpg)

![文字识别](https://github.com/171013100/API-PRD/blob/master/word1.png)

![输出结果](https://github.com/171013100/API-PRD/blob/master/word2.png)

- [百度语言识别api技术文档](https://ai.baidu.com/ai-doc/SPEECH/Ek39uxgre)

输入：用户语音 输出：用户语音转文字

![语音识别](https://github.com/171013100/API-PRD/blob/master/listen1.png)

![输出结果](https://github.com/171013100/API-PRD/blob/master/listen2.png)
### 使用比较分析
- 商品图片搜索api对比

对比项|百度|Azure
--|:--:|--:
成熟度|比较好，有自定义图像训练库，还有训练报告|目前只有自定义图像训练库
性价比|有提供免费试用、开通续费0.0007元/次|有提供免费试用、WebAPI接入0.0005-0.01元/次等	

- 文字识别api对比

对比项|百度|阿里云
--|:--:|--:
成熟度|文档清晰且详细，预估准确率达到95%|使用教程完善、但API文档较不完善
性价比|500次/天免费,超出需付费|	0元/500次,238元/1000次,2008元/1W次等

- 语音识别api对比

对比项|百度|阿里云
--|:--:|--:
成熟度|支持超过60秒的实时长语音识别。同时也支持上传完整录音文件。支持离线唤醒词、命令词、通用语义解析等功能。|可以使用自学习平台等工具改善语音识别效果，而且提供了功能更丰富的管理控制台和更易用的SDK
性价比|按调用量计费，前5万次调用免费。默认为限额为5QPS，开通付费后限额提升至50QPS|3.5元/小时

### 使用后风险报告 
- 图片的清晰度较大程度影响商品图片识别的准确度，一般需高清图片，如果图片中不止一本书籍，识别正确率会下降
- 文字识别无法识别某些特殊字体或艺术字，不能适用于全部场景
- 用户发音不标准、语速过快等都会影响语音识别的准确度
