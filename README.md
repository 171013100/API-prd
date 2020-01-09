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

- 1句话：“二货”，让压箱底的知识重见天日
- 1分钟：“二货”是面向在校大学生的二手书交易平台，以学校为单位，用户可以在各自的学校圈子买卖二手书，主打简便。利用百度文字识别api，让用户拍照即可上架商品，简单快捷；利用百度语音识别api，让用户说话即可搜索商品，解放用户双手；利用百度商品识别api，用户搜索无结果时可以获得图书的信息。“二货”既能帮助用户解决闲置书籍的烦恼，也能让用户收获淘书的喜悦。
- ![20×20](https://github.com/171013100/API-PRD/blob/master/API.pptx)
## 简介
“二货”旨在帮助在校大学生处理闲置书籍，为二手书转让提供一个交易平台

## 背景
- 很多大学生或多或少都有不需要的闲置书籍，却不知道怎么处理，这时与其让书籍闲置，不如卖给其他有需要的人，既能回收成本，又能帮助他人
- 二手书往往磨损较为严重，可能存在条形码破损的情况
- 套书的条形码有时候只会出现在最后一册，而部分书可以拆卖，导致有些书没有条形码
- 有一些书，出版社出于设计考虑不会把条形码印制在封底，而是在书内，不易发现
- 少数书尤其是画册、工具书，高价甚至自由定价（无定价），没有标准书号，也就没有条形码
- 部分内部刊物如学校报刊等没有条形码

## 目标
- 书籍智能识别：利用百度文字识别api，用户拍照后自动识别书籍封面文字，进行自动搜索
- 书籍智能推荐：利用百度商品识别api，用户上传图片后进行搜索，如果对结果不满意，可以在智能推荐的相似商品选择
- 语音自动搜索：利用百度语音识别api，用户可以在语音转文字后直接进行搜索

## 价值主张设计
### 加值宣言
- 平台的商品识别api可以智能推荐相关书籍，方便用户找到合适书籍
- 平台的文字识别api可以自动提取图中书籍的封面信息，包括书名、作者、出版社等，方便用户搜索或上架商品
- 平台的语音识别api可以通过语音转文字进行搜索，解放用户双手

### 核心价值
最小可行性产品是可以自动识别图片物体和文字的二手书交易app

### 核心价值与用户痛点
用户痛点：
- 卖家对书籍信息描述不够详尽，对书籍的分类定位也不明晰，导致用户判断出错
- 书籍类的信息较繁杂，信息录入不方便
- 买家在使用时想偷懒，想通过语音进行搜索

### 人工智能概率性与用户痛点
- 商品识别的准确度受图片清晰度、大小、有无其他杂物等影响
- 文字识别的准确度受文字的字体、字号、颜色等影响
- 语音识别的准确度受用户发音、语速、语言等影响

### 需求列表与人工智能API加值
|  主题   |  用户案例   |  重要性   |  备注   |  api加值   |
| --- | --- | --- | --- | --- |
|  文字识别   |  用户A想卖书，但书名和作者名字是英文的，不想手动输入，在拍照后自动识别书籍基本信息 |  重要   |  核心功能   |  百度文字识别api   |
|  商品识别   |  用户B想买套书，但只找到套书的一册，想要找到类似书籍   |  重要   |  核心功能   |  百度商品识别api   |
|  语言识别   | 用户C懒得打字搜索，想直接用语音搜索   |  次重要   |  辅助功能  |  百度语音识别api   |

## 原型
### 交互及界面设计
#### 基本界面
![首页](https://github.com/171013100/API-PRD/blob/master/shouye.png)

- 首页上方为搜索框，用户点击可进行搜索，支持文字和语音搜索
- 右上角为消息通知，用户点击可查看具体通知内容，当有系统通知或有人购买自己出售的书籍时会通知本人
- 轮播图是精选内容和广告位，根据所处时间不同进行调整，如每年5月和11月会放送四六级相关信息，用户点击可跳转到相应页面
- 中间是10个交易量最高的书籍分类，用户点击可直接跳转到相应分类，方便用户提高检索效率
- 下方信息流是所在学校的书籍上架情况，用户点击可直接跳转到对应商品，便于用户有效利用最新信息
- 最下方为5个页面图标，点击可切换页面
***
![分类](https://github.com/171013100/API-PRD/blob/master/fenlei.png)

- 分类页上方为搜索框，用户点击可进行搜索，支持文字和语音搜索
- 右上角为消息通知，用户点击可查看具体通知内容，当有系统通知或有人购买自己出售的书籍时会通知本人
- 搜索框下方是筛选按钮，支持按书籍类别分和专业分，方便用户筛选
- 左侧是书籍类别，点击可查看不同类别的书
- 右侧是具体分类，点击可进入商品列表
***
![发布](https://github.com/171013100/API-PRD/blob/master/fabu.png)

- 发布页使用时接入手机相机，图书置于框内
- 点击左下方图标可开启闪光灯
- 点击下方图标可进行拍摄
- 点击右下角图标可上传图片
***
![购物车](https://github.com/171013100/API-PRD/blob/master/shop.png)

- 购物车页标题右侧为删除按钮
- 标题下方为商品信息，显示商品图片、基本信息、价格，点击可跳转到商品页面
- 下方可选择“全选”，计算全选金额，右下方可进行结算
***
![个人](https://github.com/171013100/API-PRD/blob/master/setting.png)

- 个人页上方显示头像、昵称和所在学校，右侧为登录按钮，点击可进行账号登录和账号切换
- 中间为已关注商品、购买记录和发布商品，点击可进入查看具体信息
- 下方为具体设置选项

#### 智能加值
![图片识别](https://github.com/171013100/API-PRD/blob/master/result.png)
##### 利用百度文字识别api，用户拍照或上传图片后，自动识别封面文字信息，用户可以直接搜索或上架商品，无需重复输入信息

- 商品推荐页标题下方为拍摄的图片
- 中间为识别的文字信息
- 下方为个人描述
***
![商品推荐](https://github.com/171013100/API-PRD/blob/master/tuijian.png)
##### 利用百度商品识别api，当用户搜索无结果时，智能推荐相似商品，给予用户更多选择

- 商品推荐页标题下方为拍摄的图片
- 中间为识别的文字信息
- 下方为推荐商品列表
### 信息设计
#### 产品架构图
![产品架构图](https://github.com/171013100/API-PRD/blob/master/jiagou.png)
***
#### 功能流程图
![功能流程图](https://github.com/171013100/API-PRD/blob/master/steps.png)
### 原型文档
##### [原型](http://nfunm100.gitee.io/goods_not_original)
### 口头操作说明
- 搜索：用户拍照或上传图片后，显示图片文字信息，用户点击搜索，反馈搜索结果，如无结果还可在相似商品中寻找
- 发布：用户拍照或上传图片后，显示图片文字信息，用户点击发布，系统自动录入识别的文本信息，用户添加个人描述后可直接发布
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

- [百度语音识别api技术文档](https://ai.baidu.com/ai-doc/SPEECH/Ek39uxgre)

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

### API加分项
使用了[百度商品图片搜索api](https://ai.baidu.com/ai-doc/IMAGESEARCH/Uk3bczr77)、
[百度文字识别api](https://ai.baidu.com/ai-doc/OCR/zk3h7xz52)、
[百度语音识别api](https://ai.baidu.com/ai-doc/SPEECH/Ek39uxgre)
