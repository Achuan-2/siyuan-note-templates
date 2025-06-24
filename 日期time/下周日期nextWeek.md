.action{$ini_date := toDate "2006-01-02" "2021-05-02"}
.action{$now_date := now}
.action{$day := mod (div ($now_date.Sub $ini_date).Hours 24) 7}
.action{if eq $day 0}
.action{$day = 7}
.action{end}
.action{$nextMondayDays := sub 8 $day}
.action{$nextSundayDays := add $nextMondayDays 6}
.action{$nextMondayHour := nospace (cat "+" (mul $nextMondayDays 24) "h")}
.action{$nextSundayHour := nospace (cat "+" (mul $nextSundayDays 24) "h")}

.action{(now | date_modify $nextMondayHour) | date "20060102"} ~ .action{(now | date_modify $nextSundayHour) | date "20060102"}