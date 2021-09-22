
.action{$ini_date := toDate "2006-01-02" "2021-05-02"}
.action{$now_date := now}
.action{$day := mod (div ($now_date.Sub $ini_date).Hours 24) 7}
.action{$leftday :=mul (sub $day 1)  24}
.action{$rightday :=mul (sub 7 $day) 24}
.action{$leftHour :=nospace (cat "-" $leftday "h") }
.action{$rightHour :=nospace (cat "+" $rightday "h")}


## .action{(now | date_modify $leftHour) | date "2006-01-02"} ~ .action{(now | date_modify $rightHour) | date "2006-01-02"} 📅周打卡


| **事项** ❌✔⚫ | **一** | **二** | **三** | **四** | **五** | **六** | **七** |
| :---------------: | -------- | -------- | -------- | -------- | -------- | -------- | -------- |
|                 |        |        |        |        |        |        |        |
|                 |        |        |        |        |        |        |        |
|                 |        |        |        |        |        |        |        |
|                 |        |        |        |        |        |        |        |
|                 |        |        |        |        |        |        |        |
|                 |        |        |        |        |        |        |        |
|                 |        |        |        |        |        |        |        |
|                |        |        |        |        |        |        |        |
