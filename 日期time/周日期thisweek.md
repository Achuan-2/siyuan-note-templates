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

.action{(now | date_modify $leftHour) | date "20060102"} ~ .action{(now | date_modify $rightHour) | date "20060102"}


 