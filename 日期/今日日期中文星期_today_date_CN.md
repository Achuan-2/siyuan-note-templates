.action{$ini_date := }
.action{$now_date := now}
.action{$subdays := mod (div ($now_date.Sub $ini_date).Hours 24) 7}
.action{$today := last (slice (list "星期一" "星期二" "星期三" "星期四" "星期五" "星期六" " 星期日") 0 $subdays)}
.action{now | date "2006.01.02"} .action{$today}

