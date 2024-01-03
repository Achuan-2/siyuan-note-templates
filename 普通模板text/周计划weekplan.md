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

### 1. 本周任务计划
> 本周计划完成哪些任务

### 2. 本周工作总结
> 本周完成了哪些任务、整体进度如何。


### 3. 下周工作计划
> 接下来要做什么、是否需要其他协助。

### 4. 思考

> 有什么想法或心得体会，都可以拿出来分享下。