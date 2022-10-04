# Meteor Templates for SiYuan v1.2

> Attention:  The new meteor templates are not compatible with version 1.1.83.



## v0.8 add `todo`,`twoCol`,`threeCol`,`fourCol` templates![image.png](https://cdn.nlark.com/yuque/0/2021/png/12649687/1620578786986-654f2863-ccd1-42e2-b0c2-2caeef322605.png#clientId=uf7604ac5-c216-4&from=paste&height=540&id=ua8de02d7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1079&originWidth=1672&originalType=binary&size=1708829&status=done&style=none&taskId=u1317dea4-62f2-4982-bb7f-4dbd228e789&width=836)




**The following is the introduction for old version meteor templates.**

---

## Meteor模板介绍


> 适用于思源笔记日记、文档模板，使用方法：在文档中任意位置使用`{{`插入模板；**日记模板**可以在设置中更改配置，修改默认**模板路径**。



## v0.7 新增toc、moc、find模板


- 缺点是静态的，需要经常维护。删除内容，手动调用模板刷新
- 改进historytodo、find查询逻辑。



## v0.6 提及反链逻辑增强


## v0.5 更新，新增快速输入时间、日期模板


- 增加完整版日记模板'dailynote.md'
- 改进反链提及逻辑，增加别名搜索



## v0.4 更新，新增快速输入时间、日期模板


## v0.2 模板更新（01/17 21:05）


主要内容


- 模板拆解成五个：日记、历史待办、链接提及、随机漫游、文档模板。
- 此次模板设计遵循**简约**原则，日记模板只提供简单背景和创建时间，其他功能可通过`{{`调用，进行功能组合
- 实现类似RR、RE的page提及功能



### 新增截图：


**daily：** 基本日记模板，可与其他模板组合


![](https://gitee.com/zhangjlsjtu/pic/raw/master/picture/daily.png#id=UmNYX&originHeight=952&originWidth=1506&originalType=binary&status=done&style=none)


historyTodo：历史待办模板


![](https://gitee.com/zhangjlsjtu/pic/raw/master/picture/historytodo.png#id=l8esv&originHeight=552&originWidth=1393&originalType=binary&status=done&style=none)


roam：随机复习模板


![](https://gitee.com/zhangjlsjtu/pic/raw/master/picture/roam.png#id=L6yUq&originHeight=666&originWidth=1383&originalType=binary&status=done&style=none)


link：链接与提及模板


![](https://gitee.com/zhangjlsjtu/pic/raw/master/picture/link.png#id=RrdVB&originHeight=1115&originWidth=1489&originalType=binary&status=done&style=none)


docSign：普通文档模板，能自动加载文档名作为二级标题


![](https://gitee.com/zhangjlsjtu/pic/raw/master/picture/docsign.png#id=hb10I&originHeight=986&originWidth=1485&originalType=binary&status=done&style=none)

---

## 截图


![](https://raw.githubusercontent.com/zhangjl-sjtu/MeteorDiary/main/preview.png#id=P8UPx&originHeight=2080&originWidth=3175&originalType=binary&status=done&style=none)


## 主要特性


- 每次使用模板都能随机加载一张 页头背景图片
- 可显示创建时间、星期
- 随机展示未完成的 待办列表
- 随机复习：随机展示 一篇文档。如要排除路径，搜索关键词、标签请使用SQL语言



## 文档模板使用示例


![](https://raw.githubusercontent.com/zhangjl-sjtu/MeteorDiary/main/example.gif#id=kgzF4&originHeight=1128&originWidth=2375&originalType=binary&status=done&style=none)
