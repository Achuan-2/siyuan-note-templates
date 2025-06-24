
## 计划

> 日记只是一个快速索引，最终目的是链接回待办背后相关的「任务笔记」去进一步处理与记录。但不是在日志上完成记录
> [工作计划（计划和实际进展、数据汇总）](siyuan://blocks/20250322110917-13iq1b3)


- [ ] 

## 实际记录

### 工作


### 学习充电


## 反思







.action{/* 获取今天日期和星期 */}
.action{$today := now | date "2006-01-02" }
.action{$today2 := now | date "20060102" }
.action{$today3 := now | date "2006.01.02" }
.action{$today4 := now | date "2006/01/02" }
.action{$weekday := now | date "Mon" }
.action{/* 工作日用红色图标，周末用蓝色图标，%23代表#号，URL不能直接输入#号，所以用URL编码%23代替 */}
.action{$color := "%23d13d51"}
.action{if or (eq $weekday "Sat")  (eq $weekday "Sun") }
.action{$color = "%233eb0ea"}
.action{end} 
.action{/* 设置文档图标：选择type6，仅返回星期样式 */}

{: icon="api/icon/getDynamicIcon?type=6&date=.action{$today}&color=.action{$color}" alias=".action{$today},.action{$today2},.action{$today3},.action{$today4}"  type="doc"}
