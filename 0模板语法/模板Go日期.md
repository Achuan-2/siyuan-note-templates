<!-------------------模板日期相关-------------------------->

‸<!-- 返回今天日期和星期 英文 -->
‸
.action{ now | date "2006-01-02  Mon "}

<!-- 返回今天日期和星期 中文 -->
.action{$ini_date := toDate "2006-01-02" "2021-05-02"}
.action{$now_date := now}
.action{$subdays := mod (div ($now_date.Sub $ini_date).Hours 24) 7}
.action{$today := last (slice (list "星期一" "星期二" "星期三" "星期四" "星期五" "星期六" " 星期日") 0 $subdays)}
.action{now | date "2006-01-02"} .action{$today}



<!-- 返回今天过去几天,date_modify好像只能接收小时吗-->
.action{(now | date_modify "-72h")| date "20060102"}

<!-- 返回这一周的日期范围-->
.action{$ini_date := toDate "2006-01-02" "2021-05-02"}
.action{$now_date := now}
.action{$day := mod (div ($now_date.Sub $ini_date).Hours 24) 7}
.action{$leftday :=mul (sub $day 1)  24}
.action{$rightday :=mul (sub 7 $day) 24}
.action{$leftHour :=nospace (cat "-" $leftday "h") }
.action{$rightHour :=nospace (cat "+" $rightday "h")}

.action{(now | date_modify $leftHour) | date "2006-01-02"} ~ .action{(now | date_modify $rightHour) | date "2006-01-02"}