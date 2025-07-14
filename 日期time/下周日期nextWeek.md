.action{/*<!-- 计算下周每一天的日期 -->*/}
.action{$weekday := ternary 7 (int (now | Weekday)) (eq (int (now | Weekday)) 0)}
.action{$monday := now.AddDate 0 0 (int (sub 8 $weekday))}
.action{$tuesday := $monday.AddDate 0 0 1}
.action{$wednesday := $monday.AddDate 0 0 2}
.action{$thursday := $monday.AddDate 0 0 3}
.action{$friday := $monday.AddDate 0 0 4}
.action{$saturday := $monday.AddDate 0 0 5}
.action{$sunday := $monday.AddDate 0 0 6}

.action{/*<!-- 获取今天的日期用于标记 -->*/}
.action{$today := (now | date "20060102")}

.action{$monday | date "20060102"} ~ .action{$sunday | date "20060102"}