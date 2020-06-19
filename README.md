# 欢迎来到我的博客
互联网是近代最伟大的发明之一。它突破了国家和地域的界限，改变着世界政治、经济、文化、生活的方式，把世界连接在了一起。它已经成为人类生活中不可或缺的重要组成部分，但同时也带来许多意想不到、需要解决的问题。如何解决这些问题，即如何进行互联网治理，已经成为全球诸多国家和地区政府和社会关注的重大课题，也是我们这门课需要探讨和学习的问题。

## 自我简介
姓名：柏若溪

年龄：21岁

家乡：贵州

学校：四川大学

学院：公共管理学院

专业：信息资源管理专业

爱好：旅游 读书 看电影……


## 课堂讨论
### 1. 什么是互联网精神？
● 讨论：开放、平等、快速、分享、协作

### 2. 什么是互联网、互联网+、互联网思维？
● 讨论：一句话表述你对互联网上述认识

### 3. 什么是Infodemic？
● 讨论：从信息角度表述你对Infodemic信息疫情，信息恐慌的认识，如何治理呢？会不会成为一个新的领域？研究方向会有哪些？

### 4. 什么是污名化Stigma？
● 讨论：从信息角度表述你对污名化的认识，如何治理呢？

### 5. 国际疫情中的信息化，中国老百姓需要什么样的信息？
● 讨论：从信息角度表述你对疫情信息国际化的认识？你认为现阶段，中国老百姓需要什么样的信息？华人需要什么样的信息？国际上需要什么样的中国方案？

### 6. 你认为新媒体时代的网站应该是一种什么样的存在？
● 讨论：你对网站的认识？ 新媒体的视角，网站？社交媒体的背景，网站怎么生存？

### 7. 什么是分布式？分布式信息系统？为什么要分布式？你知道的分布式有哪些知名信息系统？
● 讨论：你对分布式的认识？有哪些知名的分布式系统和理念？

### 8. 什么是信息的可视化？你对信息可视化的认识？为什么要信息的可视化？可视化的重要地位？可视化的工具？可视化的手段？
● 讨论：你对分可视化的认识？有哪些知名的分布式系统和理念？

### 9. 什么是互联网治理和信息治理？为什么要治理？治理的手段有哪些？作业合作给了我们什么启示？
● 讨论：你对互联网治理和信息治理的认识？

## 课后作业
[✔] 社区信息化方案     

[✔] infodemic治理

[✔] 当政府遇上互联网   

[✔] git理解和学习

......

## R学习资源
●期刊[R Journal](https://journal.r-project.org/)|  
●图书[R Bookdown](https://bookdown.org/home/)|  
●博客[R Bloggers](https://www.r-bloggers.com/)|
●教程[W3CSchool](https://www.w3cschool.cn/r/r_overview.html)|
●视频[R语言基础](https://mooc1.chaoxing.com/course/97619275.html?_from_=208815890_17811461_117047994_ad050eece3f6dddeb97c04d1c57108ef)|

## R语言学习
### R 简介
R是一套由数据操作、计算和图形展示功能整合而成的套件。包括：有效的数据存储和处理功能，一套完整的数组（特别是矩阵）计算操作符，拥有完整体系的数据分析工具，为数据分析和显示提供的强大图形功能，一套（源自S语言）完善、简单、有效的编程语言（包括条件、循环、自定义函数、输入输出功能）。

### 练习：R+新冠
```R
library(nCov2019)
library(ggplot2)
library(treemap)
library(treemapify)
library(dplyr)

x<-get_nCov2019()
d<-x['湖北',]
ggplot(d, aes(area = confirm, fill = name, label = paste(name, confirm, sep="\n")))+
  geom_treemap()+
  geom_treemap_text(frontface = "italic", colour = "white", place = "centre",grow = TRUE)
```

### 练习：R+地图
```R
url<-"https://geo.datav.aliyun.com/areas/bound/100000.json"
url
length(url)
library(rjson)
require(rjson)
json<-rjson::fromJSON(file = url)
json
summary(json)
class(json)

toJSon<-rjson::toJSON(json)
write(toJSon,"cn100000.json")
cn100000<-rjson::fromJSON(file = "cn100000.json")

cn<-sf::st_read(dsn="cn100000.json",stringsAsFactors=F)
library(ggplot2)
p<-ggplot()+
   geom_sf(data = cn,aes(fill=name))
```

## R blogdown学习
### R blogdown是什么
R语言的一个扩展包，用来制作网站的工具。
可以用非常简洁的方式快速搭建静态网页构成的网站。
虽然名字里有“博客”（blog）字样，但并不仅限于博客。非常适合搭建一个科研小组的展示窗口。
基于 markdown 扩展语法，可以在网页中方便地插入图表、脚注、数学公式、R 代码等元素。
非常容易将 bookdown 生成的论文转化成网页展示。
非常易于维护，迁移，备份。

### 1. 制作一份待办事宜

- [ ] 支持以 PDF 格式导出文稿
- [ ] 改进 Cmd 渲染算法，使用局部渲染技术提高渲染效率
- [x] 新增 Todo 列表功能
- [x] 修复 LaTex 公式渲染问题
- [x] 新增 LaTex 公式编号功能

### 2. 书写一个质能守恒公式[^LaTeX]

$$E=mc^2$$

### 3. 高亮一段代码[^code]

```python
@requires_authorization
class SomeClass:
    pass

if __name__ == '__main__':
    # A comment
    print 'hello world'
```

### 4. 绘制表格

| 项目        | 价格   |  数量  |
| --------   | -----:  | :----:  |
| 计算机     | \$1600 |   5     |
| 手机        |   \$12   |   12   |
| 管线        |    \$1    |  234  |

......

总而言之，Markdown 是一种方便记忆、书写的纯文本标记语言，你可以使用这些标记符号以最小的输入代价生成极富表现力的文档。
