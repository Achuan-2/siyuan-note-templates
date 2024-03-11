.action{$ini_date := toDate "2006-01-02" "2021-05-02"}
.action{$now_date := now}
.action{$day := mod (div ($now_date.Sub $ini_date).Hours 24) 7}
.action{if eq $day 0}
.action{$day = 7}
.action{end}
.action{$leftday :=mul (sub $day 1)  24}
.action{$rightday :=mul (sub 7 $day) 24}
.action{$leftHour :=nospace (cat "-" $leftday "h") }
.action{$rightHour :=nospace (cat "+" $rightday "h")}
## .action{(now | date_modify $leftHour) | date "2006.01.02"} ~ .action{(now | date_modify $rightHour) | date "2006.01.02"}

### 1. 本周计划

#### 周整体计划
* [ ] 本周计划完成哪些任务

#### 周内计划

* 星期一
  
  * [ ] 1
    
  * [ ] 2
    
  * [ ] 3
    
  
* 星期二
  
  * [ ] 1
    
  * [ ] 2
    
  * [ ] 3
    
  
* 星期三
  
  * [ ] 1
    
  * [ ] 2
    
  * [ ] 3
    
  
* 星期四
  
  * [ ] 1
    
  * [ ] 2
    
  * [ ] 3
    
  
* 星期五
  
  * [ ] 1
    
  * [ ] 2
    
  * [ ] 3
    
  
* 星期六
  
  * [ ] 1
    
  * [ ] 2
    
  * [ ] 3
    
  
* 星期日
  
  * [ ] 1
    
  * [ ] 2
    
  * [ ] 3
    
{: custom-f="kb"}


#### 习惯打卡
| 习惯✅🟠❌            | 星期一 | 星期二 | 星期三 | 星期四 | 星期五 | 星期六 | 星期日 |
| ------------------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ |
| 八点半起床         |        |        |        |        |        |        |        |
| 十二点不带手机上床 |        |        |        |        |        |        |        |
### 2. 本周工作总结

- 工作
  - 本周完成了哪些任务、整体进度如何。
- 学习与充电
  - 记录工作领域、兴趣爱好、技能的学习笔记。
- 生活记录
  - 记录生活中发生了什么有趣的事情，去哪里游玩，遇见了什么人和事。

### 3. 反思与展望

本周有什么想法或心得体会，工作和生活有没有一些可以改进的地方。