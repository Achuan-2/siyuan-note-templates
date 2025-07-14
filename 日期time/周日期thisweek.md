.action{$weekday := ternary 7 (int (now | Weekday)) (eq (int (now | Weekday)) 0)}
.action{$monday := now.AddDate 0 0 (int (sub 1 $weekday))}
.action{$sunday := now.AddDate 0 0 (int (sub 7 $weekday))}

.action{$monday | date "20060102"} ~ .action{$sunday | date "20060102"}