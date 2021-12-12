.action{$ini_date := toDate "2006-01-02" "2021-05-02"}
.action{$now_date := now}
.action{$subdays := add (mod (div ($now_date.Sub $ini_date).Hours 24) 7) 1}
.action{$today := last (slice (list "星期日" "星期一" "星期二" "星期三" "星期四" "星期五" "星期六" ) 0 $subdays)}
.action{now | date "2006.01.02"} .action{$today}

