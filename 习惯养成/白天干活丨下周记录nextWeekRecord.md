.action{/*<!-- 计算下周日期范围 -->*/}
.action{$ini_date := toDate "2006-01-02" "2021-05-02"}
.action{$now_date := now}
.action{$day := mod (div ($now_date.Sub $ini_date).Hours 24) 7}
.action{if eq $day 0}
.action{$day = 7}
.action{end}
.action{$nextMondayDays := sub 8 $day}
.action{$nextMondayHour := nospace (cat "+" (mul $nextMondayDays 24) "h")}

.action{/*<!-- 计算下周每一天的日期 -->*/}
.action{$monday := (now | date_modify $nextMondayHour)}
.action{$tuesday := ($monday | date_modify "+24h")}
.action{$wednesday := ($monday | date_modify "+48h")}
.action{$thursday := ($monday | date_modify "+72h")}
.action{$friday := ($monday | date_modify "+96h")}
.action{$saturday := ($monday | date_modify "+120h")}
.action{$sunday := ($monday | date_modify "+144h")}

.action{/*<!-- 获取今天的日期用于标记 -->*/}
.action{$today := (now | date "20060102")}

### 下周记录（.action{$monday | date "20060102"} ~ .action{$sunday | date "20060102"}）

| 日期                          | 白天是否有摸鱼       | 晚上是否有充电 | 明天如何改进                                |
| ----------------------------- | -------------------- | -------------- | ------------------------------------------- |
| .action{$monday               | date "20060102 Mon"} |                |                                             |  |
| .action{$tuesday              | date "20060102 Mon"} |                |                                             |  |
| .action{$wednesday            | date "20060102 Mon"} |                |                                             |  |
| .action{$thursday             | date "20060102 Mon"} |                |                                             |  |
| .action{$friday               | date "20060102 Mon"} |                |                                             |  |
| .action{$saturday             | date "20060102 Mon"} |                |                                             |  |
| .action{$sunday               | date "20060102 Mon"} |                |                                             |  |
{: colgroup="min-width: 60px; | width: 250px;        | width: 145px;  | width: 100px;" id="20250617161045-w2cpg8c"}